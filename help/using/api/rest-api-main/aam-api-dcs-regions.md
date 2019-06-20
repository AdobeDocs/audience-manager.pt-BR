---
description: Métodos que permitem listar programaticamente as regiões do Audience Manager DCS.
seo-description: Métodos que permitem listar programaticamente as regiões do Audience Manager DCS.
seo-title: Métodos de API de região DCS
solution: Audience Manager
title: Métodos de API de região DCS
uuid: 00 b 70927-b 3 b 7-46 bb -8 be 1-37 c 6100 ecf 80
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DCS Region API Methods {#dcs-region-api-methods}

Methods that let you programmatically list Audience Manager [!UICONTROL DCS] regions.

<!-- c_rest_api_regions.xml -->

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## List a Specific DCS Region {#list-specific-dcs-region}

A `GET` method to list a specific [!UICONTROL DCS] region.

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

Returns `200 OK` if successful.

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## List DCS Regions {#list-dcs-regions}

A `GET` method to list [!UICONTROL DCS] regions.

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

Returns `200 OK` if successful.

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
