---
description: O relatório de Desempenho do segmento compara segmentos mapeados e não mapeados por impressões e Únicos de segmentos em tempo real. Um segmento mapeado é um segmento criado e enviado para um destino para direcionamento. Um segmento não mapeado é um segmento criado, mas que não foi enviado para um destino para direcionamento. A comparação desses diferentes tipos de segmentos dentro e entre relatórios ajuda a otimizar campanhas existentes e encontrar segmentos ignorados que você pode enviar para um destino para direcionamento.
seo-description: O relatório de Desempenho do segmento compara segmentos mapeados e não mapeados por impressões e Únicos de segmentos em tempo real. Um segmento mapeado é um segmento criado e enviado para um destino para direcionamento. Um segmento não mapeado é um segmento criado, mas que não foi enviado para um destino para direcionamento. A comparação desses diferentes tipos de segmentos dentro e entre relatórios ajuda a otimizar campanhas existentes e encontrar segmentos ignorados que você pode enviar para um destino para direcionamento.
seo-title: Relatório de desempenho do segmento
solution: Audience Manager
title: Relatório de desempenho do segmento para editores
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
feature: Audience Optimization Reports
exl-id: 0cc10399-5737-4d82-a1f6-9561e024054d
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 2%

---

# Relatório de desempenho do segmento{#segment-performance-report}

O relatório de Desempenho do segmento compara segmentos mapeados e não mapeados por impressões e Únicos de segmentos em tempo real.

Um segmento mapeado é um segmento criado e enviado para um destino para direcionamento. Um segmento não mapeado é um segmento criado, mas que não foi enviado para um destino para direcionamento.

A comparação desses diferentes tipos de segmentos dentro e entre relatórios ajuda a otimizar campanhas existentes e encontrar segmentos ignorados que você pode enviar para um destino para direcionamento.

## Casos de uso {#use-cases}

Com o relatório [!UICONTROL Segment Performance], você pode:

* Identifique segmentos de público-alvo mapeados que estejam proporcionando escala ou desempenho.
* Identifique segmentos não mapeados para apresentar em campanhas futuras, com base na contribuição de um público-alvo para o desempenho anterior.

## Usando o Relatório de desempenho do segmento {#using-segment-performance-report}

Alterne entre **[!UICONTROL Mapped]** e **[!UICONTROL Unmapped]** para selecionar segmentos que estão ou não mapeados para um destino. Selecione **[!UICONTROL All]** para incluir todos os seus segmentos no relatório.

Use os controles **Intervalo de dia** e **Até** para ajustar o intervalo de análise. Observe que os períodos de retrospectiva de 7 dias e 30 dias só estão disponíveis para datas de domingo.

Use a caixa suspensa **[!UICONTROL Line Item]** para selecionar as propriedades da Web para as quais deseja retornar informações.

Na caixa suspensa **[!UICONTROL Segment Data Source]**, selecione as fontes de dados que contêm os segmentos que você deseja visualizar no relatório.

Use a caixa suspensa **[!UICONTROL Segment]** para selecionar quais segmentos você deseja visualizar no relatório.

>[!IMPORTANT]
>
>Ao ativar [!UICONTROL Audience Optimization for Publishers], você deve incluir metadados descritivos para [!UICONTROL Line Item IDs], conforme descrito na Etapa 3 de [Importar arquivos de dados do Google Ad Manager (antigo DFP) para o Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Ao fazer isso, você garante que o relatório detalhe a propriedade da Web como [!UICONTROL Line Item] em vez de [!UICONTROL Line Item ID].

## Interpretação dos resultados {#interpreting-results}

Seu relatório [!UICONTROL Segment Performance] pode ser semelhante ao abaixo. No seu relatório, clique em uma bolha para visualizar os dados subjacentes. Consulte descrições para obter as informações adicionais na tabela abaixo do relatório de amostra.

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
   <td colname="col2"> <p>O nome alfanumérico atribuído a este segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID do segmento </p> </td> 
   <td colname="col2"> <p>A ID exclusiva deste segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Item de linha </p> </td> 
   <td colname="col2"> <p>A propriedade da Web para a qual você está vendo este relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cliques </p> </td> 
   <td colname="col2"> <p>O número de vezes que membros dessa característica clicaram em itens na propriedade da Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Impressões </p> </td> 
   <td colname="col2"> <p>O número de vezes que membros dessa característica foram expostos ao seu inventário. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>Índice de click-through. </p> <p>Essa métrica relata a porcentagem de impressões seguidas pelos cliques. Divida cliques por impressões para obter essa métrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>População de segmentos em tempo real </p> </td> 
   <td colname="col2"> <p>O número real de visitantes únicos vistos em tempo real para o intervalo de tempo especificado e que foram qualificados para o segmento no momento em que foram vistos por <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Como ler os resultados do segmento mapeado {#read-mapped-segment}

A posição dos segmentos mapeados em um relatório pode informar muito sobre quais segmentos estão funcionando bem e onde você pode precisar fazer alguns ajustes.

Para ler o relatório, é útil dividir os resultados em quatro seções com linhas imaginárias (em vermelho) e as categorias mostradas no relatório de amostra abaixo. Os rótulos no exemplo podem ajudar você a entender o desempenho do segmento e como responder a esses resultados.

![](assets/publisher_segment_performance_mapped.png)

## Como ler os resultados do segmento não mapeado {#read-unmapped-segment}

Olhar os segmentos não mapeados em um relatório [!UICONTROL Segment Performance] é uma ótima maneira de encontrar novos segmentos que você não considerou para o direcionamento. Na verdade, alguns desses segmentos podem ter desempenho superior aos segmentos mapeados.

Para ler este relatório, é útil dividir os resultados em quatro seções com linhas imaginárias (em vermelho) e categorias mostradas no relatório de amostra abaixo.

![](assets/publisher_segment_performance_unmapped.png)
