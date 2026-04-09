---
description: Métodos que permitem listar programaticamente as regiões do Audience Manager DCS.
seo-description: Methods that let you programmatically list Audience Manager DCS regions.
seo-title: DCS Region API Methods
solution: Audience Manager
title: Métodos da API da região DCS
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
exl-id: 3cd1700e-6914-46be-a0be-a870c472343e
TQID: https://experienceleague.adobe.com/ipsOlq24Y00SHvGKgUFJHnRQ11DZIuDNY76D5LCAgso
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2: id: d8f681b8-67cc-42dc-85c5-a0977528a942
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 110
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
