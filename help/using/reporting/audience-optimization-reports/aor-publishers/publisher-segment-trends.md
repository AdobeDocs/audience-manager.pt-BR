---
description: O relatório de Tendência do segmento retorna dados sobre impressões e taxas de click-through de segmentos mapeados e não mapeados ao longo do tempo. Um segmento mapeado é um segmento criado e enviado para um destino para direcionamento. Um segmento não mapeado é um segmento criado, mas que não foi enviado para um destino para direcionamento. Compare tendências e volumes de suas métricas selecionadas para obter uma imagem melhor de como seus públicos-alvo se comportam ao longo do tempo.
seo-description: O relatório de Tendência do segmento retorna dados sobre impressões e taxas de click-through de segmentos mapeados e não mapeados ao longo do tempo. Um segmento mapeado é um segmento criado e enviado para um destino para direcionamento. Um segmento não mapeado é um segmento criado, mas que não foi enviado para um destino para direcionamento. Compare tendências e volumes de suas métricas selecionadas para obter uma imagem melhor de como seus públicos-alvo se comportam ao longo do tempo.
seo-title: Relatório de tendência do segmento
solution: Audience Manager
title: Relatório de tendência do segmento
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: Relatórios de otimização de público-alvo
exl-id: 1fdca05a-b661-4875-88d7-b0893e2ca08f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 3%

---

# Relatório de tendência do segmento{#segment-trend-report}

O relatório de Tendência do segmento retorna dados sobre impressões e taxas de click-through de segmentos mapeados e não mapeados ao longo do tempo.

Um segmento mapeado é um segmento criado e enviado para um destino para direcionamento. Um segmento não mapeado é um segmento criado, mas que não foi enviado para um destino para direcionamento.

Compare tendências e volumes de suas métricas selecionadas para obter uma imagem melhor de como seus públicos-alvo se comportam ao longo do tempo.

## Caso de uso {#use-cases}

Use o relatório [!UICONTROL Segment Trend] para validar o desempenho de um segmento ao longo do tempo e para identificar tendências com base em alto desempenho ou escala.

Com esse relatório, você pode entender quais de suas propriedades da Web mostram um aumento ou falha e solucionar problemas, conforme necessário. Este relatório é a próxima etapa após identificar seu público-alvo de interesse no relatório [!UICONTROL Segment Performance], para garantir que o desempenho forte ou ruim visualizado na guia [!UICONTROL Segment Performance] seja consistente ao longo do tempo.

## Uso do Relatório de tendência do segmento {#using-the-report}

Alterne entre **[!UICONTROL Mapped]** e **[!UICONTROL Unmapped]** para selecionar segmentos que estão ou não mapeados para um destino. Selecione **[!UICONTROL All]** para incluir todos os seus segmentos no relatório.

Ajuste a janela de retrospectiva com o controle deslizante **[!UICONTROL Date Through]**.

Clique em qualquer um dos segmentos no controle deslizante **[!UICONTROL Date Through]** para exibir a opção para manter somente esse segmento no relatório ou excluí-lo.

Use a caixa suspensa **[!UICONTROL Line Item]** para selecionar as propriedades no portfólio para as quais deseja retornar informações.

Na caixa suspensa **[!UICONTROL Segment Data Source]**, selecione as fontes de dados que contêm os segmentos que você deseja visualizar no relatório.

Use a caixa suspensa **[!UICONTROL Segment]** para selecionar quais segmentos você deseja visualizar no relatório.

>[!IMPORTANT]
>
>Ao ativar [!UICONTROL Audience Optimization for Publishers], você deve incluir metadados descritivos para [!UICONTROL Line Item] IDs, conforme descrito na Etapa 3 de [Importar arquivos de dados do Google Ad Manager (antigo DFP) para o Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Ao fazer isso, você garante que o relatório detalhe a propriedade da Web como [!UICONTROL Line Item] em vez da ID [!UICONTROL Line Item].

## Interpretação dos resultados {#interpreting-results}

O relatório [!UICONTROL Segment Trend] retorna dados em um gráfico de linhas somente para um intervalo de 14 dias. Neste exemplo, o relatório mostra impressões e tendências de click-through para um conjunto de segmentos mapeados e não mapeados.

Passe o mouse sobre qualquer linha para obter mais informações sobre essa tendência do segmento específico. Consulte descrições para obter as informações adicionais na tabela abaixo do relatório de amostra.

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
   <td colname="col2"> <p>O número de vezes que membros dessa característica clicaram em itens na propriedade da Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressões</span> </p> </td> 
   <td colname="col2"> <p>O número de vezes que membros dessa característica foram expostos ao seu inventário. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>Índice de click-through. Essa métrica relata a porcentagem de impressões seguidas pelos cliques. Divida cliques por impressões para obter essa métrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segmento único</span> </p> </td> 
   <td colname="col2"> <p>O número de membros do segmento, nos últimos 30 dias. </p> </td> 
  </tr> 
 </tbody> 
</table>
