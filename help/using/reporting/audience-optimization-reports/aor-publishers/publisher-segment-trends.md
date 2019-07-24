---
description: O relatório de Tendência do segmento retorna dados sobre impressões e taxas de click-through de segmentos mapeados e não mapeados ao longo do tempo. Um segmento mapeado é um segmento criado e enviado para um destino para definição de metas. Um segmento não mapeado é um segmento criado, mas que não foi enviado para um destino de definição de metas. Compare as tendências e o volume das métricas selecionadas para obter uma imagem melhor de como seus públicos se comportam ao longo do tempo.
seo-description: O relatório de Tendência do segmento retorna dados sobre impressões e taxas de click-through de segmentos mapeados e não mapeados ao longo do tempo. Um segmento mapeado é um segmento criado e enviado para um destino para definição de metas. Um segmento não mapeado é um segmento criado, mas que não foi enviado para um destino de definição de metas. Compare as tendências e o volume das métricas selecionadas para obter uma imagem melhor de como seus públicos se comportam ao longo do tempo.
seo-title: Relatório de tendência do segmento
solution: Audience Manager
title: Relatório de tendência do segmento
uuid: f 84 e 8 d 0 a -74 e 5-430 c-b 61 c-efb 696 faee 93
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segment Trend Report{#segment-trend-report}

O relatório de Tendência do segmento retorna dados sobre impressões e taxas de click-through de segmentos mapeados e não mapeados ao longo do tempo.

Um segmento mapeado é um segmento criado e enviado para um destino para definição de metas. Um segmento não mapeado é um segmento criado, mas que não foi enviado para um destino de definição de metas.

Compare as tendências e o volume das métricas selecionadas para obter uma imagem melhor de como seus públicos se comportam ao longo do tempo.

## Caso de uso {#use-cases}

Use the [!UICONTROL Segment Trend] report to validate a segment's performance over time and to pinpoint trends based on strong performance or scale.

Com este relatório, você pode entender qual das propriedades da Web mostrar um declínio ou um defeito de defeito e solucionar problemas conforme necessário. This report is the next step after you identify your audience of interest in the [!UICONTROL Segment Performance] report, to ensure that the strong or poor performance you saw in the [!UICONTROL Segment Performance] tab is consistent over time.

## Using the Segment Trend Report {#using-the-report}

Toggle between **[!UICONTROL Mapped]** and **[!UICONTROL Unmapped]** to select segments that are mapped to a destination or not. Select **[!UICONTROL All]** to include all your segments in the report.

Adjust the look-back window with the **[!UICONTROL Date Through]** slider.

Click any of the segments under the **[!UICONTROL Date Through]** slider to bring up the option to keep only that segment in the report or exclude it.

Use the **[!UICONTROL Line Item]** drop-down box to select the properties in your portfolio for which you want to return information.

In the **[!UICONTROL Segment Data Source]** drop-down box, select the data sources containing the segments you want to see in the report.

Use the **[!UICONTROL Segment]** drop-down box to select which segments you want to see in the report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Line Item] IDs, as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Line Item] instead of the [!UICONTROL Line Item] ID.

## Interpreting the Results {#interpreting-results}

The [!UICONTROL Segment Trend] report returns data in a line graph for a 14-day interval only. Neste exemplo, o relatório mostra as tendências de impressão e click-through para um conjunto de segmentos mapeados e não mapeados.

Passe o mouse sobre qualquer linha para obter mais informações sobre essa tendência de segmento específica. Consulte descrições para as informações adicionais na tabela abaixo do relatório de amostra.

![](assets/publisher_segment_trend.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segmento</span> </p> </td> 
   <td colname="col2"> <p>O nome alfanumérico atribuído a esse segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ID do segmento</span> </p> </td> 
   <td colname="col2"> <p>A ID exclusiva desse segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Item de linha</span> </p> </td> 
   <td colname="col2"> <p>A propriedade da Web para a qual você está vendo este relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Cliques</span> </p> </td> 
   <td colname="col2"> <p>O número de vezes que os membros desta característica clicaram em itens na propriedade da Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressões</span> </p> </td> 
   <td colname="col2"> <p>O número de vezes que os membros desta característica foram expostos ao inventário. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>Índice de click-through. Essa métrica recarrega a porcentagem de impressões seguidas por cliques. Dividir cliques por impressões para obter essa métrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Únicos de segmento</span> </p> </td> 
   <td colname="col2"> <p>O número de membros do segmento, nos últimos 30 dias. </p> </td> 
  </tr> 
 </tbody> 
</table>
