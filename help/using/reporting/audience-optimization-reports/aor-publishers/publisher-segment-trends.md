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
source-wordcount: '537'
ht-degree: 0%

---

# Relatório de tendência do segmento{#segment-trend-report}

O relatório Tendência de segmento retorna dados sobre impressões e taxas de click-through de segmentos mapeados e não mapeados ao longo do tempo.

Um segmento mapeado é um segmento que você cria e envia para um destino para direcionamento. Um segmento não mapeado é um segmento que você criou, mas que não enviou a um destino para direcionamento.

Compare as tendências e o volume das métricas selecionadas para obter uma imagem melhor de como seus públicos-alvo se comportam ao longo do tempo.

## Caso de uso {#use-cases}

Use o relatório [!UICONTROL Segment Trend] para validar o desempenho de um segmento ao longo do tempo e apontar tendências com base no desempenho ou na escala forte.

Com esse relatório, você pode entender quais de suas propriedades da Web mostram um aumento decrescente ou com falha e solucionar problemas, conforme necessário. Este relatório é a próxima etapa depois de identificar o público-alvo de interesse no relatório [!UICONTROL Segment Performance], para garantir que o desempenho forte ou ruim observado na guia [!UICONTROL Segment Performance] seja consistente ao longo do tempo.

## Uso do Relatório de Tendência de Segmento {#using-the-report}

Alterne entre **[!UICONTROL Mapped]** e **[!UICONTROL Unmapped]** para selecionar segmentos que estão mapeados para um destino ou não. Selecione **[!UICONTROL All]** para incluir todos os seus segmentos no relatório.

Ajuste a janela retrospectiva com o controle deslizante **[!UICONTROL Date Through]**.

Clique em qualquer um dos segmentos abaixo do controle deslizante **[!UICONTROL Date Through]** para exibir a opção para manter somente esse segmento no relatório ou excluí-lo.

Use a caixa suspensa **[!UICONTROL Line Item]** para selecionar as propriedades no portfólio para as quais deseja retornar informações.

Na caixa suspensa **[!UICONTROL Segment Data Source]**, selecione as fontes de dados que contêm os segmentos que você deseja ver no relatório.

Use a caixa suspensa **[!UICONTROL Segment]** para selecionar quais segmentos você deseja ver no relatório.

>[!IMPORTANT]
>
>Ao habilitar [!UICONTROL Audience Optimization for Publishers], você deve incluir metadados descritivos para [!UICONTROL Line Item] IDs, conforme descrito na Etapa 3 de [Importar arquivos de dados do Google Ad Manager (antigo DFP) para o Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Ao fazer isso, você garante que o relatório detalhe a propriedade da Web como [!UICONTROL Line Item] em vez da ID [!UICONTROL Line Item].

## Interpretação dos resultados {#interpreting-results}

O relatório [!UICONTROL Segment Trend] retorna dados em um gráfico de linhas somente para um intervalo de 14 dias. Neste exemplo, o relatório mostra tendências de impressão e click-through para um conjunto de segmentos mapeados e não mapeados.

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
   <td colname="col1"> <p><span class="wintitle"> Item de linha</span> </p> </td> 
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
   <td colname="col2"> <p>Taxa de cliques. Essa métrica retransmite a porcentagem de impressões seguida de cliques. Divida os cliques por impressões para obter essa métrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segmentos únicos</span> </p> </td> 
   <td colname="col2"> <p>O número de membros do segmento nos últimos 30 dias. </p> </td> 
  </tr> 
 </tbody> 
</table>
