---
description: Envie dados para a API DCS usando os métodos GET ou POST.
seo-description: Send data to the DCS API using GET or POST methods.
seo-title: DCS API Methods
solution: Audience Manager
title: Métodos da DCS API
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
exl-id: 258994e1-6b15-4ae1-9e1f-c6e0685350c1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 0%

---

# [!DNL DCS] [!DNL API] Métodos {#dcs-api-methods}

Enviar dados para [!DNL DCS] [!DNL API] usando os métodos `GET` ou `POST`.

Você pode enviar dados para [!DNL DCS] usando um dos métodos `GET` ou `POST`. Veja as chamadas de exemplo abaixo, usando [curl](https://curl.haxx.se/). Em todas as três chamadas de exemplo, estamos adicionando os sinais `c_likes = famous popstar` e `c_loves = famous actress` ao perfil do dispositivo `12345678901234567890123456789012345678`.

## Enviar Dados via [!DNL GET] {#send-data-via-get}

Observe que o tamanho máximo permitido para chamadas de `GET` é de 8K.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Enviar Dados via [!DNL POST] {#send-data-via-post}

Observe os requisitos para enviar dados usando o método `POST`:

* O tamanho máximo permitido é 32K.
* Defina o tipo de conteúdo como `application/x-www-form-urlencoded`.

### Exemplo de chamada

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
