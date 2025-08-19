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
source-git-commit: bda66cb9aaee3a40ae64dda100f42b88696a027e
workflow-type: tm+mt
source-wordcount: '403'
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

Para concluir a seção [!UICONTROL Data Source Details], preencha os seguintes campos:

1. **[!UICONTROL Name]**: Forneça um nome para a fonte de dados.
1. **[!UICONTROL Description]** (opcional): insira uma descrição para sua fonte de dados para ajudá-lo a definir a função ou a finalidade da fonte de dados.
1. **[!UICONTROL Integration Code]** (opcional): insira um código de integração. Esses códigos são necessários quando você deseja:
   * [Criar uma fonte de dados entre dispositivos](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Use o [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR).
   * Trabalhar com [Regras de mesclagem de perfis](../features/profile-merge-rules/merge-rules-start.md).
1. **[!UICONTROL Namespace]** (somente leitura): este campo é somente leitura e é gerado automaticamente quando você salva a fonte de dados. Se você deseja exportar segmentos do Audience Manager para o Experience Platform, deve criar um [namespace de identidade](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=pt-BR#manage-namespaces) correspondente no Experience Platform, usando o valor gerado automaticamente como o namespace [símbolo de identidade](https://experienceleague.adobe.com/pt-br/docs/experience-platform/identity/features/namespaces#components-of-a-namespace) no Experience Platform.
1. **[!UICONTROL ID Type]**: Selecione o tipo de IDs que esta fonte de dados conterá:
   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Necessário para criar um [!UICONTROL Profile Merge Rule]). Observe que, para alguns clientes, essa seleção expõe as opções de **[!UICONTROL ID Definition]**.
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
>* Para clientes que usam o Adobe Analytics: o Audience Manager não permite que você exclua fontes de dados criadas automaticamente a partir de seus conjuntos de relatórios do [!DNL Analytics]. Use o [Serviço Principal](https://experienceleague.adobe.com/pt-br/docs/core-services/interface/services/customer-attributes/attributes) para desmapear essas fontes de dados.

1. Clique em **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Marque a caixa de seleção ao lado de uma ou mais fontes de dados.
Você pode usar a caixa [!UICONTROL Search] para localizar as fontes de dados desejadas se tiver uma lista longa.
1. Clique em ![](assets/icon_trash.png) e confirme a exclusão.


>[!MORELIKETHIS]
>
>* [Opções de Menu e Configurações do Data Source](../features/datasources-list-and-settings.md#settings-menu-options)
