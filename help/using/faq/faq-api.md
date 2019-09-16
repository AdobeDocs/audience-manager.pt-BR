---
description: Perguntas e problemas comuns da API.
seo-description: Perguntas e problemas comuns da API.
seo-title: Perguntas frequentes sobre API
solution: Audience Manager
title: Perguntas frequentes sobre API
uuid: 8222ebf0-b50e-4f48-8021-dbfca2828b7c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Perguntas frequentes sobre API{#api-faq}

Perguntas e problemas comuns da API.

<!-- 

faq_api.xml

 -->

A documentação da API [](../api/rest-api-main/rest-api-main.md) REST contém detalhes sobre métodos específicos e exemplos de código.

<br> 

**Por que faz[!UICONTROL DIL]chamadas de evento com[!UICONTROL GET]e[!UICONTROL POST]métodos?**

[!UICONTROL DIL] transmite dados para [!DNL Audience Manager] com um `GET` método ou `POST` com base no comprimento da string de consulta da chamada de evento. Esse comportamento é incorporado aos métodos `GET` e `POST` aos métodos por padrão. Não é específico de [!DNL Audience Manager].

* [!UICONTROL DIL] efetua chamadas de evento com `GET` quando um URL contém 2048 caracteres ou menos. Uma chamada `GET` de evento inclui dados no URL como parâmetros da string de consulta, que são passados como pares de valores chave.

* [!UICONTROL DIL] efetua chamadas de evento com `POST` quando um URL contém mais de 2048 caracteres. Uma chamada `POST` de evento inclui dados no corpo da solicitação. [!UICONTROL DIL] coloca dados em pares de valores chave e transmite informações como dados de formulário, em vez de na string de consulta URL.

Embora cada método passe os dados de forma diferente, isso não afeta a funcionalidade. Por exemplo, com qualquer um dos métodos, [!DNL Audience Manager] ainda envia dados para destinos, a sincronização de ID funciona normalmente e você pode criar características a partir de sinais de dados.

<br> 

**O que eles me[!UICONTROL REST API]permitem fazer?**

O [!UICONTROL REST API]s permite que você trabalhe de forma programática com a maioria dos [!DNL Audience Manager] recursos e funções disponíveis na interface do usuário.

<br> 

**Como obter uma ID de[!UICONTROL REST API]cliente e um segredo?**

Entre em contato com seu representante de soluções de parceiros para obter as credenciais de [!DNL API] acesso. Nossas APIs usam os padrões [OAuth 2.0](https://oauth.net/2/) para autenticação, autorização e renovação de token. Consulte Autenticação [OAuth](../api/rest-api-main/aam-api-getting-started.md#oauth) para obter mais informações.
