---
description: Métodos DELETE e POST que permitem remover destinos e mapeamentos de segmento.
seo-description: Métodos DELETE e POST que permitem remover destinos e mapeamentos de segmento.
seo-title: Excluir destinos
solution: Audience Manager
title: Excluir destinos
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
exl-id: eaac3908-75ab-42d2-93bd-e8979f8b2427
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 8%

---

# Excluir destinos {#delete-destinations}

`DELETE` e  `POST` métodos que permitem remover destinos e mapeamentos de segmento.

<!-- r_delete_destinations_all.xml -->

## Excluir um destino

Um método `DELETE` que remove um destino.

>[!NOTE]
>
>Você deve remover todos os mapeamentos de segmento antes de excluir um destino.

* Solicitação: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Resposta: Retorna o código `204 No Content` se bem-sucedido.

## Destinos de exclusão em massa

Remova vários destinos com este método `POST`. Transmita IDs de destino ( `destinationId`) com uma matriz no corpo da solicitação.

* Solicitação: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Resposta: Retorna o código `204 No Content` se bem-sucedido.

## Excluir mapeamentos de destino por ID de mapeamento de segmento

Um método `POST` que remove os mapeamentos de destino de acordo com a ID de segmento especificada.

* Solicitação: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Resposta: Retorna o código `204 No Content` se bem-sucedido.
