---
description: O Audience Manager exige que as solicitações HTTP(S) servidor para servidor sejam assinadas digitalmente para validade. Este documento descreve como você pode assinar solicitações HTTP com chaves privadas.
seo-description: Audience Manager requires the HTTP(S) server-to-server requests to be digitally signed for validity. This document describes how you can sign HTTP(S) requests with private keys.
seo-title: Digitally Signed HTTP(S) Requests
solution: Audience Manager
title: Solicitações HTTP(S) assinadas digitalmente
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
feature: Outbound Data Transfers
exl-id: 55907a25-a361-494a-86b9-c693faea4f0e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 0%

---

# Assinado digitalmente `HTTP(S)` Solicitações {#digitally-signed-http-requests}

O Audience Manager exige o `HTTP(S)` solicitações de servidor para servidor para serem assinadas digitalmente para validade. Este documento descreve como você pode assinar `HTTP(S)` solicitações com chaves privadas.

## Visão geral {#overview}

<!-- digitally_signed_http_requests.xml -->

Uso de uma chave privada fornecida por você e compartilhada com [!DNL Audience Manager], podemos assinar digitalmente o `HTTP(S)` solicitações que são enviadas entre [ÍRIS](../../../reference/system-components/components-data-action.md#iris) e seu servidor HTTP(S). Isso garante:

* **Autenticidade**: somente o remetente que tem a chave privada ([!UICONTROL IRIS]) pode enviar informações `HTTP(S)` para o parceiro.
* **Integridade da mensagem**: com essa abordagem, mesmo em `HTTP`Você está protegido de um homem no meio do ataque, onde as mensagens são distorcidas.

[!UICONTROL IRIS] tem suporte integrado para girar as chaves sem tempo de inatividade, conforme mostrado na [Rotação da chave privada](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) abaixo.

## Informações que você precisa fornecer {#info-to-provide}

Para um `HTTP(S)` destino de servidor para servidor em tempo real, entre em contato com o [!DNL Audience Manager] consultor e especifique:

* A chave usada para assinar a solicitação.
* O nome do `HTTP(S)` cabeçalho que conterá a assinatura gerada (Assinatura X no cabeçalho de exemplo abaixo).
* Opcional: o tipo de hash usado para a assinatura (md5, sha1, sha256).

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

## Como funciona {#how-it-works}

1. [!UICONTROL IRIS] cria o `HTTP(S)` mensagem a ser enviada ao parceiro.
1. [!UICONTROL IRIS] cria uma assinatura com base no `HTTP(S)` e a chave privada comunicada pelo parceiro.
1. [!UICONTROL IRIS] envia o `HTTP(S)` solicitação ao parceiro. Essa mensagem contém a assinatura e a mensagem real, como visto no exemplo acima.
1. O servidor parceiro recebe a variável `HTTP(S)` solicitação. Ele lê o corpo da mensagem e a assinatura recebida de [!UICONTROL IRIS].
1. Com base no corpo da mensagem recebida e na chave privada, o servidor parceiro recalcula a assinatura. Consulte a [Como calcular a assinatura](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) seção logo abaixo sobre como fazer isso.
1. Comparar a assinatura criada no servidor parceiro (receptor) com a recebida de [!UICONTROL IRIS] (remetente).
1. Se as assinaturas forem correspondentes, a variável **autenticidade** e **integridade da mensagem** foram validados. Somente o remetente, que tem a chave privada, pode enviar uma assinatura válida (autenticidade). Além disso, um homem do meio não pode modificar a mensagem e gerar uma nova assinatura válida, já que não tem a chave privada (integridade da mensagem).

![](assets/iris-digitally-sign-http-request.png)

## Como calcular a assinatura {#calculate-signature}

[!DNL HMAC] (Código de autenticação de mensagem baseado em hash) é o método usado pelo [!UICONTROL IRIS] para assinatura de mensagens. Implementações e bibliotecas estão disponíveis basicamente em todas as linguagens de programação. [!DNL HMAC] O não tem ataques de extensão conhecidos. Veja um exemplo em [!DNL Java] abaixo:

```
// Message to be signed.
// For GET type HTTP(S) destinations, the message used for signing will be the REQUEST_PATH + QUERY_STRING
// For POST type HTTP(S) destinations, the message used for signing will be the REQUEST_BODY.
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

A RFC para o [!DNL HMAC] a implementação de hash está [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). Um site de teste: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (observe que é necessário [converter](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) a codificação hex (para base64).

## Rotação da chave privada {#rotate-private-key}

Para girar a chave privada, os parceiros devem comunicar a nova chave privada à sua [!DNL Adobe Audience Manager] consultor. A chave antiga é removida de [!DNL Audience Manager] e [!UICONTROL IRIS] envia somente o novo cabeçalho de assinatura. As chaves foram rotacionadas.

## Dados usados para assinatura {#data-signing}

Para `GET` destinos de tipo, a mensagem usada para assinatura será a *REQUEST_PATH + SEQUÊNCIA DE CONSULTA* (por exemplo, */from-aam-s2s?sids=1,2,3*). IRIS não leva em conta o nome do host ou `HTTP(S)` cabeçalhos - podem ser modificados/configurados incorretamente ao longo do caminho ou relatados incorretamente.

Para `POST` destinos de tipo, a mensagem usada para assinatura é a *CORPO DA SOLICITAÇÃO*. Novamente, os cabeçalhos ou outros parâmetros de solicitação são ignorados.
