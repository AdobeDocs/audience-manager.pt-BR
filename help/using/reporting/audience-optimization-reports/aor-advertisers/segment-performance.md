---
description: O relatório de Desempenho do segmento compara segmentos mapeados e não mapeados por impressões e taxas de conversão. Um segmento mapeado é um segmento criado e enviado para um destino para direcionamento. Um segmento não mapeado é um segmento criado, mas que não foi enviado para um destino para direcionamento. A comparação desses diferentes tipos de segmentos dentro e entre relatórios ajuda a otimizar campanhas existentes e encontrar segmentos ignorados que você pode enviar para um destino para direcionamento.
seo-description: O relatório de Desempenho do segmento compara segmentos mapeados e não mapeados por impressões e taxas de conversão. Um segmento mapeado é um segmento criado e enviado para um destino para direcionamento. Um segmento não mapeado é um segmento criado, mas que não foi enviado para um destino para direcionamento. A comparação desses diferentes tipos de segmentos dentro e entre relatórios ajuda a otimizar campanhas existentes e encontrar segmentos ignorados que você pode enviar para um destino para direcionamento.
seo-title: Relatório de desempenho do segmento
solution: Audience Manager
title: Relatório de desempenho do segmento
uuid: 5156a4c7-831d-4a95-a1be-eb516f0d91b7
feature: Audience Optimization Reports
exl-id: 2cd54b18-6916-4d69-bd65-7b8c8846c446
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 1%

---

# Relatório de desempenho do segmento{#segment-performance-report}

O relatório [!UICONTROL Segment Performance] compara segmentos mapeados e não mapeados por impressões e taxas de conversão. Um segmento mapeado é um segmento criado e enviado para um destino para direcionamento. Um segmento não mapeado é um segmento criado, mas que não foi enviado para um destino para direcionamento. A comparação desses diferentes tipos de segmentos dentro e entre relatórios ajuda a otimizar campanhas existentes e encontrar segmentos ignorados que você pode enviar para um destino para direcionamento.

## Como ler os resultados do segmento mapeado {#read-mapped-segment-results}

O relatório [!UICONTROL Segment Performance] mapeado exibe todos os segmentos criados e enviados para um destino para direcionamento. A posição dos segmentos mapeados em um relatório pode informar muito sobre quais segmentos estão bem e onde você pode precisar fazer alguns ajustes.

Para ler o relatório, ele ajuda a dividir os resultados em 4 seções com linhas imaginárias (em vermelho) e as categorias mostradas no relatório de amostra abaixo.

![](assets/mapped-segment-performance.png)

Os rótulos no exemplo e na tabela a seguir podem ajudar você a entender o desempenho do segmento e como responder a esses resultados.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Position </th> 
   <th colname="col2" class="entry"> Indicações de posicionamento </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Superior esquerdo</b> </p> </td> 
   <td colname="col2"> <p>Bons índices de conversão. </p> <p>Você pode conseguir mais conversões aumentando as impressões. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Inferior Esquerdo</b> </p> </td> 
   <td colname="col2"> <p>Taxas de conversão baixas. </p> <p>Você pode evitar o direcionamento desses segmentos. Os segmentos nesta seção fazem grandes candidatos para comparação com aqueles nos resultados de segmentos não mapeados. Alguns de seus segmentos não mapeados podem ter um desempenho melhor do que os segmentos que você já está direcionando. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Superior direito</b> </p> </td> 
   <td colname="col2"> <p>Forte desempenho. Deixe esses segmentos sozinhos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Parte inferior direita</b> </p> </td> 
   <td colname="col2"> <p>Taxas de conversão baixas e impressões altas. </p> <p>Os segmentos nesta seção não estão funcionando bem. Você pode querer afastar o orçamento desses segmentos e transformá-lo em segmentos no quadrante superior esquerdo do relatório. Isso ajudará a reduzir as impressões e pode ajudar a melhorar as taxas de conversão dos segmentos nesta seção inferior direita. Além disso, compare esses segmentos mapeados com seus segmentos não mapeados. Alguns de seus segmentos não mapeados podem ter um desempenho melhor do que os segmentos que você já está direcionando. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Como ler os resultados do segmento não mapeado {#read-unmapped-segment-results}

Olhar os segmentos não mapeados em um relatório [!UICONTROL Segment Performance] é uma ótima maneira de encontrar novos segmentos que você não considerou para o direcionamento. Na verdade, alguns desses segmentos podem ter desempenho superior aos segmentos mapeados. Isso ocorre porque um segmento não mapeado precisa atender a um conjunto de critérios de qualificação para ser incluído nesse relatório. Para ser incluído neste relatório, um segmento não mapeado deve:

* Ter conversões maiores que a média de todos os segmentos mapeados.
* Esteja nos 100 segmentos não mapeados principais por taxa de conversão.

Para ler este relatório, ele ajuda a dividir os resultados em 4 seções com linhas imaginárias (em vermelho) e categorias mostradas no relatório de amostra abaixo.

![](assets/unmapped-segment-performance.png)

Neste relatório, você só deseja se concentrar nos segmentos não mapeados na seção superior esquerda. Esses segmentos não mapeados exibem altas taxas de conversão para um baixo nível de impressões em comparação aos segmentos das outras três seções.

>[!NOTE]
>
>Os períodos de análise de 7 dias e 30 dias só estão disponíveis para datas de domingo **[!UICONTROL Date Through]**.
