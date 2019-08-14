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
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# Administração (controles RBAC) {#administration}

![](assets/rbac-controls.png)

As opções no [!UICONTROL Administration] menu permitem que você crie usuários do Audience Manager e os atribua a grupos. Também é possível visualizar limites (características, segmentos, destinos e modelos).

Os clientes do Enterprise que usam [!DNL Audience Manager] uma plataforma de gerenciamento de dados para todos os seus dados, mas devem ser capazes de controlar a visibilidade dos diferentes elementos de dados para unidades comerciais específicas. Você pode fazer isso usando permissões de grupo, também conhecido como [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] usa grupos para atribuir permissões. As permissões não são atribuídas no nível do usuário. As permissões de grupo estão vinculadas a objetos (características, segmentos etc.) e as ações que você pode executar nesses objetos (editar, exibir etc.). Esses controles também estão disponíveis por meio das apis REST do Audience Manager. Consulte [Métodos de API de gerenciamento de usuários](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [gerenciamento](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)de grupos e [permissões](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) .

## Create Users {#create-users}

<!-- t_create_users.xml -->

Crie usuários em [!DNL Audience Manager] e especifique detalhes do usuário, status de logon e atribua usuários a grupos.

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Users]**.
1. Clique ![](assets/icon_add.png) em para exibir a [!UICONTROL Create New User] página.
1. Under **[!UICONTROL User Details]**, fill in the fields:
   * **Nome de usuário:** Especifique um nome de usuário exclusivo para o Audience Manager.
   * **Nome:** Especifique o primeiro nome do usuário.
   * **Sobrenome:** Especifique o sobrenome do usuário.
   * **Endereço de email:** Especifique o endereço de email do usuário. [!DNL Audience Manager] não envia uma notificação regular para os usuários. [!DNL Audience Manager] os administradores têm acesso aos endereços de email dos usuários e podem enviar por e-mail manualmente os usuários conforme necessário. Por exemplo, se um usuário esquecer sua senha, o endereço de e-mail especificado neste campo será usado para enviar uma senha temporária e instruções para redefinir a senha.
   * **Número de telefone:** Especifique o número de telefone do usuário.
   * **É Administrador:** Especifique se este usuário é [!DNL Audience Manager] um administrador. Os usuários administradores podem gerenciar usuários (criar, editar etc.) e grupos (criar, atribuir permissões, etc.). Usuários não administradores podem controlar somente seus próprios perfis de usuário, incluindo editar seus endereços de email e redefinir suas próprias senhas. Para obter mais informações, consulte [Editar configurações de conta](../../features/administration/edit-account-settings.md).
1. Em **[!UICONTROL Login]**, selecione o status desejado:
   * **Ativo:** Os usuários ativos podem acessar [!DNL Audience Manager] e ter as permissões concedidas por associação de grupo.
   * **Desativado:** Os usuários desativados não podem acessar [!DNL Audience Manager] e não têm permissões. Se você desativar usuários, suas informações de usuário permanecerão em [!DNL Audience Manager] e você poderá reativá-las simples, se necessário. Se você remover usuários, será necessário recriá-los se eles precisarem usá-los [!DNL Audience Manager] novamente no futuro.
   * **Expirado:** A senha de um usuário é superior a 90 dias.
   * **Pendente:** O usuário tem uma senha temporária, como após uma redefinição de senha ou uma nova conta, e ainda não definiu uma senha permanente.
   * **Bloqueado:** 5 tentativas de login incorretas bloquearão um usuário.
1. Na **[!UICONTROL Assigned Groups]**lista suspensa, selecione os grupos desejados aos quais você deseja atribuir esse usuário.
Para obter mais informações sobre grupos e permissões, consulte [Criar um grupo](../../features/administration/administration-overview.md#create-group).
1. Clique em **[!UICONTROL Save]**.

## Criar um grupo {#create-group}

Um *grupo* é uma coleção de usuários que compartilham direitos de acesso a objetos de destino, segmento e característica. É possível limitar grupos somente a objetos individuais ou conceder a eles amplo acesso a combinações de objetos diferentes.

<!-- t_create_groups.xml -->

Para criar um grupo:

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Groups]**.
1. Clique ![](assets/icon_add.png) em para abrir a [!UICONTROL Group Settings] página.
1. Em [!UICONTROL Group Details]:
   * Dê um nome para o grupo.
   * Forneça uma descrição resumida do grupo.
1. Em [!UICONTROL Group Members], clique em um usuário de **[!UICONTROL Add Users]** opções para adicioná-las ao grupo.
1. Em [!UICONTROL Group Permissions], selecione uma [característica](../../features/traits/trait-details-page.md), [segmento](../../features/segments/segments-purpose.md)ou [destino](../../features/destinations/destinations.md) de **[!UICONTROL Add Object]**.
Isso abre uma janela de permissões para o objeto selecionado.
1. Marque a caixa de seleção para obter as permissões que deseja que os membros do grupo tenham.
1. *(Opcional)* Atribuir [permissões curinga](../../features/administration/administration-overview.md#wild-card-permissions) ao grupo.
1. Clique em **[!UICONTROL Save Group]**.

## Noções básicas sobre permissões curinga {#wild-card-permissions}

Simplifique o gerenciamento de direitos do grupo.[!UICONTROL Wild Card Permissions]

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] conceder aos membros do grupo acesso automático a cada fonte de dados associada a um segmento, destino ou característica. Por comparação, as permissões regulares apenas permitem atribuir fontes de dados específicas a um desses objetos. E, quando você adiciona novas fontes de dados, os membros do grupo não obtêm acesso a essas novas fontes.

Você precisa abrir as permissões do grupo e atribuir essas novas fontes de dados ao grupo. [!UICONTROL Wild Card Permissions] permite evitar esse processo manual de atualização de fonte de dados. Grupos com [!UICONTROL Wild Card Permissions] acesso a novas fontes de dados sem autorização explícita.

![](assets/wild-card.png)

Ler abaixo para obter uma descrição do que cada permissão de caractere curinga significa:

**Características**

* `MAP_ALL_TRAITS_TO_MODELS` - Os usuários podem selecionar características como a linha de base para modelos.
* `EDIT_ALL_TRAITS` - Os usuários podem editar todas as características definidas na conta da empresa.
* `VIEW_ALL_TRAITS` - Os usuários podem exibir todas as características definidas na conta da empresa.
* `DELETE_ALL_TRAITS` - Os usuários podem excluir todas as características definidas na conta da empresa.
* `CREATE_ALL_ALGO_TRAITS` - Os usuários podem criar características algorítmicas.
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
* `MAP_ALL_SEGMENTS_TO_MODELS` - Os usuários podem selecionar segmentos como a linha de base para modelos.
* `VIEW_ALL_SEGMENTS` - Os usuários podem exibir todos os segmentos configurados na conta da empresa.

**Sinais**

* `VIEW_ALL_SIGNALS` - Os usuários podem exibir todos os sinais capturados no [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).