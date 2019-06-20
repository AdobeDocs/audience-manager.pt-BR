---
description: O Audience Manager requer que as solicitações do servidor HTTP para servidor sejam assinadas digitalmente para validade. Este documento descreve como é possível assinar solicitações HTTP com chaves privadas.
seo-description: O Audience Manager requer que as solicitações do servidor HTTP para servidor sejam assinadas digitalmente para validade. Este documento descreve como é possível assinar solicitações HTTP com chaves privadas.
seo-title: Solicitações HTTP assinadas digitalmente
solution: Audience Manager
title: Solicitações HTTP assinadas digitalmente
uuid: 1183 a 70 f -0 c 96-42 cf-a 4 f 5-37 a 83 ffa 1286
translation-type: tm+mt
source-git-commit: 9bf1f3771b6a4b9bb9a52149e812b37d1c8e27f8

---


# `HTTP` Solicitações digitalmente assinadas {#digitally-signed-http-requests}

Audience Manager requires the `HTTP` server-to-server requests to be digitally signed for validity. This document describes how you can sign `HTTP` requests with private keys.

## Visão geral {#overview}

<!-- digitally_signed_http_requests.xml -->

Using a private key provided by you and shared with [!DNL Audience Manager], we can digitally sign the `HTTP` requests that are sent between [IRIS](../../../reference/system-components/components-data-action.md#iris) and your HTTP server. Isso garante:

* **Autenticidade**: somente o remetente que tem a chave privada ([!UICONTROL IRIS]) pode enviar `HTTP(S)` mensagens válidas para o parceiro.
* **Integridade da mensagem**: com essa abordagem, mesmo em `HTTP`, você está protegido de um homem no meio do ataque no qual as mensagens ficam distorcidas.

[!UICONTROL IRIS] tem suporte incorporado para girar as teclas com zero tempo de inatividade, como mostrado na [seção Girar a chave](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) privada abaixo.

## Information you need to provide {#info-to-provide}

For an `HTTP` real-time server-to-server destination, contact your [!DNL Audience Manager] consultant and specify:

* A chave usada para assinar a solicitação.
* The name of the `HTTP` header that will hold the generated signature (X-Signature in the example header below).
* Opcional: o tipo de hash usado para a assinatura (md 5, sha 1, sha 256).

```
* Connected to partner.website.com (127.0.0.1) port 80 (#0)
> POST /webpage HTTP/1.1
> Host: partner.host.com
> Accept: */*
> Content-Type: application/json
> Content-Length: 20
> X-Signature: +wFdR/afZNoVqtGl8/e1KJ4ykPU=
POST message content
```

## How it works {#how-it-works}

1. [!UICONTROL IRIS] cria `HTTP` a mensagem a ser enviada para o parceiro.
1. [!UICONTROL IRIS] cria uma assinatura com base na `HTTP` mensagem e na chave privada comunicada pelo parceiro.
1. [!UICONTROL IRIS] envia `HTTP(S)` a solicitação para o parceiro. Esta mensagem contém a assinatura e a mensagem real, como visto no exemplo acima.
1. The partner server receives the `HTTP(S)` request. It reads the message body and the signature received from [!UICONTROL IRIS].
1. Com base no corpo da mensagem recebido e na chave privada, o servidor do parceiro recalcula a assinatura. See the [How to calculate the signature](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) section just below on how to achieve this.
1. Compare the signature created on the partner server (receiver) with the one received from [!UICONTROL IRIS] (sender).
1. If the signatures match, then the **authenticity** and **message integrity** have been validated. Somente o remetente, que tem a chave privada, pode enviar uma assinatura válida (autenticidade). Além disso, um homem no meio não pode modificar a mensagem e gerar uma nova assinatura válida, já que ela não tem a chave privada (integridade da mensagem).

![](assets/iris-digitally-sign-http-request.png)

## How to calculate the signature {#calculate-signature}

[!DNL HMAC] (Código de autenticação de mensagem com base em hash) é o método usado para [!UICONTROL IRIS] a assinatura de mensagens. As implementações e bibliotecas estão disponíveis basicamente em cada linguagem de programação. [!DNL HMAC] não tem ataques de extensão conhecidos. See an example in [!DNL Java] below:

```
// Message to be signed.
// For GET type HTTP destinations, the message used for signing will be the REQUEST_PATH + QUERY_STRING
// For POST type HTTP destinations, the message used for signing will be the REQUEST_BODY.
// String getData = "/from-aam-s2s?sids=1,2,3";
String postData = "POST message content";
// Algorithm used. Currently supported: HmacSHA1, HmacSHA256, HmacMD5.
String algorithm = "HmacSHA1";
// Private key shared between the partner and Adobe Audience Manager.
String key = "sample_partner_private_key";
  
// Perform signing.
SecretKeySpec signingKey = new SecretKeySpec(key.getBytes(), algorithm);
Mac mac = Mac.getInstance(algorithm);
mac.init(signingKey);
byte[] result = mac.doFinal(postData.getBytes());
  
String signature = Base64.encodeBase64String(result).trim(); 
// signature = +wFdR/afZNoVqtGl8/e1KJ4ykPU=
```

The RFC for the [!DNL HMAC] hash implementation is [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). A test site: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (note that you have to [convert](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) the hex encoding to base64).

## Rotating the private key {#rotate-private-key}

Por motivos de segurança, é recomendado girar periodicamente a chave privada. Cabe a você decidir a chave privada e o período de rotação. In order to achieve the key rotation with zero downtime, [!UICONTROL IRIS] supports adding multiple signature headers. Um cabeçalho conterá a assinatura gerada com a tecla antiga, outro cabeçalho conterá a assinatura gerada usando a nova chave privada. Veja abaixo as etapas detalhadas:

1. Partner communicates the new private key to [!DNL Adobe Audience Manager].
1. [!UICONTROL IRIS] começará a enviar dois cabeçalhos de assinatura (um usando a tecla antiga, a outra usando a nova chave).
1. Depois de começar a receber cabeçalhos, você pode optar por descartar a tecla antiga e observar apenas a nova assinatura.
1. The old key is removed from [!DNL Audience Manager] and [!UICONTROL IRIS] only sends the new signature header. As chaves foram giradas.

## Data used for signing {#data-signing}

For `GET` type destinations, the message used for signing will be the *REQUEST_PATH + QUERY STRING* (e.g. */from-aam-s2s?sids=1,2,3*). IRIS does not take into account the hostname or `HTTP` headers - these can be modified / misconfigured along the path or reported incorrectly.

For `POST` type destinations, the message used for signing is the *REQUEST BODY*. Novamente, os cabeçalhos ou outros parâmetros de solicitação são ignorados.
