---
description: O relatório de Sobreposição de segmento para a unidade de publicidade é exibido como um gráfico de calor que destaca sobreposições alto e baixo entre os segmentos de Unidades de anúncios e do Audience Manager.
seo-description: O relatório de Sobreposição de segmento para a unidade de publicidade é exibido como um gráfico de calor que destaca sobreposições alto e baixo entre os segmentos de Unidades de anúncios e do Audience Manager.
seo-title: Segmento da sobreposição da unidade de publicidade
solution: Audience Manager
title: Segmento da sobreposição da unidade de publicidade
uuid: aaa 20163-58 aa -42 c 9-8 f 72-a 1 dfb 0 d 20 e 57
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segment to Ad Unit Overlap{#segment-to-ad-unit-overlap}

O relatório de Sobreposição de segmento para a unidade de publicidade é exibido como um gráfico de calor que destaca sobreposições alto e baixo entre os segmentos de Unidades de anúncios e do Audience Manager.

## Caso de uso {#use-cases}

With the [!UICONTROL Segment to Ad Unit Overlap] report, you can understand which audiences visit your web properties. The report displays the overlap between members of your [!DNL Audience Manager] segments and the number of visitors to your web properties. Uma sobreposição maior significa que muitos membros de um segmento visitam sua propriedade da Web.

## Using the Segment to Ad Unit Overlap Report {#using-the-report}

Use the **[!UICONTROL Top N Ad Units]** and **[!UICONTROL Top N Segments]** controls to select your desired number of ad units and segments for the overlap. Você pode selecionar um número máximo de 100 itens para cada um.

Use the **Day Range** and **Date Through** controls to adjust your look-back range. Observe que os períodos de retrospectiva de 7 dias e 30 dias estão disponíveis apenas para datas de domingo.

Use the **[!UICONTROL Segment Name]** and the **[!UICONTROL Ad Unit]** boxes to filter any of segments and ad units.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Ad Unit IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Ad Unit] instead of the [!UICONTROL Ad Unit ID].

## Interpreting the Results {#interpreting-results}

Your [!UICONTROL Segment to Ad Unit Overlap] report could look similar to the one below. Passe o mouse sobre qualquer célula para obter mais informações sobre essa sobreposição específica. Consulte descrições para as informações adicionais na tabela abaixo do relatório de amostra.

![](assets/publisher_segment_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Unidade de publicidade </span> </p> </td> 
   <td colname="col2"> <p>O nome do item de inventário. Por exemplo, pode ser um dos seus sites ou um artigo em seu site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem de únicos de únicos em tempo real</span> </p> </td> 
   <td colname="col2"> <p>The number of unique visitors seen in real-time for the specified time range and who were qualified for the segment at the moment they were seen by <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem de Únicos de Unidade de Publicidade</span> </p> </td> 
   <td colname="col2"> <p>O número de visitantes para esta unidade de anúncio específica. Essas informações são extraídas dos logs DFP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem de únicos de sobreposição</span> </p> </td> 
   <td colname="col2"> <p>Os membros do segmento que foram expostos ao item de unidade de anúncio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Porcentagem de sobreposição</span> </p> </td> 
   <td colname="col2"> <p>A sobreposição entre a unidade de anúncio e as populações de segmentos. This is the <span class="wintitle"> Overlap Uniques Count</span>, expressed as a percentage of the <span class="wintitle"> Segment Real Time Uniques</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

