---
description: Descreve as etapas e os recursos da configuração exclusivos do processo de criação de características algorítmicas.
seo-description: Descreve as etapas e os recursos da configuração exclusivos do processo de criação de características algorítmicas.
seo-title: Criar características algorítmicas
solution: Audience Manager
title: Criar características algorítmicas
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
feature: 'Características '
exl-id: dc799688-e38b-469b-bc55-507df0d28f43
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 5%

---

# Criar características algorítmicas {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

Para criar uma característica algorítmica, vá para [!UICONTROL Traits] e siga as etapas abaixo:

1. Clique em **[!UICONTROL Create New Trait]** e selecione **[!UICONTROL Algorithmic]** no menu suspenso.
1. Na seção [Informações básicas](../../features/traits/create-onboarded-rule-based-traits.md)
   * Nomeie a característica.
   * Selecione uma fonte de dados.
   * Escolha uma pasta de armazenamento.
1. Expanda o painel [!UICONTROL Configuration] e clique em **[!UICONTROL Browse All Models]**.
Isso abre uma nova janela que permite selecionar o modelo que deseja usar com a característica.
1. Selecione um modelo e clique em **[!UICONTROL Add Selected Model to Trait]**.
Adicionar o modelo expõe as configurações de alcance e precisão.
1. Selecione alcance ou precisão como meta e escolha um valor nos respectivos menus suspensos. Clique em **[!UICONTROL Save]** quando terminar.

## Configurações para características algorítmicas {#configure-settings}

Em [!UICONTROL Trait Builder], a seção [!UICONTROL Configuration] permite associar um modelo algorítmico a uma característica. Para concluir o processo de criação de características algorítmicas, selecione um modelo e escolha uma meta de alcance ou precisão.

### Pré-requisitos

<!-- r_algo_trait_config_section.xml -->

* [Criar um modelo semelhante](../../features/algorithmic-models/create-model.md).
* Aguarde o email de notificação que informa que o modelo de dados executado foi concluído.
* Preencha os campos obrigatórios na seção [Informações básicas](../../features/traits/create-onboarded-rule-based-traits.md).

### Campos e configurações de configuração

| Elemento da interface | Explicação |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Clique no botão **[!UICONTROL Update]** para abrir a janela de modelos. Na janela , selecione o modelo algorítmico que deseja usar para criar a característica. |
| **[!UICONTROL Select Goal Accuracy]** | Selecione essa opção para criar uma característica com base na precisão. A precisão é um valor pontuado que indica o quão próximos usuários em potencial estão de sua linha de base. A escala de precisão varia de 0 (menos precisa) a 1 (mais precisa). |
| **[!UICONTROL Reach and Accuracy Data Columns]** | Localizada à direita, esta seção exibe até 21 linhas de dados numéricos que exibem a precisão e os valores de alcance do modelo. |
| **[!UICONTROL Reach and Accuracy Slider]** | Localizado na parte inferior do gráfico, o controle deslizante permite definir um valor numérico para suas metas de alcance ou precisão. Você pode definir o controle deslizante e escolher o botão de meta de alcance ou precisão para criar uma característica. |

>[!MORELIKETHIS]
>
>* [Precisão e alcance](../../features/traits/trait-accuracy-reach.md)

