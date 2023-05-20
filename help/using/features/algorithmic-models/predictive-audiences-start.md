---
description: Públicos preditivos ajudam a classificar públicos desconhecidos em personas distintas em tempo real, usando a ciência de dados.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Managing Predictive Audiences
solution: Audience Manager
title: Introdução aos públicos preditivos
feature: Algorithmic Models
exl-id: beb314de-f679-4397-8e14-2dd6576243fd
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 4%

---

# Introdução aos públicos preditivos {#predictive-audiences-getting-started}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo pela configuração e pelo uso desse recurso. Nada contido aqui é aconselhamento jurídico. Consulte seu próprio serviço jurídico para obter orientação jurídica.

## Criar um modelo de públicos preditivos {#create-predictive-audiences}

Antes de criar um [!UICONTROL Predictive Audiences] precisa decidir qual fonte de dados primária você deseja atribuir ao seu [!UICONTROL Predictive Audiences] características e segmentos a. Você pode usar uma fonte de dados primária existente ou criar uma nova. Consulte [Gerenciar fontes de dados](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html) para obter detalhes sobre como criar uma nova fonte de dados primária.

Depois de saber qual fonte de dados você usará, siga as etapas abaixo.

1. Ir para **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. No [!UICONTROL Predictive Audiences] clique em **[!UICONTROL Add New]**.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. Em seguida, defina os perfis pelos quais deseja classificar o público. Você pode fazer isso escolhendo características ou segmentos a partir dos quais criar perfis. Use o [!UICONTROL Traits] e [!UICONTROL Segments] guias no canto superior esquerdo da tela para alternar entre o catálogo de características e segmentos. Depois de identificar as características ou os segmentos que deseja usar como personas, clique no link correspondente **[!UICONTROL Add]** ícone no [!UICONTROL Action] coluna.
   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >Você deve escolher no mínimo duas características ou dois segmentos para seus perfis de linha de base. Não é possível usar uma combinação de características e segmentos.
1. Clique em **[!UICONTROL Next]** depois de definir suas personas.
1. Em seguida, selecione o público-alvo primário que deseja classificar escolhendo uma característica ou segmento primário para esse público-alvo. Use o [!UICONTROL Traits] e [!UICONTROL Segments] guias no canto superior esquerdo da tela para alternar entre seu catálogo de características e segmentos. Selecione a característica ou o segmento primário que deseja usar como público-alvo para adicioná-lo ao modelo.
   ![smart-persona-select-audience](assets/predictive-audiences-audience.png)
1. Clique em **[!UICONTROL Next]** depois de escolher seu público-alvo.
1. Preencha os detalhes do modelo:
   * **[!UICONTROL Model Name]**: insira um nome descritivo para o modelo, que ajudará você a identificá-lo posteriormente. Os nomes dos segmentos gerados pelo modelo começarão com o nome do modelo.
   * **[!UICONTROL Description]**: insira uma descrição do modelo que ajudará você a identificar seu caso de uso.
   * **[!UICONTROL Data Source]**: selecione a fonte de dados primária cuja [!UICONTROL Predictive Audiences] segmentos deste modelo a serem atribuídos.
   * **[!UICONTROL Profile Merge Rule]**: selecione a variável [!UICONTROL Profile Merge Rule] a ser atribuído para todas as métricas preditivas [!UICONTROL segments] criado por este modelo. Se o público-alvo selecionado for um [!UICONTROL segment], recomendamos selecionar o mesmo [!UICONTROL Profile Merge Rule] do público-alvo.
      ![predictive-audiences-save](assets/predictive-audiences-save.png)
1. Clique em **[!UICONTROL Save]**.

## Clonagem e edição de modelos de públicos preditivos {#clone-predictive-audiences}

O Audience Manager não oferece suporte à edição de arquivos existentes [!UICONTROL Predictive Audiences] modelos. Para alterar a configuração de um modelo, você pode criar um clone de um modelo existente e editá-lo. Veja como fazer isso:

1. Ir para **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
2. Clique no nome do [!UICONTROL Predictive Audiences] que deseja clonar.
3. Clique em **[!UICONTROL Clone]** no lado superior esquerdo da tela.
   ![predictive-audiences-clone](assets/predictive-audiences-clone.png)
4. Depois de clonar o modelo, você será direcionado para a [!DNL Save & Configure] página do modelo clonado. Nesta página, você pode alterar a variável [!UICONTROL data source] e o atribuído[!UICONTROL Profile Merge Rule] do modelo. Para editar as personas e o público-alvo do modelo clonado, use o [!UICONTROL Back] e [!UICONTROL Next] botões para navegar entre as três guias ou clique nos nomes das três guias

   ![predictive-audiences-clone-navigate](assets/predictive-audiences-clone-navigate.png)

5. Quando terminar de editar um modelo, clique em **[!UICONTROL Save]**.

## Exclusão de públicos preditivos {#delete-predictive-audiences}

Para excluir um [!UICONTROL Predictive Audiences] modelo, vá para **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, localize o modelo que deseja excluir e clique no link **[!UICONTROL Delete]** ícone.
