---
description: O relatório de desempenho do segmento compara segmentos mapeados e não mapeados por impressões e taxas de conversão. Um segmento mapeado é um segmento que você cria e envia para um destino para direcionamento. Um segmento não mapeado é um segmento que você criou, mas que não enviou a um destino para direcionamento. A comparação desses diferentes tipos de segmentos nos relatórios e entre eles ajuda a otimizar campanhas existentes e encontrar segmentos ignorados que você pode enviar para um destino para direcionamento.
seo-description: The Segment Performance report compares mapped and unmapped segments by impressions and conversion rates. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Comparing these different segment types within and between reports helps you optimize existing campaigns and find overlooked segments that you may want to send to a destination for targeting.
seo-title: Segment Performance Report
solution: Audience Manager
title: Relatório de desempenho do segmento
uuid: 5156a4c7-831d-4a95-a1be-eb516f0d91b7
feature: Audience Optimization Reports
exl-id: 2cd54b18-6916-4d69-bd65-7b8c8846c446
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 0%

---

# Relatório de desempenho do segmento{#segment-performance-report}

O relatório [!UICONTROL Segment Performance] compara segmentos mapeados e não mapeados por impressões e taxas de conversão. Um segmento mapeado é um segmento que você cria e envia para um destino para direcionamento. Um segmento não mapeado é um segmento que você criou, mas que não enviou a um destino para direcionamento. A comparação desses diferentes tipos de segmentos nos relatórios e entre eles ajuda a otimizar campanhas existentes e encontrar segmentos ignorados que você pode enviar para um destino para direcionamento.

## Como ler os resultados do segmento mapeado {#read-mapped-segment-results}

O relatório de [!UICONTROL Segment Performance] mapeado exibe todos os segmentos que você criou e enviou para um destino para direcionamento. A posição dos segmentos mapeados em um relatório pode informar muito sobre quais segmentos estão tendo um bom desempenho e onde você pode precisar fazer alguns ajustes.

Para ler o relatório, ele ajuda a dividir os resultados em 4 seções com linhas imaginárias (em vermelho) e as categorias mostradas no relatório de amostra abaixo.

![](assets/mapped-segment-performance.png)

Os rótulos no exemplo e na tabela a seguir podem ajudar você a entender o desempenho do segmento e como responder a esses resultados.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Position </th> 
   <th colname="col2" class="entry"> Posicionamento indica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Superior esquerdo</b> </p> </td> 
   <td colname="col2"> <p>Boas taxas de conversão. </p> <p>Você pode conseguir mais conversões aumentando as impressões. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Inferior esquerdo</b> </p> </td> 
   <td colname="col2"> <p>Baixas taxas de conversão. </p> <p>Talvez você queira evitar o direcionamento desses segmentos. Os segmentos desta seção são excelentes candidatos para comparação com aqueles nos resultados de segmentos não mapeados. Alguns dos segmentos não mapeados podem ter um desempenho melhor do que os segmentos que você já está direcionando. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Cima à Direita</b> </p> </td> 
   <td colname="col2"> <p>Alto desempenho. Deixe esses segmentos em paz. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Parte Inferior Direita</b> </p> </td> 
   <td colname="col2"> <p>Baixas taxas de conversão e altas impressões. </p> <p>Os segmentos nesta seção não estão apresentando um bom desempenho. Talvez você queira deslocar o orçamento desses segmentos para segmentos no quadrante superior esquerdo do relatório. Isso ajudará a reduzir as impressões e pode ajudar a melhorar as taxas de conversão para segmentos nesta seção inferior direita. Além disso, compare esses segmentos mapeados com os segmentos não mapeados. Alguns dos segmentos não mapeados podem ter um desempenho melhor do que os segmentos que você já está direcionando. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Como ler os resultados do segmento não mapeado {#read-unmapped-segment-results}

Analisar segmentos não mapeados em um relatório do [!UICONTROL Segment Performance] é uma ótima maneira de encontrar novos segmentos que você não considerou para segmentação. Na verdade, alguns desses segmentos podem ter um desempenho melhor do que os segmentos mapeados. Isso ocorre porque um segmento não mapeado precisa atender a um conjunto de critérios de qualificação para ser incluído neste relatório. Para ser incluído neste relatório, um segmento não mapeado deve:

* Ter conversões maiores que a média de todos os segmentos mapeados.
* Estar entre os 100 principais segmentos não mapeados por taxa de conversão.

Para ler este relatório, ele ajuda a dividir os resultados em quatro seções com linhas imaginárias (em vermelho) e categorias mostradas no relatório de amostra abaixo.

![](assets/unmapped-segment-performance.png)

Nesse relatório, você deseja apenas se concentrar nos segmentos não mapeados na seção superior esquerda. Esses segmentos não mapeados apresentam altas taxas de conversão para um baixo nível de impressões, quando comparados aos segmentos nas outras três seções.

>[!NOTE]
>
>Os períodos retroativos de 7 dias e 30 dias só estão disponíveis para datas de domingo **[!UICONTROL Date Through]**.
