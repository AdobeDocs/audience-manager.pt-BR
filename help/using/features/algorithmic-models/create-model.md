---
description: Descreve as etapas obrigatórias e opcionais que permitem criar um modelo algorítmico no Construtor de modelos.
keywords: algo how funciona
seo-description: Describes the required and optional steps that let you create an algorithmic model in Model Builder.
seo-title: Create an Algorithmic Model
solution: Audience Manager
title: Criar um modelo algorítmico
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
feature: Algorithmic Models
exl-id: 8b7c4f57-f2c8-46f1-8924-5513fd6ede04
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 0%

---

# Criar um modelo semelhante {#create-an-algorithmic-model}

Descreve as etapas obrigatórias e opcionais que permitem criar um [!UICONTROL Look-Alike Model].

## Seção Construtor de modelos

[!UICONTROL Model Builder] consiste nas seções [!UICONTROL Basic Information] e [!UICONTROL Configuration]. Para criar um modelo, preencha os campos obrigatórios nessas duas seções. Salve seu modelo para iniciar o algoritmo. [!DNL Audience Manager] envia a você uma notificação automática após a conclusão da primeira execução de dados. Após receber o email, você pode acessar o [Construtor de características](../../features/traits/about-trait-builder.md) e criar características algorítmicas.

>[!NOTE]
>
>* O processo de modelagem é executado apenas uma vez se você criar um modelo e não criar características com ele.
>* Crie modelos a partir de fontes de dados que contenham uma quantidade significativa de informações. Serão executados modelos com dados insuficientes, mas eles não retornarão resultados.
>* *Não* crie modelos com outras características ou segmentos algorítmicos.
>* A notificação por email automatizada é enviada apenas uma vez (após a primeira execução de dados).

## Criar o modelo

Siga as etapas abaixo para criar um [!UICONTROL Look-Alike Model]:

1. Vá para **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** e clique em **[!UICONTROL Add New]** na seção [!UICONTROL Look-Alike Modeling].
   ![adicionar-semelhante](assets/look-alike-add.png)
1. Na seção [Informações Básicas](../../features/algorithmic-models/create-model.md#basic-information)
   * Nomeie o modelo.
   * *(Opcional)* Forneça uma breve descrição sobre o modelo.
   * Defina o status do modelo para **[!UICONTROL Active]** ou **[!UICONTROL Inactive]**. Modelos inativos não serão executados e não produzirão dados.
     ![sósia-básica](assets/look-alike-basic.png)
1. Na seção [Configuração](../../features/algorithmic-models/create-model.md#configuration):
   * Clique em **[!UICONTROL Browse All Traits]** ou **[!UICONTROL Browse All Segments]** para selecionar uma característica ou segmento em relação ao qual deseja modelar. Procure características por nome, ID, descrição ou fonte de dados. Clique em uma pasta enquanto pesquisa para limitar os resultados a essa pasta e suas subpastas. Você também pode filtrar características por tipo de característica ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded] e [!UICONTROL Algorithmic]) ou tipo de população ([ID de Dispositivo](../../reference/ids-in-aam.md) e [ID entre Dispositivos](../../reference/ids-in-aam.md)).
     ![características de navegação](assets/browse-traits.png)
   * Escolha um período retroativo de 30, 60 ou 90 dias. Isso define um intervalo de tempo para o modelo.
   * O algoritmo [!UICONTROL TraitWeight] é selecionado por padrão.
   * Selecione uma fonte de dados na lista [!UICONTROL Available Data].
   * Clique em **[!UICONTROL Save]** quando terminar.
     ![configuração semelhante](assets/look-alike-configuration.png)

Assista ao vídeo abaixo para obter uma visão detalhada de como as métricas entre dispositivos funcionam.

>[!VIDEO](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html?lang=pt-BR)

## Informações Básicas para Modelos Algorítmicos {#basic-information}

<!-- r_model_basic.xml -->

No [!UICONTROL Model Builder], as configurações de [!UICONTROL Basic Information] permitem criar modelos novos ou editar modelos existentes. Para criar um novo modelo, forneça um nome e siga para as configurações de [!UICONTROL Configuration]. O campo de descrição é opcional.

| Campo | Descrição |
|---|---|
| **[!UICONTROL Name]** | Dê ao modelo um nome curto e lógico que descreva sua função ou finalidade. Evite abreviações, caracteres especiais e marcas de ênfase. |
| **[!UICONTROL Description]** | Um campo para informações descritivas adicionais sobre o modelo. |
| **[!UICONTROL Status]** | Ativa ou desativa o modelo (ativo por padrão). |

## Configuração {#configuration}

Em [!UICONTROL Model Builder], a seção [!UICONTROL Configuration] permite adicionar características ou segmentos ao modelo. Nesta seção, selecione uma característica ou segmento de linha de base, um período retroativo e dados de suas fontes de dados originais e de terceiros.

<!-- r_model_configuration.xml -->

### Pré-requisitos

Preencha primeiro os campos obrigatórios na seção [!UICONTROL Basic Information].

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
   <td colname="col1"> <p><b>Selecione uma Característica ou um Segmento de Linha de Base (1)</b> </p> </td> 
   <td colname="col2"> <p>Clique no botão de característica ou segmento para ver uma lista de todas as características ou segmentos. O segmento ou característica selecionado se torna a linha de base que os algoritmos do sistema usam para modelagem. </p> <p> <p><b>Observação</b>: selecione uma característica integrada, uma característica com base em regras ou um segmento como linha de base. Caso contrário, seus modelos não serão executados. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Selecionar Período de Retrospectiva (2)</b> </p> </td> 
   <td colname="col2"> <p>Define um intervalo de tempo para o modelo. Com base em sua seleção, o algoritmo inclui e avalia dados dos últimos 30, 60 ou 90 dias. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Selecionar algoritmo (3)</b> </p> </td> 
   <td colname="col2"> <p>No momento, o Construtor de Modelos funciona somente com nosso algoritmo <span class="keyword"> de Peso da Característica</span> proprietário. <span class="keyword"> O Audience Manager</span> pode adicionar outras funções algorítmicas em versões subsequentes. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Selecionar Dados de Modelo do Data Source (4)</b> </p> </td> 
   <td colname="col2"> <p>Permite selecionar a fonte de dados própria e de terceiros que você deseja usar no modelo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exclusões (5)</b> </p> </td> 
   <td colname="col2"> <p>É possível excluir características das fontes de dados selecionadas para modelagem. Use a lista <span class="wintitle"> Exclusões</span> e leia <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> Modelos Algorítmicos: Exclusão de Característica</a> para saber mais. </p> </td>
  </tr> 
 </tbody>
</table>

Assista ao vídeo abaixo para saber como criar um modelo semelhante próprio, para que você possa encontrar mais de seus próprios visitantes que se parecem com seus conversores.

>[!VIDEO](https://video.tv.adobe.com/v/23504/)

>[!MORELIKETHIS]
>
>* [Noções básicas sobre TraitWeight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)
