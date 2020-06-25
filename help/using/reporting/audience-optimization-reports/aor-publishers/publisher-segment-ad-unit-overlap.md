---
description: O relatório Segmento para sobreposição de unidade de publicidade é exibido como um gráfico de calor que destaca sobreposições elevadas e baixas entre os segmentos de Unidades de publicidade e Audience Manager.
seo-description: O relatório Segmento para sobreposição de unidade de publicidade é exibido como um gráfico de calor que destaca sobreposições elevadas e baixas entre os segmentos de Unidades de publicidade e Audience Manager.
seo-title: Segmentar para sobreposição de unidade de publicidade
solution: Audience Manager
title: Segmentar para sobreposição de unidade de publicidade
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 0%

---


# Segmentar para sobreposição de unidade de publicidade{#segment-to-ad-unit-overlap}

O relatório Segmento para sobreposição de unidade de publicidade é exibido como um gráfico de calor que destaca sobreposições elevadas e baixas entre os segmentos de Unidades de publicidade e Audience Manager.

## Caso de uso {#use-cases}

Com o [!UICONTROL Segment to Ad Unit Overlap] relatório, você pode entender quais audiências visitam suas propriedades da Web. O relatório exibe a sobreposição entre os membros de seus [!DNL Audience Manager] segmentos e o número de visitantes para suas propriedades da Web. Uma sobreposição maior significa que muitos membros de um segmento visitam sua propriedade da Web.

## Usando o relatório Segmento para sobreposição de unidade de publicidade {#using-the-report}

Use os controles **[!UICONTROL Top N Ad Units]** e **[!UICONTROL Top N Segments]** para selecionar o número desejado de unidades de anúncios e segmentos para a sobreposição. Você pode selecionar um número máximo de 100 itens para cada um.

Use os controles Intervalo **de** dias e Intervalo de **datas até** para ajustar o intervalo de retrospectiva. Observe que os períodos de retrospectiva de 7 e 30 dias só estão disponíveis para datas de domingo.

Use as caixas **[!UICONTROL Segment Name]** e **[!UICONTROL Ad Unit]** para filtrar qualquer um dos segmentos e unidades de anúncios.

>[!IMPORTANT]
>
>Ao ativar [!UICONTROL Audience Optimization for Publishers], você deve incluir metadados descritivos para [!UICONTROL Ad Unit IDs], conforme descrito na Etapa 3 de [Importar arquivos de dados DFP para o Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Ao fazer isso, você garante que o relatório detalhe a propriedade da Web como [!UICONTROL Ad Unit] não como [!UICONTROL Ad Unit ID].

## Interpretação dos resultados {#interpreting-results}

O seu [!UICONTROL Segment to Ad Unit Overlap] relatório pode ser semelhante ao que se segue. Passe o mouse sobre qualquer célula para obter mais informações sobre essa sobreposição específica. Consulte descrições para obter as informações adicionais na tabela abaixo do relatório de amostra.

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
   <td colname="col1"> <p><span class="wintitle"> Unidade de anúncio </span> </p> </td> 
   <td colname="col2"> <p>O nome do item de inventário. Por exemplo, este pode ser um de seus sites ou um artigo em seu site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem de Únicos em Tempo Real do Segmento</span> </p> </td> 
   <td colname="col2"> <p>O número de visitantes únicos vistos em tempo real para o intervalo de tempo especificado e que eram qualificados para o segmento no momento em que eram vistos pelo <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem exclusiva da unidade de publicidade</span> </p> </td> 
   <td colname="col2"> <p>O número de visitantes desta unidade de publicidade específica. Essas informações são extraídas dos registros DFP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem exclusiva de sobreposição</span> </p> </td> 
   <td colname="col2"> <p>Os membros do seu segmento que foram expostos ao item da unidade de anúncio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Porcentagem de sobreposição</span> </p> </td> 
   <td colname="col2"> <p>A sobreposição entre a unidade de anúncio e as populações de segmentos. Esta é a Contagem <span class="wintitle"> de Únicos de Sobreposição, expressa como uma porcentagem dos Únicos</span>em Tempo Real do <span class="wintitle"></span>Segmento. </p> </td> 
  </tr> 
 </tbody> 
</table>

