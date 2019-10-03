---
description: A Exclusão de características fornece controles adicionais no fluxo de trabalho de modelagem, permitindo que você adicione os trilhos de proteção necessários ao modelo, com base na sua experiência em domínio e nos requisitos normativos. Use a opção Exclusões para selecionar quais características devem ser ignoradas ao criar modelos de uma ou mais fontes de dados.
seo-description: A Exclusão de características fornece controles adicionais no fluxo de trabalho de modelagem, permitindo que você adicione os trilhos de proteção necessários ao modelo, com base na sua experiência em domínio e nos requisitos normativos. Use a opção Exclusões para selecionar quais características devem ser ignoradas ao criar modelos de uma ou mais fontes de dados.
seo-title: Exclusão de Características de Modelos Algorítmicos
title: Exclusão de Características de Modelos Algorítmicos
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
translation-type: tm+mt
source-git-commit: 0eb6a6f67d87377a044b18118fac0185219b0347

---


# Modelos algorítmicos: Exclusão de características {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] fornece controles adicionais no fluxo de trabalho de modelagem, permitindo que você adicione os trilhos de proteção necessários ao modelo, com base na sua experiência em domínio e nos requisitos normativos. Use a [!UICONTROL Exclusions] opção para selecionar quais características devem ser ignoradas ao criar modelos de uma ou mais fontes de dados.

## Casos de uso {#use-cases}

Estes são alguns casos de uso que você pode abordar com [!UICONTROL Trait Exclusion]:

* [!UICONTROL Trait Exclusion] permite que você exclua certas características capturadas, como características do visitante do site, para que você não influencie o modelo, resultando em resultados simples.
* Você pode remover características que você não conhece ou não confia em uma fonte de dados, para entender melhor as características influentes.
* Você pode excluir certas características, como características demográficas, para ajudar com quaisquer obrigações de conformidade que você possa ter.

>[!IMPORTANT]
>
>Uma observação importante sobre o terceiro caso de uso. Se o provedor de dados de terceiros adicionar uma nova característica demográfica ao feed de dados *depois que você criou o modelo*, a característica será automaticamente selecionada pelo modelo. Não é possível excluir características da modelagem após a criação do modelo. Consulte Aspectos [importantes e limitações](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). Tenha cuidado ao usar esse recurso e trabalhe com o provedor de dados para garantir que você seja informado de quaisquer alterações na estrutura do feed.

![](assets/lam_exclude_traits.png)

## Como usar exclusões de características {#how-to-use}

Use o fluxo de trabalho [Criar um modelo](../../features/algorithmic-models/create-model.md#build-model) para criar novos modelos algorítmicos.

1. A [!UICONTROL Exclusions] seleção fica acinzentada até que você selecione uma ou mais fontes de dados para modelagem.
2. Depois de selecionar uma ou mais fontes de dados para modelagem, pressione **[!UICONTROL Browse All Traits]**.
3. Na **[!UICONTROL Select Traits to Exclude]** janela, você pode ver todas as características associadas às fontes de dados selecionadas anteriormente. Selecione as características que deseja excluir.
4. Você pode filtrar as características por tipo de característica ou pode navegar pelas pastas de características. Observe que as pastas de características exibem apenas as características associadas às fontes de dados selecionadas.
5. Press **[!UICONTROL Exclude Selected Traits]**.

>[!TIP]
>
>É possível excluir pastas inteiras excluindo a característica da pasta em vez de excluir as características na pasta, uma por uma. Por exemplo, em uma pasta com 20 características, seria necessário excluir apenas a característica da pasta em vez de excluir todas as características uma por uma.

Se preferir tutoriais em vídeo, assista a nossa demonstração em vídeo para obter a Exclusão de características:

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12&captions=por_br)

## Aspectos e limitações importantes {#important-aspects-and-limitations}

Tomar nota dos seguintes aspectos e limitações relacionados com [!UICONTROL Trait Exclusion]:

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Descrição </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Características excluídas na exibição Resumo de modelos </p> </td>
   <td colname="col2"> <p>As características excluídas <i>não são exibidas</i> na exibição Resumo de modelos. Você pode ver as características excluídas somente no fluxo de trabalho <b><span class="uicontrol"> Editar modelo</span></b> . </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>RBAC (Role-Based Access Controls) </p> </td>
   <td colname="col2"> <p>Observe as seguintes limitações para empresas que usam <a href="../../features/administration/administration-overview.md#administration"> RBAC</a>: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">Se você não tiver acesso para visualizar uma característica, <i>não poderá</i> selecioná-la para ser excluída do modelo. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">Se você não tiver acesso para exibir uma característica, <i>não poderá</i> visualizá-la na lista de características excluídas. </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modificar características excluídas após salvar o modelo </p> </td>
   <td colname="col2"> <p>Não é possível modificar as características excluídas depois de criar e salvar um modelo. Se quiser ajustar os resultados, você pode clonar o modelo e alterar as características excluídas. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Número máximo de características que podem ser excluídas </p> </td>
   <td colname="col2"> <p>O número máximo de características que podem ser excluídas de um modelo é 500. Use as características da pasta para maximizar suas exclusões. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Excluir característica da linha de base </p> </td>
   <td colname="col2"> <p>A característica da linha de base é excluída por padrão, portanto, não aparece na lista <b><span class="uicontrol"> Exclusões</span></b> ao criar o modelo. </p> </td>
  </tr>
 </tbody>
</table>

Assista ao vídeo abaixo para saber como e por que excluir características específicas de um [!UICONTROL Look-Alike Model].

[!VIDEO](https://video.tv.adobe.com/v/25569/?captions=por_br)

## Links relacionados

* [Sobre características algorítmicas](/help/using/features/algorithmic-models/understanding-models.md)
* [Exclusão de características - Tutorial](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)