---
description: Não estamos usando o Audience Manager, mas estamos vendo chamadas Javascript do Audience Manager no depurador Javascript - Por quê?
seo-description: Não estamos usando, mas estamos vendo chamadas Javascript do Audience Manager no depurador Javascript - Por quê?
seo-title: Não estamos usando o Audience Manager, mas estamos vendo chamadas Javascript do Audience Manager no depurador Javascript - Por quê?
solution: Audience Manager
title: Não estamos usando o Audience Manager, mas estamos vendo chamadas Javascript do Audience Manager no depurador Javascript - Por quê?
feature: support
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 100%

---


# Não somos clientes do Audience Manager, mas vemos as chamadas do Javascript do Audience Manager em nosso site

## Pergunta

Não estamos usando o Adobe Audience Manager, mas estamos vendo chamadas Javascript do Audience Manager no depurador Javascript.

Por que isso está acontecendo?

## Resposta

É provável que você esteja executando o [Experience Cloud Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html) na sua propriedade. Se estiver, ter essa referência do Audience Manager não necessariamente se refere à propriedade que executa o Audience Manager. Em vez disso, significa que o Audience Manager está acionando esse serviço.

Normalmente, a chamada do servidor do Audience Manager é feita para [sincronizar as IDs do cliente](https://docs.adobe.com/content/help/pt-BR/id-service/using/id-service-api/methods/setcustomerids.html).
