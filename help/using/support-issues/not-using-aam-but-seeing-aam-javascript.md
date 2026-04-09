---
description: Não estamos usando o Audience Manager, mas estamos vendo chamadas Javascript do Audience Manager no depurador Javascript - Por quê?
seo-description: We are not using  but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
seo-title: We are not using Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
solution: Audience Manager
title: Não estamos usando o Audience Manager, mas estamos vendo chamadas Javascript do Audience Manager no depurador Javascript - Por quê?
feature: Support
exl-id: f409e326-17b3-40ee-8570-8d99119fe337
TQID: https://experienceleague.adobe.com/Zpe6ML-WJ5tu4x-gYuPJfAn4IklOxFw2bW8E7ys8YSc
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 136
ht-degree: 98%

---

# Não somos clientes do Audience Manager, mas vemos as chamadas do Javascript do Audience Manager em nosso site

## Pergunta

Não estamos usando o Adobe Audience Manager, mas estamos vendo chamadas Javascript do Audience Manager no depurador Javascript.

Por que isso está acontecendo?

## Resposta

É provável que você esteja executando o [Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) na sua propriedade. Se estiver, ter essa referência do Audience Manager não necessariamente se refere à propriedade que executa o Audience Manager. Em vez disso, significa que o Audience Manager está acionando esse serviço.

Normalmente, a chamada do servidor do Audience Manager é feita para [sincronizar as IDs do cliente](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html).
