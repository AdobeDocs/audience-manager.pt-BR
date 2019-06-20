---
description: Métodos DELETE e POST que permitem remover destinos e mapeamentos de segmentos.
seo-description: Métodos DELETE e POST que permitem remover destinos e mapeamentos de segmentos.
seo-title: Excluir destinos
solution: Audience Manager
title: Excluir destinos
uuid: 38 fb 2228-e 564-49 a 3-9930-3139 f 8799 a 8 f
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# Delete Destinations {#delete-destinations}

`DELETE``POST` e métodos que permitem remover destinos e mapeamentos de segmentos.

<!-- r_delete_destinations_all.xml -->

## Excluir um destino

A `DELETE` method that removes a destination.

>[!NOTE]
>
>É necessário remover todos os mapeamentos de segmento antes de excluir um destino.

* Request: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Response: Returns code `204 No Content` if successful.

## Destinos de exclusão em massa

Remove multiple destinations with this `POST` method. Pass in destination IDs ( `destinationId`) with an array in the request body.

* Solicitação: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Response: Returns code `204 No Content` if successful.

## Excluir mapeamentos de destino por ID de mapeamento de segmento

`POST` Um método que remove mapeamentos de destino de acordo com a ID do segmento especificada.

* Request: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Response: Returns code `204 No Content` if successful.