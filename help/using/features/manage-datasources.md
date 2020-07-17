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

Para criar um novo [!UICONTROL data source], vá para **[!UICONTROL Audience Data > Data Sources > Add New]** e conclua as etapas para cada seção descrita aqui. Permissões de administrador são necessárias para criar um [!UICONTROL data source].

<!-- create-datasource.xml -->

>[!TIP]
>
>Consulte Configurações da fonte de [dados e Opções](../features/datasources-list-and-settings.md#settings-menu-options) de menu para obter descrições desses diferentes controles.

## [!UICONTROL Data Source] Detalhes {#details}

Para concluir a [!UICONTROL Data Source Details] seção:

1. Dê um nome ao [!UICONTROL data source].
1. *(Opcional)* Descreva o [!UICONTROL data source]. Uma descrição concisa ajuda a definir a função ou a finalidade do [!UICONTROL data source].
1. Forneça um [!UICONTROL integration code]. Geralmente, [!UICONTROL integration codes] são opcionais. Eles são necessários quando você deseja:

   * [Crie uma fonte](../features/profile-merge-rules/merge-rules-start.md#create-data-source)de dados entre dispositivos.
   * Use the [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html).
   * Trabalhar com regras [de mesclagem de](../features/profile-merge-rules/merge-rules-start.md)Perfis.

1. Escolha um **[!UICONTROL ID Type]**. [!UICONTROL ID Type] as opções incluem:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Obrigatório para criar um [!UICONTROL Profile Merge Rule]). Observe que para alguns clientes, essa seleção expõe as **[!UICONTROL ID Definition]** opções.

1. Choose an **[!UICONTROL ID Definition]** option. As opções incluem:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[Os Controles](../features/data-export-controls.md) de exportação de dados são regras de classificação opcionais que podem ser aplicadas a um [!UICONTROL data source] e [!UICONTROL destination]. Elas impedem que você envie dados para um [!UICONTROL destination] quando essa ação viola a privacidade dos dados ou o contrato de uso. Ignore esta seção se não usar [!UICONTROL Data Export Controls].

## [!UICONTROL Data Source] Configurações {#settings}

Essas configurações determinam como um [!UICONTROL data source] é identificado, usado e compartilhado. Você também pode ativar o relatórios de erro para arquivos de dados de entrada. Para concluir a [!UICONTROL Data Source Settings] seção:

1. Marque uma caixa de [!UICONTROL Data Source Setting] seleção para aplicar uma opção à sua [!UICONTROL data source].
2. Clique em **[!UICONTROL Save]**.

## Excluir uma fonte de dados {#delete-data-source}

<!-- t_datasource_delete.xml -->

Exclua um item de [!UICONTROL data source] que você não precisa mais.

>[!NOTE]
>
>Observe as seguintes restrições:
>
>* Não é possível excluir uma Audiência [ativa ou uma característica](../features/traits/client-activity-synced-audience-traits.md)sincronizada da fonte de dados.
>* Para clientes que usam o Adobe Analytics: O Audience Manager não permite que você exclua fontes de dados criadas automaticamente de seus conjuntos de [!DNL Analytics] relatórios. Use o Serviço [](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services-landing.html) principal para desmapear essas fontes de dados.


1. Clique em **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Marque a caixa de seleção ao lado de uma ou mais fontes de dados.
Você pode usar a [!UICONTROL Search] caixa para localizar as fontes de dados desejadas se tiver uma lista longa.
1. Clique em ![](assets/icon_trash.png)e confirme a exclusão.


>[!MORELIKETHIS]
>
>* [Configurações da fonte de dados e opções de menu](../features/datasources-list-and-settings.md#settings-menu-options)