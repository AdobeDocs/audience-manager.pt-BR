---
description: Descreve as etapas necessárias e opcionais que permitem criar um modelo algorítmico no Construtor de modelos.
keywords: algo how works
seo-description: Descreve as etapas necessárias e opcionais que permitem criar um modelo algorítmico no Construtor de modelos.
seo-title: Criar um modelo algorítmico
solution: Audience Manager
title: Criar um modelo algorítmico
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: bff108115e7ebd4375d81c1c32ec9bb7d1a207c1
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 1%

---


# Criar um modelo semelhante {#create-an-algorithmic-model}

Descreve as etapas necessárias e opcionais que permitem criar um [!UICONTROL Look-Alike Model].

## Seção do Construtor de modelos

[!UICONTROL Model Builder] consiste nas seções [!UICONTROL Basic Information] e [!UICONTROL Configuration] . Para criar um modelo, preencha os campos obrigatórios nessas duas seções. Salve o modelo para start do algoritmo. [!DNL Audience Manager] envia uma notificação automática após a conclusão da primeira execução de dados. Depois de receber o email, você pode ir para o Construtor de [características](../../features/traits/about-trait-builder.md) e criar traços algorítmicos.

>[!NOTE]
>
>* O processo de modelagem é executado apenas uma vez se você criar um modelo e não criar nenhuma característica com ele.
>* Crie modelos a partir de fontes de dados que contêm uma quantidade significativa de informações. Os modelos com dados insuficientes serão executados, mas não retornarão resultados.
>* *Não* crie modelos com outros traços ou segmentos algorítmicos.
>* A notificação por email automatizada é enviada apenas uma vez (após a primeira execução dos dados).


## Criar o modelo

Siga as etapas abaixo para criar um [!UICONTROL Look-Alike Model]:

1. Vá até **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** e clique **[!UICONTROL Add New]** na [!UICONTROL Look-Alike Modeling] seção.
   ![look-like-add](assets/look-alike-add.png)
1. Na seção Informações [](../../features/algorithmic-models/create-model.md#basic-information) básicas
   * Nomeie o modelo.
   * *(Opcional)* Forneça uma breve descrição sobre o modelo.
   * Defina o status do modelo como **[!UICONTROL Active]** ou **[!UICONTROL Inactive]**. Os modelos inativos não serão executados e não produzirão dados.
      ![sósia-básica](assets/look-alike-basic.png)
1. Na seção [Configuração](../../features/algorithmic-models/create-model.md#configuration) :
   * Clique **[!UICONTROL Browse All Traits]** ou **[!UICONTROL Browse All Segments]** para selecionar uma característica ou segmento para o qual deseja criar um modelo. Procure características por nome, ID, descrição ou fonte de dados. Clique em uma pasta enquanto pesquisa para limitar os resultados a essa pasta e suas subpastas. Você também pode filtrar características por tipo de característica ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded]e [!UICONTROL Algorithmic]) ou tipo de preenchimento (ID[do](../../reference/ids-in-aam.md) dispositivo e ID [de](../../reference/ids-in-aam.md)dispositivo cruzado).
      ![características de navegação](assets/browse-traits.png)
   * Escolha um período de retrospectiva de 30, 60 ou 90 dias. Isso define um intervalo de tempo para o modelo.
   * The [!UICONTROL TraitWeight] algorithm is selected by default.
   * Selecione uma fonte de dados da [!UICONTROL Available Data] lista.
   * Clique **[!UICONTROL Save]** quando concluído.
      ![configuração semelhante](assets/look-alike-configuration.png)

Assista ao vídeo abaixo para ver detalhadamente como as métricas entre dispositivos funcionam.

>[!VIDEO](https://video.tv.adobe.com/v/33445/)

## Informações básicas para modelos algorítmicos {#basic-information}

<!-- r_model_basic.xml -->

Em [!UICONTROL Model Builder], as [!UICONTROL Basic Information] configurações permitem criar modelos novos ou editar modelos existentes. Para criar um novo modelo, forneça um nome e siga para as [!UICONTROL Configuration] configurações. O campo de descrição é opcional.

| Campo | Descrição |
|---|---|
| **[!UICONTROL Name]** | Dê ao seu modelo um nome curto e lógico que descreva sua função ou propósito. Evite abreviações, caracteres especiais e marcas de ênfase. |
| **[!UICONTROL Description]** | Um campo para obter informações descritivas adicionais sobre o modelo. |
| **[!UICONTROL Status]** | Ativa ou desativa o modelo (ativo por padrão). |

## Configuração {#configuration}

Em [!UICONTROL Model Builder], a [!UICONTROL Configuration] seção permite que você adicione características ou segmentos ao modelo. Nesta seção, selecione uma característica ou segmento de linha de base, um período de análise e dados de suas fontes de dados originais e de terceiros.

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
   <td colname="col2"> <p>No momento, o Construtor de modelos funciona apenas com nosso algoritmo de Peso <span class="keyword"></span> de características proprietário. <span class="keyword"> Audience Manager</span> pode adicionar outras funções algorítmicas em versões subsequentes. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Selecionar Dados do Modelo da Fonte de Dados (4)</b> </p> </td> 
   <td colname="col2"> <p>Permite que você selecione as fontes de dados originais e de terceiros que deseja usar no modelo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exclusões (5)</b> </p> </td> 
   <td colname="col2"> <p>É possível excluir características das fontes de dados selecionadas para modelagem. Use a lista de exclusões <span class="wintitle"> e leia os Modelos algorítmicos</span> <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> : Exclusão</a> de características para saber mais. </p> </td>
  </tr> 
 </tbody>
</table>

Assista ao vídeo abaixo para saber como criar um modelo parecido, para que você possa encontrar mais visitantes que se pareçam com seus conversores.

>[!VIDEO](https://video.tv.adobe.com/v/23504/)

>[!MORELIKETHIS]
>
>* [Compreensão de TraitWeight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

