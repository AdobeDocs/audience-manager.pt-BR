---
description: As opções no menu Administração permitem criar usuários do Audience Manager e atribuí-los a grupos. Também é possível visualizar limites (características, segmentos, destinos e modelos).
keywords: rbac; RBAC; baseado em função; baseado em função; controles de acesso baseados em função
seo-description: The options under the Administration menu let you create Audience Manager users and assign them to groups. You can also view limits (traits, segments, destinations, and models).
seo-title: Administration
solution: Audience Manager
title: Administração
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
source-git-commit: 8ef6e8eb4351c24b55703b1788c68c580f199fc8
workflow-type: tm+mt
source-wordcount: '1159'
ht-degree: 2%

---

# [!UICONTROL Administration] (Controles RBAC) {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> O gerenciamento da conta de usuário está sendo transferido para o [Admin Console](https://helpx.adobe.com/br/enterprise/using/admin-console.html). Para iniciar a migração de usuários, exigimos que todos os clientes do Audience Manager tomem imediatamente as medidas necessárias descritas neste artigo: [Migração do usuário do Audience Manager para o Admin Console](admin-console-migration.md).
> 
> Depois que todos os clientes tiverem migrado, as seções de gerenciamento de usuários deste documento desaparecerão.


As opções na [!UICONTROL Administration] permite criar usuários do Audience Manager e atribuí-los a grupos. Também é possível visualizar limites (características, segmentos, destinos e modelos).

Clientes empresariais que utilizam [!DNL Audience Manager] precisa de uma plataforma de gerenciamento de dados para todos os seus dados, mas deve ser capaz de controlar a visibilidade dos diferentes elementos de dados para unidades de negócios específicas. Você pode fazer isso usando permissões de grupo, também conhecidas como [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] O usa grupos para atribuir permissões. As permissões não são atribuídas no nível do usuário. Permissões de grupo são vinculadas a objetos ([!UICONTROL traits], segmentos etc.) e às ações que você pode executar nesses objetos (editar, exibir, etc.). Esses controles também estão disponíveis por meio das APIs REST do Audience Manager. Consulte [Gerenciamento de usuários](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Gerenciamento de grupos](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)e [Gerenciamento de permissões](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) Métodos da API.

## Criar usuários {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> O gerenciamento da conta de usuário está sendo transferido para o [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Para iniciar a migração de usuários, exigimos que todos os clientes do Audience Manager tomem imediatamente as medidas necessárias descritas neste artigo: [Migração do usuário do Audience Manager para o Admin Console](admin-console-migration.md).
> 
> Depois que todos os clientes tiverem migrado, a seção de gerenciamento de usuários deste documento desaparecerá.
Criar usuários em [!DNL Audience Manager] e especificar detalhes do usuário, status de logon e atribuir usuários a grupos.

1. Clique em **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Clique em ![](assets/icon_add.png) para exibir o [!UICONTROL Create New User] página.
1. Em **[!UICONTROL User Details]**, preencha os campos:
   * **[!UICONTROL Username]:** Especifique um nome de usuário exclusivo para Audience Manager.
   * **[!UICONTROL First Name]:** Especifique o nome do usuário.
   * **[!UICONTROL Last Name]:** Especifique o sobrenome do usuário.
   * **[!UICONTROL Email Address]:** Especifique o endereço de email do usuário. [!DNL Audience Manager] não envia notificações regulares aos usuários. [!DNL Audience Manager] Os administradores têm acesso aos endereços de email dos usuários e podem enviar emails manualmente aos usuários, conforme necessário. Por exemplo, se um usuário esquecer a senha, o endereço de email especificado nesse campo será usado para enviar uma senha temporária e instruções para redefinir a senha.
   * **[!UICONTROL Phone Number]:** Especifique o número de telefone do usuário.
   * **[!UICONTROL Is Admin]:** Especificar se este usuário é um [!DNL Audience Manager] administrador. Usuários administradores podem gerenciar usuários (criar, editar etc.) e grupos (criar, atribuir permissões etc.). Usuários não administradores podem controlar somente seus próprios perfis de usuário, incluindo a edição de seus endereços de email e a redefinição de suas próprias senhas. Para obter mais informações, consulte [Editar as configurações da conta](../../features/administration/edit-account-settings.md).
1. Em **[!UICONTROL Login]**, selecione o status desejado:
   * **[!UICONTROL Active]:**  Os usuários ativos podem acessar [!DNL Audience Manager] e ter as permissões concedidas pela associação a grupos.
   * **[!UICONTROL Deactivated]:**  Usuários desativados não podem acessar [!DNL Audience Manager] e não têm permissões. Se você desativar usuários, as informações dele permanecerão em [!DNL Audience Manager] e você pode simplesmente reativá-los, se necessário. Se você remover usuários, será necessário recriá-los se eles precisarem usar [!DNL Audience Manager] de novo no futuro.
   * **[!UICONTROL Expired]:** A senha de um usuário tem mais de 90 dias.
   * **[!UICONTROL Pending]:** O usuário tem uma senha temporária, como após uma redefinição de senha ou como uma conta totalmente nova, e ainda não definiu uma senha permanente.
   * **[!UICONTROL Locked Out]:** 5 tentativas incorretas de logon bloquearão um usuário.
1. Em **[!UICONTROL Assigned Groups]**, na lista suspensa, selecione os grupos desejados aos quais deseja atribuir esse usuário.
Para obter mais informações sobre grupos e permissões, consulte [Criar um grupo](../../features/administration/administration-overview.md#create-group).
1. Clique em **[!UICONTROL Save]**.

## Criar um [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> O gerenciamento da conta de usuário está sendo transferido para o [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Para iniciar a migração de usuários, recomendamos que todos os clientes do Audience Manager tomem imediatamente as medidas necessárias descritas neste artigo: [Migração do usuário do Audience Manager para o Admin Console](admin-console-migration.md).
> 
> Depois que todos os clientes tiverem migrado, esta seção desaparecerá.

A *grupo* é uma coleção de usuários que compartilham direitos de acesso com a [!UICONTROL destination], [!UICONTROL segment]e [!UICONTROL trait] objetos. É possível limitar grupos a objetos únicos ou conceder a eles amplo acesso a combinações de objetos diferentes.

<!-- t_create_groups.xml -->

Para criar um grupo:

1. Clique em **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. Clique em  ![](assets/icon_add.png) para abrir o [!UICONTROL Group Settings] página.
3. Em [!UICONTROL Group Details]:
   * Nomeie o grupo.
   * Forneça uma breve descrição do grupo.
4. Em [!UICONTROL Group Members], clique em um usuário de **[!UICONTROL Add Users]** para adicioná-las ao grupo.
5. Em [!UICONTROL Group Permissions], selecione um [característica](../../features/traits/trait-details-page.md), [segmento](../../features/segments/segments-purpose.md)ou [destino](../../features/destinations/destinations.md) from **[!UICONTROL Add Object]**.
Isso abre uma janela de permissões para o objeto selecionado.
6. Marque a caixa de seleção das permissões que você deseja que os membros do grupo tenham.
7. *(Opcional)* Atribuir [Permissões curinga](../../features/administration/administration-overview.md#wild-card-permissions) ao grupo.
8. Clique em **[!UICONTROL Save Group]**.

## Noções básicas [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> O gerenciamento da conta de usuário está sendo transferido para o [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Para iniciar a migração de usuários, recomendamos que todos os clientes do Audience Manager tomem imediatamente as medidas necessárias descritas neste artigo: [Migração do usuário do Audience Manager para o Admin Console](admin-console-migration.md).
> 
> Depois que todos os clientes tiverem migrado, esta seção desaparecerá.

Simplifique o gerenciamento de direitos de grupo com [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] conceder aos membros do grupo acesso automático a cada fonte de dados associada a uma [!UICONTROL segment], [!UICONTROL destination]ou [!UICONTROL trait]. Por comparação, as permissões regulares permitem atribuir somente permissões específicas [!UICONTROL data sources] para um desses objetos. E quando você adiciona novos [!UICONTROL data sources], os membros do grupo não têm acesso a essas novas fontes.

É necessário abrir as permissões do grupo e atribuir as novas [!UICONTROL data sources] ao grupo. [!UICONTROL Wild Card Permissions] permita evitar este manual [!UICONTROL data source] processo de atualização. Grupos com [!UICONTROL Wild Card Permissions] obter acesso a novos [!UICONTROL data sources] sem autorização expressa.

![](assets/wild-card.png)

Leia abaixo uma descrição do que cada [!UICONTROL wildcard permission] significa:

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Os usuários podem selecionar [!UICONTROL traits] como a linha de base para [!UICONTROL models].
* `EDIT_ALL_TRAITS` - Os usuários podem editar tudo [!UICONTROL traits] configurar na conta da empresa.
* `VIEW_ALL_TRAITS` - Os usuários podem visualizar tudo [!UICONTROL traits] configurar na conta da empresa.
* `DELETE_ALL_TRAITS` - Os usuários podem excluir tudo [!UICONTROL traits] configurar na conta da empresa.
* `CREATE_ALL_ALGO_TRAITS` - Usuários podem criar [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS` - Os usuários podem adicionar qualquer um dos [!UICONTROL traits] que pertençam à sua empresa [!UICONTROL segments].
* `CREATE_ALL_TRAITS` - Usuários podem criar [!UICONTROL traits].

**[!UICONTROL Models]**

* `VIEW_MODELS` - Os usuários têm permissão para visualizar [!UICONTROL models] que pertençam à sua empresa.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Os usuários podem visualizar todas as [!UICONTROL derived signals] que pertençam à sua empresa.
* `CREATE_DERIVED_SIGNALS` - Usuários podem criar [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS` - Os usuários podem editar todas as [!UICONTROL derived signals] que pertençam à sua empresa.
* `DELETE_DERIVED_SIGNALS` - Os usuários podem excluir qualquer um dos [!UICONTROL derived signals] que pertençam à sua empresa.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Os usuários podem editar todas as [!UICONTROL destinations] configurar na conta da empresa.
* `CREATE_DESTINATIONS` - Usuários podem criar [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS` - Os usuários podem visualizar todas as [!UICONTROL destinations] configurar na conta da empresa.
* `DELETE_ALL_DESTINATIONS` - Os usuários podem excluir todas as [!UICONTROL destinations] configurar na conta da empresa.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Os usuários podem fazer tudo (exibir, criar, editar, excluir) em seus [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Os usuários podem fazer tudo (exibir, criar, editar, excluir) em seus [!UICONTROL Audience Lab] grupos de teste.

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Os usuários podem criar segmentos.
* `DELETE_ALL_SEGMENTS` - Os usuários podem excluir todos os segmentos configurados em sua conta da empresa.
* `MAP_ALL_TO_DESTINATIONS` - Os usuários podem mapear qualquer um dos segmentos pertencentes à sua empresa para destinos.
* `EDIT_ALL_SEGMENTS` - Os usuários podem editar todos os segmentos configurados em sua conta da empresa.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Os usuários podem selecionar segmentos como linha de base para os modelos.
* `VIEW_ALL_SEGMENTS` - Os usuários podem visualizar todos os segmentos configurados em sua conta da empresa.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - Os usuários podem visualizar todos os sinais capturados em [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## Casos de uso {#use-cases}

### Monitorar o acesso do usuário {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] O pode ajudar você a monitorar o status de logon do usuário, fornecendo uma imagem clara de quem pode acessar a instância do Audience Manager.

Dependendo dos requisitos de sua empresa, você pode ativar e desativar as contas de usuário, conforme necessário.

![monitorar-usuário-acesso](assets/monitor-user-access.png)

### Garantir proteção de acesso para sensibilidade [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

Você pode configurar [!UICONTROL Role-Based Access Control] at [!UICONTROL trait], segmento e [!UICONTROL destination] , para cada grupo de usuários.

Esse recurso ajuda você a gerenciar a forma como seus usuários visualizam, criam, leem, gravam e editam conjuntos de dados específicos, e até mesmo impede que os usuários acessem conjuntos de dados que não devem estar disponíveis para eles.

![proteção de acesso](assets/access-protection.png)
