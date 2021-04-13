---
description: O relatório Segmento para sobreposição de unidade de anúncio é exibido como um gráfico de calor que destaca sobreposições altas e baixas entre os segmentos de Audience Manager e Unidades de anúncio.
seo-description: O relatório Segmento para sobreposição de unidade de anúncio é exibido como um gráfico de calor que destaca sobreposições altas e baixas entre os segmentos de Audience Manager e Unidades de anúncio.
seo-title: Segmentar para sobreposição de unidade de anúncio
solution: Audience Manager
title: Segmentar para sobreposição de unidade de anúncio
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: Relatórios de otimização de público-alvo
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 5%

---

# Segmentar para sobreposição de unidade de anúncio{#segment-to-ad-unit-overlap}

O relatório Segmento para sobreposição de unidade de anúncio é exibido como um gráfico de calor que destaca sobreposições altas e baixas entre os segmentos de Audience Manager e Unidades de anúncio.

## Caso de uso {#use-cases}

Com o relatório [!UICONTROL Segment to Ad Unit Overlap], você pode entender quais públicos-alvo visitam suas propriedades da Web. O relatório exibe a sobreposição entre os membros dos segmentos [!DNL Audience Manager] e o número de visitantes das propriedades da Web. Uma sobreposição mais alta significa que muitos membros de um segmento visitam sua propriedade da Web.

## Uso do segmento para o relatório de sobreposição de unidade de anúncio {#using-the-report}

Use os controles **[!UICONTROL Top N Ad Units]** e **[!UICONTROL Top N Segments]** para selecionar o número desejado de unidades de publicidade e segmentos para a sobreposição. Você pode selecionar um número máximo de 100 itens para cada.

Use os controles **Intervalo de dia** e **Até** para ajustar o intervalo de análise. Observe que os períodos de retrospectiva de 7 dias e 30 dias só estão disponíveis para datas de domingo.

Use as caixas **[!UICONTROL Segment Name]** e **[!UICONTROL Ad Unit]** para filtrar qualquer um dos segmentos e unidades de anúncio.

>[!IMPORTANT]
>
>Ao ativar [!UICONTROL Audience Optimization for Publishers], você deve incluir metadados descritivos para [!UICONTROL Ad Unit IDs], conforme descrito na Etapa 3 de [Importar arquivos de dados do Google Ad Manager (antigo DFP) para o Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Ao fazer isso, você garante que o relatório detalhe a propriedade da Web como [!UICONTROL Ad Unit] em vez de [!UICONTROL Ad Unit ID].

## Interpretação dos resultados {#interpreting-results}

Seu relatório [!UICONTROL Segment to Ad Unit Overlap] pode ser semelhante ao abaixo. Passe o mouse sobre qualquer célula para obter mais informações sobre essa sobreposição específica. Consulte descrições para obter as informações adicionais na tabela abaixo do relatório de amostra.

![](assets/publisher_segment_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Unidade de anúncio  </span> </p> </td> 
   <td colname="col2"> <p>O nome do item de inventário. Por exemplo, este pode ser um de seus sites ou um artigo em seu site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem de únicos em tempo real do segmento</span> </p> </td> 
   <td colname="col2"> <p>O número de visitantes únicos vistos em tempo real para o intervalo de tempo especificado e que foram qualificados para o segmento no momento em que foram vistos por <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem de unidades de publicidade</span> </p> </td> 
   <td colname="col2"> <p>O número de seus visitantes para essa unidade de anúncio específica. Essas informações são extraídas dos registros do Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem de únicos de sobreposição</span> </p> </td> 
   <td colname="col2"> <p>Os membros do seu segmento que foram expostos ao item de unidade de anúncio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Porcentagem de sobreposição</span> </p> </td> 
   <td colname="col2"> <p>A sobreposição entre a unidade de anúncio e as populações de segmentos. Essa é a <span class="wintitle"> Contagem de únicos de sobreposição</span>, expressa como uma porcentagem dos <span class="wintitle"> Segmentos de Uniques em tempo real</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
