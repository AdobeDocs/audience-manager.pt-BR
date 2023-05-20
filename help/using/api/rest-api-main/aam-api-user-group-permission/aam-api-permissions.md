---
description: Métodos da API Rest para gerenciar permissões para objetos e grupos.
seo-description: Rest API methods to manage permissions for objects and groups.
seo-title: Permissions Management API Methods
solution: Audience Manager
title: Métodos da API de gerenciamento de permissões
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
exl-id: 7aac8ea8-4120-4c6b-88a6-30e8aa727dc8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 12%

---

# Métodos da API de gerenciamento de permissões {#permissions-management-api-methods}

Rest [!DNL API] métodos para gerenciar permissões para objetos e grupos.

<!-- c_rest_api_perm_man.xml -->

## Listar Tipos de Objeto Disponíveis {#list-object-types}

A `GET` para listar os tipos de objetos disponíveis nos quais os controles de acesso baseados em função podem ser definidos.

<!-- r_rest_api_perm_list.xml -->

### Solicitação

`GET /api/v1/permissionable-object-types/`

### Resposta

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## Listar Permissões Disponíveis para um Tipo de Objeto {#list-permissions-object-type}

A `GET` para listar as permissões disponíveis para um tipo de objeto.

<!-- r_rest_api_perm_list_perms.xml -->

### Solicitação

`GET /api/v1/permissionable-object-types/SEGMENT/`

### Resposta

```
{ 
 "wildcard" : [ "VIEW_ALL_SEGMENTS", "EDIT_ALL_SEGMENTS", "CREATE_ALL_SEGMENTS", "DELETE_ALL_SEGMENTS", "MAP_ALL_SEGMENTS_TO_MODELS", "MAP_ALL_TO_DESTINATIONS" ], 
 "perObject" : [ "READ", "WRITE", "CREATE", "DELETE", "MAP_TO_MODELS", "MAP_TO_DESTINATION" ]
}
```

>[!NOTE]
>
>Os tipos de objetos TAGS e DERIVED SIGNALS não têm permissões regulares para usar. Os controles desses tipos de objetos são alterados somente pelas Permissões com curinga Tudo ou Nada.
