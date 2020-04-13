---
description: Não estamos usando o Gerenciador de Audiências, mas estamos vendo chamadas Javascript do Gerenciador de Audiências no depurador Javascript - Por quê?
seo-description: Não estamos usando, mas estamos vendo chamadas Javascript do Gerenciador de Audiências no depurador Javascript - Por quê?
seo-title: Não estamos usando o Gerenciador de Audiências, mas estamos vendo chamadas Javascript do Gerenciador de Audiências no depurador Javascript - Por quê?
solution: Audience Manager
title: Não estamos usando o Gerenciador de Audiências, mas estamos vendo chamadas Javascript do Gerenciador de Audiências no depurador Javascript - Por quê?
translation-type: tm+mt
source-git-commit: 1f5c1a91f0b5df5291d3143d297e25128b5bb716

---


# Não somos clientes do Gerenciador de Audiências, mas vejam as chamadas do Javascript do Gerenciador de Audiências em nosso site

## Pergunta

Não estamos usando o Adobe Audiência Manager, mas estamos vendo chamadas de Javascript do Audiência Manager no depurador do Javascript.

Por que isso está acontecendo?

## Resposta

É provável que você esteja executando o Serviço [de identidade da](https://docs.adobe.com/content/help/en/id-service/using/home.html) Experience Cloud em sua propriedade. Se estiver, ter essa referência do Gerenciador de Audiências não necessariamente se refere à propriedade que executa o Gerenciador de Audiências. Em vez disso, isso significa que o Gerenciador de Audiências está acionando esse serviço.

Normalmente, a chamada do servidor do Gerenciador de Audiências é feita para [sincronizar as IDs](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html)do cliente.
