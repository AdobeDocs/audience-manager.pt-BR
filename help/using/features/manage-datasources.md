---
description: Para criar uma nova fonte de dados, vá até Dados de Audiência > Fontes de dados > Adicionar novo e conclua as etapas para cada seção descrita aqui. São necessárias permissões de administrador para criar uma fonte de dados.
keywords: data sources;manage data source;audience manager data source
seo-description: Para criar uma nova fonte de dados, vá até Dados de Audiência > Fontes de dados > Adicionar novo e conclua as etapas para cada seção descrita aqui. São necessárias permissões de administrador para criar uma fonte de dados.
seo-title: Criar uma fonte de dados
solution: Audience Manager
title: Gerenciar fontes de dados
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 5%

---


# Gerenciar [!UICONTROL Data Sources] {#manage-data-sources}

## Criar um [!UICONTROL Data Source] {#create-data-source}

Para criar um novo [!UICONTROL data source], vá até **[!UICONTROL Audience Data > Data Sources > Add New]** e conclua as etapas para cada seção descrita aqui. São necessárias permissões de administrador para criar um [!UICONTROL data source].

<!-- create-datasource.xml -->

>[!TIP]
>
>Consulte [Configurações da fonte de dados e Opções de menu](../features/datasources-list-and-settings.md#settings-menu-options) para obter descrições desses diferentes controles.

## [!UICONTROL Data Source] Detalhes {#details}

Para concluir a seção [!UICONTROL Data Source Details]:

1. Nomeie o [!UICONTROL data source].
1. *(Opcional)* Descreva o  [!UICONTROL data source]. Uma descrição concisa ajuda a definir a função ou a finalidade do [!UICONTROL data source].
1. Forneça um [!UICONTROL integration code]. Geralmente, [!UICONTROL integration codes] são opcionais. Eles são necessários quando você deseja:

   * [Crie uma fonte](../features/profile-merge-rules/merge-rules-start.md#create-data-source) de dados entre dispositivos.
   * Use o [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html).
   * Trabalhe com [Regras de mesclagem de Perfis](../features/profile-merge-rules/merge-rules-start.md).

1. Escolha um **[!UICONTROL ID Type]**. [!UICONTROL ID Type] as opções incluem:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Obrigatório para criar um  [!UICONTROL Profile Merge Rule]). Observe que para alguns clientes, essa seleção expõe as opções **[!UICONTROL ID Definition]**.

1. Escolha uma opção **[!UICONTROL ID Definition]**. As opções incluem:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[Os ](../features/data-export-controls.md) controles de exportação de dados são regras de classificação opcionais que podem ser aplicadas a um  [!UICONTROL data source] e  [!UICONTROL destination]. Elas impedem que você envie dados para [!UICONTROL destination] quando essa ação viola uma privacidade de dados ou um contrato de uso. Ignore esta seção se você não usar [!UICONTROL Data Export Controls].

## [!UICONTROL Data Source] Configurações {#settings}

Essas configurações determinam como um [!UICONTROL data source] é identificado, usado e compartilhado. Você também pode ativar o relatórios de erro para arquivos de dados de entrada. Para concluir a seção [!UICONTROL Data Source Settings]:

1. Marque uma caixa de seleção [!UICONTROL Data Source Setting] para aplicar uma opção a [!UICONTROL data source].
2. Clique em **[!UICONTROL Save]**.

## Excluir uma Fonte de Dados {#delete-data-source}

<!-- t_datasource_delete.xml -->

Exclua um [!UICONTROL data source] que não é mais necessário.

>[!NOTE]
>
>Observe as seguintes restrições:
>
>* Não é possível excluir uma [Audiência ativa ou característica sincronizada da fonte de dados](../features/traits/client-activity-synced-audience-traits.md).
>* Para clientes que usam o Adobe Analytics: O Audience Manager não permite que você exclua fontes de dados criadas automaticamente de seus conjuntos de relatórios [!DNL Analytics]. Use o [Core Service](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services-landing.html) para desmapear essas fontes de dados.


1. Clique em **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Marque a caixa de seleção ao lado de uma ou mais fontes de dados.
Você pode usar a caixa [!UICONTROL Search] para localizar as fontes de dados desejadas se tiver uma lista longa.
1. Clique em ![](assets/icon_trash.png) e confirme a exclusão.


>[!MORELIKETHIS]
>
>* [Configurações da fonte de dados e opções de menu](../features/datasources-list-and-settings.md#settings-menu-options)