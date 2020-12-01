---
description: Públicos preditivos ajudam a classificar públicos desconhecidos em personas distintas em tempo real, usando a ciência de dados.
seo-description: Públicos preditivos ajudam a classificar públicos desconhecidos em personas distintas em tempo real, usando a ciência de dados.
seo-title: Gerenciamento de Audiências preditivas
solution: Audience Manager
title: Públicos preditivos do Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 48bf17a2899fd06c525ba6b4fddb9ec805efb5c3
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 7%

---


# Introdução aos públicos preditivos {#predictive-audiences-getting-started}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo durante a configuração e o uso deste recurso. Nada aqui contido é aconselhamento jurídico. Consulte o seu próprio advogado para obter orientação jurídica.

## Criar um modelo de Audiências preditivo {#create-predictive-audiences}

Antes de criar um modelo [!UICONTROL Predictive Audiences], é necessário decidir a qual fonte de dados primária você deseja atribuir suas [!UICONTROL Predictive Audiences] características e segmentos. Você pode usar uma fonte de dados primária existente ou criar uma nova. Consulte [Gerenciar fontes de dados](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html) para obter detalhes sobre como criar uma nova fonte de dados primária.

Depois de saber qual fonte de dados você usará, siga as etapas abaixo.

1. Vá para **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. Na seção [!UICONTROL Predictive Audiences], clique em **[!UICONTROL Add New]**.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. Em seguida, defina as pessoas pelas quais deseja classificar a audiência. Você pode fazer isso escolhendo características ou segmentos dos quais criar personas. Use as guias [!UICONTROL Traits] e [!UICONTROL Segments] no canto superior esquerdo da tela para alternar entre sua característica e o catálogo de segmentos. Depois de identificar as características ou os segmentos que deseja usar como personas, clique no ícone **[!UICONTROL Add]** correspondente na coluna [!UICONTROL Action].
   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >Você deve escolher um mínimo de duas características ou dois segmentos para suas personas de linha de base. Não é possível usar uma combinação de características e segmentos.
1. Clique em **[!UICONTROL Next]** depois de definir suas personas.
1. Em seguida, selecione a audiência primária que deseja classificar escolhendo uma característica ou segmento primário para essa audiência. Use as guias [!UICONTROL Traits] e [!UICONTROL Segments] no canto superior esquerdo da tela para alternar entre suas características e o catálogo de segmentos. Selecione a característica ou o segmento primário que deseja usar como sua audiência para adicioná-lo ao modelo.
   ![smart-persona-select-audiência](assets/predictive-audiences-audience.png)
1. Clique em **[!UICONTROL Next]** depois de escolher sua audiência.
1. Preencha os detalhes do modelo:
   * **[!UICONTROL Model Name]**: Insira um nome descritivo para o modelo, que o ajudará a identificá-lo posteriormente. Os nomes dos segmentos gerados pelo modelo serão start com o nome do modelo.
   * **[!UICONTROL Description]**: Insira uma descrição do modelo que o ajudará a identificar seu caso de uso.
   * **[!UICONTROL Data Source]**: Selecione a fonte de dados primária à qual deseja que os  [!UICONTROL Predictive Audiences] segmentos deste modelo sejam atribuídos.
   * **[!UICONTROL Profile Merge Rule]**: Selecione o  [!UICONTROL Profile Merge Rule] a ser atribuído para todos os preditivos  [!UICONTROL segments] criados por este modelo. Se a audiência de público alvo selecionada for [!UICONTROL segment], recomendamos selecionar o mesmo [!UICONTROL Profile Merge Rule] da audiência de público alvo.
      ![previsão-audiências-salvamento](assets/predictive-audiences-save.png)
1. Clique em **[!UICONTROL Save]**.

## Clonagem e edição de modelos de Audiência preditiva {#clone-predictive-audiences}

O Audience Manager não suporta a edição de modelos [!UICONTROL Predictive Audiences] existentes. Para alterar a configuração de um modelo, é possível criar um clone de um modelo existente e editá-lo. Veja como fazer isso:

1. Vá para **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
2. Clique no nome do modelo [!UICONTROL Predictive Audiences] que você deseja clonar.
3. Clique no botão **[!UICONTROL Clone]** no canto superior esquerdo da tela.
   ![audiências preditivas-clone](assets/predictive-audiences-clone.png)
4. Depois de clonar o modelo, você é levado para a página [!DNL Save & Configure] do modelo clonado. Nesta página, você pode alterar [!UICONTROL data source] e as [!UICONTROL Profile Merge Rule] atribuídas do modelo. Para editar as pessoas e a audiência do modelo clonado, use os botões [!UICONTROL Back] e [!UICONTROL Next] para navegar entre as três guias ou clique nos três nomes das guias

   ![previsão-audiência-navegação clone](assets/predictive-audiences-clone-navigate.png)

5. Quando terminar de editar um modelo, clique em **[!UICONTROL Save]**.

## Excluindo Audiências preditivas {#delete-predictive-audiences}

Para excluir um modelo [!UICONTROL Predictive Audiences], vá até **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, localize o modelo que deseja excluir e clique no ícone **[!UICONTROL Delete]**.
