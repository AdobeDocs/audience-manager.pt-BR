---
description: As opções no menu Administração permitem que você crie usuários de Audience Manager e os atribua a grupos. Você também pode visualização de limites (características, segmentos, destinos e modelos).
keywords: rbac;RBAC;baseado em função;baseado em função;controles de acesso baseados em função
seo-description: As opções no menu Administração permitem que você crie usuários de Audience Manager e os atribua a grupos. Você também pode visualização de limites (características, segmentos, destinos e modelos).
seo-title: Administração
solution: Audience Manager
title: Administração
topic: DIL API
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
translation-type: tm+mt
source-git-commit: 55cb69bad1f369ed3b58bece54aebdca4b14f7a7
workflow-type: tm+mt
source-wordcount: '1203'
ht-degree: 2%

---


# [!UICONTROL Administration] (Controles RBAC)  {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> O gerenciamento de conta de usuário está mudando para [Admin Console](https://helpx.adobe.com/br/enterprise/using/admin-console.html). Para a migração de usuários do start, exigimos que todos os clientes do Audience Manager para tomar imediatamente as medidas necessárias descritas neste artigo: [migração de usuário Audience Manager para Admin Console](admin-console-migration.md).
> 
> Depois que todos os clientes migrarem, as seções de gerenciamento de usuários desse documento desaparecerão.


As opções no menu [!UICONTROL Administration] permitem que você crie usuários do Audience Manager e os atribua a grupos. Você também pode visualização de limites (características, segmentos, destinos e modelos).

Os clientes corporativos que usam [!DNL Audience Manager] precisam de uma plataforma de gestão de dados para todos os seus dados, mas devem ser capazes de controlar a visibilidade dos diferentes elementos de dados para unidades comerciais específicas. Você pode fazer isso usando permissões de grupo, também conhecido como [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] usa grupos para atribuir permissões. As permissões não são atribuídas no nível do usuário. As permissões de grupo estão vinculadas a objetos ([!UICONTROL traits], segmentos etc.) e às ações que você pode executar nesses objetos (edição, visualização etc.). Esses controles também estão disponíveis por meio das APIs REST do Audience Manager. Consulte [Gerenciamento de usuários](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Gerenciamento de grupos](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md) e [Métodos de API do Gerenciamento de permissões](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md).

## Criar usuários {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> O gerenciamento de conta de usuário está mudando para [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Para a migração de usuários do start, exigimos que todos os clientes do Audience Manager para tomar imediatamente as medidas necessárias descritas neste artigo: [migração de usuário Audience Manager para Admin Console](admin-console-migration.md).
> 
> Depois que todos os clientes migrarem, a seção de gerenciamento de usuários desse documento desaparecerá.

Crie usuários em [!DNL Audience Manager] e especifique detalhes de usuários, status de logon e atribua usuários a grupos.

1. Clique em **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Clique em ![](assets/icon_add.png) para exibir a página [!UICONTROL Create New User].
1. Em **[!UICONTROL User Details]**, preencha os campos:
   * **[!UICONTROL Username]:** Especifique um nome de usuário exclusivo para Audience Manager.
   * **[!UICONTROL First Name]:** Especifique o nome do usuário.
   * **[!UICONTROL Last Name]:** Especifique o sobrenome do usuário.
   * **[!UICONTROL Email Address]:** Especifique o endereço de email do usuário. [!DNL Audience Manager] não envia notificações regulares aos usuários. [!DNL Audience Manager] os administradores têm acesso aos endereços de email dos usuários e podem enviar manualmente os usuários por email, conforme necessário. Por exemplo, se um usuário esquecer sua senha, o endereço de email especificado nesse campo será usado para enviar uma senha temporária e instruções para redefinir a senha.
   * **[!UICONTROL Phone Number]:** Especifique o número de telefone do usuário.
   * **[!UICONTROL Is Admin]:** Especifique se este usuário é um  [!DNL Audience Manager] administrador. Os usuários administradores podem gerenciar usuários (criar, editar etc.) e grupos (criar, atribuir permissões etc.). Os usuários não administradores podem controlar somente seus próprios perfis de usuário, incluindo a edição de seus endereços de email e a redefinição de suas próprias senhas. Para obter mais informações, consulte [Editar suas configurações de conta](../../features/administration/edit-account-settings.md).
1. Em **[!UICONTROL Login]**, selecione o status desejado:
   * **[!UICONTROL Active]:Os usuários**  ativos podem acessar  [!DNL Audience Manager] e ter as permissões concedidas pela associação ao grupo.
   * **[!UICONTROL Deactivated]:Os usuários**  desativados não podem acessar  [!DNL Audience Manager] e não têm permissões. Se você desativar os usuários, as informações deles permanecerão em [!DNL Audience Manager] e você poderá simplesmente reativá-los, se necessário. Se você remover usuários, será necessário recriá-los se eles precisarem usar [!DNL Audience Manager] novamente no futuro.
   * **[!UICONTROL Expired]:** A senha de um usuário tem mais de 90 dias.
   * **[!UICONTROL Pending]:** O usuário tem uma senha temporária, como depois de uma redefinição de senha ou como uma conta totalmente nova, e ainda não definiu uma senha permanente.
   * **[!UICONTROL Locked Out]:** 5 tentativas incorretas de login bloquearão um usuário.
1. Em **[!UICONTROL Assigned Groups]**, na lista suspensa, selecione os grupos desejados aos quais você deseja atribuir esse usuário.
Para obter mais informações sobre grupos e permissões, consulte [Criar um Grupo](../../features/administration/administration-overview.md#create-group).
1. Clique em **[!UICONTROL Save]**.

## Criar um [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> O gerenciamento de conta de usuário está mudando para [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Para a migração de usuários do start, recomendamos que todos os clientes do Audience Manager tomem imediatamente as medidas necessárias descritas neste artigo: [migração de usuário Audience Manager para Admin Console](admin-console-migration.md).
> 
> Depois que todos os clientes migrarem, esta seção desaparecerá.

Um *grupo* é uma coleção de usuários que compartilham direitos de acesso aos objetos [!UICONTROL destination], [!UICONTROL segment] e [!UICONTROL trait]. É possível limitar grupos somente a objetos únicos ou conceder a eles amplo acesso a combinações de objetos diferentes.

<!-- t_create_groups.xml -->

Para criar um grupo:

1. Clique em **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. Clique em ![](assets/icon_add.png) para abrir a página [!UICONTROL Group Settings].
3. Em [!UICONTROL Group Details]:
   * Nomeie o grupo.
   * Forneça uma breve descrição do grupo.
4. Em [!UICONTROL Group Members], clique em um usuário das opções **[!UICONTROL Add Users]** para adicioná-las ao grupo.
5. Em [!UICONTROL Group Permissions], selecione [característica](../../features/traits/trait-details-page.md), [segment](../../features/segments/segments-purpose.md) ou [destino](../../features/destinations/destinations.md) de **[!UICONTROL Add Object]**.
Isso abre uma janela de permissões para o objeto selecionado.
6. Marque a caixa de seleção das permissões que você deseja que os membros do grupo tenham.
7. *(Opcional)* Atribuir  [permissões de curinga ](../../features/administration/administration-overview.md#wild-card-permissions) ao grupo.
8. Clique em **[!UICONTROL Save Group]**.

## Noções básicas sobre [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> O gerenciamento de conta de usuário está mudando para [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Para a migração de usuários do start, recomendamos que todos os clientes do Audience Manager tomem imediatamente as medidas necessárias descritas neste artigo: [migração de usuário Audience Manager para Admin Console](admin-console-migration.md).
> 
> Depois que todos os clientes migrarem, esta seção desaparecerá.

Simplifique o gerenciamento de direitos de grupo com [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] conceder aos membros do grupo acesso automático a cada fonte de dados associada a uma  [!UICONTROL segment],  [!UICONTROL destination]ou  [!UICONTROL trait]. Por comparação, as permissões regulares permitem que você atribua somente [!UICONTROL data sources] a um desses objetos. E, quando você adiciona novos [!UICONTROL data sources], os membros do grupo não têm acesso a essas novas fontes.

É necessário abrir as permissões do grupo e atribuir os novos [!UICONTROL data sources] ao grupo. [!UICONTROL Wild Card Permissions] permite evitar esse processo de  [!UICONTROL data source] atualização manual. Grupos com [!UICONTROL Wild Card Permissions] obtêm acesso a novos [!UICONTROL data sources] sem autorização explícita.

![](assets/wild-card.png)

Leia abaixo uma descrição do que cada [!UICONTROL wildcard permission] significa:

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Os usuários podem selecionar  [!UICONTROL traits] como linha de base para  [!UICONTROL models].
* `EDIT_ALL_TRAITS` - Os usuários podem editar todas as  [!UICONTROL traits] configurações dentro de sua conta de empresa.
* `VIEW_ALL_TRAITS` - Os usuários podem visualização todas as  [!UICONTROL traits] configurações dentro de sua conta de empresa.
* `DELETE_ALL_TRAITS` - Os usuários podem excluir todas as  [!UICONTROL traits] configurações dentro de sua conta de empresa.
* `CREATE_ALL_ALGO_TRAITS` - Os usuários podem criar  [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS` - Os usuários podem adicionar qualquer uma das  [!UICONTROL traits] pertencentes à sua empresa  [!UICONTROL segments].
* `CREATE_ALL_TRAITS` - Os usuários podem criar  [!UICONTROL traits].

**[!UICONTROL Reports]**

* `PTRREPORTS` - Isso  [!UICONTROL wildcard permission] se refere à funcionalidade desatualizada e será removido da interface do usuário do Audience Manager em breve.

**[!UICONTROL Models]**

* `VIEW_MODELS` - Os usuários têm permissão para visualizações  [!UICONTROL models] pertencentes à empresa.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Os usuários podem visualização todas as  [!UICONTROL derived signals] pessoas pertencentes à sua empresa.
* `CREATE_DERIVED_SIGNALS` - Os usuários podem criar  [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS` - Os usuários podem editar todas as  [!UICONTROL derived signals] informações pertencentes à sua empresa.
* `DELETE_DERIVED_SIGNALS` - Os usuários podem excluir qualquer uma das  [!UICONTROL derived signals] empresas.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Os usuários podem editar todas as  [!UICONTROL destinations] configurações dentro de suas contas de empresa.
* `CREATE_DESTINATIONS` - Os usuários podem criar  [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS` - Os usuários podem visualização todas as  [!UICONTROL destinations] configurações dentro de sua conta de empresa.
* `DELETE_ALL_DESTINATIONS` - Os usuários podem excluir todas as  [!UICONTROL destinations] configurações dentro de sua conta de empresa.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Os usuários podem fazer tudo (visualização, criar, editar, excluir) em seus  [!UICONTROL Tag Containers]computadores.

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Os usuários podem fazer tudo (visualização, criar, editar, excluir) em seus grupos  [!UICONTROL Audience Lab] de teste.

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Os usuários podem criar segmentos.
* `DELETE_ALL_SEGMENTS` - Os usuários podem excluir todos os segmentos configurados em suas contas de empresa.
* `MAP_ALL_TO_DESTINATIONS` - Os usuários podem mapear qualquer um dos segmentos pertencentes à sua empresa para destinos.
* `EDIT_ALL_SEGMENTS` - Os usuários podem editar todos os segmentos configurados em suas contas de empresa.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Os usuários podem selecionar segmentos como linha de base para modelos.
* `VIEW_ALL_SEGMENTS` - Os usuários podem visualização todos os segmentos configurados em suas contas de empresa.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - Os utilizadores podem visualização todos os sinais captados à  [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## Casos de uso {#use-cases}

### Monitorando o Acesso do Usuário {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] pode ajudá-lo a monitorar o status de login do usuário, fornecendo uma imagem clara de quem pode acessar a instância do Audience Manager.

Dependendo dos requisitos de sua empresa, você pode ativar e desativar as contas de usuário, conforme necessário.

![acesso do usuário ao monitor](assets/monitor-user-access.png)

### Garanta a Proteção de Acesso para [!UICONTROL Data Sources] {#protect-sensitive-data-sources} Sensível

Você pode configurar [!UICONTROL Role-Based Access Control] no nível [!UICONTROL trait], segmento e [!UICONTROL destination] para cada grupo de usuários.

Esse recurso ajuda a gerenciar como seus usuários visualizações, criam, leem, gravam e editam conjuntos de dados específicos, além de impedir que eles acessem conjuntos de dados que não devem estar disponíveis para eles.

![proteção de acesso](assets/access-protection.png)
