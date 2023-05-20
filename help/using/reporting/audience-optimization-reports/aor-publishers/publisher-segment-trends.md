---
description: O relatório Tendência de segmento retorna dados sobre impressões e taxas de click-through de segmentos mapeados e não mapeados ao longo do tempo. Um segmento mapeado é um segmento que você cria e envia para um destino para direcionamento. Um segmento não mapeado é um segmento que você criou, mas que não enviou a um destino para direcionamento. Compare as tendências e o volume das métricas selecionadas para obter uma imagem melhor de como seus públicos-alvo se comportam ao longo do tempo.
seo-description: The Segment Trend report returns data on impressions and click-through rates of mapped and unmapped segments over time. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Compare trends and volume for your selected metrics to get a better picture of how your audiences behave over time.
seo-title: Segment Trend Report
solution: Audience Manager
title: Relatório de tendência do segmento
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: Audience Optimization Reports
exl-id: 1fdca05a-b661-4875-88d7-b0893e2ca08f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 2%

---

# Relatório de tendência do segmento{#segment-trend-report}

O relatório Tendência de segmento retorna dados sobre impressões e taxas de click-through de segmentos mapeados e não mapeados ao longo do tempo.

Um segmento mapeado é um segmento que você cria e envia para um destino para direcionamento. Um segmento não mapeado é um segmento que você criou, mas que não enviou a um destino para direcionamento.

Compare as tendências e o volume das métricas selecionadas para obter uma imagem melhor de como seus públicos-alvo se comportam ao longo do tempo.

## Caso de uso {#use-cases}

Use o [!UICONTROL Segment Trend] relatório para validar o desempenho de um segmento ao longo do tempo e apontar tendências com base no desempenho ou na escala forte.

Com esse relatório, você pode entender quais de suas propriedades da Web mostram um aumento decrescente ou com falha e solucionar problemas, conforme necessário. Este relatório é a próxima etapa depois de identificar o público-alvo de interesse na [!UICONTROL Segment Performance] relatório, para garantir que o desempenho forte ou ruim que você viu no [!UICONTROL Segment Performance] é consistente ao longo do tempo.

## Uso do Relatório de Tendência de Segmento {#using-the-report}

Alternar entre **[!UICONTROL Mapped]** e **[!UICONTROL Unmapped]** para selecionar segmentos mapeados para um destino ou não. Selecionar **[!UICONTROL All]** para incluir todos os segmentos no relatório.

Ajuste a janela retrospectiva com a **[!UICONTROL Date Through]** controle deslizante.

Clique em qualquer um dos segmentos na **[!UICONTROL Date Through]** controle deslizante para ativar a opção para manter somente esse segmento no relatório ou excluí-lo.

Use o **[!UICONTROL Line Item]** para selecionar as propriedades no portfólio para as quais deseja retornar informações.

No **[!UICONTROL Segment Data Source]** selecione as fontes de dados que contêm os segmentos que você deseja ver no relatório.

Use o **[!UICONTROL Segment]** para selecionar quais segmentos você deseja ver no relatório.

>[!IMPORTANT]
>
>Ao ativar [!UICONTROL Audience Optimization for Publishers], você deve incluir metadados descritivos para [!UICONTROL Line Item] IDs, conforme descrito na Etapa 3 do [Importação de arquivos de dados do Google Ad Manager (antigo DFP) para o Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Ao fazer isso, você garante que o relatório detalhe a propriedade da Web como [!UICONTROL Line Item] em vez de [!UICONTROL Line Item] ID.

## Interpretação dos resultados {#interpreting-results}

A variável [!UICONTROL Segment Trend] O relatório retorna dados em um gráfico de linhas somente para um intervalo de 14 dias. Neste exemplo, o relatório mostra tendências de impressão e click-through para um conjunto de segmentos mapeados e não mapeados.

Passe o mouse sobre qualquer linha para obter mais informações sobre essa tendência de segmento específica. Consulte as descrições para obter as informações adicionais na tabela abaixo do relatório de amostra.

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
   <td colname="col2"> <p>O nome alfanumérico que você atribuiu a este segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ID do segmento</span> </p> </td> 
   <td colname="col2"> <p>O identificador exclusivo deste segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Item da linha</span> </p> </td> 
   <td colname="col2"> <p>A propriedade da Web para a qual você está vendo este relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Cliques</span> </p> </td> 
   <td colname="col2"> <p>O número de vezes que os membros dessa característica clicaram em itens em sua propriedade da Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressões</span> </p> </td> 
   <td colname="col2"> <p>O número de vezes que os membros desta característica foram expostos ao inventário. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>Índice de click-through. Essa métrica retransmite a porcentagem de impressões seguida de cliques. Divida os cliques por impressões para obter essa métrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Únicos do segmento</span> </p> </td> 
   <td colname="col2"> <p>O número de membros do segmento nos últimos 30 dias. </p> </td> 
  </tr> 
 </tbody> 
</table>
