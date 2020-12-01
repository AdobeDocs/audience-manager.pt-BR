---
description: Restaure métodos de API para gerenciar grupos, incluindo criação, atualização, listagem, exclusão de grupos.
seo-description: Restaure métodos de API para gerenciar grupos, incluindo criação, atualização, listagem, exclusão de grupos.
seo-title: Métodos da API de gerenciamento de grupos
solution: Audience Manager
title: Métodos da API de gerenciamento de grupos
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 13%

---


# Métodos da API de gerenciamento de grupos {#group-management-api-methods}

Restaure métodos [!DNL API] para gerenciar grupos, incluindo criação, atualização, listagem e exclusão de grupos.

<!-- c_rest_api_user_man_group.xml -->

## Criar um grupo {#create-group}

Um método `POST` para criar um novo grupo de usuários.

<!-- r_rest_api_group_create.xml -->

### Solicitação

`POST /api/v1/groups/`

### Corpo de solicitação de amostra

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

## Atualizar um Grupo {#update-group}

Um método `PUT` para atualizar um grupo de usuários.

<!--
r_rest_api_group_update.xml
-->

### Solicitação

`PUT /api/v1/groups/`*`<groupId>`*

### Corpo de solicitação de amostra

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

## Grupos de listas {#list-groups}

Um método `GET` para lista de grupos de usuários.

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

Um método `DELETE` para excluir um grupo de usuários e remover todos os membros desse grupo.

<!-- r_rest_api_group_delete.xml -->

### Solicitação

`DELETE /api/v1/groups/`*`<groupId>`*

Retorna `204 No Content` se bem-sucedido. Em caso de conflito, retorna `409 Conflict`.

## Excluir grupos em massa {#delete-groups-bulk}

Um método `DELETE` para excluir vários grupos em massa e remover todos os membros desse grupo.

<!-- r_rest_api_group_delete_bulk.xml -->

### Solicitação

`DELETE /api/v1/groups/bulk-delete`

Retorna `204 No Content` se bem-sucedido. Em caso de conflito, retorna `409 Conflict`.

## Lista de todas as permissões para um grupo {#list-permissions-group}

Um método `GET` para lista os objetos de permissão em um grupo.

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

Retorna `400 Bad Request` se o grupo estiver inacessível.

## Definir permissões para um grupo {#set-permissions-group}

Um método `PUT` para atualizar permissões de grupo. Este método substitui as permissões antigas pelas novas permissões.

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

Retorna `200 OK` se bem-sucedido. Retorna `400` se qualquer permissão fornecida for inválida. Também pode retornar `403` se o objeto não for acessível pelo usuário conectado.