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

Antes de criar um [!UICONTROL Predictive Audiences] modelo, é necessário decidir a qual fonte de dados primária você deseja atribuir suas [!UICONTROL Predictive Audiences] características e segmentos. Você pode usar uma fonte de dados primária existente ou criar uma nova. Consulte [Gerenciar fontes](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html) de dados para obter detalhes sobre como criar uma nova fonte de dados primária.

Depois de saber qual fonte de dados você usará, siga as etapas abaixo.

1. Vá até **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. Na [!UICONTROL Predictive Audiences] seção, clique em **[!UICONTROL Add New]**.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. Em seguida, defina as pessoas pelas quais deseja classificar a audiência. Você pode fazer isso escolhendo características ou segmentos dos quais criar personas. Use as guias [!UICONTROL Traits] e [!UICONTROL Segments] no canto superior esquerdo da tela para alternar entre sua característica e o catálogo de segmentos. Depois de identificar as características ou os segmentos que deseja usar como personas, clique no **[!UICONTROL Add]** ícone correspondente na [!UICONTROL Action] coluna.
   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >Você deve escolher um mínimo de duas características ou dois segmentos para suas personas de linha de base. Não é possível usar uma combinação de características e segmentos.
1. Clique **[!UICONTROL Next]** depois de definir suas personas.
1. Em seguida, selecione a audiência primária que deseja classificar escolhendo uma característica ou segmento primário para essa audiência. Use as guias [!UICONTROL Traits] e [!UICONTROL Segments] no canto superior esquerdo da tela para alternar entre suas características e o catálogo de segmentos. Selecione a característica ou o segmento primário que deseja usar como sua audiência para adicioná-lo ao modelo.
   ![smart-persona-select-audiência](assets/predictive-audiences-audience.png)
1. Clique **[!UICONTROL Next]** depois de escolher sua audiência.
1. Preencha os detalhes do modelo:
   * **[!UICONTROL Model Name]**: Insira um nome descritivo para o modelo, que o ajudará a identificá-lo posteriormente. Os nomes dos segmentos gerados pelo modelo serão start com o nome do modelo.
   * **[!UICONTROL Description]**: Insira uma descrição do modelo que o ajudará a identificar seu caso de uso.
   * **[!UICONTROL Data Source]**: Selecione a fonte de dados primária à qual deseja que os [!UICONTROL Predictive Audiences] segmentos deste modelo sejam atribuídos.
   * **[!UICONTROL Profile Merge Rule]**: Selecione o [!UICONTROL Profile Merge Rule] a ser atribuído para todos os preditivos [!UICONTROL segments] criados por este modelo. Se sua audiência de público alvo selecionada for uma  [!UICONTROL segment], recomendamos selecionar a mesma audiência [!UICONTROL Profile Merge Rule] da público alvo.
      ![previsão-audiências-salvamento](assets/predictive-audiences-save.png)
1. Clique em **[!UICONTROL Save]**.

## Clonagem e edição de modelos de Audiência preditiva {#clone-predictive-audiences}

O Audience Manager não oferece suporte à edição de [!UICONTROL Predictive Audiences] modelos existentes. Para alterar a configuração de um modelo, é possível criar um clone de um modelo existente e editá-lo. Veja como fazer isso:

1. Vá até **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
2. Clique no nome do [!UICONTROL Predictive Audiences] modelo que deseja clonar.
3. Clique no **[!UICONTROL Clone]** botão no canto superior esquerdo da tela.
   ![audiências preditivas-clone](assets/predictive-audiences-clone.png)
4. Depois de clonar o modelo, você é levado para a [!DNL Save & Configure] página do modelo clonado. Nesta página, você pode alterar o modelo [!UICONTROL data source] e a atribuição[!UICONTROL Profile Merge Rule] do modelo. Para editar as pessoas e a audiência do modelo clonado, use os botões [!UICONTROL Back] e [!UICONTROL Next] para navegar entre as três guias ou clique nos três nomes das guias

   ![previsão-audiência-navegação clone](assets/predictive-audiences-clone-navigate.png)

5. Quando terminar de editar um modelo, clique em **[!UICONTROL Save]**.

## Excluindo Audiências preditivas {#delete-predictive-audiences}

Para excluir um [!UICONTROL Predictive Audiences] modelo, vá até **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, localize o modelo que deseja excluir e clique no **[!UICONTROL Delete]** ícone.
