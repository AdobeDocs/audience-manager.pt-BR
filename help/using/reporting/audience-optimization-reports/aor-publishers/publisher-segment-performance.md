---
description: O relatório de Desempenho do segmento compara segmentos mapeados e não mapeados por impressões e Únicos do segmento em tempo real. Um segmento mapeado é um segmento que você cria e envia para um destino para direcionamento. Um segmento não mapeado é um segmento que você criou, mas que não enviou a um destino para direcionamento. A comparação desses diferentes tipos de segmentos nos relatórios e entre eles ajuda a otimizar campanhas existentes e encontrar segmentos ignorados que você pode enviar para um destino para direcionamento.
seo-description: The Segment Performance report compares mapped and unmapped segments by impressions and Real-Time Segment Uniques. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Comparing these different segment types within and between reports helps you optimize existing campaigns and find overlooked segments that you may want to send to a destination for targeting.
seo-title: Segment Performance Report
solution: Audience Manager
title: Relatório de desempenho do segmento para editores
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
feature: Audience Optimization Reports
exl-id: 0cc10399-5737-4d82-a1f6-9561e024054d
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%

---

# Relatório de desempenho do segmento{#segment-performance-report}

O relatório de Desempenho do segmento compara segmentos mapeados e não mapeados por impressões e Únicos do segmento em tempo real.

Um segmento mapeado é um segmento que você cria e envia para um destino para direcionamento. Um segmento não mapeado é um segmento que você criou, mas que não enviou a um destino para direcionamento.

A comparação desses diferentes tipos de segmentos nos relatórios e entre eles ajuda a otimizar campanhas existentes e encontrar segmentos ignorados que você pode enviar para um destino para direcionamento.

## Casos de uso {#use-cases}

Com o relatório [!UICONTROL Segment Performance], você pode:

* Identifique segmentos de público mapeados que estão impulsionando a escala ou o desempenho.
* Identifique segmentos não mapeados para apresentar em campanhas futuras, com base na contribuição de um público-alvo para o desempenho anterior.

## Uso do relatório de desempenho do segmento {#using-segment-performance-report}

Alterne entre **[!UICONTROL Mapped]** e **[!UICONTROL Unmapped]** para selecionar segmentos que estão mapeados para um destino ou não. Selecione **[!UICONTROL All]** para incluir todos os seus segmentos no relatório.

Use os controles **Intervalo de Dias** e **De Data até** para ajustar o intervalo de retrospectiva. Observe que os períodos retroativos de 7 dias e 30 dias só estão disponíveis para datas domingo.

Use a caixa suspensa **[!UICONTROL Line Item]** para selecionar as propriedades da Web para as quais deseja retornar informações.

Na caixa suspensa **[!UICONTROL Segment Data Source]**, selecione as fontes de dados que contêm os segmentos que você deseja ver no relatório.

Use a caixa suspensa **[!UICONTROL Segment]** para selecionar quais segmentos você deseja ver no relatório.

>[!IMPORTANT]
>
>Ao habilitar [!UICONTROL Audience Optimization for Publishers], você deve incluir metadados descritivos para [!UICONTROL Line Item IDs], conforme descrito na Etapa 3 de [Importar Arquivos de Dados do Google Ad Manager (antigo DFP) para o Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Ao fazer isso, você garante que o relatório detalhe a propriedade da Web como [!UICONTROL Line Item] em vez de [!UICONTROL Line Item ID].

## Interpretação dos resultados {#interpreting-results}

O relatório [!UICONTROL Segment Performance] pode ser semelhante ao mostrado abaixo. No relatório, clique em uma bolha para visualizar os dados subjacentes. Consulte as descrições para obter as informações adicionais na tabela abaixo do relatório de amostra.

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
   <td colname="col2"> <p>O nome alfanumérico que você atribuiu a este segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID do segmento </p> </td> 
   <td colname="col2"> <p>O identificador exclusivo deste segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Item da linha </p> </td> 
   <td colname="col2"> <p>A propriedade da Web para a qual você está vendo este relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cliques </p> </td> 
   <td colname="col2"> <p>O número de vezes que os membros dessa característica clicaram em itens em sua propriedade da Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Impressões </p> </td> 
   <td colname="col2"> <p>O número de vezes que os membros desta característica foram expostos ao inventário. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>Taxa de cliques. </p> <p>Essa métrica retransmite a porcentagem de impressões seguida de cliques. Dividir cliques por impressões para obter essa métrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Preenchimento de segmentos em tempo real </p> </td> 
   <td colname="col2"> <p>O número real de visitantes únicos vistos em tempo real para o intervalo de tempo especificado e que foram qualificados para o segmento no momento em que foram vistos pelo <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Como ler os resultados do segmento mapeado {#read-mapped-segment}

A posição dos segmentos mapeados em um relatório pode informar muito sobre quais segmentos estão apresentando um bom desempenho e onde talvez seja necessário fazer alguns ajustes.

Para ler o relatório, é útil dividir os resultados em quatro seções com linhas imaginárias (em vermelho) e as categorias mostradas no relatório de amostra abaixo. Os rótulos no exemplo podem ajudar você a entender o desempenho do segmento e como responder a esses resultados.

![](assets/publisher_segment_performance_mapped.png)

## Como ler os resultados do segmento não mapeado {#read-unmapped-segment}

Analisar segmentos não mapeados em um relatório do [!UICONTROL Segment Performance] é uma ótima maneira de encontrar novos segmentos que você não considerou para segmentação. Na verdade, alguns desses segmentos podem ter um desempenho melhor do que os segmentos mapeados.

Para ler este relatório, é útil dividir os resultados em quatro seções com linhas imaginárias (em vermelho) e categorias mostradas no relatório de amostra abaixo.

![](assets/publisher_segment_performance_unmapped.png)
