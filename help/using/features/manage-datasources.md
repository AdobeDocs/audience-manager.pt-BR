---
description: Para criar uma nova fonte de dados, vá para Dados de público-alvo > Fontes de dados > Adicionar novo e conclua as etapas de cada seção descrita aqui. Permissões de administrador são necessárias para criar uma fonte de dados.
keywords: fontes de dados, gerenciar fonte de dados, fonte de dados do audience manager
seo-description: To create a new data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create a data source.
seo-title: Create a Data Source
solution: Audience Manager
title: Gerenciar fontes de dados
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
source-git-commit: 6ec76227dd8c7581550c3d95e24fc5b6a4b01093
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 2%

---

# Gerenciar [!UICONTROL Data Sources] {#manage-data-sources}

## Criar um [!UICONTROL Data Source] {#create-data-source}

Para criar um novo [!UICONTROL data source], vá para **[!UICONTROL Audience Data > Data Sources > Add New]** e conclua as etapas de cada seção descrita aqui. Permissões de administrador são necessárias para criar um [!UICONTROL data source].

<!-- create-datasource.xml -->

>[!TIP]
>
>Consulte [Configurações da fonte de dados e opções do menu](../features/datasources-list-and-settings.md#settings-menu-options) para obter descrições destes diferentes controlos.

## [!UICONTROL Data Source] Detalhes {#details}

Para concluir a [!UICONTROL Data Source Details] seção:

1. Nomeie a função [!UICONTROL data source].
1. *(Opcional)* Descreva o [!UICONTROL data source]. Uma descrição concisa ajuda a definir a função ou a finalidade da variável [!UICONTROL data source].
1. Forneça uma [!UICONTROL integration code]. Geralmente, [!UICONTROL integration codes] são opcionais. Eles são necessários quando você deseja:

   * [Criar uma fonte de dados entre dispositivos](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Use o [Serviço de identidade da Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html).
   * Trabalhar com [Regras de mesclagem de perfis](../features/profile-merge-rules/merge-rules-start.md).

1. Escolha um **[!UICONTROL ID Type]**. [!UICONTROL ID Type] as opções incluem:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Obrigatório para criar um [!UICONTROL Profile Merge Rule]). Observe que para alguns clientes, essa seleção expõe a variável **[!UICONTROL ID Definition]** opções.

   >[!NOTE]
   >
   >Para cada organização provisionada para Audience Manager e Experience Platform, mesmo que você não tenha o compartilhamento de segmentos configurado entre os dois aplicativos, ao criar uma fonte de dados entre dispositivos, uma [namespace de identidade](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#manage-namespaces) é criado no Experience Platform.

1. Escolha um **[!UICONTROL ID Definition]** opção. As opções incluem:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[Controles da exportação de dados](../features/data-export-controls.md) são regras de classificação opcionais que podem ser aplicadas a um [!UICONTROL data source] e [!UICONTROL destination]. Eles impedem que você envie dados para um [!UICONTROL destination] quando essa ação violar a privacidade dos dados ou o contrato de uso. Ignore esta seção se não utilizar [!UICONTROL Data Export Controls].

## [!UICONTROL Data Source] Configurações {#settings}

Essas configurações determinam como uma [!UICONTROL data source] é identificada, usada e compartilhada. Você também pode ativar o relatório de erros para arquivos de dados de entrada. Para concluir a [!UICONTROL Data Source Settings] seção:

1. Selecione um [!UICONTROL Data Source Setting] caixa de seleção para aplicar uma opção a seu [!UICONTROL data source].
2. Clique em **[!UICONTROL Save]**.

## Excluir uma fonte de dados {#delete-data-source}

<!-- t_datasource_delete.xml -->

Excluir um [!UICONTROL data source] que você não precisa mais.

>[!NOTE]
>
>Observe as seguintes restrições:
>
>* Não é possível excluir um [Público-alvo ativo ou característica sincronizada da fonte de dados](../features/traits/client-activity-synced-audience-traits.md).
>* Para clientes que usam o Adobe Analytics: O Audience Manager não permite excluir fontes de dados criadas automaticamente a partir do [!DNL Analytics] conjuntos de relatórios. Use o [Serviço principal](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services-landing.html) para desmapear essas fontes de dados.


1. Clique em **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Marque a caixa de seleção ao lado de uma ou mais fontes de dados.
Você pode usar o [!UICONTROL Search] para localizar as fontes de dados desejadas se tiver uma lista longa.
1. Clique em  ![](assets/icon_trash.png)e, em seguida, confirme a exclusão.


>[!MORELIKETHIS]
>
>* [Configurações da fonte de dados e opções do menu](../features/datasources-list-and-settings.md#settings-menu-options)

