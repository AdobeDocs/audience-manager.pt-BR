---
description: Não estamos usando o Gerenciador de Audiências, mas estamos vendo chamadas Javascript do Gerenciador de Audiências no depurador Javascript - Por quê?
seo-description: Não estamos usando, mas estamos vendo chamadas Javascript do Gerenciador de Audiências no depurador Javascript - Por quê?
seo-title: Não estamos usando o Gerenciador de Audiências, mas estamos vendo chamadas Javascript do Gerenciador de Audiências no depurador Javascript - Por quê?
solution: Audience Manager
title: Não estamos usando o Gerenciador de Audiências, mas estamos vendo chamadas Javascript do Gerenciador de Audiências no depurador Javascript - Por quê?
translation-type: tm+mt
source-git-commit: 7206b43562eded19bfb30f8aea3bcad946a3f834

---


# Não somos clientes do Gerenciador de Audiências, mas vejam as chamadas do Javascript do Gerenciador de Audiências em nosso site

## Pergunta

Não estamos usando o Adobe Audiência Manager, mas estamos vendo chamadas de Javascript do Audiência Manager no depurador do Javascript.  Por que isso estaria acontecendo?

## Resposta

É provável que você esteja executando o serviço de ID do Visitante em sua propriedade. Se você estiver, essa referência do AAM não se refere necessariamente à propriedade que executa o Gerenciador de Audiências, mas significa que o Gerenciador de Audiências está acionando esse serviço.

Observe que a chamada do AAM geralmente é feita para sincronizar Definir IDs do cliente.
