---
description: Para criar uma nova fonte de dados, vá para Dados de público-alvo > Fontes de dados > Adicionar novo e conclua as etapas para cada seção descrita aqui. São necessárias permissões de administrador para criar uma fonte de dados.
keywords: fontes de dados;gerenciar fonte de dados;fonte de dados do audience manager
seo-description: To create a new data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create a data source.
seo-title: Create a Data Source
solution: Audience Manager
title: Gerenciar fontes de dados
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
source-git-commit: 6ec76227dd8c7581550c3d95e24fc5b6a4b01093
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 0%

---

# Gerenciar [!UICONTROL Data Sources] {#manage-data-sources}

## Criar um [!UICONTROL Data Source] {#create-data-source}

Para criar um novo [!UICONTROL data source], vá para **[!UICONTROL Audience Data > Data Sources > Add New]** e conclua as etapas para cada seção descrita aqui. São necessárias permissões de administrador para criar um [!UICONTROL data source].

<!-- create-datasource.xml -->

>[!TIP]
>
>Consulte [Configurações de Data Source e Opções de Menu](../features/datasources-list-and-settings.md#settings-menu-options) para obter descrições desses diferentes controles.

## Detalhes de [!UICONTROL Data Source] {#details}

Para concluir a seção [!UICONTROL Data Source Details]:

1. Nomeie o [!UICONTROL data source].
1. *(Opcional)* Descreva o [!UICONTROL data source]. Uma descrição concisa ajuda a definir a função ou a finalidade do [!UICONTROL data source].
1. Forneça um [!UICONTROL integration code]. Geralmente, [!UICONTROL integration codes] são opcionais. Elas são necessárias quando você deseja:

   * [Criar uma fonte de dados entre dispositivos](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Use o [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html).
   * Trabalhar com [Regras de mesclagem de perfis](../features/profile-merge-rules/merge-rules-start.md).

1. Escolha um **[!UICONTROL ID Type]**. [!UICONTROL ID Type] opções incluem:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Necessário para criar um [!UICONTROL Profile Merge Rule]). Observe que, para alguns clientes, essa seleção expõe as opções de **[!UICONTROL ID Definition]**.

   >[!NOTE]
   >
   >Para cada organização provisionada para Audience Manager e Experience Platform, mesmo que você não tenha o compartilhamento de segmentos configurado entre os dois aplicativos, ao criar uma fonte de dados entre dispositivos, um [namespace de identidade](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#manage-namespaces) correspondente será criado no Experience Platform.

1. Escolha uma opção **[!UICONTROL ID Definition]**. As opções incluem:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[Os Controles da Exportação de Dados](../features/data-export-controls.md) são regras de classificação opcionais que você pode aplicar a um [!UICONTROL data source] e [!UICONTROL destination]. Eles impedem que você envie dados para um [!UICONTROL destination] quando essa ação viola a privacidade dos dados ou o contrato de uso. Pule esta seção se você não usar [!UICONTROL Data Export Controls].

## Configurações de [!UICONTROL Data Source] {#settings}

Essas configurações determinam como um [!UICONTROL data source] é identificado, usado e compartilhado. Você também pode ativar o relatório de erros para arquivos de dados de entrada. Para concluir a seção [!UICONTROL Data Source Settings]:

1. Marque uma caixa de seleção [!UICONTROL Data Source Setting] para aplicar uma opção ao seu [!UICONTROL data source].
2. Clique em **[!UICONTROL Save]**.

## Excluir uma Source de dados {#delete-data-source}

<!-- t_datasource_delete.xml -->

Exclua um [!UICONTROL data source] que você não precisa mais.

>[!NOTE]
>
>Observe as seguintes restrições:
>
>* Você não pode excluir uma [Característica sincronizada do Ative Audience ou Data Source](../features/traits/client-activity-synced-audience-traits.md).
>* Para clientes que usam o Adobe Analytics: o Audience Manager não permite excluir fontes de dados criadas automaticamente a partir dos conjuntos de relatórios do [!DNL Analytics]. Use o [Serviço Principal](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services-landing.html) para desmapear essas fontes de dados.

1. Clique em **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Marque a caixa de seleção ao lado de uma ou mais fontes de dados.
Você pode usar a caixa [!UICONTROL Search] para localizar as fontes de dados desejadas se tiver uma lista longa.
1. Clique em ![](assets/icon_trash.png) e confirme a exclusão.


>[!MORELIKETHIS]
>
>* [Opções de Menu e Configurações do Data Source](../features/datasources-list-and-settings.md#settings-menu-options)
