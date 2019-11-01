---
description: Descreve as etapas necessárias e opcionais que permitem criar um modelo algorítmico no Construtor de modelos.
keywords: algo funciona
seo-description: Descreve as etapas necessárias e opcionais que permitem criar um modelo algorítmico no Construtor de modelos.
seo-title: Criar um modelo algorítmico
solution: Audience Manager
title: Criar um modelo algorítmico
topic: API DIL
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Criar um modelo algorítmico {#create-an-algorithmic-model}

Descreve as etapas necessárias e opcionais que permitem criar um modelo algorítmico em [!UICONTROL Model Builder].

## Criar um modelo {#build-model}

<!-- t_model_build.xml -->

### Seção do Construtor de modelos

[!UICONTROL Model Builder] consiste nas seções [!UICONTROL Basic Information] e [!UICONTROL Configuration] . Para criar um modelo, preencha os campos obrigatórios nessas duas seções. Salve o modelo para iniciar o algoritmo. [!DNL Audience Manager] envia uma notificação automática após a conclusão da primeira execução de dados. Depois de receber o email, você pode acessar o Construtor de [características](../../features/traits/about-trait-builder.md) e criar traços algorítmicos.

>[!NOTE]
>
>* O processo de modelagem é executado apenas uma vez se você criar um modelo e não criar nenhuma característica com ele.
>* Crie modelos a partir de fontes de dados que contêm uma quantidade significativa de informações. Os modelos com dados insuficientes serão executados, mas não retornarão resultados.
>* *Não* crie modelos com outros traços ou segmentos algorítmicos.
>* A notificação por email automatizada é enviada apenas uma vez (após a primeira execução dos dados).


### Criar o modelo

Para criar um modelo, vá para a [!UICONTROL Models] seção e clique **[!UICONTROL Add New]** e siga as etapas abaixo:

1. Na seção Informações [](../../features/algorithmic-models/create-model.md#basic-information) básicas
   * Nomeie o modelo.
   * *(Opcional)* Forneça uma breve descrição sobre o modelo.
   * Defina o status do modelo como **[!UICONTROL Active]** ou **[!UICONTROL Inactive]**. Os modelos inativos não serão executados e não produzirão dados.
1. Na seção [Configuração](../../features/algorithmic-models/create-model.md#configuration) :
   * Clique **[!UICONTROL Browse All Traits]** ou **[!UICONTROL Browse All Segments]** para selecionar uma característica ou segmento para o qual deseja criar um modelo.   Selecione uma característica integrada, uma característica baseada em regras ou um segmento como linha de base. Caso contrário, seus modelos não serão executados.
   * Escolha um período de retrospectiva de 30, 60 ou 90 dias. Isso define um intervalo de tempo para o modelo.
   * The [!UICONTROL TraitWeight] algorithm is selected by default.
   * Selecione uma fonte de dados na [!UICONTROL Available Data] lista.
   * Click **[!UICONTROL Save]** when done.

## Informações básicas para modelos algorítmicos {#basic-information}

<!-- r_model_basic.xml -->

Em [!UICONTROL Model Builder], as [!UICONTROL Basic Information] configurações permitem criar modelos novos ou editar modelos existentes. Para criar um novo modelo, forneça um nome e siga para as [!UICONTROL Configuration] configurações. O campo de descrição é opcional.

| Campo | Descrição |
|---|---|
| **[!UICONTROL Name]** | Dê ao seu modelo um nome curto e lógico que descreva sua função ou propósito. Evite abreviações, caracteres especiais e marcas de ênfase. |
| **[!UICONTROL Description]** | Um campo para obter informações descritivas adicionais sobre o modelo. |
| **[!UICONTROL Status]** | Ativa ou desativa o modelo (ativo por padrão). |

## Configuração {#configuration}

Em [!UICONTROL Model Builder], a [!UICONTROL Configuration] seção permite adicionar características ou segmentos ao modelo. Nesta seção, selecione uma característica ou segmento de linha de base, um período de análise e dados de suas fontes de dados originais e de terceiros.

<!-- r_model_configuration.xml -->

### Pré-requisitos

Preencha os campos obrigatórios na [!UICONTROL Basic Information] seção primeiro.

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
   <td colname="col2"> <p>Clique no botão de característica ou segmento para ver uma lista de todas as suas características ou segmentos. Seu segmento ou característica selecionado se torna a linha de base que os algoritmos do sistema usam para modelagem. </p> <p> <p><b>Observação</b>:  Selecione uma característica integrada, uma característica baseada em regras ou um segmento como linha de base. Caso contrário, seus modelos não serão executados. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Selecionar período de retrospectiva (2)</b> </p> </td> 
   <td colname="col2"> <p>Define um intervalo de tempo para o modelo. Com base na sua seleção, o algoritmo inclui e avalia dados dos 30, 60 ou 90 dias anteriores. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Selecionar algoritmo (3)</b> </p> </td> 
   <td colname="col2"> <p>No momento, o Construtor de modelos funciona somente com nosso algoritmo de peso <span class="keyword"></span> de característica proprietário. <span class="keyword"> O Audience Manager</span> pode adicionar outras funções algorítmicas em versões subsequentes. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Selecionar Dados do Modelo da Fonte de Dados (4)</b> </p> </td> 
   <td colname="col2"> <p>Permite selecionar as fontes de dados originais e de terceiros que deseja usar no modelo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exclusões (5)</b> </p> </td> 
   <td colname="col2"> <p>É possível excluir características das fontes de dados selecionadas para modelagem. Use a lista <span class="wintitle"> Exclusões</span> e leia os Modelos <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> Algorítmicos: Exclusão</a> de características para saber mais. </p> </td>
  </tr> 
 </tbody>
</table>

Assista ao vídeo abaixo para saber como criar um modelo parecido, para que você possa encontrar mais visitantes que se pareçam com seus conversores.

>[!VIDEO](https://video.tv.adobe.com/v/23504/?captions=por_br)

>[!MORELIKETHIS]
>
>* [Compreensão de TraitWeight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

