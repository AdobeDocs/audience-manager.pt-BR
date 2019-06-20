---
description: Perguntas e problemas comuns da API.
seo-description: Perguntas e problemas comuns da API.
seo-title: Perguntas frequentes sobre API
solution: Audience Manager
title: Perguntas frequentes sobre API
uuid: 8222 ebf 0-b 50 e -4 f 48-8021-dbfca 2828 b 7 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# API FAQ{#api-faq}

Perguntas e problemas comuns da API.

<!-- 

faq_api.xml

 -->

The [REST API](../api/rest-api-main/rest-api-main.md) documentation contains details about specific methods and code samples.

<br> 

**Por que[!UICONTROL DIL]fazer chamadas de evento e[!UICONTROL GET][!UICONTROL POST]métodos?**

[!UICONTROL DIL] envia dados com [!DNL Audience Manager] base no `GET``POST` comprimento da string de consulta da chamada de evento. This behavior is built in to `GET` and `POST` methods by default. It is not specific to [!DNL Audience Manager].

* [!UICONTROL DIL] faz chamadas de evento com `GET` o URL com 2048 caracteres ou menos. A `GET` event call includes data in the URL as query string parameters, which are passed in as key-value pairs.

* [!UICONTROL DIL] faz chamadas de evento com `POST` quando um URL contém mais de 2048 caracteres. A `POST` event call includes data in the body of the request. [!UICONTROL DIL] coloca dados em pares de valores chave e passa informações como dados do formulário, em vez da sequência de consulta do URL.

Embora cada método passe dados de uma maneira diferente, isso não afeta a funcionalidade. For example, with either method, [!DNL Audience Manager] still sends data to destinations, ID syncs works normally, and you can create traits from data signals.

<br> 

**O que[!UICONTROL REST API]é permitido para mim?**

[!UICONTROL REST API]s permite que você trabalhe de forma programática com a maioria [!DNL Audience Manager] dos recursos e funções disponíveis na interface do usuário.

<br> 

**Como obtenho uma ID[!UICONTROL REST API]do cliente e um segredo?**

Contact your Partner Solutions representative to obtain [!DNL API] access credentials. Our APIs use [OAuth 2.0](https://oauth.net/2/) standards for token authentication, authorization, and renewal. See [OAuth Authentication](../api/rest-api-main/aam-api-getting-started.md#oauth) for more information.
