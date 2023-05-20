---
description: Métodos da API Rest para gerenciar usuários, incluindo criação, atualização, listagem, exclusão e retorno de objetos de usuário.
seo-description: Rest API methods to manage users, including creating, updating, listing, deleting, and returning user objects.
seo-title: User Management API Methods
solution: Audience Manager
title: Métodos da API de gerenciamento de usuários
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
feature: API
exl-id: c015c42c-63c7-4392-9fef-f48dc787a56f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 6%

---

# Métodos da API de gerenciamento de usuários {#user-management-api-methods}

Rest [!DNL API] métodos para gerenciar usuários, incluindo criação, atualização, listagem, exclusão e retorno de objetos de usuário.

<!-- c_rest_api_user_man_user.xml -->

## Criar um usuário {#create-user}

A `POST` para criar um novo usuário.

<!-- r_rest_api_user_create.xml -->

### Solicitação

`POST /api/v1/users/`

### Exemplo de corpo da solicitação

```
{ 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...], 
  "isAdmin" : true | false 
}
```

### Resposta

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...], 
  "isAdmin" : <"true"|"false"> 
 
}
```

Se `isAdmin` for definido como true, o usuário será criado como um administrador parceiro. Essa propriedade também permite saber se um usuário é um administrador de parceiros.

Devoluções `409 Conflict` se o nome de usuário já estiver sendo usado.

## Atualizar um usuário {#update-user}

A `PUT` para atualizar um usuário.

<!-- r_rest_api_user_update.xml -->

### Solicitação

`PUT /api/v1/users/`*`<userId>`*

### Exemplo de corpo da solicitação

```
{ 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...] 
}
```

### Resposta

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "groups" : [<group_1_id>, ...] 
 
}
```

Devoluções `409 Conflict` se o nome de usuário já estiver sendo usado.

## Atualizar Usuário Conectado {#update-logged-in-user}

A `PUT` para atualizar o usuário conectado no momento.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>Considerando que a maioria [!DNL API] Os métodos só podem ser chamados por administradores parceiros. Esse método pode ser chamado por usuários não administradores.

### Solicitação

`PUT /self/update`

### Exemplo de corpo da solicitação

```
{  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null> 
}
```

### Resposta

```
{ 
  "userId": <integer>,,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string> 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null> 
}
```

Devoluções `409 Conflict` se o nome de usuário já estiver sendo usado.

## Atualizar Senha do Usuário Conectado {#update-logged-in-user-pw}

A `PUT` para atualizar o usuário conectado no momento.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>Considerando que a maioria [!DNL API] Os métodos só podem ser chamados por administradores parceiros. Esse método pode ser chamado por usuários não administradores.

### Solicitação

`POST /users/self/update-password`

### Exemplo de corpo da solicitação

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Devoluções `200 OK` se for bem-sucedido. Devoluções `400 Bad Request` se algo estiver errado com uma senha.

## Redefinir Senha do Usuário Conectado {#reset-logged-in-user-pw}

A `PUT` para redefinir o usuário conectado no momento. [!UICONTROL Audience Management] envia ao usuário uma senha gerada pelo sistema.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>Considerando que a maioria [!DNL API] Os métodos só podem ser chamados por administradores parceiros. Esse método pode ser chamado por usuários não administradores.

### Solicitação

`POST /self/reset-password`

Devoluções `200 OK` se for bem-sucedido.

## Retornar objeto de usuário para uma ID de usuário {#return-user-object-for-id}

A `Get` método para retornar o objeto do usuário para uma ID de usuário.

<!-- r_rest_api_user_get_user_obj.xml -->

### Solicitação

`GET /api/v1/users/`*`<userId>`*

### Resposta

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<groupd_id_1>, ...] 
 
}
```

## Retornar objeto de usuário para usuário conectado {#return-user-object-for-logged-in-user}

A `Get` método para retornar o objeto do usuário conectado no momento.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>Considerando que a maioria [!DNL API] Os métodos só podem ser chamados por administradores parceiros. Esse método pode ser chamado por usuários não administradores.

### Solicitação

`GET /api/v1/users/self`

### Resposta

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<groupd_id_1>, ...] 
 
}
```

## Listar Usuários {#list-users}

A `GET` para listar usuários.

<!-- r_rest_api_user_list.xml -->

### Solicitação

`GET /api/v1/users/`

Você pode especificar várias IDs de grupo nos parâmetros de consulta:

`GET /api/v1/users/?groupId=343&groupdId=12`

Esta consulta retorna uma lista de todos os usuários nos grupos especificados.

### Resposta

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...] 
 
}
```

## Excluir um usuário {#delete-users}

A `DELETE` para excluir um usuário.

<!-- r_rest_api_user_delete.xml -->

### Solicitação

`DELETE /api/v1/users/`*`<user_id>`*

Devoluções `204 No Content` se for bem-sucedido. Em caso de retornos de conflito `409 Conflict`.

## Excluir usuários em massa {#delete-users-bulk}

A `POST` para excluir vários usuários em massa.

<!-- r_rest_api_user_delete_bulk.xml -->

### Solicitação

`POST /api/v1/users/bulk-delete`

### Exemplo de corpo da solicitação

```
{[<user_id_1>, <user_id_2>, ...]}
```
