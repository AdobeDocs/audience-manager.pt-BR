---
description: Descreve as etapas e os recursos da configuração exclusivos ao processo de criação de traços algorítmicos.
seo-description: Descreve as etapas e os recursos da configuração exclusivos ao processo de criação de traços algorítmicos.
seo-title: Criar características algorítmicas
solution: Audience Manager
title: Criar características algorítmicas
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 5%

---


# Criar características algorítmicas {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

Para criar uma característica algorítmica, vá para [!UICONTROL Traits] e siga as etapas abaixo:

1. Clique **[!UICONTROL Create New Trait]** e selecione **[!UICONTROL Algorithmic]** no menu suspenso.
1. Na seção Informações [](../../features/traits/create-onboarded-rule-based-traits.md) básicas
   * Dê um nome ao traço.
   * Selecione uma fonte de dados.
   * Escolha uma pasta de armazenamento.
1. Expanda o [!UICONTROL Configuration] painel e clique em **[!UICONTROL Browse All Models]**.
Isso abre uma nova janela que permite selecionar o modelo que deseja usar com a característica.
1. Selecione um modelo e clique em **[!UICONTROL Add Selected Model to Trait]**.
Adicionar o modelo expõe as configurações de alcance e precisão.
1. Selecione o alcance ou a precisão como sua meta e escolha um valor nos respectivos menus suspensos. Clique **[!UICONTROL Save]** quando concluído.

## Configurações para características algorítmicas {#configure-settings}

Em [!UICONTROL Trait Builder], a [!UICONTROL Configuration] seção permite associar um modelo algorítmico a uma característica. Para concluir o processo de criação de característica algorítmica, selecione um modelo e escolha uma meta de alcance ou precisão.

### Pré-requisitos

<!-- r_algo_trait_config_section.xml -->

* [Criar um modelo semelhante](../../features/algorithmic-models/create-model.md).
* Aguarde o e-mail de notificação que informa que o modelo de execução de dados foi concluído.
* Preencha os campos obrigatórios na seção Informações [](../../features/traits/create-onboarded-rule-based-traits.md) básicas.

### Campos e configurações

| Elemento de interface | Explicação |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Clique no **[!UICONTROL Update]** botão para abrir a janela de modelos. Na janela, selecione o modelo algorítmico que deseja usar para criar a característica. |
| **[!UICONTROL Select Goal Accuracy]** | Selecione essa opção para criar uma característica com base na precisão. A precisão é um valor pontuado que indica quão próximos os usuários potenciais estão da sua linha de base. A escala de precisão varia de 0 (menos precisa) a 1 (mais precisa). |
| **[!UICONTROL Reach and Accuracy Data Columns]** | Localizada à direita, esta seção exibe até 21 linhas de dados numéricos que exibem a precisão e os valores de alcance do modelo. |
| **[!UICONTROL Reach and Accuracy Slider]** | Localizado na parte inferior do gráfico, o controle deslizante permite que você defina um valor numérico para suas metas de alcance ou precisão. Você pode definir o controle deslizante e escolher o botão de objetivo de alcance ou precisão para criar uma característica. |

>[!MORELIKETHIS]
>
>* [Precisão e alcance](../../features/traits/trait-accuracy-reach.md)

