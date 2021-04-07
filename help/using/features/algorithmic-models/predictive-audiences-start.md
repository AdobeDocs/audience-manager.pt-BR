---
description: Públicos preditivos ajudam a classificar públicos desconhecidos em personas distintas em tempo real, usando a ciência de dados.
seo-description: Públicos preditivos ajudam a classificar públicos desconhecidos em personas distintas em tempo real, usando a ciência de dados.
seo-title: Gerenciamento de públicos-alvo preditivos
solution: Audience Manager
title: Introdução aos públicos preditivos
feature: Modelos algorítmicos
exl-id: beb314de-f679-4397-8e14-2dd6576243fd
translation-type: tm+mt
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 7%

---

# Introdução aos públicos preditivos {#predictive-audiences-getting-started}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo pela configuração e uso deste recurso. Nada neste documento é de aconselhamento jurídico. Consulte o seu advogado para obter orientação jurídica.

## Criar um modelo de Predictive Audiences {#create-predictive-audiences}

Antes de criar um modelo [!UICONTROL Predictive Audiences], é necessário decidir a fonte de dados primária à qual deseja atribuir suas características e segmentos [!UICONTROL Predictive Audiences]. Você pode usar uma fonte de dados primária existente ou criar uma nova. Consulte [Gerenciar fontes de dados](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html) para obter detalhes sobre como criar uma nova fonte de dados primária.

Depois de saber qual fonte de dados você usará, siga as etapas abaixo.

1. Vá para **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. Na seção [!UICONTROL Predictive Audiences], clique em **[!UICONTROL Add New]**.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. Em seguida, defina as personas para as quais deseja classificar o público-alvo. Você pode fazer isso escolhendo características ou segmentos dos quais criar personas. Use as guias [!UICONTROL Traits] e [!UICONTROL Segments] no canto superior esquerdo da tela para alternar entre sua característica e o catálogo de segmentos. Depois de identificar as características ou segmentos que deseja usar como personas, clique no ícone **[!UICONTROL Add]** correspondente na coluna [!UICONTROL Action].
   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >Você deve escolher um mínimo de duas características ou dois segmentos para suas personas de linha de base. Não é possível usar uma combinação de características e segmentos.
1. Clique em **[!UICONTROL Next]** após definir suas personas.
1. Em seguida, selecione o público-alvo próprio que deseja classificar escolhendo uma característica ou segmento primário para esse público-alvo. Use as guias [!UICONTROL Traits] e [!UICONTROL Segments] no canto superior esquerdo da tela para alternar entre suas características e o catálogo de segmentos. Selecione a característica ou o segmento primário que você deseja usar como público-alvo, para adicioná-lo ao modelo.
   ![smart-persona-select-audience](assets/predictive-audiences-audience.png)
1. Clique em **[!UICONTROL Next]** após escolher o público-alvo.
1. Preencha os detalhes do modelo:
   * **[!UICONTROL Model Name]**: Insira um nome descritivo para o modelo, que ajudará a identificá-lo posteriormente. Os nomes dos segmentos gerados pelo modelo começarão com o nome do modelo.
   * **[!UICONTROL Description]**: Insira uma descrição do modelo que ajudará a identificar o caso de uso.
   * **[!UICONTROL Data Source]**: Selecione a fonte de dados primária à qual deseja que os  [!UICONTROL Predictive Audiences] segmentos deste modelo sejam atribuídos.
   * **[!UICONTROL Profile Merge Rule]**: Selecione o  [!UICONTROL Profile Merge Rule] a ser atribuído para todos os preditivos  [!UICONTROL segments] criados por este modelo. Se o público-alvo selecionado for um [!UICONTROL segment], recomendamos selecionar o mesmo [!UICONTROL Profile Merge Rule] do público-alvo.
      ![salvamento de públicos-alvo preditivos](assets/predictive-audiences-save.png)
1. Clique em **[!UICONTROL Save]**.

## Clonagem e edição de modelos de público-alvo preditivo {#clone-predictive-audiences}

O Audience Manager não suporta a edição de modelos [!UICONTROL Predictive Audiences] existentes. Para alterar a configuração de um modelo, você pode criar um clone de um modelo existente e editá-lo. Veja como fazer isso:

1. Vá para **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
2. Clique no nome do modelo [!UICONTROL Predictive Audiences] que deseja clonar.
3. Clique no botão **[!UICONTROL Clone]** no lado superior esquerdo da tela.
   ![predictive-audiences-clone](assets/predictive-audiences-clone.png)
4. Depois de clonar o modelo, você é levado para a página [!DNL Save & Configure] do modelo clonado. Nesta página, você pode alterar o [!UICONTROL data source] e o [!UICONTROL Profile Merge Rule] atribuído do modelo. Para editar as personas e o público-alvo do modelo clonado, use os botões [!UICONTROL Back] e [!UICONTROL Next] para navegar entre as três guias ou clique nos três nomes de guia

   ![predictive-audiences-clone-navigate](assets/predictive-audiences-clone-navigate.png)

5. Quando terminar de editar um modelo, clique em **[!UICONTROL Save]**.

## Excluir públicos preditivos {#delete-predictive-audiences}

Para excluir um modelo [!UICONTROL Predictive Audiences], vá para **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, localize o modelo que deseja excluir e clique no ícone **[!UICONTROL Delete]**.
