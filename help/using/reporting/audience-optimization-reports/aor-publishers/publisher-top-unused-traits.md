---
description: As Características principais não usadas são representadas como um diagrama de dispersão de características que ainda não são membros de um segmento, com base no tipo de característica, fonte de dados e desempenho.
seo-description: As Características principais não usadas são representadas como um diagrama de dispersão de características que ainda não são membros de um segmento, com base no tipo de característica, fonte de dados e desempenho.
seo-title: Principais características não usadas
solution: Audience Manager
title: Principais características não usadas
uuid: 90 bcd 333-41 b 8-416 e-aa 4 e-a 8661891 df 50
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Top Unused Traits{#top-unused-traits}

As Características principais não usadas são representadas como um diagrama de dispersão de características que ainda não são membros de um segmento, com base no tipo de característica, fonte de dados e desempenho.

## Caso de uso {#use-cases}

With the [!UICONTROL Top Unused Traits] report, you can analyze and compare the performance of first and third party traits that are currently not mapped to a segment. Essa exibição pode apontar as melhores características para usar em um segmento de público-alvo para otimização de campanhas ou novas oportunidades líquidas.

## Using the Top Unused Traits Report {#using-the-report}

Use the **[!UICONTROL Data Provider Type]** controls to toggle between first party and third party traits. Select **[!UICONTROL All]** to return first and third party traits in the report.

With the **[!UICONTROL Impressions]** slider, you can select a minimum and maximum value for returned impressions. Qualquer característica responsável por menos ou mais do que os limites definidos não é exibida no relatório.

Use the **[!UICONTROL Day Range]** and **[!UICONTROL Date Through]** controls to adjust your look-back range. Observe que apenas o período de retrospectiva de 30 dias está disponível para este relatório.

Use the **[!UICONTROL Order]** drop-down box to select the web properties in your portfolio for which you want to return information.

In the **[!UICONTROL Data Provider]** drop-down box, select the data sources containing the traits you want to see in the report.

Use the **[!UICONTROL Traits]** drop-down box to select which traits you want to see in the report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Order IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Order] instead of the [!UICONTROL Order ID].

## Interpreting the Results {#interpreting-results}

**Relatório de exemplo**

Your [!UICONTROL Top Unused Traits] report could look similar to the one below. Em seu relatório, clique em uma bolha para exibir os dados subjacentes.

Consulte descrições para as informações adicionais na tabela abaixo do relatório de amostra.

![](assets/publisher_unused_traits.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Tipo de provedor de dados</span> </p> </td> 
   <td colname="col2"> <p>Especifica se a fonte de dados selecionada contém características originais ou de terceiros. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ID de característica</span> </p> </td> 
   <td colname="col2"> <p>A ID exclusiva dessa característica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nome da característica</span> </p> </td> 
   <td colname="col2"> <p>O nome alfanumérico que você ou o provedor de dados atribuído a essa característica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Pedido</span> </p> </td> 
   <td colname="col2"> <p>A propriedade da Web para a qual você está vendo este relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressões</span> </p> </td> 
   <td colname="col2"> <p>O número de vezes que os membros desta característica foram expostos ao inventário. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Únicos de característica</span> </p> </td> 
   <td colname="col2"> <p>O número de membros de características, nos últimos 30 dias. </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

A posição de suas características em um relatório pode informar muito sobre quais características você pode usar para otimizar os segmentos existentes do público-alvo.

As características localizadas no eixo de Impressões são aquelas que você deseja usar em suas campanhas. Para características com um número baixo de impressões, é pouco provável que você esteja acessando esse público na propriedade da Web, com base nos dados do DFP.

Look to the left of the [!UICONTROL Unique Trait Realizations] axis for highly accurate traits and to the right for traits that can drive scale.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Posição </th> 
   <th colname="col2" class="entry"> Posicionamento Indica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Parte superior esquerda</b> </p> </td> 
   <td colname="col2"> <p>Número alto de impressões, número baixo de realizações de características. </p> <p>Este é um público altamente preciso que ainda não é membro de um segmento. Considere o direcionamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Inferior esquerdo</b> </p> </td> 
   <td colname="col2"> <p>Número baixo de impressões, número baixo de realizações de características. </p> <p> Exclua essas características, pois os membros não estão contribuindo para impressões nas suas propriedades da Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Parte superior direita</b> </p> </td> 
   <td colname="col2"> <p>Número alto de impressões, maior número de realizações de características. </p> <p>Um alcance alto em relação a um público que ainda não é denotado em um segmento. Esse público é um candidato importante para a definição de metas devido ao alto número de impressões e a escala. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Inferior direito</b> </p> </td> 
   <td colname="col2"> <p>Número baixo de impressões, maior número de realizações de características. </p> <p> Você pode excluir essas características, já que os membros não estão contribuindo para impressões nas suas propriedades da Web. </p> </td> 
  </tr> 
 </tbody> 
</table>
