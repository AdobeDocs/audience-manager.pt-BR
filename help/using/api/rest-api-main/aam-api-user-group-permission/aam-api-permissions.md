---
description: Restaure métodos de API para gerenciar permissões para objetos e grupos.
seo-description: Restaure métodos de API para gerenciar permissões para objetos e grupos.
seo-title: Métodos da API de gerenciamento de permissões
solution: Audience Manager
title: Métodos da API de gerenciamento de permissões
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 14%

---


# Métodos da API de gerenciamento de permissões {#permissions-management-api-methods}

Restaure [!DNL API] métodos para gerenciar permissões para objetos e grupos.

<!-- c_rest_api_perm_man.xml -->

## Tipos de objetos disponíveis de Lista {#list-object-types}

Um `GET` método para lista de tipos de objetos disponíveis nos quais controles de acesso baseados em funções podem ser definidos.

<!-- r_rest_api_perm_list.xml -->

### Solicitação

`GET /api/v1/permissionable-object-types/`

### Resposta

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## Permissões disponíveis de Lista para um tipo de objeto {#list-permissions-object-type}

Um `GET` método para lista de permissões disponíveis para um tipo de objeto.

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
>Os tipos de objetos TAGS e SINAIS DERIVADOS não têm permissões regulares para usar. Os controles nesses tipos de objetos são alterados somente pelas Permissões de Todos ou Nenhum Curinga.