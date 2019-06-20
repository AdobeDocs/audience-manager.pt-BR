---
description: A seção de relatórios de grupo de teste retorna informações sobre conversões de grupo de teste, permitindo uma comparação fácil da eficácia do segmento de teste. Vários filtros e dimensões estão disponíveis para visualização de dados.
seo-description: A seção de relatórios de grupo de teste retorna informações sobre conversões de grupo de teste, permitindo uma comparação fácil da eficácia do segmento de teste. Vários filtros e dimensões estão disponíveis para visualização de dados.
seo-title: Relatórios de grupo de teste
solution: Audience Manager
title: Relatórios de grupo de teste
topic: API DIL
uuid: 21303 c 3 e -4 c 05-4728-a 759-96 c 2 a 1 d 99 b 69
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Test Group Reporting {#test-group-reporting}

A seção de relatórios de grupo de teste retorna informações sobre conversões de grupo de teste, permitindo uma comparação fácil da eficácia do segmento de teste. Vários filtros e dimensões estão disponíveis para visualização de dados.

[!UICONTROL Audience Lab] retorna informações detalhadas de relatório para os segmentos de teste criados e permite salvar os dados do relatório como [!DNL CSV] arquivos. You can select between **[!UICONTROL Aggregate Reporting]** and **[!UICONTROL Trend Reporting]**.

**[!UICONTROL Aggregate Reporting]** retorna os números absolutos dos segmentos de teste. **[!UICONTROL Trend Reporting]** retorna um gráfico da tendência *em um período específico*. Quatro guias permitem personalizar os relatórios:

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Taxa de conversão de população</span></b> </p> </td> 
   <td colname="col2"> <p>Retorna a porcentagem de dispositivos pertencentes a um segmento de teste específico, que foi convertido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Conversores</span></b> </p> </td> 
   <td colname="col2"> <p>Retorna o número de dispositivos que exibiram os traços de conversão selecionados nos grupos de teste. <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> Assista a este vídeo</a> para saber como criar características de conversão. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Conversões totais</span></b> </p> </td> 
   <td colname="col2"> <p>Retorna o número de conversões geradas pelos segmentos de teste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Testar populações de segmentos</span></b> </p> </td> 
   <td colname="col2"> <p>Retorna o número de dispositivos pertencentes aos segmentos de teste. Toggle between <b><span class="uicontrol"> Total Population</span></b> or <b><span class="uicontrol"> Real-time Population</span></b>. The difference is explained in the <a href="../../faq/faq-reporting.md"> Reporting FAQ</a> . </p> </td>
  </tr>
 </tbody>
</table>

Você pode selecionar uma característica de conversão específica para a qual gerar o relatório ou selecionar todas as características combinadas. You can define a date range for which the information should be returned and export the report as a [!DNL CSV] file.

>[!NOTE]
>
>* Os relatórios para um grupo de teste preencherão o dia após sua data de início.
>* Uma conversão é contada somente para um dispositivo depois da data de início de um teste e depois que o dispositivo foi adicionado a um segmento de teste. Se ocorrer uma conversão para esse dispositivo antes de receber um grupo de teste, a conversão não será contada.


A returned **[!UICONTROL Aggregate Reporting]** chart could look like this:

![](assets/aggregate-reporting.PNG)

A returned **[!UICONTROL Trend Reporting]** chart could look like the one below. Select **[!UICONTROL Normalized]** in the check box if you want to ignore the absolute numbers and simply focus on the test segments trends.

![](assets/trend-reporting.PNG)