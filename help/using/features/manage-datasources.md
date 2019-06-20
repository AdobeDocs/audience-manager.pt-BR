---
description: Para criar uma nova fonte de dados, vá para Dados de público-alvo > Fontes de dados > Adicionar novo e complete as etapas para cada seção descrita aqui. Permissões de administrador são necessárias para criar uma fonte de dados.
keywords: cdf; feed de dados personalizados
seo-description: Para criar uma nova fonte de dados, vá para Dados de público-alvo > Fontes de dados > Adicionar novo e complete as etapas para cada seção descrita aqui. Permissões de administrador são necessárias para criar uma fonte de dados.
seo-title: Criar uma fonte de dados
solution: Audience Manager
title: Criar uma fonte de dados
uuid: 4 df 65 bcb -9 ad 9-4 b 72-a 71 e -8918 b 43 d 4850
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Manage Data Sources {#manage-data-sources}

## Create a Data Source {#create-data-source}

To create a new data source, go to **[!UICONTROL Audience Data > Data Sources > Add New]** and complete the steps for each section described here. Permissões de administrador são necessárias para criar uma fonte de dados.

<!-- create-datasource.xml -->

>[!TIP]
>
>See [Data Source Settings and Menu Options](../features/datasources-list-and-settings.md#settings-menu-options) for descriptions of these different controls.

## Data Source Details {#details}

To complete the [!UICONTROL Data Source Details] section:

1. Dê um nome para a fonte de dados.
1. *(Opcional)* Descreva a fonte de dados. Uma descrição concisa ajuda a definir a função ou finalidade da fonte de dados.
1. Forneça um código de integração. Geralmente, os códigos de integração são opcionais. Eles são necessários quando você deseja:

   * [Crie uma fonte de dados entre dispositivos](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Use the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
   * Work with [Profile Merge Rules](../features/profile-merge-rules/merge-rules-start.md).

1. Choose an **[!UICONTROL ID Type]**. As opções de Tipo de ID incluem:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Obrigatório para criar a [!UICONTROL Profile Merge Rule]). Note, for some customers, this selection exposes the **[!UICONTROL ID Definition]** options.

1. Choose an **[!UICONTROL ID Definition]** option. As opções incluem:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## Controles da exportação de dados {#export-controls}

[Os controles de exportação de dados](../features/data-export-controls.md) são regras de classificação opcionais que podem ser aplicadas a uma fonte de dados e destino. Eles impedem que você envie dados para um destino quando essa ação violar a privacidade de dados ou usar o contrato. Skip this section if you do not use [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

Essas configurações determinam como uma fonte de dados é identificada, usada e compartilhada. Também é possível ativar o relatório de erros para arquivos de dados de entrada. To complete the [!UICONTROL Data Source Settings] section:

1. Select a [!UICONTROL Data Source Setting] check box to apply an option to your data source.
2. Clique em **[!UICONTROL Save]**.

>[!MORE_ LIKE_ THIS]
>
>* [Configurações de fonte de dados e opções de menu](../features/datasources-list-and-settings.md#settings-menu-options)


## Delete a Data Source {#delete-data-source}

<!-- t_datasource_delete.xml -->

Exclua uma fonte de dados que não é mais necessária.

>[!NOTE]
>
>Observe as seguintes restrições:
>
>* You cannot delete an [Active Audience or Data Source Synced Trait](../features/traits/client-activity-synced-audience-traits.md).
>* For customers using Adobe Analytics: Audience Manager does not allow you to delete data sources created automatically from your [!DNL Analytics] report suites. Use the [Core Service](https://marketing.adobe.com/resources/help/en_US/mcloud/) to unmap these data sources.


1. Click **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**.
1. Marque a caixa de seleção ao lado de uma ou mais fontes de dados.
You can use the [!UICONTROL Search] box to locate the desired data sources if you have a long list.
1. Click  ![](assets/icon_trash.png), then confirm the deletion.