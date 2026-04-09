---
description: Perguntas e problemas comuns da API.
seo-description: Common API questions and issues.
seo-title: API FAQ
solution: Audience Manager
title: Perguntas frequentes sobre API
uuid: 8222ebf0-b50e-4f48-8021-dbfca2828b7c
feature: API
exl-id: 9a51220e-3f53-4911-876b-16e968d44d0f
TQID: https://experienceleague.adobe.com/IKztfem2G3SCH36c-2Qe5cJWVhPWRLQXjU5TEgF9Cgs
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2:
  - id: c2c33729-f309-4bc2-92ba-87c475259df3
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 239
ht-degree: 100%

---

# Perguntas frequentes sobre API{#api-faq}

Perguntas e problemas comuns da API.

<!-- 

faq_api.xml

 -->

A documentação da [REST API](../api/rest-api-main/rest-api-main.md) tem detalhes sobre métodos específicos e exemplos de código.

<br> 

**Por que [!UICONTROL DIL] fazer chamadas de evento com os métodos [!UICONTROL GET] e [!UICONTROL POST]?**

O [!UICONTROL DIL] transmite dados para o [!DNL Audience Manager] com um método `GET` ou `POST` com base no comprimento da sequência de consulta da chamada de evento. Esse comportamento é incorporado aos métodos `GET` e `POST` por padrão. Não é específico do [!DNL Audience Manager].

* O [!UICONTROL DIL] faz chamadas de evento com `GET` quando um URL tem 2048 caracteres ou menos. Uma chamada de evento `GET` inclui dados no URL como parâmetros de sequência de consulta, que são passados como pares de valor chave.

* O [!UICONTROL DIL] faz chamadas de evento com `POST` quando um URL contém mais de 2048 caracteres. Uma chamada de evento `POST` inclui dados no corpo da solicitação. O [!UICONTROL DIL] coloca os dados em pares de valores chave e transmite as informações como dados de formulário, e não na sequência de caracteres de consulta de URL.

Embora cada método passe os dados de uma maneira diferente, a funcionalidade não é afetada. Por exemplo, com qualquer um dos métodos, o [!DNL Audience Manager] ainda envia dados para destinos, a sincronização de ID funciona normalmente e você pode criar características a partir de sinais de dados.

<br> 

**O que posso fazer com as [!UICONTROL REST API]s?**

Com as [!UICONTROL REST API]s você pode trabalhar de forma programática com a maioria dos recursos e funções do [!DNL Audience Manager] disponíveis na interface do usuário.

<br> 

**Como obter uma ID de cliente [!UICONTROL REST API] e uma senha?**

Entre em contato com seu representante de soluções de parceiros para obter as credenciais de acesso da [!DNL API]. Nossas APIs usam os padrões [OAuth 2.0](https://oauth.net/2/) para autenticação, autorização e renovação de token. Consulte [Autenticação OAuth](../api/rest-api-main/aam-api-getting-started.md#oauth) para obter mais informações.
