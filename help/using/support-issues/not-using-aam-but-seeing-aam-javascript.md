---
description: Não estamos usando o Audience Manager, mas estamos vendo chamadas de Audience Manager Javascript no depurador Javascript - Por quê?
seo-description: Não estamos usando, mas estamos vendo chamadas Audience Manager Javascript no depurador Javascript - Por quê?
seo-title: Não estamos usando o Audience Manager, mas estamos vendo chamadas de Audience Manager Javascript no depurador Javascript - Por quê?
solution: Audience Manager
title: Não estamos usando o Audience Manager, mas estamos vendo chamadas de Audience Manager Javascript no depurador Javascript - Por quê?
feature: support
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 1%

---


# Não somos clientes Audience Manager, mas vejam as chamadas do Audience Manager Javascript em nosso site

## Pergunta

Não estamos usando o Adobe Audience Manager, mas estamos vendo chamadas Audience Manager Javascript no depurador Javascript.

Por que isso está acontecendo?

## Resposta

É provável que você esteja executando o Serviço [de identidade do](https://docs.adobe.com/content/help/en/id-service/using/home.html) Experience Cloud em sua propriedade. Se estiver, ter essa referência de Audience Manager não necessariamente se refere à propriedade que está executando o Audience Manager. Em vez disso, significa que a Audience Manager está acionando esse serviço.

A chamada do servidor Audience Manager geralmente é feita para [sincronizar as IDs](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html)do cliente.
