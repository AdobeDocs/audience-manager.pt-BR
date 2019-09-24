---
description: Para criar uma nova fonte de dados, vá até Dados de público-alvo > Fontes de dados > Adicionar novo e conclua as etapas para cada seção descrita aqui. São necessárias permissões de administrador para criar uma fonte de dados.
keywords: fontes de dados;gerenciar fonte de dados;fonte de dados do Audience Manager
seo-description: Para criar uma nova fonte de dados, vá até Dados de público-alvo > Fontes de dados > Adicionar novo e conclua as etapas para cada seção descrita aqui. São necessárias permissões de administrador para criar uma fonte de dados.
seo-title: Create a Data Source
solution: Audience Manager
title: Manage Data Sources
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
translation-type: tm+mt
source-git-commit: 9e1abb305c66a4adf6a42a7873144222491692f9

---


# Manage Data Sources {#manage-data-sources}

## Create a Data Source {#create-data-source}

Para criar uma nova fonte de dados, vá até **[!UICONTROL Audience Data > Data Sources > Add New]** e conclua as etapas para cada seção descrita aqui. São necessárias permissões de administrador para criar uma fonte de dados.

<!-- create-datasource.xml -->

>[!TIP]
>
>Consulte Configurações da fonte de [dados e Opções](../features/datasources-list-and-settings.md#settings-menu-options) de menu para obter descrições desses diferentes controles.

## Detalhes da fonte de dados {#details}

Para concluir a [!UICONTROL Data Source Details] seção:

1. Nomeie a fonte de dados.
1. *(Opcional)* Descreva a fonte de dados. Uma descrição concisa ajuda a definir a função ou a finalidade da fonte de dados.
1. Forneça um código de integração. Geralmente, os códigos de integração são opcionais. Eles são necessários quando você deseja:

   * [Crie uma fonte](../features/profile-merge-rules/merge-rules-start.md#create-data-source)de dados entre dispositivos.
   * Use o serviço [da](https://marketing.adobe.com/resources/help/en_US/mcvid/)Experience Cloud ID.
   * Trabalhar com regras [de mesclagem de](../features/profile-merge-rules/merge-rules-start.md)perfil.

1. Escolha um **[!UICONTROL ID Type]**. As opções de Tipo de ID incluem:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Obrigatório para criar um [!UICONTROL Profile Merge Rule]). Observe que para alguns clientes, essa seleção expõe as **[!UICONTROL ID Definition]** opções.

1. Choose an **[!UICONTROL ID Definition]** option. As opções incluem:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## Controles da exportação de dados {#export-controls}

[Os Controles](../features/data-export-controls.md) de exportação de dados são regras de classificação opcionais que podem ser aplicadas a uma fonte de dados e destino. Elas impedem que você envie dados para um destino quando essa ação viola a privacidade dos dados ou o contrato de uso. Ignore esta seção se não usar [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

These settings determine how a data source is identified, used, and shared. You can also enable error reporting for inbound data files. To complete the  section:[!UICONTROL Data Source Settings]

1. Select a  check box to apply an option to your data source.[!UICONTROL Data Source Setting]
2. Clique em **[!UICONTROL Save]**.

>[!MORE_LIKE_THIS]
>
>* [Configurações da fonte de dados e opções de menu](../features/datasources-list-and-settings.md#settings-menu-options)


## Excluir uma fonte de dados {#delete-data-source}

<!-- t_datasource_delete.xml -->

Delete a data source that you no longer need.

>[!NOTE]
>
>Please note the following restrictions:
>
>* You cannot delete an Active Audience or Data Source Synced Trait.[](../features/traits/client-activity-synced-audience-traits.md)
>* For customers using Adobe Analytics: Audience Manager does not allow you to delete data sources created automatically from your  report suites. [!DNL Analytics] Use the [Core Service](https://marketing.adobe.com/resources/help/en_US/mcloud/) to unmap these data sources.


1. Click **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**.
1. Marque a caixa de seleção ao lado de uma ou mais fontes de dados.
You can use the  box to locate the desired data sources if you have a long list.[!UICONTROL Search]
1. Click  , then confirm the deletion.![](assets/icon_trash.png)