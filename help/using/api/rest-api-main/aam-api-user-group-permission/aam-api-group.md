---
description: Métodos de API rest para gerenciar grupos, incluindo criar, atualizar, listar, excluir grupos.
seo-description: Métodos de API rest para gerenciar grupos, incluindo criar, atualizar, listar, excluir grupos.
seo-title: Métodos de API de gerenciamento de grupos
solution: Audience Manager
title: Métodos de API de gerenciamento de grupos
uuid: fe 042 eb 5-ea 12-42 fe-be 98-d 721 f 987 a 914
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Group Management API Methods {#group-management-api-methods}

Rest [!DNL API] methods to manage groups, including creating, updating, listing, deleting groups.

<!-- c_rest_api_user_man_group.xml -->

## Criar um grupo {#create-group}

`POST` Um método para criar um novo grupo de usuários.

<!-- r_rest_api_group_create.xml -->

### Solicitação

`POST /api/v1/groups/`

### Exemplo de corpo da solicitação

```
 {
    "name" : <string>,
    "description" : <string_may_be_null>,
 }
```

### Resposta

```
  {
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }
```

## Update a Group {#update-group}

`PUT` Um método para atualizar um grupo de usuários.

<!--
r_rest_api_group_update.xml
-->

### Solicitação

`PUT /api/v1/groups/`*`<groupId>`*

### Exemplo de corpo da solicitação

```
 {
    "name" : <string>,
    "description" : <string_may_be_null>,
 }
```

### Resposta

```
  {
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }
```

## List Groups {#list-groups}

A `GET` method to list user groups.

<!--
r_rest_api_group_list.xml
-->

### Solicitação

`GET /api/v1/groups/`

### Resposta

```
[
  { 
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }, ...
]
```

## Excluir um grupo {#delete-groups}

`DELETE` Um método para excluir um grupo de usuários e remover todos os membros desse grupo.

<!-- r_rest_api_group_delete.xml -->

### Solicitação

`DELETE /api/v1/groups/`*`<groupId>`*

Returns `204 No Content` if successful. In case of conflict returns `409 Conflict`.

## Delete Groups in Bulk {#delete-groups-bulk}

`DELETE` Um método para excluir vários grupos em massa e remover todos os membros desse grupo.

<!-- r_rest_api_group_delete_bulk.xml -->

### Solicitação

`DELETE /api/v1/groups/bulk-delete`

Returns `204 No Content` if successful. In case of conflict returns `409 Conflict`.

## List All Permissions for a Group {#list-permissions-group}

A `GET` method to list the permission objects on a group.

<!-- r_rest_api_perm_list_group.xml -->

### Solicitação

`GET /api/v1/groups/{groupId}/permissions`

### Resposta

```
[{
 "objectId" : 34,
 "objectType": "SEGMENT",
 "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
 },

{
 "objectId" : "234",
 "objectType": "TRAIT",
 "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
 },
 {
 "objectId" : 277,
 "objectType": "SEGMENT",
 "permissions": ["READ", "WRITE", "MAP_TO_MODELS"]
 }
]
```

Returns `400 Bad Request` if the group is inaccessible.

## Set Permissions for a Group {#set-permissions-group}

A `PUT` method to update group permissions. Esse método substitui as permissões antigas com as novas permissões.

<!-- r_rest_api_perm_set.xml -->

### Solicitação

`PUT /api/v1/groups/{groupId}/permissions/`

### Resposta

```
[ 
  { "objectType" : "SEGMENT",
    "objectId" : 563,
    "permissions" : [ "READ", "WRITE"]
  },
  { "objectType" : "SEGMENT",
    "objectId" : 2363,
    "permissions" : [ "CREATE", "WRITE"]
  },
  { "objectType" : "TRAIT",
    "objectId" : 83498,
    "permissions" : [ "READ", "MAP_TO_SEGMENTS"]
  },
  { "objectType" : "DESTINATION",
    "objectId" : 304,
    "permissions" : [ "READ", "WRITE", "CREATE"]
  }
]
```

A resposta de amostra representa a lista atualizada de objetos de permissão.

Returns `200 OK` if successful. Returns `400` if any given permission is invalid. Can also return `403` if the object is not accessible by the logged-in user.