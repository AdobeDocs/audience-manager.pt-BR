---
description: Métodos que permitem listar programaticamente as regiões do Audience Manager DCS.
seo-description: Methods that let you programmatically list Audience Manager DCS regions.
seo-title: DCS Region API Methods
solution: Audience Manager
title: Métodos da API da região DCS
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
exl-id: 3cd1700e-6914-46be-a0be-a870c472343e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 12%

---

# Métodos da API da região DCS {#dcs-region-api-methods}

Métodos que permitem listar o Audience Manager de forma programática [!DNL DCS] regiões.

<!-- c_rest_api_regions.xml -->

Para obter uma lista de regiões e seus números inteiros correspondentes, consulte [IDs da região do DCS, locais e nomes de host](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Listar uma região específica do DCS {#list-specific-dcs-region}

A `GET` para listar um item específico [!DNL DCS] região.

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

Devoluções `200 OK` se for bem-sucedido.

Para obter uma lista de regiões e seus números inteiros correspondentes, consulte [IDs da região do DCS, locais e nomes de host](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Listar regiões DCS {#list-dcs-regions}

A `GET` método para listar [!DNL DCS] regiões.

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

Devoluções `200 OK` se for bem-sucedido.

Para obter uma lista de regiões e seus números inteiros correspondentes, consulte [IDs da região do DCS, locais e nomes de host](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
