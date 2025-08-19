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
ht-degree: 3%

---

# Métodos da API da região DCS {#dcs-region-api-methods}

Métodos que permitem listar programaticamente as regiões [!DNL DCS] do Audience Manager.

<!-- c_rest_api_regions.xml -->

Para obter uma lista de regiões e seus números inteiros correspondentes, consulte [IDs de região, locais e nomes de host do DCS](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Listar uma região específica do DCS {#list-specific-dcs-region}

Um método `GET` para listar uma região [!DNL DCS] específica.

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

Retorna `200 OK` em caso de sucesso.

Para obter uma lista de regiões e seus números inteiros correspondentes, consulte [IDs de região, locais e nomes de host do DCS](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Listar regiões DCS {#list-dcs-regions}

Um método `GET` para listar [!DNL DCS] regiões.

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

Retorna `200 OK` em caso de sucesso.

Para obter uma lista de regiões e seus números inteiros correspondentes, consulte [IDs de região, locais e nomes de host do DCS](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
