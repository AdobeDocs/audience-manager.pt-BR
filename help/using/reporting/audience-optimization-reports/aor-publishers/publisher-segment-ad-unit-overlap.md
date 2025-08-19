---
description: O relatório Segmento para sobreposição de unidade de anúncio é exibido como um gráfico de aquecimento que destaca as sobreposições alta e baixa entre os segmentos de Unidades de anúncio e Audience Manager.
seo-description: The Segment to Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units and Audience Manager segments.
seo-title: Segment to Ad Unit Overlap
solution: Audience Manager
title: Segmentar para sobreposição de unidade de anúncio
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: Audience Optimization Reports
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 1%

---

# Segmentar para sobreposição de unidade de anúncio{#segment-to-ad-unit-overlap}

O relatório Segmento para sobreposição de unidade de anúncio é exibido como um gráfico de aquecimento que destaca as sobreposições alta e baixa entre os segmentos de Unidades de anúncio e Audience Manager.

## Caso de uso {#use-cases}

Com o relatório [!UICONTROL Segment to Ad Unit Overlap], você pode entender quais públicos visitam suas propriedades da Web. O relatório exibe a sobreposição entre membros de seus segmentos do [!DNL Audience Manager] e o número de visitantes das suas propriedades da Web. Uma sobreposição maior significa que muitos membros de um segmento visitam a propriedade da Web.

## Uso do relatório de sobreposição do segmento à unidade de anúncio {#using-the-report}

Use os controles **[!UICONTROL Top N Ad Units]** e **[!UICONTROL Top N Segments]** para selecionar o número desejado de unidades de anúncio e segmentos para a sobreposição. É possível selecionar um número máximo de 100 itens para cada um.

Use os controles **Intervalo de Dias** e **De Data até** para ajustar o intervalo de retrospectiva. Observe que os períodos retroativos de 7 dias e 30 dias só estão disponíveis para datas domingo.

Use as caixas **[!UICONTROL Segment Name]** e **[!UICONTROL Ad Unit]** para filtrar qualquer segmento e unidade de anúncio.

>[!IMPORTANT]
>
>Ao habilitar [!UICONTROL Audience Optimization for Publishers], você deve incluir metadados descritivos para [!UICONTROL Ad Unit IDs], conforme descrito na Etapa 3 de [Importar Arquivos de Dados do Google Ad Manager (antigo DFP) para o Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Ao fazer isso, você garante que o relatório detalhe a propriedade da Web como [!UICONTROL Ad Unit] em vez de [!UICONTROL Ad Unit ID].

## Interpretação dos resultados {#interpreting-results}

O relatório [!UICONTROL Segment to Ad Unit Overlap] pode ser semelhante ao mostrado abaixo. Passe o mouse sobre qualquer célula para obter mais informações sobre essa sobreposição específica. Consulte as descrições para obter as informações adicionais na tabela abaixo do relatório de amostra.

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
   <td colname="col1"> <p><span class="wintitle"> Unidade de publicidade </span> </p> </td> 
   <td colname="col2"> <p>O nome do item de inventário. Por exemplo, pode ser um dos sites ou um artigo do site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contagem de únicos em tempo real do segmento <span class="wintitle"></span> </p> </td> 
   <td colname="col2"> <p>O número de visitantes únicos vistos em tempo real para o intervalo de tempo especificado e que foram qualificados para o segmento no momento em que foram vistos pelo <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem de únicos da unidade de publicidade</span> </p> </td> 
   <td colname="col2"> <p>O número de visitantes para esta unidade de anúncio específica. Essas informações são extraídas dos registros do Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem de únicos de sobreposição</span> </p> </td> 
   <td colname="col2"> <p>Os membros do segmento que foram expostos ao item da unidade de anúncio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Porcentagem de sobreposição</span> </p> </td> 
   <td colname="col2"> <p>A sobreposição entre a unidade de anúncio e as populações do segmento. Esta é a <span class="wintitle"> Contagem de Uniques de Sobreposição</span>, expressa como uma porcentagem de <span class="wintitle"> Uniques de Tempo Real de Segmento</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
