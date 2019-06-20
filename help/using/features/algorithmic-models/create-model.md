---
description: Descreve as etapas obrigatórias e opcionais que permitem criar um modelo algorítmico no Criador de modelos.
keywords: como funciona funciona
seo-description: Descreve as etapas obrigatórias e opcionais que permitem criar um modelo algorítmico no Criador de modelos.
seo-title: Criar um modelo algorítmico
solution: Audience Manager
title: Criar um modelo algorítmico
topic: API DIL
uuid: ccf 4 fc 4 e-cf 92-445 f-b 2 d 9-71 c 3 ca 624 e 26
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create an Algorithmic Model {#create-an-algorithmic-model}

Describes the required and optional steps that let you create an algorithmic model in [!UICONTROL Model Builder].

## Build a Model {#build-model}

<!-- t_model_build.xml -->

### Seção do Construtor de modelo

[!UICONTROL Model Builder] é composta por [!UICONTROL Basic Information] seções e [!UICONTROL Configuration] seções. Para criar um modelo, preencha os campos obrigatórios nessas duas seções. Salve o modelo para iniciar o algoritmo. [!DNL Audience Manager] envia uma notificação automatizada após a conclusão dos primeiros dados. After you receive the email, you can go to [Trait Builder](../../features/traits/about-trait-builder.md) and create algorithmic traits.

>[!NOTE]
>
>* O processo de modelagem é executado apenas uma vez se você criar um modelo e não criar nenhuma característica com ela.
>* Crie modelos a partir de fontes de dados que contêm uma quantidade significativa de informações. Os modelos com dados insuficientes serão executados, mas não serão gerados.
>* *Não* crie modelos com outras características ou segmentos algoritmicos.
>* A notificação automática de email é enviada apenas uma vez (após a primeira execução dos dados).


### Criar o modelo

To build a model, go to the [!UICONTROL Models] section and click **[!UICONTROL Add New]** and follow the steps below:

1. In the [Basic Information](../../features/algorithmic-models/create-model.md#basic-information) section
   * Nomeie o modelo.
   * *(Opcional)* Forneça uma breve descrição sobre o modelo.
   * Set the status for the model to **[!UICONTROL Active]** or **[!UICONTROL Inactive]**. Os modelos inativos não serão executados e não serão produzidos nenhum dado.
1. In the [Configuration](../../features/algorithmic-models/create-model.md#configuration) section:
   * Click **[!UICONTROL Browse All Traits]** or **[!UICONTROL Browse All Segments]** to select a trait or segment you want to model against. Selecione uma característica embutida, uma característica baseada em regras ou um segmento como linha de base. Caso contrário, seus modelos não serão executados.
   * Escolha um período de retrospectiva de 30, 60 ou 90 dias. Isso define um intervalo de tempo para o modelo.
   * The [!UICONTROL TraitWeight] algorithm is selected by default.
   * Select a data source from the [!UICONTROL Available Data] list.
   * Click **[!UICONTROL Save]** when done.

## Basic Information for Algorithmic Models {#basic-information}

<!-- r_model_basic.xml -->

In [!UICONTROL Model Builder], the [!UICONTROL Basic Information] settings let you create new or edit existing models. To create a new model, provide a name and move on to the [!UICONTROL Configuration] settings. O campo de descrição é opcional.

| Campo | Descrição |
|---|---|
| **[!UICONTROL Name]** | Dê um nome curto e lógico ao seu modelo que descreva sua função ou finalidade. Evite abreviações, caracteres especiais e marcas de acento. |
| **[!UICONTROL Description]** | Um campo para obter informações descritivas adicionais sobre o modelo. |
| **[!UICONTROL Status]** | Ativa ou desativa o modelo (ativo por padrão). |

## Configuração {#configuration}

In [!UICONTROL Model Builder], the [!UICONTROL Configuration] section lets you add traits or segments to the model. Nesta seção, selecione uma característica ou segmento de linha de base, um período de retrospectiva e dados de suas fontes de dados originais e de terceiros.

<!-- r_model_configuration.xml -->

### Pré-requisitos

Complete the required fields in the [!UICONTROL Basic Information] section first.

![](assets/lam_exclude_traits_numbered.png)

<table id="table_7A6BE5E5498D4776A30323B743954150"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Selecione uma característica de linha de base ou um segmento (1)</b> </p> </td> 
   <td colname="col2"> <p>Clique no botão de características ou segmento para ver uma lista de todos os seus traços ou segmentos. Seu segmento ou característica selecionado se torna a linha de base que os algoritmos do sistema usam para modelagem. </p> <p> <p><b>Observação</b>: Selecione uma característica embutida, uma característica baseada em regras ou um segmento como linha de base. Caso contrário, seus modelos não serão executados. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Selecione o período de retrospectiva (2)</b> </p> </td> 
   <td colname="col2"> <p>Define um intervalo de tempo para o modelo. Com base em sua seleção, o algoritmo inclui e avalia os dados dos últimos 30, 60 ou 90 dias. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Selecionar algoritmo (3)</b> </p> </td> 
   <td colname="col2"> <p>At this time, Model Builder works with our proprietary <span class="keyword"> Trait Weight</span> algorithm only. <span class="keyword"> O Audience Manager</span> pode adicionar outras funções algorítmicas em versões subsequentes. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Selecionar dados de modelo da fonte de dados (4)</b> </p> </td> 
   <td colname="col2"> <p>Permite selecionar as fontes de dados originais e de terceiros que você deseja usar no modelo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exclusões (5)</b> </p> </td> 
   <td colname="col2"> <p>É possível excluir características das fontes de dados selecionadas para modelagem. Use the <span class="wintitle"> Exclusions</span> list and read <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> Algorithmic Models: Trait Exclusion</a> to learn more. </p> </td>
  </tr> 
 </tbody>
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Noções básicas de traitweight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

