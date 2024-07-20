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
ht-degree: 1%

---

# Métodos da API de gerenciamento de usuários {#user-management-api-methods}

Restaure [!DNL API] métodos para gerenciar usuários, incluindo criação, atualização, listagem, exclusão e retorno de objetos de usuário.

<!-- c_rest_api_user_man_user.xml -->

## Criar um usuário {#create-user}

Um método `POST` para criar um novo usuário.

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

Se `isAdmin` estiver definido como verdadeiro, o usuário será criado como administrador parceiro. Essa propriedade também permite saber se um usuário é um administrador de parceiros.

Retorna `409 Conflict` se o nome de usuário já estiver em uso.

## Atualizar um usuário {#update-user}

Um método `PUT` para atualizar um usuário.

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

Retorna `409 Conflict` se o nome de usuário já estiver em uso.

## Atualizar Usuário Conectado {#update-logged-in-user}

Um método `PUT` para atualizar o usuário conectado no momento.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>Embora a maioria dos métodos [!DNL API] possa ser chamada apenas por administradores parceiros, esse método pode ser chamado por usuários não administradores.

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

Retorna `409 Conflict` se o nome de usuário já estiver em uso.

## Atualizar Senha do Usuário Conectado {#update-logged-in-user-pw}

Um método `PUT` para atualizar o usuário conectado no momento.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>Embora a maioria dos métodos [!DNL API] possa ser chamada apenas por administradores parceiros, esse método pode ser chamado por usuários não administradores.

### Solicitação

`POST /users/self/update-password`

### Exemplo de corpo da solicitação

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Retorna `200 OK` em caso de sucesso. Retorna `400 Bad Request` se algo estiver errado com uma das senhas.

## Redefinir Senha do Usuário Conectado {#reset-logged-in-user-pw}

Um método `PUT` para redefinir o usuário conectado no momento. [!UICONTROL Audience Management] envia ao usuário uma senha gerada pelo sistema.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>Embora a maioria dos métodos [!DNL API] possa ser chamada apenas por administradores parceiros, esse método pode ser chamado por usuários não administradores.

### Solicitação

`POST /self/reset-password`

Retorna `200 OK` em caso de sucesso.

## Retornar objeto de usuário para uma ID de usuário {#return-user-object-for-id}

Um método `Get` para retornar o objeto de usuário para uma ID de Usuário.

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

Um método `Get` para retornar o objeto do usuário conectado no momento.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>Embora a maioria dos métodos [!DNL API] possa ser chamada apenas por administradores parceiros, esse método pode ser chamado por usuários não administradores.

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

Método `DELETE` para excluir usuário.

<!-- r_rest_api_user_delete.xml -->

### Solicitação

`DELETE /api/v1/users/`*`<user_id>`*

Retorna `204 No Content` em caso de sucesso. Em caso de conflito retorna `409 Conflict`.

## Excluir usuários em massa {#delete-users-bulk}

Um método `POST` para excluir vários usuários em massa.

<!-- r_rest_api_user_delete_bulk.xml -->

### Solicitação

`POST /api/v1/users/bulk-delete`

### Exemplo de corpo da solicitação

```
{[<user_id_1>, <user_id_2>, ...]}
```
