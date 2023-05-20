---
description: Descreve as etapas de configuração e os recursos exclusivos do processo de criação de características algorítmicas.
seo-description: Describes set up steps and features unique to the algorithmic trait creation process.
seo-title: Create Algorithmic Traits
solution: Audience Manager
title: Criar características algorítmicas
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
feature: Traits
exl-id: dc799688-e38b-469b-bc55-507df0d28f43
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 4%

---

# Criar características algorítmicas {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

Para criar uma característica algorítmica, acesse [!UICONTROL Traits] e siga as etapas abaixo:

1. Clique em **[!UICONTROL Create New Trait]** e selecione **[!UICONTROL Algorithmic]** no menu suspenso.
1. No [Informações básicas](../../features/traits/create-onboarded-rule-based-traits.md) seção
   * Nomeie a característica.
   * Selecione uma fonte de dados.
   * Escolha uma pasta de armazenamento.
1. Expanda a [!UICONTROL Configuration] e clique em **[!UICONTROL Browse All Models]**.
Essa ação abre uma nova janela que permite selecionar o modelo que você deseja usar com a característica.
1. Selecione um modelo e clique em **[!UICONTROL Add Selected Model to Trait]**.
A adição do modelo expõe as configurações de alcance e precisão.
1. Selecione alcance ou precisão como meta e escolha um valor nos respectivos menus suspensos. Clique em **[!UICONTROL Save]** quando terminar.

## Configurações para características algorítmicas {#configure-settings}

Entrada [!UICONTROL Trait Builder], o [!UICONTROL Configuration] permite associar um modelo algorítmico a uma característica. Para concluir o processo de criação de características algorítmicas, selecione um modelo e escolha um objetivo de alcance ou precisão.

### Pré-requisitos

<!-- r_algo_trait_config_section.xml -->

* [Criar um modelo semelhante](../../features/algorithmic-models/create-model.md).
* Aguarde o email de notificação que informa que a execução dos dados do modelo foi concluída.
* Preencha os campos obrigatórios na [Informações básicas](../../features/traits/create-onboarded-rule-based-traits.md) seção.

### Campos e configurações

| Elemento de interface | Explicação |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Clique em **[!UICONTROL Update]** botão para abrir a janela modelos. Na janela, selecione o modelo algorítmico que deseja usar para criar a característica. |
| **[!UICONTROL Select Goal Accuracy]** | Selecione essa opção para criar uma característica com base na precisão. A precisão é um valor pontuado que indica o quão próximos os usuários em potencial estão da sua linha de base. A escala de precisão varia de 0 (menos precisa) a 1 (mais precisa). |
| **[!UICONTROL Reach and Accuracy Data Columns]** | Localizada à direita, esta seção exibe até 21 linhas de dados numéricos que exibem os valores de precisão e alcance do seu modelo. |
| **[!UICONTROL Reach and Accuracy Slider]** | Localizado na parte inferior do gráfico, o controle deslizante permite definir um valor numérico para suas metas de alcance ou precisão. Você pode definir o controle deslizante e escolher o botão de meta de alcance ou precisão para criar uma característica. |

>[!MORELIKETHIS]
>
>* [Precisão e alcance](../../features/traits/trait-accuracy-reach.md)

