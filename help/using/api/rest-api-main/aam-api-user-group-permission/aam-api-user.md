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

Restaure métodos [!DNL API] para gerenciar usuários, incluindo criação, atualização, listagem, exclusão e retorno de objetos de usuário.

<!-- c_rest_api_user_man_user.xml -->

## Criar um usuário {#create-user}

Um método `POST` para criar um novo usuário.

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

Se `isAdmin` estiver definido como true, o usuário será criado como um administrador parceiro. Essa propriedade também permite saber se um usuário é um administrador parceiro.

Retorna `409 Conflict` se o nome de usuário já estiver sendo usado.

## Atualizar um usuário {#update-user}

Um método `PUT` para atualizar um usuário.

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

Um método `PUT` para atualizar o usuário conectado no momento.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>Embora a maioria dos métodos [!DNL API] só possa ser chamada por administradores de parceiros, esse método pode ser chamado por usuários não administradores.

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

## Atualizar Senha de Usuário Conectado {#update-logged-in-user-pw}

Um método `PUT` para atualizar o usuário conectado no momento.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>Embora a maioria dos métodos [!DNL API] só possa ser chamada por administradores de parceiros, esse método pode ser chamado por usuários não administradores.

### Solicitação

`POST /users/self/update-password`

### Corpo de solicitação de amostra

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Retorna `200 OK` se bem-sucedido. Retorna `400 Bad Request` se algo estiver errado com qualquer uma das senhas.

## Redefinir a senha do usuário conectado {#reset-logged-in-user-pw}

Um método `PUT` para redefinir o usuário conectado no momento. [!UICONTROL Audience Management] envia ao usuário uma senha gerada pelo sistema.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>Embora a maioria dos métodos [!DNL API] só possa ser chamada por administradores de parceiros, esse método pode ser chamado por usuários não administradores.

### Solicitação

`POST /self/reset-password`

Retorna `200 OK` se bem-sucedido.

## Retornar objeto de usuário para uma ID de usuário {#return-user-object-for-id}

Um método `Get` para retornar o objeto de usuário para uma ID de usuário.

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

## Objeto de Retorno de Usuário para Usuário Conectado {#return-user-object-for-logged-in-user}

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

## Usuários da lista {#list-users}

Um método `GET` para lista de usuários.

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

### Corpo de solicitação de amostra

```
{[<user_id_1>, <user_id_2>, ...]}
```
