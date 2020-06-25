---
description: O relatório de Tendência do segmento retorna dados sobre impressões e taxas de cliques de segmentos mapeados e não mapeados ao longo do tempo. Um segmento mapeado é um segmento criado e enviado para um destino para definição de metas. Um segmento não mapeado é um segmento criado, mas não enviado para um destino para definição de metas. Compare as tendências e o volume de suas métricas selecionadas para obter uma ideia melhor de como suas audiências se comportam ao longo do tempo.
seo-description: O relatório de Tendência do segmento retorna dados sobre impressões e taxas de cliques de segmentos mapeados e não mapeados ao longo do tempo. Um segmento mapeado é um segmento criado e enviado para um destino para definição de metas. Um segmento não mapeado é um segmento criado, mas não enviado para um destino para definição de metas. Compare as tendências e o volume de suas métricas selecionadas para obter uma ideia melhor de como suas audiências se comportam ao longo do tempo.
seo-title: Relatório de tendência do segmento
solution: Audience Manager
title: Relatório de tendência do segmento
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 1%

---


# Relatório de tendência do segmento{#segment-trend-report}

O relatório de Tendência do segmento retorna dados sobre impressões e taxas de cliques de segmentos mapeados e não mapeados ao longo do tempo.

Um segmento mapeado é um segmento criado e enviado para um destino para definição de metas. Um segmento não mapeado é um segmento criado, mas não enviado para um destino para definição de metas.

Compare as tendências e o volume de suas métricas selecionadas para obter uma ideia melhor de como suas audiências se comportam ao longo do tempo.

## Caso de uso {#use-cases}

Use o [!UICONTROL Segment Trend] relatório para validar o desempenho de um segmento ao longo do tempo e para identificar as tendências com base no alto desempenho ou na escala.

Com esse relatório, você pode entender quais de suas propriedades da Web mostram um aumento ou falha e solucionar problemas, conforme necessário. Este relatório é o próximo passo após identificar sua audiência de interesse no [!UICONTROL Segment Performance] [!UICONTROL Segment Performance] relatório, para garantir que o desempenho forte ou ruim que você viu na guia seja consistente ao longo do tempo.

## Usando o relatório de tendência do segmento {#using-the-report}

Alterne entre **[!UICONTROL Mapped]** e **[!UICONTROL Unmapped]** para selecionar segmentos que estão mapeados para um destino ou não. Selecione **[!UICONTROL All]** para incluir todos os seus segmentos no relatório.

Ajuste a janela de olhar para trás com o **[!UICONTROL Date Through]** controle deslizante.

Clique em qualquer um dos segmentos sob o **[!UICONTROL Date Through]** controle deslizante para exibir a opção de manter somente esse segmento no relatório ou excluí-lo.

Use a caixa **[!UICONTROL Line Item]** suspensa para selecionar as propriedades no seu portfólio para as quais deseja retornar informações.

Na caixa **[!UICONTROL Segment Data Source]** suspensa, selecione as fontes de dados que contêm os segmentos que você deseja ver no relatório.

Use a caixa **[!UICONTROL Segment]** suspensa para selecionar quais segmentos você deseja ver no relatório.

>[!IMPORTANT]
>
>Ao ativar [!UICONTROL Audience Optimization for Publishers], você deve incluir metadados descritivos para [!UICONTROL Line Item] IDs, conforme descrito na Etapa 3 de [Importar arquivos de dados DFP para o Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Ao fazer isso, você garante que o relatório detalhe a propriedade da Web [!UICONTROL Line Item] em vez da [!UICONTROL Line Item] ID.

## Interpretação dos resultados {#interpreting-results}

O [!UICONTROL Segment Trend] relatório retorna os dados em um gráfico de linhas somente para um intervalo de 14 dias. Neste exemplo, o relatório mostra impressões e tendências de click-through para um conjunto de segmentos mapeados e não mapeados.

Passe o cursor do mouse sobre qualquer linha para obter mais informações sobre essa tendência de segmento específica. Consulte descrições para obter as informações adicionais na tabela abaixo do relatório de amostra.

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
   <td colname="col2"> <p>O nome alfanumérico atribuído a este segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ID do segmento</span> </p> </td> 
   <td colname="col2"> <p>A ID exclusiva deste segmento. </p> </td> 
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
   <td colname="col2"> <p>O número de vezes que membros dessa característica foram expostos ao seu inventário. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>Índice de click-through. Essa métrica relata a porcentagem de impressões seguidas por cliques. Divida cliques por impressões para obter essa métrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Únicos do segmento</span> </p> </td> 
   <td colname="col2"> <p>O número de membros do segmento, nos últimos 30 dias. </p> </td> 
  </tr> 
 </tbody> 
</table>
