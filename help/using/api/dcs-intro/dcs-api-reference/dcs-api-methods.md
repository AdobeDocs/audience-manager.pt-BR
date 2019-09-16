---
description: Envie dados para a API DCS usando os métodos GET ou POST.
seo-description: Envie dados para a API DCS usando os métodos GET ou POST.
seo-title: Métodos da API DCS
solution: Audience Manager
title: Métodos da API DCS
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
translation-type: tm+mt
source-git-commit: bdea2609b84d7f80d67452b4c43e11cbef01a368

---


# Métodos da API DCS {#dcs-api-methods}

Envie dados para o [!UICONTROL DCS] usando [!DNL API] ou `GET` `POST` métodos.

É possível enviar dados para o [!UICONTROL DCS] usando um dos métodos `GET` ou `POST` . Veja as chamadas de amostra abaixo, usando [curl](https://curl.haxx.se/). Em todas as três chamadas de amostra, estamos adicionando os sinais `c_likes = famous popstar` e `c_loves = famous actress` ao perfil do dispositivo `12345678901234567890123456789012345678`.


## Enviar dados via GET {#send-data-via-get}

Observe que o tamanho máximo permitido para `GET` chamadas é de 8K.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Enviar dados via POST {#send-data-via-post}

Observe os requisitos para o envio de dados usando o `POST` método:

* O tamanho máximo permitido é 32 K.
* Defina o tipo de conteúdo como `application/x-www-form-urlencoded`.

### Exemplo de chamada

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
