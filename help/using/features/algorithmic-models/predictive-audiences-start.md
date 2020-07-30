---
description: Públicos preditivos ajudam a classificar públicos desconhecidos em personas distintas em tempo real, usando a ciência de dados.
seo-description: Públicos preditivos ajudam a classificar públicos desconhecidos em personas distintas em tempo real, usando a ciência de dados.
seo-title: Gerenciamento de Audiências preditivas
solution: Audience Manager
title: Públicos preditivos do Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 71e129a39cf85d5f07979ede8f3aa862f93b6512
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 8%

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

## Edição de Audiências preditivas {#edit-predictive-audiences}

O Audience Manager não oferece suporte à edição de [!UICONTROL Predictive Audiences] modelos existentes. Para alterar a configuração de um modelo, é necessário criar um novo modelo. Se você atingiu o limite de 10 [!UICONTROL Predictive Audiences] modelos e precisa editar um de seus modelos, é necessário excluir um modelo e criar um novo.

## Excluindo Audiências preditivas {#delete-predictive-audiences}

Para excluir um [!UICONTROL Predictive Audiences] modelo, vá até **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, localize o modelo que deseja excluir e clique no **[!UICONTROL Delete]** ícone.
