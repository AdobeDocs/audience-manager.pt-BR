---
description: O Audience Manager requer que as solicitações HTTP de servidor para servidor sejam assinadas digitalmente para validade. Este documento descreve como você pode assinar solicitações HTTP com chaves privadas.
seo-description: O Audience Manager requer que as solicitações HTTP de servidor para servidor sejam assinadas digitalmente para validade. Este documento descreve como você pode assinar solicitações HTTP com chaves privadas.
seo-title: Solicitações HTTP Assinadas Digitalmente
solution: Audience Manager
title: Solicitações HTTP Assinadas Digitalmente
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
translation-type: tm+mt
source-git-commit: 9bf1f3771b6a4b9bb9a52149e812b37d1c8e27f8

---


# Solicitações Assinadas Digitalmente `HTTP`{#digitally-signed-http-requests}

O Audience Manager exige que as solicitações de servidor para servidor sejam assinadas digitalmente para validade. `HTTP` Este documento descreve como você pode assinar `HTTP` solicitações com chaves privadas.

## Visão geral {#overview}

<!-- digitally_signed_http_requests.xml -->

Usando uma chave privada fornecida por você e compartilhada com [!DNL Audience Manager], podemos assinar digitalmente as `HTTP` solicitações enviadas entre o [IRIS](../../../reference/system-components/components-data-action.md#iris) e o servidor HTTP. Isso garante:

* **Autenticidade**: somente o remetente que tem a chave privada ([!UICONTROL IRIS]) pode enviar `HTTP(S)` mensagens válidas para o parceiro.
* **Integridade** da mensagem: com esta abordagem, mesmo assim, `HTTP`você está protegido de um homem no meio do ataque onde as mensagens ficam distorcidas.

[!UICONTROL IRIS] tem suporte integrado para girar as teclas com tempo de inatividade zero, conforme mostrado na seção [Girando a chave](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) privada abaixo.

## Informações que você precisa fornecer {#info-to-provide}

Para obter um destino de servidor para servidor em tempo `HTTP` real, entre em contato com seu [!DNL Audience Manager] consultor e especifique:

* A chave usada para assinar a solicitação.
* O nome do `HTTP` cabeçalho que manterá a assinatura gerada (assinatura X no cabeçalho de exemplo abaixo).
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

## How it works {#how-it-works}

1. [!UICONTROL IRIS] cria a `HTTP` mensagem a ser enviada ao parceiro.
1. [!UICONTROL IRIS] cria uma assinatura com base na `HTTP` mensagem e na chave privada comunicada pelo parceiro.
1. [!UICONTROL IRIS] envia a `HTTP(S)` solicitação ao parceiro. Esta mensagem contém a assinatura e a mensagem real, como visto no exemplo acima.
1. O servidor parceiro recebe a `HTTP(S)` solicitação. Ele lê o corpo da mensagem e a assinatura recebida de [!UICONTROL IRIS].
1. Com base no corpo da mensagem recebida e na chave privada, o servidor parceiro recalcula a assinatura. Consulte a seção [Como calcular a assinatura](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) logo abaixo sobre como conseguir isso.
1. Compare a assinatura criada no servidor parceiro (receptor) com a recebida do [!UICONTROL IRIS] (remetente).
1. Se as assinaturas corresponderem, a **autenticidade** e a integridade **da** mensagem serão validadas. Somente o remetente, que tem a chave privada, pode enviar uma assinatura válida (autenticidade). Além disso, um homem no meio não pode modificar a mensagem e gerar uma nova assinatura válida, já que não tem a chave privada (integridade da mensagem).

![](assets/iris-digitally-sign-http-request.png)

## Como calcular a assinatura {#calculate-signature}

[!DNL HMAC] (Código de autenticação de mensagem baseado em hash) é o método usado para assinatura [!UICONTROL IRIS] de mensagem. Implementações e bibliotecas estão disponíveis basicamente em cada linguagem de programação. [!DNL HMAC] não tem ataques de extensão conhecidos. Veja um exemplo em [!DNL Java] abaixo:

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

A RFC para a implementação de [!DNL HMAC] hash é [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). Um local de teste: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (observe que é necessário [converter](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) a codificação hexadecimal em base64).

## Girar a chave privada {#rotate-private-key}

Por motivos de segurança, é recomendável girar periodicamente a chave privada. Cabe a você decidir a chave privada e o período de rotação. Para obter a rotação da chave com tempo de inatividade zero, [!UICONTROL IRIS] é possível adicionar vários cabeçalhos de assinatura. Um cabeçalho conterá a assinatura gerada com a chave antiga, outro cabeçalho conterá a assinatura gerada usando a nova chave privada. Veja abaixo as etapas em detalhes:

1. O parceiro comunica a nova chave privada para [!DNL Adobe Audience Manager].
1. [!UICONTROL IRIS] começará a enviar dois cabeçalhos de assinatura (um usando a chave antiga, o outro usando a nova chave).
1. Depois de começar a receber ambos os cabeçalhos, você pode optar por descartar a chave antiga e apenas observar a nova assinatura.
1. A chave antiga é removida [!DNL Audience Manager] e [!UICONTROL IRIS] envia somente o novo cabeçalho de assinatura. As teclas foram giradas.

## Dados usados para assinar {#data-signing}

Para destinos de `GET` tipo, a mensagem usada para assinatura será *REQUEST_PATH + QUERY STRING* (por exemplo, */from-aam-s2s?sids=1,2,3*). O IRIS não leva em conta o nome do host ou `HTTP` cabeçalhos - eles podem ser modificados/configurados incorretamente ao longo do caminho ou reportados incorretamente.

Para destinos de `POST` tipo, a mensagem usada para assinatura é o CORPO *DE* SOLICITAÇÃO. Novamente, os cabeçalhos ou outros parâmetros de solicitação são ignorados.
