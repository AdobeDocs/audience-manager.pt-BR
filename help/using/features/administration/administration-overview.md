---
description: As opções no menu Administração permitem criar usuários Audience Manager e atribuí-los a grupos. Também é possível visualizar limites (características, segmentos, destinos e modelos).
keywords: rbac;RBAC;baseado em função;baseado em função;controles de acesso baseados em função
seo-description: The options under the Administration menu let you create Audience Manager users and assign them to groups. You can also view limits (traits, segments, destinations, and models).
seo-title: Administration
solution: Audience Manager
title: Administração
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
source-git-commit: c29e581c736e03066df7d0698d4ea384e14db467
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 2%

---

# [!UICONTROL Administration] (Controles RBAC) {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> O gerenciamento de conta de usuário está sendo transferido para a [Admin Console](https://helpx.adobe.com/br/enterprise/using/admin-console.html). Para iniciar a migração de usuários, exigimos que todos os clientes do Audience Manager adotem imediatamente as medidas necessárias descritas neste artigo: [Migração de usuário do Audience Manager para o Admin Console](admin-console-migration.md).
> 
> Depois que todos os clientes tiverem migrado, as seções de gerenciamento de usuários deste documento desaparecerão.

>[!IMPORTANT]
>
> Antes que você possa usar [!DNL RBAC], esse recurso deve ser ativado pelo Adobe para sua organização. Entre em contato com a equipe de conta para solicitar [!DNL RBAC] ativação ou entre em contato com o Atendimento ao cliente.


As opções no âmbito do [!UICONTROL Administration] permite criar usuários do Audience Manager e atribuí-los a grupos. Também é possível visualizar limites (características, segmentos, destinos e modelos).

Clientes empresariais que usam o [!DNL Audience Manager] precisam de uma plataforma de gerenciamento de dados para todos os seus dados, mas devem ser capazes de controlar a visibilidade dos diferentes elementos de dados para unidades de negócios específicas. Você pode fazer isso usando permissões de grupo, também chamadas de [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] O usa grupos para atribuir permissões. As permissões não são atribuídas no nível do usuário. As permissões de grupo estão vinculadas aos objetos ([!UICONTROL traits], segmentos etc.) e ações que podem ser executadas nesses objetos (editar, exibir etc.). Esses controles também estão disponíveis por meio das APIs REST do Audience Manager. Consulte [User Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Gerenciamento de grupo](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md), e [Gerenciamento de permissões](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) Métodos da API.

## Criar usuários {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> O gerenciamento de conta de usuário está sendo transferido para a [Admin Console](https://helpx.adobe.com/br/enterprise/using/admin-console.html). Para iniciar a migração de usuários, exigimos que todos os clientes do Audience Manager adotem imediatamente as medidas necessárias descritas neste artigo: [Migração de usuário do Audience Manager para o Admin Console](admin-console-migration.md).
> 
> Depois que todos os clientes tiverem migrado, a seção Gerenciamento de usuários deste documento desaparecerá.
> 
Criar usuários no [!DNL Audience Manager] e especificar detalhes do usuário, status de login e atribuir usuários a grupos.

1. Clique em **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Clique em ![](assets/icon_add.png) para exibir o [!UICONTROL Create New User] página.
1. Em **[!UICONTROL User Details]**, preencha os campos:
   * **[!UICONTROL Username]:** Especifique um nome de usuário exclusivo para o Audience Manager.
   * **[!UICONTROL First Name]:** Especifique o nome do usuário.
   * **[!UICONTROL Last Name]:** Especifique o sobrenome do usuário.
   * **[!UICONTROL Email Address]:** Especifique o endereço de email do usuário. [!DNL Audience Manager] O não envia notificações regulares aos usuários. [!DNL Audience Manager] Os administradores do têm acesso aos endereços de email dos usuários e podem enviar emails manualmente aos usuários, conforme necessário. Por exemplo, se um usuário esquecer a senha, o endereço de email especificado nesse campo será usado para enviar uma senha temporária e instruções para redefinir a senha.
   * **[!UICONTROL Phone Number]:** Especifique o telefone do usuário.
   * **[!UICONTROL Is Admin]:** Especificar se este usuário é um [!DNL Audience Manager] administrador. Usuários administradores podem gerenciar usuários (criar, editar, etc.) e grupos (criar, atribuir permissões etc.). Usuários não administradores podem controlar somente seus próprios perfis de usuário, incluindo editar seus endereços de email e redefinir suas próprias senhas. Para obter mais informações, consulte [Editar as configurações da conta](../../features/administration/edit-account-settings.md).
1. Em **[!UICONTROL Login]**, selecione o status desejado:
   * **[!UICONTROL Active]:**  Os usuários ativos podem acessar [!DNL Audience Manager] e têm as permissões concedidas pela associação de grupo.
   * **[!UICONTROL Deactivated]:**  Usuários desativados não podem acessar o [!DNL Audience Manager] e não têm permissões. Se você desativar os usuários, as informações deles permanecerão em [!DNL Audience Manager] e você pode simplesmente reativá-los, se necessário. Se você remover usuários, será necessário recriá-los se precisarem usar [!DNL Audience Manager] novamente no futuro.
   * **[!UICONTROL Expired]:** A senha de um usuário tem mais de 90 dias.
   * **[!UICONTROL Pending]:** O usuário tem uma senha temporária, como após uma redefinição de senha ou como uma conta totalmente nova, e ainda não definiu uma senha permanente.
   * **[!UICONTROL Locked Out]:** 5 tentativas incorretas de logon bloquearão um usuário.
1. Em **[!UICONTROL Assigned Groups]**, na lista suspensa, selecione os grupos desejados aos quais deseja atribuir esse usuário.
Para obter mais informações sobre grupos e permissões, consulte [Criar um grupo](../../features/administration/administration-overview.md#create-group).
1. Clique em **[!UICONTROL Save]**.

## Criar um [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> O gerenciamento de conta de usuário está sendo transferido para a [Admin Console](https://helpx.adobe.com/br/enterprise/using/admin-console.html). Para iniciar a migração de usuários, recomendamos que todos os clientes do Audience Manager adotem imediatamente as medidas necessárias descritas neste artigo: [Migração de usuário do Audience Manager para o Admin Console](admin-console-migration.md).
> 
> Depois que todos os clientes tiverem migrado, esta seção desaparecerá.

A *grupo* é uma coleção de usuários que compartilham direitos de acesso ao [!UICONTROL destination], [!UICONTROL segment], e [!UICONTROL trait] objetos. Você pode limitar grupos a objetos únicos ou conceder a eles acesso amplo a combinações de objetos diferentes.

<!-- t_create_groups.xml -->

Para criar um grupo:

1. Clique em **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. Clique em  ![](assets/icon_add.png) para abrir o [!UICONTROL Group Settings] página.
3. Em [!UICONTROL Group Details]:
   * Nomeie o grupo.
   * Forneça uma breve descrição do grupo.
4. Entrada [!UICONTROL Group Members], clique em um usuário em **[!UICONTROL Add Users]** opções para adicioná-los ao grupo.
5. Entrada [!UICONTROL Group Permissions], selecione um [característica](../../features/traits/trait-details-page.md), [segmento](../../features/segments/segments-purpose.md)ou [destino](../../features/destinations/destinations.md) de **[!UICONTROL Add Object]**.
Isso abre uma janela de permissões para o objeto selecionado.
6. Marque a caixa de seleção das permissões que você deseja que os membros do grupo tenham.
7. *(Opcional)* Atribuir [Permissões curinga](../../features/administration/administration-overview.md#wild-card-permissions) ao grupo.
8. Clique em **[!UICONTROL Save Group]**.

## Noções básicas [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> O gerenciamento de conta de usuário está sendo transferido para a [Admin Console](https://helpx.adobe.com/br/enterprise/using/admin-console.html). Para iniciar a migração de usuários, recomendamos que todos os clientes do Audience Manager adotem imediatamente as medidas necessárias descritas neste artigo: [Migração de usuário do Audience Manager para o Admin Console](admin-console-migration.md).
> 
> Depois que todos os clientes tiverem migrado, esta seção desaparecerá.

Simplifique o gerenciamento de direitos de grupo com [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] conceder aos membros do grupo acesso automático a cada origem de dados associada a um [!UICONTROL segment], [!UICONTROL destination]ou [!UICONTROL trait]. Por comparação, as permissões regulares permitem apenas atribuir permissões específicas [!UICONTROL data sources] para o um desses objetos. E, quando você adicionar novas [!UICONTROL data sources], os membros do grupo não terão acesso a essas novas fontes.

É necessário abrir as permissões do grupo e atribuir as novas [!UICONTROL data sources] ao grupo. [!UICONTROL Wild Card Permissions] permitir que você evite este manual [!UICONTROL data source] processo de atualização. Grupos com [!UICONTROL Wild Card Permissions] obter acesso a novos [!UICONTROL data sources] sem autorização explícita.

![](assets/wild-card.png)

Leia abaixo uma descrição do que cada [!UICONTROL wildcard permission] significa:

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Os usuários podem selecionar [!UICONTROL traits] como base para [!UICONTROL models].
* `EDIT_ALL_TRAITS` - Os usuários podem editar tudo [!UICONTROL traits] configurados na conta da empresa.
* `VIEW_ALL_TRAITS` - Os usuários podem visualizar todas [!UICONTROL traits] configurados na conta da empresa.
* `DELETE_ALL_TRAITS` - Os usuários podem excluir tudo [!UICONTROL traits] configurados na conta da empresa.
* `CREATE_ALL_ALGO_TRAITS` - Os usuários podem criar [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS` - Os usuários podem adicionar qualquer um dos [!UICONTROL traits] pertencentes à sua empresa para [!UICONTROL segments].
* `CREATE_ALL_TRAITS` - Os usuários podem criar [!UICONTROL traits].

**[!UICONTROL Models]**

* `VIEW_MODELS` - Os usuários têm permissão para visualizar [!UICONTROL models] pertencentes à sua empresa.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Os usuários podem visualizar todas as [!UICONTROL derived signals] pertencentes à sua empresa.
* `CREATE_DERIVED_SIGNALS` - Os usuários podem criar [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS` - Os usuários podem editar todas as [!UICONTROL derived signals] pertencentes à sua empresa.
* `DELETE_DERIVED_SIGNALS` - Os usuários podem excluir qualquer um dos [!UICONTROL derived signals] pertencentes à sua empresa.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Os usuários podem editar todas as [!UICONTROL destinations] configurados na conta da empresa.
* `CREATE_DESTINATIONS` - Os usuários podem criar [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS` - Os usuários podem visualizar todas as [!UICONTROL destinations] configurados na conta da empresa.
* `DELETE_ALL_DESTINATIONS` - Os usuários podem excluir todas as [!UICONTROL destinations] configurados na conta da empresa.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Os usuários podem fazer tudo (exibir, criar, editar, excluir) em seus [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Os usuários podem fazer tudo (exibir, criar, editar, excluir) em seus [!UICONTROL Audience Lab] grupos de teste.

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Os usuários podem criar segmentos.
* `DELETE_ALL_SEGMENTS` - Os usuários podem excluir todos os segmentos configurados em sua conta da empresa.
* `MAP_ALL_TO_DESTINATIONS` - Os usuários podem mapear qualquer um dos segmentos pertencentes à sua empresa para destinos.
* `EDIT_ALL_SEGMENTS` - Os usuários podem editar todos os segmentos configurados em sua conta da empresa.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Os usuários podem selecionar segmentos como linha de base para modelos.
* `VIEW_ALL_SEGMENTS` - Os usuários podem visualizar todos os segmentos configurados em sua conta da empresa.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - Os usuários podem visualizar todos os sinais capturados no [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## Casos de uso {#use-cases}

### Monitorar o acesso do usuário {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] O pode ajudar a monitorar o status de logon do usuário, fornecendo uma imagem clara de quem pode acessar a instância do Audience Manager.

Dependendo das necessidades da sua empresa, você pode ativar e desativar contas de usuário conforme necessário.

![monitor-user-access](assets/monitor-user-access.png)

### Garantir proteção de acesso para informações confidenciais [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

Você pode configurar [!UICONTROL Role-Based Access Control] em [!UICONTROL trait], segmento e [!UICONTROL destination] para cada grupo de usuários.

Esse recurso ajuda a gerenciar como os usuários visualizam, criam, leem, gravam e editam conjuntos de dados específicos e até mesmo a restringir o acesso de usuários a conjuntos de dados que não devem estar disponíveis para eles.

![proteção de acesso](assets/access-protection.png)
