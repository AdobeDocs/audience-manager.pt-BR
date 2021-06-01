---
description: Renda os métodos da API para gerenciar usuários, incluindo criar, atualizar, listar, excluir e retornar objetos do usuário.
seo-description: Renda os métodos da API para gerenciar usuários, incluindo criar, atualizar, listar, excluir e retornar objetos do usuário.
seo-title: Métodos da API de gerenciamento de usuários
solution: Audience Manager
title: Métodos da API de gerenciamento de usuários
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
feature: API
exl-id: c015c42c-63c7-4392-9fef-f48dc787a56f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 7%

---

# Métodos da API de gerenciamento de usuários {#user-management-api-methods}

Rastreie métodos [!DNL API] para gerenciar usuários, incluindo criar, atualizar, listar, excluir e retornar objetos do usuário.

<!-- c_rest_api_user_man_user.xml -->

## Criar um usuário {#create-user}

Um método `POST` para criar um novo usuário.

<!-- r_rest_api_user_create.xml -->

### Solicitação

`POST /api/v1/users/`

### Corpo da solicitação de amostra

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

Se `isAdmin` for definido como true, o usuário será criado como um administrador parceiro. Essa propriedade também permite saber se um usuário é um administrador parceiro.

Retorna `409 Conflict` se o nome de usuário já estiver sendo usado.

## Atualizar um Usuário {#update-user}

Um método `PUT` para atualizar um usuário.

<!-- r_rest_api_user_update.xml -->

### Solicitação

`PUT /api/v1/users/`*`<userId>`*

### Corpo da solicitação de amostra

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

Retorna `409 Conflict` se o nome de usuário já estiver sendo usado.

## Atualizar Usuário Conectado {#update-logged-in-user}

Um método `PUT` para atualizar o usuário conectado no momento.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>Embora a maioria dos métodos [!DNL API] só possa ser chamada por administradores de parceiros, esse método pode ser chamado por usuários não administradores.

### Solicitação

`PUT /self/update`

### Corpo da solicitação de amostra

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

Retorna `409 Conflict` se o nome de usuário já estiver sendo usado.

## Atualizar senha de usuário conectado {#update-logged-in-user-pw}

Um método `PUT` para atualizar o usuário conectado no momento.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>Embora a maioria dos métodos [!DNL API] só possa ser chamada por administradores de parceiros, esse método pode ser chamado por usuários não administradores.

### Solicitação

`POST /users/self/update-password`

### Corpo da solicitação de amostra

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Retorna `200 OK` se bem-sucedido. Retorna `400 Bad Request` se algo estiver errado com uma das senhas.

## Redefinir senha de usuário conectado {#reset-logged-in-user-pw}

Um método `PUT` para redefinir o usuário conectado no momento. [!UICONTROL Audience Management] envia ao usuário uma senha gerada pelo sistema.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>Embora a maioria dos métodos [!DNL API] só possa ser chamada por administradores de parceiros, esse método pode ser chamado por usuários não administradores.

### Solicitação

`POST /self/reset-password`

Retorna `200 OK` se bem-sucedido.

## Retornar objeto de usuário para uma ID de usuário {#return-user-object-for-id}

Um método `Get` para retornar o objeto do usuário para uma ID de usuário.

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

Um método `Get` para retornar o objeto do usuário para o usuário conectado no momento.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>Embora a maioria dos métodos [!DNL API] só possa ser chamada por administradores de parceiros, esse método pode ser chamado por usuários não administradores.

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

## Listar usuários {#list-users}

Um método `GET` para listar usuários.

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

Um método `DELETE` para excluir um usuário.

<!-- r_rest_api_user_delete.xml -->

### Solicitação

`DELETE /api/v1/users/`*`<user_id>`*

Retorna `204 No Content` se bem-sucedido. Em caso de conflito, retorna `409 Conflict`.

## Excluir usuários em massa {#delete-users-bulk}

Um método `POST` para excluir vários usuários em massa.

<!-- r_rest_api_user_delete_bulk.xml -->

### Solicitação

`POST /api/v1/users/bulk-delete`

### Corpo da solicitação de amostra

```
{[<user_id_1>, <user_id_2>, ...]}
```
