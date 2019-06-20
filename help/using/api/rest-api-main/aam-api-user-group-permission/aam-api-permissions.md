---
description: Métodos de API rest para gerenciar permissões para objetos e grupos.
seo-description: Métodos de API rest para gerenciar permissões para objetos e grupos.
seo-title: Métodos de API de gerenciamento de permissões
solution: Audience Manager
title: Métodos de API de gerenciamento de permissões
uuid: 111 d 0 f 92-d 92 c -4 d 4 b-b 0 d 6-10 dd 3 fa 4fa 6 ad
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Permissions Management API Methods {#permissions-management-api-methods}

Rest [!DNL API] methods to manage permissions for objects and groups.

<!-- c_rest_api_perm_man.xml -->

## List Available Object Types {#list-object-types}

A `GET` method to list available object types on which role-based access controls can be set.

<!-- r_rest_api_perm_list.xml -->

### Solicitação

`GET /api/v1/permissionable-object-types/`

### Resposta

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## List Available Permissions for an Object Type {#list-permissions-object-type}

A `GET` method to list available permissions for an object type.

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
>Os tipos de objeto TAGS e DERIVADOS derivados não têm permissões regulares para serem usados. Os controles nesses tipos de objeto são alterados somente pelas permissões Todas ou Nada curinga.