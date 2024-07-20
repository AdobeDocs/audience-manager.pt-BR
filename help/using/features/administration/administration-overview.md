---
description: As opções no menu Administração permitem criar usuários Audience Manager e atribuí-los a grupos. Também é possível visualizar limites (características, segmentos, destinos e modelos).
keywords: rbac;RBAC;baseado em função;baseado em função;controles de acesso baseados em função
seo-description: The options under the Administration menu let you create Audience Manager users and assign them to groups. You can also view limits (traits, segments, destinations, and models).
seo-title: Administration
solution: Audience Manager
title: API de
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
source-git-commit: c29e581c736e03066df7d0698d4ea384e14db467
workflow-type: tm+mt
source-wordcount: '1173'
ht-degree: 0%

---

# [!UICONTROL Administration] (Controles RBAC) {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> O gerenciamento de conta de usuário está sendo movido para o [Admin Console](https://helpx.adobe.com/br/enterprise/using/admin-console.html). Para iniciar a migração de usuários, exigimos que todos os clientes do Audience Manager adotem imediatamente as medidas necessárias descritas neste artigo: [Migração de usuários do Audience Manager para o Admin Console](admin-console-migration.md).
> 
> Depois que todos os clientes tiverem migrado, as seções de gerenciamento de usuários deste documento desaparecerão.

>[!IMPORTANT]
>
> Para que você possa usar o [!DNL RBAC], esse recurso deve ser habilitado pelo Adobe para sua organização. Entre em contato com a equipe de conta para solicitar a ativação do [!DNL RBAC] ou com o Atendimento ao cliente.


As opções no menu [!UICONTROL Administration] permitem criar usuários Audience Manager e atribuí-los a grupos. Também é possível visualizar limites (características, segmentos, destinos e modelos).

Os clientes corporativos que usam o [!DNL Audience Manager] precisam de uma plataforma de gerenciamento de dados para todos os seus dados, mas devem ser capazes de controlar a visibilidade dos diferentes elementos de dados para unidades de negócios específicas. Você pode fazer isso usando permissões de grupo, também chamadas de [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] usa grupos para atribuir permissões. As permissões não são atribuídas no nível do usuário. Permissões de grupo são vinculadas a objetos ([!UICONTROL traits], segmentos, etc.) e ações que podem ser executadas nesses objetos (editar, exibir etc.). Esses controles também estão disponíveis por meio das APIs REST do Audience Manager. Consulte os métodos de API de [Gerenciamento de usuários](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Gerenciamento de grupos](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md) e [Gerenciamento de permissões](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md).

## Criar usuários {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> O gerenciamento de conta de usuário está sendo movido para o [Admin Console](https://helpx.adobe.com/br/enterprise/using/admin-console.html). Para iniciar a migração de usuários, exigimos que todos os clientes do Audience Manager adotem imediatamente as medidas necessárias descritas neste artigo: [Migração de usuários do Audience Manager para o Admin Console](admin-console-migration.md).
> 
> Depois que todos os clientes tiverem migrado, a seção Gerenciamento de usuários deste documento desaparecerá.
> 
Crie usuários no [!DNL Audience Manager] e especifique os detalhes do usuário, o status de logon e atribua usuários a grupos.

1. Clique em **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Clique em ![](assets/icon_add.png) para exibir a página [!UICONTROL Create New User].
1. Em **[!UICONTROL User Details]**, preencha os campos:
   * **[!UICONTROL Username]:** Especifique um nome de usuário exclusivo para o Audience Manager.
   * **[!UICONTROL First Name]:** Especifique o nome do usuário.
   * **[!UICONTROL Last Name]:** Especifique o sobrenome do usuário.
   * **[!UICONTROL Email Address]:** Especifique o endereço de email do usuário. [!DNL Audience Manager] não envia notificações regulares aos usuários. Os administradores do [!DNL Audience Manager] têm acesso aos endereços de email dos usuários e podem enviar emails manualmente aos usuários, conforme necessário. Por exemplo, se um usuário esquecer a senha, o endereço de email especificado nesse campo será usado para enviar uma senha temporária e instruções para redefinir a senha.
   * **[!UICONTROL Phone Number]:** Especifique o número de telefone do usuário.
   * **[!UICONTROL Is Admin]:** Especifique se este usuário é um administrador [!DNL Audience Manager]. Usuários administradores podem gerenciar usuários (criar, editar, etc.) e grupos (criar, atribuir permissões etc.). Usuários não administradores podem controlar somente seus próprios perfis de usuário, incluindo editar seus endereços de email e redefinir suas próprias senhas. Para obter mais informações, consulte [Editar Configurações da Conta](../../features/administration/edit-account-settings.md).
1. Em **[!UICONTROL Login]**, selecione o status desejado:
   * **[!UICONTROL Active]:** usuários ativos podem acessar [!DNL Audience Manager] e ter as permissões concedidas pela associação de grupo.
   * **[!UICONTROL Deactivated]:** Usuários desativados não podem acessar [!DNL Audience Manager] e não têm permissões. Se você desativar os usuários, as informações deles permanecerão no [!DNL Audience Manager] e você poderá simplesmente reativá-los, se necessário. Se você remover usuários, será necessário recriá-los se eles precisarem usar [!DNL Audience Manager] novamente no futuro.
   * **[!UICONTROL Expired]:** A senha de um usuário tem mais de 90 dias.
   * **[!UICONTROL Pending]:** O usuário tem uma senha temporária, como após uma redefinição de senha ou como uma conta totalmente nova, e ainda não definiu uma senha permanente.
   * **[!UICONTROL Locked Out]:** 5 tentativas de logon incorretas bloquearão um usuário.
1. Em **[!UICONTROL Assigned Groups]**, na lista suspensa, selecione os grupos desejados aos quais deseja atribuir este usuário.
Para obter mais informações sobre grupos e permissões, consulte [Criar um grupo](../../features/administration/administration-overview.md#create-group).
1. Clique em **[!UICONTROL Save]**.

## Criar um [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> O gerenciamento de conta de usuário está sendo movido para o [Admin Console](https://helpx.adobe.com/br/enterprise/using/admin-console.html). Para iniciar a migração de usuários, recomendamos que todos os clientes do Audience Manager adotem imediatamente as medidas necessárias descritas neste artigo: [Migração de usuários do Audience Manager para o Admin Console](admin-console-migration.md).
> 
> Depois que todos os clientes tiverem migrado, esta seção desaparecerá.

Um *grupo* é uma coleção de usuários que compartilham direitos de acesso a objetos [!UICONTROL destination], [!UICONTROL segment] e [!UICONTROL trait]. Você pode limitar grupos a objetos únicos ou conceder a eles acesso amplo a combinações de objetos diferentes.

<!-- t_create_groups.xml -->

Para criar um grupo:

1. Clique em **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. Clique em ![](assets/icon_add.png) para abrir a página [!UICONTROL Group Settings].
3. Em [!UICONTROL Group Details]:
   * Nomeie o grupo.
   * Forneça uma breve descrição do grupo.
4. Em [!UICONTROL Group Members], clique em um usuário em **[!UICONTROL Add Users]** opções para adicioná-lo ao grupo.
5. Em [!UICONTROL Group Permissions], selecione uma [característica](../../features/traits/trait-details-page.md), [segmento](../../features/segments/segments-purpose.md) ou [destino](../../features/destinations/destinations.md) de **[!UICONTROL Add Object]**.
Isso abre uma janela de permissões para o objeto selecionado.
6. Marque a caixa de seleção das permissões que você deseja que os membros do grupo tenham.
7. *(Opcional)* Atribuir [Permissões Curinga](../../features/administration/administration-overview.md#wild-card-permissions) ao grupo.
8. Clique em **[!UICONTROL Save Group]**.

## Compreendendo [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> O gerenciamento de conta de usuário está sendo movido para o [Admin Console](https://helpx.adobe.com/br/enterprise/using/admin-console.html). Para iniciar a migração de usuários, recomendamos que todos os clientes do Audience Manager adotem imediatamente as medidas necessárias descritas neste artigo: [Migração de usuários do Audience Manager para o Admin Console](admin-console-migration.md).
> 
> Depois que todos os clientes tiverem migrado, esta seção desaparecerá.

Simplifique o gerenciamento de direitos de grupo com [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] conceda aos membros do grupo acesso automático a cada fonte de dados associada a [!UICONTROL segment], [!UICONTROL destination] ou [!UICONTROL trait]. Por comparação, as permissões regulares permitem atribuir somente [!UICONTROL data sources] específicos a um desses objetos. E, quando você adiciona um novo [!UICONTROL data sources], os membros do grupo não obtêm acesso a essas novas fontes.

Você precisa abrir as permissões do grupo e atribuir os novos [!UICONTROL data sources] ao grupo. O [!UICONTROL Wild Card Permissions] permite que você evite esse processo manual de atualização do [!UICONTROL data source]. Grupos com [!UICONTROL Wild Card Permissions] obtêm acesso ao novo [!UICONTROL data sources] sem autorização explícita.

![](assets/wild-card.png)

Leia abaixo uma descrição do que cada [!UICONTROL wildcard permission] significa:

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Os usuários podem selecionar [!UICONTROL traits] como a linha de base para [!UICONTROL models].
* `EDIT_ALL_TRAITS` - Os usuários podem editar todos os [!UICONTROL traits] configurados em suas contas da empresa.
* `VIEW_ALL_TRAITS` - Os usuários podem exibir todos os [!UICONTROL traits] configurados em suas contas da empresa.
* `DELETE_ALL_TRAITS` - Os usuários podem excluir todos os [!UICONTROL traits] configurados em suas contas da empresa.
* `CREATE_ALL_ALGO_TRAITS` - Usuários podem criar [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS` - Os usuários podem adicionar qualquer um dos [!UICONTROL traits] pertencentes à sua empresa em [!UICONTROL segments].
* `CREATE_ALL_TRAITS` - Usuários podem criar [!UICONTROL traits].

**[!UICONTROL Models]**

* `VIEW_MODELS` - Os usuários têm permissão para exibir [!UICONTROL models] pertencente à sua empresa.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Os usuários podem exibir todos os [!UICONTROL derived signals] que pertencem à sua empresa.
* `CREATE_DERIVED_SIGNALS` - Usuários podem criar [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS` - Os usuários podem editar todas as [!UICONTROL derived signals] pertencentes à sua empresa.
* `DELETE_DERIVED_SIGNALS` - Os usuários podem excluir qualquer [!UICONTROL derived signals] pertencente à sua empresa.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Os usuários podem editar todas as [!UICONTROL destinations] configuradas em suas contas da empresa.
* `CREATE_DESTINATIONS` - Usuários podem criar [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS` - Os usuários podem exibir todas as [!UICONTROL destinations] configuradas em suas contas da empresa.
* `DELETE_ALL_DESTINATIONS` - Os usuários podem excluir todas as [!UICONTROL destinations] configuradas em suas contas da empresa.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Os usuários podem fazer tudo (exibir, criar, editar, excluir) em seus [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Os usuários podem fazer tudo (exibir, criar, editar, excluir) em seus grupos de teste [!UICONTROL Audience Lab].

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Usuários podem criar segmentos.
* `DELETE_ALL_SEGMENTS` - Os usuários podem excluir todos os segmentos configurados em sua conta da empresa.
* `MAP_ALL_TO_DESTINATIONS` - Os usuários podem mapear qualquer um dos segmentos pertencentes à sua empresa para destinos.
* `EDIT_ALL_SEGMENTS` - Os usuários podem editar todos os segmentos configurados em sua conta da empresa.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Os usuários podem selecionar segmentos como linha de base para modelos.
* `VIEW_ALL_SEGMENTS` - Os usuários podem exibir todos os segmentos configurados em sua conta da empresa.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - Os usuários podem exibir todos os sinais capturados na [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## Casos de uso {#use-cases}

### Monitorar o acesso do usuário {#monitoring-user-access}

O [!UICONTROL Role-Based Access Control] pode ajudá-lo a monitorar o status de logon do usuário, fornecendo uma visão clara de quem pode acessar sua instância do Audience Manager.

Dependendo das necessidades da sua empresa, você pode ativar e desativar contas de usuário conforme necessário.

![acesso-monitor-usuário](assets/monitor-user-access.png)

### Assegurar Proteção de Acesso para [!UICONTROL Data Sources] Confidencial {#protect-sensitive-data-sources}

Você pode configurar o [!UICONTROL Role-Based Access Control] no nível [!UICONTROL trait], segmento e [!UICONTROL destination] para cada grupo de usuários.

Esse recurso ajuda a gerenciar como os usuários visualizam, criam, leem, gravam e editam conjuntos de dados específicos e até mesmo a restringir o acesso de usuários a conjuntos de dados que não devem estar disponíveis para eles.

![proteção de acesso](assets/access-protection.png)
