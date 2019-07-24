---
description: O relatório de Desempenho do segmento compara segmentos mapeados e não mapeados por impressões e Únicos de segmentos em tempo real. Um segmento mapeado é um segmento criado e enviado para um destino para definição de metas. Um segmento não mapeado é um segmento criado, mas que não foi enviado para um destino de definição de metas. Comparar esses tipos de segmento diferentes dentro e entre relatórios ajuda você a otimizar campanhas existentes e encontrar segmentos ignorados que talvez você queira enviar para um destino de definição de metas.
seo-description: O relatório de Desempenho do segmento compara segmentos mapeados e não mapeados por impressões e Únicos de segmentos em tempo real. Um segmento mapeado é um segmento criado e enviado para um destino para definição de metas. Um segmento não mapeado é um segmento criado, mas que não foi enviado para um destino de definição de metas. Comparar esses tipos de segmento diferentes dentro e entre relatórios ajuda você a otimizar campanhas existentes e encontrar segmentos ignorados que talvez você queira enviar para um destino de definição de metas.
seo-title: Relatório de desempenho do segmento
solution: Audience Manager
title: Relatório de desempenho do segmento
uuid: c 9 a 1 e 9 ad -4 f 3 f -4334-a 3 ff -0 f 241 c 7303 c 4
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segment Performance Report{#segment-performance-report}

O relatório de Desempenho do segmento compara segmentos mapeados e não mapeados por impressões e Únicos de segmentos em tempo real.

Um segmento mapeado é um segmento criado e enviado para um destino para definição de metas. Um segmento não mapeado é um segmento criado, mas que não foi enviado para um destino de definição de metas.

Comparar esses tipos de segmento diferentes dentro e entre relatórios ajuda você a otimizar campanhas existentes e encontrar segmentos ignorados que talvez você queira enviar para um destino de definição de metas.

## Casos de uso {#use-cases}

With the [!UICONTROL Segment Performance] report, you can:

* Identifique segmentos de público mapeados que estão impulsionando a escala ou o desempenho.
* Identifique segmentos não mapeados a serem introduzidos em campanhas futuras, com base na contribuição de um público-alvo para o desempenho passado.

## Using the Segment Performance Report {#using-segment-performance-report}

Toggle between **[!UICONTROL Mapped]** and **[!UICONTROL Unmapped]** to select segments that are mapped to a destination or not. Select **[!UICONTROL All]** to include all your segments in the report.

Use the **Day Range** and **Date Through** controls to adjust your look-back range. Observe que os períodos de retrospectiva de 7 dias e 30 dias estão disponíveis apenas para datas de domingo.

Use the **[!UICONTROL Line Item]** drop-down box to select the web properties for which you want to return information.

In the **[!UICONTROL Segment Data Source]** drop-down box, select the data sources containing the segments you want to see in the report.

Use the **[!UICONTROL Segment]** drop-down box to select which segments you want to see in the report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Line Item IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Line Item] instead of the [!UICONTROL Line Item ID].

## Interpreting the Results {#interpreting-results}

Your [!UICONTROL Segment Performance] report could look similar to the one below. Em seu relatório, clique em uma bolha para exibir os dados subjacentes. Consulte descrições para as informações adicionais na tabela abaixo do relatório de amostra.

![](assets/publisher_segment_performance.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Segmento </p> </td> 
   <td colname="col2"> <p>O nome alfanumérico atribuído a esse segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID do segmento </p> </td> 
   <td colname="col2"> <p>A ID exclusiva desse segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Item de linha </p> </td> 
   <td colname="col2"> <p>A propriedade da Web para a qual você está vendo este relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cliques </p> </td> 
   <td colname="col2"> <p>O número de vezes que os membros desta característica clicaram em itens na propriedade da Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Impressões </p> </td> 
   <td colname="col2"> <p>O número de vezes que os membros desta característica foram expostos ao inventário. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>Índice de click-through. </p> <p>Essa métrica recarrega a porcentagem de impressões seguidas por cliques. Dividir cliques por impressões para obter essa métrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Preenchimento de segmentos em tempo real </p> </td> 
   <td colname="col2"> <p>The actual number of unique visitors seen in real-time for the specified time range and who were qualified for the segment at the moment they were seen by <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## How to Read Your Mapped Segment Results {#read-mapped-segment}

A posição de seus segmentos mapeados em um relatório pode informar muito sobre quais segmentos estão bem sendo executados e onde pode ser necessário fazer alguns ajustes.

Para ler o relatório, ele ajuda a dividir os resultados em quatro seções com linhas imaginárias (em vermelho) e as categorias mostradas no relatório de amostra abaixo. Os rótulos no exemplo podem ajudar você a entender o desempenho do segmento e a responder a esses resultados.

![](assets/publisher_segment_performance_mapped.png)

## How to Read Your Unmapped Segment Results {#read-unmapped-segment}

Looking at unmapped segments in a [!UICONTROL Segment Performance] report is a great way to find new segments you haven't considered for targeting. Na verdade, alguns desses segmentos podem ignorar seus segmentos mapeados.

Para ler este relatório, ele ajuda a dividir os resultados em quatro seções com linhas imaginárias (em vermelho) e categorias mostradas no relatório de amostra abaixo.

![](assets/publisher_segment_performance_unmapped.png)
