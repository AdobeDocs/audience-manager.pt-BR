---
description: Métodos que permitem lista de forma programática para regiões de Audience Manager DCS.
seo-description: Métodos que permitem lista de forma programática para regiões de Audience Manager DCS.
seo-title: Métodos da API da região DCS
solution: Audience Manager
title: Métodos da API da região DCS
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 14%

---


# Métodos da API da região DCS {#dcs-region-api-methods}

Métodos que permitem lista programaticamente [!DNL DCS] as regiões Audience Manager.

<!-- c_rest_api_regions.xml -->

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Lista de uma região específica do DCS {#list-specific-dcs-region}

Um `GET` método para lista uma [!DNL DCS] região específica.

<!-- r_rest_api_regions_list_specific.xml -->

### Solicitação

`GET /v1/dcs-regions/`*`<id>`*

### Resposta de exemplo

```
{ 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code>",
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  }
```

Retorna `200 OK` se bem-sucedido.

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Regiões do DCS de Lista {#list-dcs-regions}

Um `GET` método para lista [!DNL DCS] regiões.

<!-- r_rest_api_regions_list.xml -->

### Solicitação

`GET /v1/dcs-regions/`

### Resposta de exemplo

```
[
  { 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code> # APSE, USE, etc,
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  },
  ...
]
```

Retorna `200 OK` se bem-sucedido.

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
