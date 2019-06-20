---
description: Descreve as etapas e os recursos configurados exclusivos para o processo de criação algorítmica.
seo-description: Descreve as etapas e os recursos configurados exclusivos para o processo de criação algorítmica.
seo-title: Criar características algorítmicas
solution: Audience Manager
title: Criar características algorítmicas
uuid: 50 c 2 d 2 d 1-f 412-479 b-bb 70-4 f 139429 c 388
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create Algorithmic Traits {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

To create an algorithmic trait, go to [!UICONTROL Traits] and follow the steps below:

1. Click **[!UICONTROL Create New Trait]** and select **[!UICONTROL Algorithmic]** from the drop down menu.
1. In the [Basic Information](../../features/traits/create-onboarded-rule-based-traits.md) section
   * Nomeie a característica.
   * Selecione uma fonte de dados.
   * Escolha uma pasta de armazenamento.
1. Expand the [!UICONTROL Configuration] pane and click **[!UICONTROL Browse All Models]**.
Isso abre uma nova janela que permite selecionar o modelo que você deseja usar com a característica.
1. Select a model and click **[!UICONTROL Add Selected Model to Trait]**.
A adição do modelo expõe as configurações de alcance e precisão.
1. Selecione alcance ou precisão como meta e escolha um valor dos respectivos menus suspensos. Click **[!UICONTROL Save]** when done.

>[!MORE_ LIKE_ THIS]
>
>* [Precisão e alcance](../../features/traits/trait-accuracy-reach.md)


## Configuration Settings for Algorithmic Traits {#configure-settings}

In [!UICONTROL Trait Builder], the [!UICONTROL Configuration] section lets you associate an algorithmic model to a trait. Para concluir o processo de criação algorítmica, selecione um modelo e escolha um alcance ou uma meta de precisão.

### Pré-requisitos

<!-- r_algo_trait_config_section.xml -->

* [Crie um modelo algorítmico](../../features/algorithmic-models/create-model.md#build-model).
* Aguarde o e-mail de notificação que permite que você saiba que a execução dos dados do modelo terminou.
* Complete the required fields in the [Basic Information](../../features/traits/create-onboarded-rule-based-traits.md) section.

### Campos e configurações de configuração

| Elemento da interface | Explicação |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Click the **[!UICONTROL Update]** button to open the models window. Na janela, selecione o modelo algorítmico que deseja usar para criar a característica. |
| **[!UICONTROL Select Goal Accuracy]** | Selecione essa opção para criar uma característica com base na precisão. A precisão é um valor pontuado que indica o quão próximo os usuários potenciais estão à sua linha de base. A precisão varia de 0 (menos preciso) para 1 (mais precisa). |
| **[!UICONTROL Reach and Accuracy Data Columns]** | Localizada à direita, esta seção exibe até 21 linhas de dados numéricos que exibem os valores de precisão e alcance para o modelo. |
| **[!UICONTROL Reach and Accuracy Slider]** | Localizado na parte inferior do gráfico, o controle deslizante permite definir um valor numérico para seus objetivos de alcance ou precisão. Você pode definir o controle deslizante e escolher o botão alcance ou precisão para criar uma característica. |

>[!MORE_ LIKE_ THIS]
>
>* [Precisão e alcance](../../features/traits/trait-accuracy-reach.md)