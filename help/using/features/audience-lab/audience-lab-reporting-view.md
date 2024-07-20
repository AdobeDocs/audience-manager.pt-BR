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
source-wordcount: '337'
ht-degree: 0%

---

# Relatórios do grupo de teste {#test-group-reporting}

A seção de relatórios do grupo de teste retorna informações sobre as conversões do grupo de teste, permitindo uma fácil comparação da eficácia do segmento de teste. Vários filtros e dimensões estão disponíveis para visualização de dados.

[!UICONTROL Audience Lab] retorna informações detalhadas sobre relatórios para os segmentos de teste que você criou e permite salvar os dados de relatório como arquivos [!DNL CSV]. Você pode selecionar entre **[!UICONTROL Aggregate Reporting]** e **[!UICONTROL Trend Reporting]**.

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
   <td colname="col1"> <p> <b><span class="uicontrol"> Taxa de Conversão da População</span></b> </p> </td> 
   <td colname="col2"> <p>Retorna o percentual de dispositivos pertencentes a um segmento de teste específico, que foram convertidos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Conversores</span></b> </p> </td> 
   <td colname="col2"> <p>Retorna o número de dispositivos que exibiram as características de conversão selecionadas nos grupos de teste. <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> Assista a este vídeo </a> para saber como criar características de conversão. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Total de conversões</span></b> </p> </td> 
   <td colname="col2"> <p>Retorna o número de conversões geradas pelos segmentos de teste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Populações de segmentos de teste</span></b> </p> </td> 
   <td colname="col2"> <p>Retorna o número de dispositivos pertencentes aos segmentos de teste. Alternar entre <b><span class="uicontrol"> População Total</span></b> ou <b><span class="uicontrol"> População em Tempo Real</span></b>. A diferença é explicada nas <a href="../../faq/faq-reporting.md"> Perguntas frequentes sobre relatórios</a>. </p> </td>
  </tr>
 </tbody>
</table>

É possível selecionar uma característica de conversão específica para a qual gerar o relatório ou selecionar todas as características combinadas. Você pode definir um intervalo de datas para o qual as informações devem ser retornadas e exportar o relatório como um arquivo [!DNL CSV].

>[!NOTE]
>
>* Os relatórios de um grupo de teste serão preenchidos no dia seguinte à data de início.
>* Uma conversão só é contada para um dispositivo após a data de início de um teste e após o dispositivo ter sido adicionado a um segmento de teste. Se ocorrer uma conversão para esse dispositivo antes de ele receber um grupo de teste, a conversão não será contada.

Um gráfico **[!UICONTROL Aggregate Reporting]** retornado pode ter esta aparência:

![](assets/aggregate-reporting.PNG)

Um gráfico **[!UICONTROL Trend Reporting]** retornado pode ter a aparência abaixo. Marque **[!UICONTROL Normalized]** na caixa de seleção se desejar ignorar os números absolutos e simplesmente se concentrar nas tendências de segmentos de teste.

![](assets/trend-reporting.PNG)
