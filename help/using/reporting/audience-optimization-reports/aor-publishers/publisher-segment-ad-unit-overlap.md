---
description: O relatório Segmento para sobreposição de unidade de publicidade é exibido como um gráfico de calor que destaca sobreposições elevadas e baixas entre os segmentos de Unidades de publicidade e Audience Manager.
seo-description: O relatório Segmento para sobreposição de unidade de publicidade é exibido como um gráfico de calor que destaca sobreposições elevadas e baixas entre os segmentos de Unidades de publicidade e Audience Manager.
seo-title: Segmentar para sobreposição de unidade de anúncio
solution: Audience Manager
title: Segmentar para sobreposição de unidade de anúncio
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 4%

---


# Segmentar para sobreposição de unidade de anúncio{#segment-to-ad-unit-overlap}

O relatório Segmento para sobreposição de unidade de publicidade é exibido como um gráfico de calor que destaca sobreposições elevadas e baixas entre os segmentos de Unidades de publicidade e Audience Manager.

## Caso de uso {#use-cases}

Com o relatório [!UICONTROL Segment to Ad Unit Overlap], você pode entender quais audiências visitam suas propriedades da Web. O relatório exibe a sobreposição entre os membros dos segmentos [!DNL Audience Manager] e o número de visitantes das propriedades da Web. Uma sobreposição maior significa que muitos membros de um segmento visitam sua propriedade da Web.

## Usando o relatório Segmento para sobreposição de unidade de publicidade {#using-the-report}

Use os controles **[!UICONTROL Top N Ad Units]** e **[!UICONTROL Top N Segments]** para selecionar o número desejado de unidades de anúncio e segmentos para a sobreposição. Você pode selecionar um número máximo de 100 itens para cada um.

Use os controles **Intervalo de dias** e **Data até** para ajustar o intervalo de retrospectiva. Observe que os períodos de retrospectiva de 7 e 30 dias só estão disponíveis para datas de domingo.

Use as caixas **[!UICONTROL Segment Name]** e **[!UICONTROL Ad Unit]** para filtrar quaisquer segmentos e unidades de anúncios.

>[!IMPORTANT]
>
>Ao ativar [!UICONTROL Audience Optimization for Publishers], você deve incluir metadados descritivos para [!UICONTROL Ad Unit IDs], conforme descrito na Etapa 3 de [Importar arquivos de dados do Google Ad Manager (antigo DFP) para Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Ao fazer isso, você garante que o relatório detalhe a propriedade da Web como [!UICONTROL Ad Unit] em vez de [!UICONTROL Ad Unit ID].

## Interpretação dos resultados {#interpreting-results}

Seu relatório [!UICONTROL Segment to Ad Unit Overlap] pode ser semelhante ao apresentado abaixo. Passe o mouse sobre qualquer célula para obter mais informações sobre essa sobreposição específica. Consulte descrições para obter as informações adicionais na tabela abaixo do relatório de amostra.

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
   <td colname="col1"> <p><span class="wintitle"> Contagem de Únicos em Tempo Real do Segmento</span> </p> </td> 
   <td colname="col2"> <p>O número de visitantes únicos vistos em tempo real para o intervalo de tempo especificado e que eram qualificados para o segmento no momento em que eram vistos por <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem exclusiva da unidade de publicidade</span> </p> </td> 
   <td colname="col2"> <p>O número de visitantes desta unidade de publicidade específica. Essas informações são extraídas dos registros do Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem exclusiva de sobreposição</span> </p> </td> 
   <td colname="col2"> <p>Os membros do seu segmento que foram expostos ao item da unidade de anúncio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Porcentagem de sobreposição</span> </p> </td> 
   <td colname="col2"> <p>A sobreposição entre a unidade de anúncio e as populações de segmentos. Esta é a <span class="wintitle"> Contagem exclusiva de sobreposição</span>, expressa como uma porcentagem do <span class="wintitle"> Segmento Uniques em tempo real</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

