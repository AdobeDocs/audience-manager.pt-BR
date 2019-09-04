---
description: Envie dados para a API DCS usando métodos GET ou POST.
seo-description: Envie dados para a API DCS usando métodos GET ou POST.
seo-title: Métodos de API DCS
solution: Audience Manager
title: Métodos de API DCS
uuid: 6 e 407458-11 d 4-4342-a 84 a -512 afa 5 fc 183
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Métodos de API DCS {#dcs-api-methods}

Enviar dados para [!UICONTROL DCS][!DNL API] o uso `GET` ou `POST` métodos.

É possível enviar dados para o [!UICONTROL DCS] uso de um dos métodos `GET` ou `POST` dos métodos. Consulte as chamadas de amostra abaixo, usando [curvas](https://curl.haxx.se/). Nas três chamadas de amostra, adicionamos os sinais `c_likes = famous popstar` e `c_loves = famous actress` o perfil `12345678901234567890123456789012345678`do dispositivo.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Substitua um valor real para o espaço reservado ao enviar dados para o método [!UICONTROL DCS] com este método.

## Enviar dados por GET {#send-data-via-get}

Observe que o tamanho máximo permitido para `GET` chamadas é de 8 K.

<pre><code>curl -i "<i>yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&amp;d_rtbd=jsonc_likes=famous%20popstar&amp;c_loves=famous%20actress</i><i></i><i></i><i></i>"</code></pre>

## Enviar dados via POST {#send-data-via-post}

Observe os requisitos para o envio de dados usando `POST` o método:

* O tamanho máximo permitido é de 32 K.
* Defina o tipo de conteúdo para `application/x-www-form-urlencoded`.

### Chamada de exemplo

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
