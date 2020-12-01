---
description: Envie dados para a API DCS usando métodos GET ou POST.
seo-description: Envie dados para a API DCS usando métodos GET ou POST.
seo-title: Métodos da DCS API
solution: Audience Manager
title: Métodos da DCS API
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 6%

---


# [!DNL DCS] [!DNL API] Métodos {#dcs-api-methods}

Envie dados para [!DNL DCS] [!DNL API] usando os métodos `GET` ou `POST`.

Você pode enviar dados para [!DNL DCS] usando um dos métodos `GET` ou `POST`. Observe as chamadas de amostra abaixo, usando [curl](https://curl.haxx.se/). Em todas as três chamadas de amostra, estamos adicionando os sinais `c_likes = famous popstar` e `c_loves = famous actress` ao perfil do dispositivo `12345678901234567890123456789012345678`.

## Enviar dados via [!DNL GET] {#send-data-via-get}

Observe que o tamanho máximo permitido para chamadas `GET` é de 8K.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Enviar dados via [!DNL POST] {#send-data-via-post}

Observe os requisitos para enviar dados usando o método `POST`:

* O tamanho máximo permitido é 32 K.
* Defina o tipo de conteúdo como `application/x-www-form-urlencoded`.

### Exemplo de chamada

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
