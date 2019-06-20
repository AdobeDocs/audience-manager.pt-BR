---
description: O relatório Sobreposição de unidade de publicidade é exibido como um gráfico de calor que destaca sobreposições altas e baixas entre as Unidades de publicidade.
seo-description: O relatório Sobreposição de unidade de publicidade é exibido como um gráfico de calor que destaca sobreposições altas e baixas entre as Unidades de publicidade.
seo-title: Sobreposição da unidade de publicidade
solution: Audience Manager
title: Sobreposição da unidade de publicidade
uuid: e 4467 e 81-acbf -474 e-b 501-89 d 57395651 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Ad Unit Overlap{#ad-unit-overlap}

The **[!UICONTROL Ad Unit Overlap]** report is displayed as a heat chart that highlights high and low overlaps between your Ad Units.

## Caso de uso {#use-cases}

With the **[!UICONTROL Ad Unit Overlap]** report, you can gain insight into where your audience overlaps across your web properties. O relatório considera suas propriedades relacionadas a 100 e exibe a sobreposição entre elas.

## Using the Ad Unit Overlap Report {#using-the-report}

Use the **[!UICONTROL Top N Base Ad Units]** and **[!UICONTROL Top N Overlapping Ad Units]** controls to select your desired number of ad units for the overlap. Você pode selecionar um número máximo de 100 itens para cada um.

Use the **Day Range** and **Date Through** controls to adjust your look-back range. Observe que os períodos de retrospectiva de 7 dias e 30 dias estão disponíveis apenas para datas de domingo.

Use the **[!UICONTROL Base Ad Unit]** and the **[!UICONTROL Overlap Ad Unit]** controls to select which of your ad units you want to display in the overlap report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Ad Unit IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Ad Unit] instead of the [!UICONTROL Ad Unit ID].

## Interpreting the Results {#interpreting-results}

Your [!UICONTROL Ad Unit Overlap] report could look similar to the one below. Passe o mouse sobre qualquer célula para obter mais informações sobre essa sobreposição específica. Consulte descrições para as informações adicionais na tabela abaixo do relatório de amostra.

![](assets/publisher_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Sobreposição de publicidade</span> </p> </td> 
   <td colname="col2"> <p>O nome do item de inventário. Por exemplo, pode ser um dos seus sites ou um artigo em seu site. Na imagem acima, as unidades de anúncios base são Artigos 9 - 18. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Unidade de anúncio base</span> </p> </td> 
   <td colname="col2"> <p>O nome do item de inventário. Por exemplo, pode ser um dos seus sites ou um artigo em seu site. Na imagem acima, as unidades de anúncios base são Artigos 1 - 8. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem de únicos de unidade de anúncio de sobreposição</span> </p> </td> 
   <td colname="col2"> <p>O número de usuários que visitaram os itens da unidade de anúncio 9 - 18. Essas informações são extraídas dos logs DFP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem de únicos de unidade de anúncio base</span> </p> </td> 
   <td colname="col2"> <p>O número de usuários que visitaram os itens da unidade de anúncio 1 - 8. Essas informações são extraídas dos logs DFP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem de únicos de sobreposição</span> </p> </td> 
   <td colname="col2"> <p>The overlap between your users who have visited a <span class="wintitle"> Base Ad Unit</span> and <span class="wintitle"> Overlap Ad Unit</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Porcentagem de sobreposição</span> </p> </td> 
   <td colname="col2"> <p>The overlap between your users who have visited a <span class="wintitle"> Base Ad Unit</span> and <span class="wintitle"> Overlap Ad Unit</span>. This is the <span class="wintitle"> Overlap Uniques Count</span>, expressed as a percentage of the <span class="wintitle"> Base Ad Unit</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
