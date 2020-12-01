---
description: O relatório Desempenho do segmento compara segmentos mapeados e não mapeados por impressões e taxas de conversão. Um segmento mapeado é um segmento criado e enviado para um destino para definição de metas. Um segmento não mapeado é um segmento criado, mas não enviado para um destino para definição de metas. A comparação desses diferentes tipos de segmentos dentro e entre relatórios ajuda a otimizar campanhas existentes e a encontrar segmentos ignorados que você pode querer enviar para um destino para definição de metas.
seo-description: O relatório Desempenho do segmento compara segmentos mapeados e não mapeados por impressões e taxas de conversão. Um segmento mapeado é um segmento criado e enviado para um destino para definição de metas. Um segmento não mapeado é um segmento criado, mas não enviado para um destino para definição de metas. A comparação desses diferentes tipos de segmentos dentro e entre relatórios ajuda a otimizar campanhas existentes e a encontrar segmentos ignorados que você pode querer enviar para um destino para definição de metas.
seo-title: Relatório de desempenho do segmento
solution: Audience Manager
title: Relatório de desempenho do segmento
uuid: 5156a4c7-831d-4a95-a1be-eb516f0d91b7
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 1%

---


# Relatório de desempenho do segmento{#segment-performance-report}

O relatório [!UICONTROL Segment Performance] compara segmentos mapeados e não mapeados por impressões e taxas de conversão. Um segmento mapeado é um segmento criado e enviado para um destino para definição de metas. Um segmento não mapeado é um segmento criado, mas não enviado para um destino para definição de metas. A comparação desses diferentes tipos de segmentos dentro e entre relatórios ajuda a otimizar campanhas existentes e a encontrar segmentos ignorados que você pode querer enviar para um destino para definição de metas.

## Como ler os resultados do segmento mapeado {#read-mapped-segment-results}

O relatório mapeado [!UICONTROL Segment Performance] exibe todos os segmentos criados e enviados para um destino para definição de metas.A posição dos segmentos mapeados em um relatório pode informar muito sobre quais segmentos estão funcionando bem e onde talvez seja necessário fazer alguns ajustes.

Para ler o relatório, ajuda a dividir os resultados em 4 seções com linhas imaginárias (em vermelho) e as categorias mostradas no relatório de amostra abaixo.

![](assets/mapped-segment-performance.png)

Os rótulos no exemplo e na tabela a seguir podem ajudá-lo a entender o desempenho do segmento e como responder a esses resultados.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Posição </th> 
   <th colname="col2" class="entry"> A disposição indica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Superior esquerdo</b> </p> </td> 
   <td colname="col2"> <p>Boas taxas de conversão. </p> <p>Você pode obter mais conversões aumentando as impressões. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Inferior esquerdo</b> </p> </td> 
   <td colname="col2"> <p>Taxas de conversão baixas. </p> <p>Talvez você queira evitar a definição de metas para esses segmentos. Os segmentos nesta seção tornam excelentes candidatos para comparação com os resultados dos segmentos não mapeados. Alguns de seus segmentos não mapeados podem ter um desempenho melhor do que os segmentos que você já está direcionando. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Superior direito</b> </p> </td> 
   <td colname="col2"> <p>Forte desempenho. Deixe esses segmentos sozinhos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Inferior direito</b> </p> </td> 
   <td colname="col2"> <p>Taxas de conversão baixas e impressões altas. </p> <p>Segmentos nesta seção não estão funcionando bem. Você pode querer afastar o orçamento desses segmentos e transformá-lo em segmentos no quadrante superior esquerdo do relatório. Isso ajudará a reduzir as impressões e poderá ajudar a melhorar as taxas de conversão para segmentos nesta seção inferior direita. Além disso, compare esses segmentos mapeados com seus segmentos não mapeados. Alguns de seus segmentos não mapeados podem ter um desempenho melhor do que os segmentos que você já está direcionando. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Como ler os resultados do segmento não mapeado {#read-unmapped-segment-results}

Analisar segmentos não mapeados em um relatório [!UICONTROL Segment Performance] é uma excelente maneira de encontrar novos segmentos que você não considerou para definição de metas. Na verdade, alguns desses segmentos podem superar seus segmentos mapeados. Isso ocorre porque um segmento não mapeado precisa atender a um conjunto de critérios de qualificação para ser incluído neste relatório. Para ser incluído neste relatório, um segmento não mapeado deve:

* Ter conversões maiores que a média de todos os segmentos mapeados.
* Esteja nos 100 principais segmentos não mapeados por taxa de conversão.

Para ler esse relatório, ajuda a dividir os resultados em 4 seções com linhas imaginárias (em vermelho) e categorias mostradas no relatório de amostra abaixo.

![](assets/unmapped-segment-performance.png)

Neste relatório, você só deseja se concentrar nos segmentos não mapeados na seção superior esquerda. Esses segmentos não mapeados exibem taxas de conversão altas para um nível baixo de impressões quando comparados aos segmentos das outras três seções.

>[!NOTE]
>
>Períodos de retrospectiva de 7 dias e 30 dias estão disponíveis somente para datas de domingo **[!UICONTROL Date Through]**.
