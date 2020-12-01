---
description: O Audience Manager exige que as solicitações de servidor para servidor HTTP(S) sejam assinadas digitalmente para validade. Este documento descreve como você pode assinar solicitações HTTP com chaves privadas.
seo-description: O Audience Manager exige que as solicitações de servidor para servidor HTTP(S) sejam assinadas digitalmente para validade. Este documento descreve como você pode assinar solicitações HTTP(S) com chaves privadas.
seo-title: Solicitações HTTP(S) Assinadas Digitalmente
solution: Audience Manager
title: Solicitações HTTP(S) Assinadas Digitalmente
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: 4877aa5391193ee2187609fdc9cb3740c91feb96
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 0%

---


# Solicitações `HTTP(S)` assinadas digitalmente {#digitally-signed-http-requests}

Audience Manager requer que as solicitações de `HTTP(S)` servidor para servidor sejam assinadas digitalmente para validade. Este documento descreve como você pode assinar `HTTP(S)` solicitações com chaves privadas.

## Visão geral {#overview}

<!-- digitally_signed_http_requests.xml -->

Usando uma chave privada fornecida por você e compartilhada com [!DNL Audience Manager], podemos assinar digitalmente as solicitações `HTTP(S)` enviadas entre [IRIS](../../../reference/system-components/components-data-action.md#iris) e seu servidor HTTP(S). Isso garante:

* **Autenticidade**: somente o remetente que tem a chave privada ([!UICONTROL IRIS]) pode enviar  `HTTP(S)` mensagens válidas para o parceiro.
* **Integridade** da mensagem: com esta abordagem, mesmo assim,  `HTTP`você está protegido de um homem no ataque do meio, onde as mensagens ficam distorcidas.

[!UICONTROL IRIS] tem suporte integrado para girar as teclas com tempo de inatividade zero, conforme mostrado na seção  [Girando a ](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) tecla privada abaixo.

## Informações que você precisa fornecer {#info-to-provide}

Para um `HTTP(S)` destino de servidor para servidor em tempo real, entre em contato com seu [!DNL Audience Manager] consultor e especifique:

* A chave usada para assinar a solicitação.
* O nome do cabeçalho `HTTP(S)` que manterá a assinatura gerada (assinatura X no cabeçalho de exemplo abaixo).
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

1. [!UICONTROL IRIS] cria a  `HTTP(S)` mensagem a ser enviada ao parceiro.
1. [!UICONTROL IRIS] cria uma assinatura com base na  `HTTP(S)` mensagem e na chave privada comunicada pelo parceiro.
1. [!UICONTROL IRIS] envia a  `HTTP(S)` solicitação ao parceiro. Esta mensagem contém a assinatura e a mensagem real, como visto no exemplo acima.
1. O servidor parceiro recebe a solicitação `HTTP(S)`. Ele lê o corpo da mensagem e a assinatura recebida de [!UICONTROL IRIS].
1. Com base no corpo da mensagem recebida e na chave privada, o servidor parceiro recalcula a assinatura. Consulte a seção [Como calcular a assinatura](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) logo abaixo sobre como fazer isso.
1. Compare a assinatura criada no servidor parceiro (receptor) com a recebida de [!UICONTROL IRIS] (remetente).
1. Se as assinaturas corresponderem, então as **autenticidade** e **integridade da mensagem** foram validadas. Somente o remetente, que tem a chave privada, pode enviar uma assinatura válida (autenticidade). Além disso, um homem no meio não pode modificar a mensagem e gerar uma nova assinatura válida, já que não tem a chave privada (integridade da mensagem).

![](assets/iris-digitally-sign-http-request.png)

## Como calcular a assinatura {#calculate-signature}

[!DNL HMAC] (Código de autenticação de mensagem baseado em hash) é o método usado  [!UICONTROL IRIS] para assinatura de mensagem. Implementações e bibliotecas estão disponíveis basicamente em todas as linguagens de programação. [!DNL HMAC] não tem ataques de extensão conhecidos. Veja um exemplo em [!DNL Java] abaixo:

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

A RFC para a implementação de hash [!DNL HMAC] é [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). Um local de teste: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (observe que é necessário [converter](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) a codificação hexadecimal para base64).

## Girar a chave privada {#rotate-private-key}

Para girar a chave privada, os parceiros devem comunicar a nova chave privada ao consultor [!DNL Adobe Audience Manager]. A chave antiga é removida de [!DNL Audience Manager] e [!UICONTROL IRIS] envia somente o novo cabeçalho de assinatura. As teclas foram giradas.

## Dados usados para assinar {#data-signing}

Para destinos do tipo `GET`, a mensagem usada para assinatura será *REQUEST_PATH + STRING de QUERY* (por exemplo, */from-aam-s2s?sids=1,2,3*). O IRIS não leva em conta o nome do host ou os cabeçalhos `HTTP(S)` - eles podem ser modificados / configurados incorretamente ao longo do caminho ou reportados incorretamente.

Para destinos do tipo `POST`, a mensagem usada para assinatura é *REQUEST BODY*. Novamente, os cabeçalhos ou outros parâmetros de solicitação são ignorados.
