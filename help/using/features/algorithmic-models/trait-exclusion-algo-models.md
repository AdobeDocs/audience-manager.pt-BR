---
description: A Exclusão de característica fornece controles adicionais no fluxo de trabalho de modelagem, permitindo que você adicione os trilhos de proteção necessários ao modelo, com base em sua especialização de domínio e requisitos regulamentares. Use a opção Exclusões para selecionar quais características ignorar ao criar modelos a partir de uma ou mais fontes de dados.
seo-description: A Exclusão de característica fornece controles adicionais no fluxo de trabalho de modelagem, permitindo que você adicione os trilhos de proteção necessários ao modelo, com base em sua especialização de domínio e requisitos regulamentares. Use a opção Exclusões para selecionar quais características ignorar ao criar modelos a partir de uma ou mais fontes de dados.
seo-title: Exclusão de perfis algorítmicos
title: Exclusão de perfis algorítmicos
uuid: 1359800 b -6 e 6 c -41 e 1-88 b 4-23 d 31952 abb 3
translation-type: tm+mt
source-git-commit: f324838a5649722545ff36faba92bf3a13c2e805

---


# Algorithmic Models: Trait Exclusion {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] fornece controles adicionais no fluxo de trabalho de modelagem, permitindo que você adicione os trilhos de proteção necessários ao modelo, com base em sua especialização de domínio e requisitos regulamentares. Use the [!UICONTROL Exclusions] option to select which traits to ignore when creating models from one or more data sources.

## Casos de uso {#use-cases}

Here are some use cases you can address with [!UICONTROL Trait Exclusion]:

* [!UICONTROL Trait Exclusion] permite excluir determinadas características catch-all, como características do visitante do site, para que você não prejudique o modelo, resultando em resultados simples.
* Você pode remover características que não conhecem ou não confiar em uma fonte de dados para compreender melhor as características influentes.
* É possível excluir determinados traços, como traços demográficos, para ajudar a cumprir quaisquer obrigações de conformidade que você tenha.

>[!IMPORTANT]
>
>Uma observação importante sobre o terceiro caso de uso. If the third-party data provider adds a new demographic trait to the data feed *after you created the model*, the trait is automatically picked up by the model. Não é possível excluir características da modelagem depois de criar o modelo. See [Important Aspects &amp; Limitations](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). Tenha cuidado ao usar este recurso e trabalhar com o provedor de dados para garantir que você esteja informado de quaisquer alterações na estrutura do feed.

![](assets/lam_exclude_traits.png)

## How to Use Trait Exclusions {#how-to-use}

Use the [Build a model](../../features/algorithmic-models/create-model.md#build-model) workflow to build new algorithmic models.

1. The [!UICONTROL Exclusions] selection is greyed out until you select one or more data sources for modeling.
2. After selecting one or more data sources for modeling, press **[!UICONTROL Browse All Traits]**.
3. In the **[!UICONTROL Select Traits to Exclude]** window, you can see all traits associated with the data sources you selected previously. Selecione as características que deseja excluir.
4. É possível filtrar as características por tipo de característica ou navegar pelas pastas de características. Observe que as pastas de características só exibem as características associadas às suas fontes de dados selecionadas.
5. Press **[!UICONTROL Exclude Selected Traits]**.

>[!TIP]
>
>É possível excluir pastas inteiras excluindo a característica da pasta em vez de excluir as características da pasta, uma por uma. Por exemplo, em uma pasta com 20 características, é necessário excluir apenas a pasta em vez de excluir todas as características um por um.

Se preferir tutoriais em vídeo, assista a nossa demonstração em vídeo para Exclusão de característica:

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12&captions=por_br)

## Important Aspects &amp; Limitations {#important-aspects-and-limitations}

Please take note of the following aspects and limitations related to [!UICONTROL Trait Exclusion]:

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Descrição </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Características excluídas na exibição de resumo de modelos </p> </td>
   <td colname="col2"> <p>The excluded traits <i>do not show up</i> in the Models Summary view. You can see the excluded traits only in the <b><span class="uicontrol"> Edit Model</span></b> workflow. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Controle de acesso com base em funções (RBAC) </p> </td>
   <td colname="col2"> <p>Note the following limitations for companies using <a href="../../features/administration/administration-overview.md#administration"> RBAC</a>: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">If you don't have access to view a trait, you <i>cannot</i> select that trait to be excluded from the model. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">If you don't have access to view a trait, you <i>cannot</i> view that trait in the excluded traits list. </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modificar características excluídas após salvar modelo </p> </td>
   <td colname="col2"> <p>Não é possível modificar as características excluídas após criar e salvar um modelo. Se você quiser ajustar os resultados, poderá clonar o modelo e alterar as características excluídas. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Número máximo de características que podem ser excluídas </p> </td>
   <td colname="col2"> <p>O número máximo de características que podem ser excluídas de um modelo é 500. Use características de pastas para maximizar suas exclusões. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Excluir característica de linha de base </p> </td>
   <td colname="col2"> <p>The baseline trait is excluded by default, so it does not show up in the <b><span class="uicontrol"> Exclusions</span></b> list, when building the model. </p> </td>
  </tr>
 </tbody>
</table>

## Links relacionados

* [Sobre as características algorítmicas](/help/using/features/algorithmic-models/understanding-models.md)
* [Exclusão de característica - Tutorial](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)