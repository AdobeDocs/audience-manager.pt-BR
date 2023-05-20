---
description: Métodos da API Rest para gerenciar grupos, incluindo criação, atualização, listagem e exclusão de grupos.
seo-description: Rest API methods to manage groups, including creating, updating, listing, deleting groups.
seo-title: Group Management API Methods
solution: Audience Manager
title: Métodos da API de gerenciamento de grupos
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
feature: API
exl-id: b43c8404-1853-4306-8f26-96d9191a2548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 12%

---

# Métodos da API de gerenciamento de grupos {#group-management-api-methods}

Rest [!DNL API] métodos para gerenciar grupos, incluindo criação, atualização, listagem e exclusão de grupos.

<!-- c_rest_api_user_man_group.xml -->

## Criar um grupo {#create-group}

A `POST` para criar um novo grupo de usuários.

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

## Atualizar um grupo {#update-group}

A `PUT` para atualizar um grupo de usuários.

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

## Listar Grupos {#list-groups}

A `GET` para listar grupos de usuários.

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

A `DELETE` método para excluir um grupo de usuários e remover todos os membros desse grupo.

<!-- r_rest_api_group_delete.xml -->

### Solicitação

`DELETE /api/v1/groups/`*`<groupId>`*

Devoluções `204 No Content` se for bem-sucedido. Em caso de retornos de conflito `409 Conflict`.

## Excluir grupos em massa {#delete-groups-bulk}

A `DELETE` método para excluir vários grupos em massa e remover todos os membros desse grupo.

<!-- r_rest_api_group_delete_bulk.xml -->

### Solicitação

`DELETE /api/v1/groups/bulk-delete`

Devoluções `204 No Content` se for bem-sucedido. Em caso de retornos de conflito `409 Conflict`.

## Listar todas as permissões de um grupo {#list-permissions-group}

A `GET` para listar os objetos de permissão em um grupo.

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

Devoluções `400 Bad Request` se o grupo estiver inacessível.

## Definir permissões para um grupo {#set-permissions-group}

A `PUT` para atualizar permissões de grupo. Esse método substitui as permissões antigas pelas novas permissões.

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

O exemplo de resposta representa a lista atualizada de objetos de permissão.

Devoluções `200 OK` se for bem-sucedido. Devoluções `400` se qualquer permissão fornecida for inválida. Também pode retornar `403` se o objeto não estiver acessível ao usuário conectado.
