---
description: As opções no menu Administração permitem que você crie usuários do Audience Manager e os atribua a grupos. Também é possível visualizar limites (características, segmentos, destinos e modelos).
keywords: rbac; RBAC; com base em funções; com base em funções; controles de acesso com base em funções
seo-description: As opções no menu Administração permitem que você crie usuários do Audience Manager e os atribua a grupos. Também é possível visualizar limites (características, segmentos, destinos e modelos).
seo-title: API de
solution: Audience Manager
title: API de
topic: API DIL
uuid: 498 e 0316-cf 1 b -43 e 9-88 ba -338 ee 0 daf 225
translation-type: tm+mt
source-git-commit: 9801bf6a1a4c2c2e7cc2aa8ab32cb81094368554

---


# Administration (RBAC Controls) {#administration}

![](assets/rbac-controls.png)

The options under the [!UICONTROL Administration] menu let you create Audience Manager users and assign them to groups. Também é possível visualizar limites (características, segmentos, destinos e modelos).

Enterprise customers using [!DNL Audience Manager] need one data management platform for all of their data, but must be able to control the visibility of the different data elements to specific business units. You can accomplish this using group permissions, also referred to as [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] usa grupos para atribuir permissões. As permissões não são atribuídas no nível do usuário. As permissões de grupo estão vinculadas a objetos (características, segmentos etc.) e as ações que você pode executar nesses objetos (editar, exibir etc.). Esses controles também estão disponíveis por meio das apis REST do Audience Manager. See [User Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Group Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md), and [Permissions Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API methods.

## Create Users {#create-users}

<!-- t_create_users.xml -->

Create users in [!DNL Audience Manager] and specify user details, login status, and assign users to groups.

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Users]**.
1. Click ![](assets/icon_add.png) to display the [!UICONTROL Create New User] page.
1. Under **[!UICONTROL User Details]**, fill in the fields:
   * **Nome de usuário:** Especifique um nome de usuário exclusivo para o Audience Manager.
   * **Nome:** Especifique o primeiro nome do usuário.
   * **Sobrenome:** Especifique o sobrenome do usuário.
   * **Endereço de email:** Especifique o endereço de email do usuário. [!DNL Audience Manager] não envia uma notificação regular para os usuários. [!DNL Audience Manager] os administradores têm acesso aos endereços de email dos usuários e podem enviar por e-mail manualmente os usuários conforme necessário. Por exemplo, se um usuário esquecer sua senha, o endereço de e-mail especificado neste campo será usado para enviar uma senha temporária e instruções para redefinir a senha.
   * **Número de telefone:** Especifique o número de telefone do usuário.
   * **É Administrador:** Especifique se este usuário é [!DNL Audience Manager] um administrador. Os usuários administradores podem gerenciar usuários (criar, editar etc.) e grupos (criar, atribuir permissões, etc.). Usuários não administradores podem controlar somente seus próprios perfis de usuário, incluindo editar seus endereços de email e redefinir suas próprias senhas. For more information, see [Edit Your Account Settings](../../features/administration/edit-account-settings.md).
1. Under **[!UICONTROL Login]**, select the desired status:
   * **Ativo:** Os usuários ativos podem acessar [!DNL Audience Manager] e ter as permissões concedidas por associação de grupo.
   * **Desativado:** Os usuários desativados não podem acessar [!DNL Audience Manager] e não têm permissões. If you deactivate users, their user information remains in [!DNL Audience Manager] and you can simple reactivate them, if necessary. If you remove users, you must re-create them if they need to use [!DNL Audience Manager] again in the future.
   * **Expirado:** A senha de um usuário é superior a 90 dias.
   * **Pendente:** O usuário tem uma senha temporária, como após uma redefinição de senha ou uma nova conta, e ainda não definiu uma senha permanente.
   * **Bloqueado:** 5 tentativas de login incorretas bloquearão um usuário.
1. Under **[!UICONTROL Assigned Groups]**, from the drop-down list, select the desired groups to which you want to assign this user.
For more information about groups and permissions, see [Create a Group](../../features/administration/administration-overview.md#create-group).
1. Clique em **[!UICONTROL Save]**.

## Criar um grupo {#create-group}

A *group* is a collection of users that share access rights to destination, segment, and trait objects. É possível limitar grupos somente a objetos individuais ou conceder a eles amplo acesso a combinações de objetos diferentes.

<!-- t_create_groups.xml -->

Para criar um grupo:

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Groups]**.
1. Click  ![](assets/icon_add.png) to open the [!UICONTROL Group Settings] page.
1. Em [!UICONTROL Group Details]:
   * Dê um nome para o grupo.
   * Forneça uma descrição resumida do grupo.
1. In [!UICONTROL Group Members], click a user from **[!UICONTROL Add Users]** options to add them to the group.
1. In [!UICONTROL Group Permissions], select a [trait](../../features/traits/trait-details-page.md), [segment](../../features/segments/segments-purpose.md), or [destination](../../features/destinations/destinations.md) from **[!UICONTROL Add Object]**.
Isso abre uma janela de permissões para o objeto selecionado.
1. Marque a caixa de seleção para obter as permissões que deseja que os membros do grupo tenham.
1. *(Opcional)* Atribuir [permissões curinga](../../features/administration/administration-overview.md#wild-card-permissions) ao grupo.
1. Clique em **[!UICONTROL Save Group]**.

## Understanding Wild Card Permissions {#wild-card-permissions}

Simplify group rights management with [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] conceder aos membros do grupo acesso automático a cada fonte de dados associada a um segmento, destino ou característica. Por comparação, as permissões regulares apenas permitem atribuir fontes de dados específicas a um desses objetos. E, quando você adiciona novas fontes de dados, os membros do grupo não obtêm acesso a essas novas fontes.

Você precisa abrir as permissões do grupo e atribuir essas novas fontes de dados ao grupo. [!UICONTROL Wild Card Permissions] permite evitar esse processo manual de atualização de fonte de dados. Groups with [!UICONTROL Wild Card Permissions] get access to new data sources without explicit authorization.

![](assets/wild-card.png)

Ler abaixo para obter uma descrição do que cada permissão de caractere curinga significa:

**Características**

* `MAP_ALL_TRAITS_TO_MODELS` - precisa esclarecer?
* `EDIT_ALL_TRAITS` - Os usuários podem editar todas as características pertencentes à empresa (PID)
* `VIEW_ALL_TRAITS` - Os usuários podem exibir todas as características pertencentes à empresa (PID)
* `DELETE_ALL_TRAITS` - Os usuários podem excluir todas as características pertencentes à sua empresa (PID).
* `CREATE_ALL_ALGO_TRAITS` - precisa esclarecer
* `MAP_ALL_TO_SEGMENTS` - Os usuários podem adicionar qualquer uma das características pertencentes à empresa a segmentos.
* `CREATE_ALL_TRAITS` - Os usuários podem criar características.

**Relatórios**

* `PTRREPORTS` - Essa permissão de curinga refere-se à funcionalidade desatualizada e será removida da interface do usuário do Audience Manager em breve.

**Modelos**

* `VIEW_MODELS` - Os usuários têm permissão para visualizar modelos que pertencem à empresa.

**Sinais derivados**

* `VIEW_DERIVED_SIGNALS` - Os usuários podem exibir todos os sinais derivados pertencentes à sua empresa.
* `CREATE_DERIVED_SIGNALS` - Os usuários podem criar sinais derivados.
* `EDIT_DERIVED_SIGNALS` - Os usuários podem editar todos os sinais derivados pertencentes à sua empresa.
* `DELETE_DERIVED_SIGNALS` - Os usuários podem excluir qualquer um dos sinais derivados pertencentes à sua empresa.

**Destino**

* `EDIT_ALL_DESTINATIONS` - Os usuários podem editar todo o destino configurado na conta da empresa.
* `CREATE_DESTINATIONS` - Os usuários podem criar destinos.
* `VIEW_ALL_DESTINATIONS` - Os usuários podem exibir todos os destinos configurados na conta da empresa.
* `DELETE_ALL_DESTINATIONS` - Os usuários podem excluir todos os destinos configurados na conta da empresa.

**Tags**

* `VIEW_TAGS` - Os usuários podem fazer tudo (exibir, criar, editar, excluir) em suas contêineres de tag.

**Laboratório de público-alvo**

* `MANAGE_SEGMENT_TEST_GROUPS` - Os usuários podem fazer tudo (exibir, criar, editar, excluir) em grupos de teste do Audience Lab.

**Segmento**

* `CREATE_ALL_SEGMENTS` - Os usuários podem criar segmentos.
* `DELETE_ALL_SEGMENTS` - Os usuários podem excluir todos os segmentos configurados na conta da empresa.
* `MAP_ALL_TO_DESTINATIONS` - Os usuários podem mapear qualquer segmento que pertence à empresa para destinos.
* `EDIT_ALL_SEGMENTS` - Os usuários podem editar todos os segmentos configurados na conta da empresa.
* `MAP_ALL_SEGMENTS_TO_MODELS` - precisa esclarecer?
* `VIEW_ALL_SEGMENTS` - Os usuários podem exibir todos os segmentos configurados na conta da empresa.

**Sinais**

* `VIEW_ALL_SIGNALS` - Os usuários podem exibir todos os sinais capturados no [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).