---
description: Describes the required and optional steps that let you create an algorithmic model in Model Builder.
keywords: algo funciona
seo-description: Descreve as etapas necessárias e opcionais que permitem criar um modelo algorítmico no Construtor de modelos.
seo-title: Criar um modelo algorítmico
solution: Audience Manager
title: Create an Algorithmic Model
topic: API DIL
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
translation-type: tm+mt
source-git-commit: a1d75c83d5876090f3a4d284b18984e2d1a70313

---


# Criar um modelo algorítmico {#create-an-algorithmic-model}

Descreve as etapas necessárias e opcionais que permitem criar um modelo algorítmico em [!UICONTROL Model Builder].

## Criar um modelo {#build-model}

<!-- t_model_build.xml -->

### Seção do Construtor de modelos

[!UICONTROL Model Builder] consiste nas seções [!UICONTROL Basic Information] e [!UICONTROL Configuration] . To create a model, complete the required fields in these two sections. Save your model to start the algorithm. [!DNL Audience Manager] sends you an automated notification after the first data run completes. After you receive the email, you can go to Trait Builder and create algorithmic traits.[](../../features/traits/about-trait-builder.md)

>[!NOTE]
>
>* The modeling process runs only once if you create a model and do not build any traits with it.
>* Build models from data sources that contain a meaningful amount of information. Os modelos com dados insuficientes serão executados, mas não retornarão resultados.
>* *Não* crie modelos com outros traços ou segmentos algorítmicos.
>* A notificação por email automatizada é enviada apenas uma vez (após a primeira execução dos dados).


### Build the Model

To build a model, go to the  section and click  and follow the steps below:[!UICONTROL Models]**[!UICONTROL Add New]**

1. Na seção Informações [](../../features/algorithmic-models/create-model.md#basic-information) básicas
   * Name the model.
   * *(Optional) Provide a brief description about the model.*
   * Defina o status do modelo como **[!UICONTROL Active]** ou **[!UICONTROL Inactive]**. Os modelos inativos não serão executados e não produzirão dados.
1. Na seção [Configuração](../../features/algorithmic-models/create-model.md#configuration) :
   * Click  or  to select a trait or segment you want to model against. **[!UICONTROL Browse All Traits]****[!UICONTROL Browse All Segments]**   Selecione uma característica integrada, uma característica baseada em regras ou um segmento como linha de base. Caso contrário, seus modelos não serão executados.
   * Escolha um período de retrospectiva de 30, 60 ou 90 dias. Isso define um intervalo de tempo para o modelo.
   * The [!UICONTROL TraitWeight] algorithm is selected by default.
   * Select a data source from the  list.[!UICONTROL Available Data]
   * Click **[!UICONTROL Save]** when done.

## Informações básicas para modelos algorítmicos {#basic-information}

<!-- r_model_basic.xml -->

Em [!UICONTROL Model Builder], as [!UICONTROL Basic Information] configurações permitem criar modelos novos ou editar modelos existentes. To create a new model, provide a name and move on to the  settings. [!UICONTROL Configuration] O campo de descrição é opcional.

| Campo | Descrição |
|---|---|
| **[!UICONTROL Name]** | Dê ao seu modelo um nome curto e lógico que descreva sua função ou propósito. Evite abreviações, caracteres especiais e marcas de ênfase. |
| **[!UICONTROL Description]** | Um campo para obter informações descritivas adicionais sobre o modelo. |
| **[!UICONTROL Status]** | Ativa ou desativa o modelo (ativo por padrão). |

## Configuração {#configuration}

Em [!UICONTROL Model Builder], a [!UICONTROL Configuration] seção permite adicionar características ou segmentos ao modelo. Nesta seção, selecione uma característica ou segmento de linha de base, um período de análise e dados de suas fontes de dados originais e de terceiros.

<!-- r_model_configuration.xml -->

### Pré-requisitos

Complete the required fields in the  section first.[!UICONTROL Basic Information]

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
   <td colname="col1"> <p><b>Selecionar uma característica ou segmento da linha de base (1)</b> </p> </td> 
   <td colname="col2"> <p>Clique no botão de característica ou segmento para ver uma lista de todas as suas características ou segmentos. Seu segmento ou característica selecionado se torna a linha de base que os algoritmos do sistema usam para modelagem. </p> <p> <p><b>Observação</b>:Selecione uma característica integrada, uma característica baseada em regras ou um segmento como linha de base. Caso contrário, seus modelos não serão executados. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Selecionar período de retrospectiva (2)</b> </p> </td> 
   <td colname="col2"> <p>Define um intervalo de tempo para o modelo. Com base na sua seleção, o algoritmo inclui e avalia dados dos 30, 60 ou 90 dias anteriores. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Select Algorithm (3)</b> </p> </td> 
   <td colname="col2"> <p>At this time, Model Builder works with our proprietary  Trait Weight algorithm only. <span class="keyword"></span> <span class="keyword"> O Audience Manager</span> pode adicionar outras funções algorítmicas em versões subsequentes. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Selecionar Dados do Modelo da Fonte de Dados (4)</b> </p> </td> 
   <td colname="col2"> <p>Lets you select the first and third-party data sources you want to use in the model. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exclusões (5)</b> </p> </td> 
   <td colname="col2"> <p>You can exclude traits from the data sources you selected for modeling. Use the  Exclusions list and read  Algorithmic Models: Trait Exclusion to learn more.<span class="wintitle"></span><a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"></a> </p> </td>
  </tr> 
 </tbody>
</table>

Assista ao vídeo abaixo para saber como criar um modelo parecido, para que você possa encontrar mais visitantes que se pareçam com seus conversores.

>[!VIDEO](https://video.tv.adobe.com/v/23504/?captions=por_br)

>[!MORE_LIKE_THIS]
>
>* [Compreensão de TraitWeight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

