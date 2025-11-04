---
description: Públicos preditivos ajudam a classificar públicos desconhecidos em personas distintas em tempo real, usando a ciência de dados.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Managing Predictive Audiences
solution: Audience Manager
title: Introdução aos públicos preditivos
feature: Algorithmic Models
exl-id: beb314de-f679-4397-8e14-2dd6576243fd
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 2%

---

# Introdução aos públicos preditivos {#predictive-audiences-getting-started}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo pela configuração e pelo uso desse recurso. Nada contido aqui é aconselhamento jurídico. Consulte seu próprio serviço jurídico para obter orientação jurídica.

## Criar um modelo de públicos preditivos {#create-predictive-audiences}

Antes de criar um modelo [!UICONTROL Predictive Audiences], é necessário decidir a qual fonte de dados primária você deseja atribuir suas características e segmentos [!UICONTROL Predictive Audiences]. Você pode usar uma fonte de dados primária existente ou criar uma nova. Consulte [Gerenciar fontes de dados](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html?lang=pt-BR) para obter detalhes sobre como criar uma nova fonte de dados própria.

Depois de saber qual fonte de dados você usará, siga as etapas abaixo.

1. Vá para **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. Na seção [!UICONTROL Predictive Audiences], clique em **[!UICONTROL Add New]**.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. Em seguida, defina os perfis pelos quais deseja classificar o público. Você pode fazer isso escolhendo características ou segmentos a partir dos quais criar perfis. Use as guias [!UICONTROL Traits] e [!UICONTROL Segments] no canto superior esquerdo da tela para alternar entre o catálogo de características e segmentos. Depois de identificar as características ou os segmentos que deseja usar como personas, clique no ícone **[!UICONTROL Add]** correspondente na coluna [!UICONTROL Action].

   ![persona-inteligente-select-personas](assets/predictive-audiences-persona.png)

   >[!NOTE]
   >
   >Você deve escolher no mínimo duas características ou dois segmentos para seus perfis de linha de base. Não é possível usar uma combinação de características e segmentos.

1. Clique em **[!UICONTROL Next]** depois de definir suas personalidades.
1. Em seguida, selecione o público-alvo primário que deseja classificar escolhendo uma característica ou segmento primário para esse público-alvo. Use as guias [!UICONTROL Traits] e [!UICONTROL Segments] no canto superior esquerdo da tela para alternar entre o catálogo de características e segmentos. Selecione a característica ou o segmento primário que deseja usar como público-alvo para adicioná-lo ao modelo.

   ![smart-persona-select-audience](assets/predictive-audiences-audience.png)

1. Clique em **[!UICONTROL Next]** depois de escolher seu público.
1. Preencha os detalhes do modelo:

   * **[!UICONTROL Model Name]**: insira um nome descritivo para o modelo, que o ajudará a identificá-lo mais tarde. Os nomes dos segmentos gerados pelo modelo começarão com o nome do modelo.
   * **[!UICONTROL Description]**: insira uma descrição do modelo que ajudará você a identificar seu caso de uso.
   * **[!UICONTROL Data Source]**: Selecione a fonte de dados primária à qual você deseja que os segmentos [!UICONTROL Predictive Audiences] deste modelo sejam atribuídos.
   * **[!UICONTROL Profile Merge Rule]**: Selecione o [!UICONTROL Profile Merge Rule] a ser atribuído a todos os [!UICONTROL segments] preditivos criados por este modelo. Se o público-alvo selecionado for [!UICONTROL segment], recomendamos selecionar o mesmo [!UICONTROL Profile Merge Rule] do público-alvo.

   ![predictive-audiences-save](assets/predictive-audiences-save.png)

1. Clique em **[!UICONTROL Save]**.

## Clonagem e edição de modelos de públicos preditivos {#clone-predictive-audiences}

O Audience Manager não oferece suporte à edição de modelos [!UICONTROL Predictive Audiences] existentes. Para alterar a configuração de um modelo, você pode criar um clone de um modelo existente e editá-lo. Veja como fazer isso:

1. Vá para **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. Clique no nome do modelo [!UICONTROL Predictive Audiences] que deseja clonar.
1. Clique no botão **[!UICONTROL Clone]** no lado superior esquerdo da tela.

   ![predictive-audiences-clone](assets/predictive-audiences-clone.png)

1. Depois de clonar o modelo, você é levado para a página [!DNL Save & Configure] do modelo clonado. Nesta página, você pode alterar o [!UICONTROL data source] e o [!UICONTROL Profile Merge Rule] atribuído do modelo. Para editar as personas e o público-alvo do modelo clonado, use os botões [!UICONTROL Back] e [!UICONTROL Next] para navegar entre as três guias ou clique nos nomes das três guias

   ![públicos-preditivos-clone-navigate](assets/predictive-audiences-clone-navigate.png)

1. Quando terminar de editar um modelo, clique em **[!UICONTROL Save]**.

## Exclusão de públicos preditivos {#delete-predictive-audiences}

Para excluir um modelo [!UICONTROL Predictive Audiences], vá para **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, localize o modelo que deseja excluir e clique no ícone **[!UICONTROL Delete]**.
