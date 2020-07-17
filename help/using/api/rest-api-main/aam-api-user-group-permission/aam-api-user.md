---
description: Restaure métodos de API para gerenciar usuários, incluindo criar, atualizar, listar, excluir e retornar objetos de usuário.
seo-description: Restaure métodos de API para gerenciar usuários, incluindo criar, atualizar, listar, excluir e retornar objetos de usuário.
seo-title: Métodos da API de gerenciamento de usuários
solution: Audience Manager
title: Métodos da API de gerenciamento de usuários
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 7%

---


# Métodos da API de gerenciamento de usuários {#user-management-api-methods}

Restaure [!DNL API] métodos para gerenciar usuários, incluindo criar, atualizar, listar, excluir e retornar objetos do usuário.

<!-- c_rest_api_user_man_user.xml -->

## Create a User {#create-user}

Um `POST` método para criar um novo usuário.

<!-- r_rest_api_user_create.xml -->

### Solicitação

`POST /api/v1/users/`

### Corpo de solicitação de amostra

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

## Atualizar um usuário {#update-user}

Um `PUT` método para atualizar um usuário.

<!-- r_rest_api_user_update.xml -->

### Solicitação

`PUT /api/v1/users/`*`<userId>`*

### Corpo de solicitação de amostra

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

## Atualizar usuário conectado {#update-logged-in-user}

Um `PUT` método para atualizar o usuário conectado no momento.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>Enquanto a maioria dos [!DNL API] métodos só é chamável por administradores de parceiros, esse método é chamável por usuários não administradores.

### Solicitação

`PUT /self/update`

### Corpo de solicitação de amostra

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

Um `PUT` método para atualizar o usuário conectado no momento.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>Enquanto a maioria dos [!DNL API] métodos só é chamável por administradores de parceiros, esse método é chamável por usuários não administradores.

### Solicitação

`POST /users/self/update-password`

### Corpo de solicitação de amostra

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Retorna `200 OK` se bem-sucedido. Retorna `400 Bad Request` se algo estiver errado com qualquer uma das senhas.

## Redefinir senha de usuário conectado {#reset-logged-in-user-pw}

Um `PUT` método para redefinir o usuário conectado no momento. [!UICONTROL Audience Management] envia ao usuário uma senha gerada pelo sistema.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>Enquanto a maioria dos [!DNL API] métodos só é chamável por administradores de parceiros, esse método é chamável por usuários não administradores.

### Solicitação

`POST /self/reset-password`

Retorna `200 OK` se bem-sucedido.

## Retornar objeto de usuário para uma ID de usuário {#return-user-object-for-id}

Um `Get` método para retornar o objeto de usuário para uma ID de usuário.

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

Um `Get` método para retornar o objeto de usuário para o usuário conectado no momento.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>Enquanto a maioria dos [!DNL API] métodos só é chamável por administradores de parceiros, esse método é chamável por usuários não administradores.

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

## Usuários da Lista {#list-users}

Um `GET` método para lista de usuários.

<!-- r_rest_api_user_list.xml -->

### Solicitação

`GET /api/v1/users/`

É possível especificar várias IDs de grupo nos parâmetros do query:

`GET /api/v1/users/?groupId=343&groupdId=12`

Esse query retorna uma lista de todos os usuários nos grupos especificados.

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

## Delete a User {#delete-users}

Um `DELETE` método para excluir um usuário.

<!-- r_rest_api_user_delete.xml -->

### Solicitação

`DELETE /api/v1/users/`*`<user_id>`*

Retorna `204 No Content` se bem-sucedido. Em caso de retornos em conflito `409 Conflict`.

## Excluir usuários em massa {#delete-users-bulk}

Um `POST` método para excluir vários usuários em massa.

<!-- r_rest_api_user_delete_bulk.xml -->

### Solicitação

`POST /api/v1/users/bulk-delete`

### Corpo de solicitação de amostra

```
{[<user_id_1>, <user_id_2>, ...]}
```
