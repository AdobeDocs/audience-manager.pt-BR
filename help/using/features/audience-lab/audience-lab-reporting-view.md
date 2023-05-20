---
description: A seção de relatórios do grupo de teste retorna informações sobre as conversões do grupo de teste, permitindo uma fácil comparação da eficácia do segmento de teste. Vários filtros e dimensões estão disponíveis para visualização de dados.
seo-description: The test group reporting section returns information on test group conversions, allowing an easy comparison of test segment efficacy. Numerous filters and dimensions are available for data visualization.
seo-title: Test Group Reporting
solution: Audience Manager
title: Relatórios do grupo de teste
uuid: 21303c3e-4c05-4728-a759-96c2a1d99b69
feature: Audience Lab
exl-id: 5d959002-e904-44df-87e6-e4c85838b076
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 2%

---

# Relatórios do grupo de teste {#test-group-reporting}

A seção de relatórios do grupo de teste retorna informações sobre as conversões do grupo de teste, permitindo uma fácil comparação da eficácia do segmento de teste. Vários filtros e dimensões estão disponíveis para visualização de dados.

[!UICONTROL Audience Lab] retorna informações detalhadas de relatórios para os segmentos de teste criados e permite salvar os dados de relatórios como [!DNL CSV] arquivos. Você pode selecionar entre **[!UICONTROL Aggregate Reporting]** e **[!UICONTROL Trend Reporting]**.

**[!UICONTROL Aggregate Reporting]** retorna os números absolutos dos segmentos de teste. **[!UICONTROL Trend Reporting]** retorna um gráfico da tendência *durante um período específico*. Quatro guias permitem personalizar os relatórios:

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Índice de conversão de população</span></b> </p> </td> 
   <td colname="col2"> <p>Retorna o percentual de dispositivos pertencentes a um segmento de teste específico, que foram convertidos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Conversores</span></b> </p> </td> 
   <td colname="col2"> <p>Retorna o número de dispositivos que exibiram as características de conversão selecionadas nos grupos de teste. <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> Assista a este vídeo</a> para saber como criar características de conversão. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Total de conversões</span></b> </p> </td> 
   <td colname="col2"> <p>Retorna o número de conversões geradas pelos segmentos de teste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Populações de segmentos de teste</span></b> </p> </td> 
   <td colname="col2"> <p>Retorna o número de dispositivos pertencentes aos segmentos de teste. Alternar entre <b><span class="uicontrol"> População total</span></b> ou <b><span class="uicontrol"> População em tempo real</span></b>. A diferença é explicada no <a href="../../faq/faq-reporting.md"> Perguntas frequentes sobre relatórios</a> . </p> </td>
  </tr>
 </tbody>
</table>

É possível selecionar uma característica de conversão específica para a qual gerar o relatório ou selecionar todas as características combinadas. Você pode definir um intervalo de datas para o qual as informações devem ser retornadas e exportar o relatório como um [!DNL CSV] arquivo.

>[!NOTE]
>
>* Os relatórios de um grupo de teste serão preenchidos no dia seguinte à data de início.
>* Uma conversão só é contada para um dispositivo após a data de início de um teste e após o dispositivo ter sido adicionado a um segmento de teste. Se ocorrer uma conversão para esse dispositivo antes de ele receber um grupo de teste, a conversão não será contada.


Um retornado **[!UICONTROL Aggregate Reporting]** o gráfico pode ter esta aparência:

![](assets/aggregate-reporting.PNG)

Um retornado **[!UICONTROL Trend Reporting]** O gráfico pode ser semelhante ao mostrado abaixo. Selecionar **[!UICONTROL Normalized]** na caixa de seleção se desejar ignorar os números absolutos e simplesmente se concentrar nas tendências de segmentos de teste.

![](assets/trend-reporting.PNG)
