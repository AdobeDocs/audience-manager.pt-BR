---
description: Métodos de DELETE e POST que permitem remover destinos e mapeamentos de segmentos.
seo-description: Métodos de DELETE e POST que permitem remover destinos e mapeamentos de segmentos.
seo-title: Excluir destinos
solution: Audience Manager
title: Excluir destinos
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 7%

---


# Excluir destinos {#delete-destinations}

`DELETE` e `POST` métodos que permitem remover destinos e mapeamentos de segmentos.

<!-- r_delete_destinations_all.xml -->

## Excluir um destino

Um `DELETE` método que remove um destino.

>[!NOTE]
>
>Você deve remover todos os mapeamentos de segmentos antes de poder excluir um destino.

* Solicitação: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Resposta: Retorna o código `204 No Content` se bem-sucedido.

## Destinos de Exclusão em Massa

Remova vários destinos com este `POST` método. Transmita IDs de destino ( `destinationId`) com um storage no corpo da solicitação.

* Solicitação: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Resposta: Retorna o código `204 No Content` se bem-sucedido.

## Excluir mapeamentos de destino por ID de mapeamento de segmento

Um `POST` método que remove mapeamentos de destino de acordo com a ID de segmento especificada.

* Solicitação: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Resposta: Retorna o código `204 No Content` se bem-sucedido.