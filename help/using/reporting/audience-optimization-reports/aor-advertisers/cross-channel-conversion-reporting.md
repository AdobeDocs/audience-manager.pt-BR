---
description: A opção de Conversão entre canais no relatório Audience Optimization permite que você atribua conversões offline para impressões online ou cliques.
seo-description: The Cross Channel Conversion option in the Audience Optimization reports allows you to attribute offline conversions to served online impressions or clicks.
seo-title: Cross Channel Conversion
solution: Audience Manager
title: Conversão entre canais
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: Audience Optimization Reports
exl-id: 7412a43f-81b5-477e-8acf-89d6c8661f1e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%

---

# Conversão entre canais{#cross-channel-conversion}

A opção de Conversão entre canais no relatório Audience Optimization permite que você atribua conversões offline para impressões online ou cliques.

Os relatórios [!UICONTROL Cross Channel Conversion] combinam resultados da plataforma [!DNL Google Campaign Manager] com [!DNL Audience Manager] características de conversão. Isso permite vincular conversões offline a impressões online ou cliques.

Você pode usar a [!UICONTROL Cross Channel Conversion] para os relatórios de [Desempenho do segmento](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) e [Frequência ideal](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md).

Para exibir os relatórios de [!UICONTROL Cross Channel Conversion], selecione o item **[!UICONTROL AAM + Ad Server Name]** na lista suspensa **[!UICONTROL Platform]**.

A tabela a seguir lista considerações importantes ao configurar o [!UICONTROL Cross Channel Conversion]:

<table id="table_62590B4AB7624B619EC9AA8FF89722C9"> 
 <thead> 
  <tr> 
   <th class="entry"> Consideração </th> 
   <th class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>Número mínimo de características de conversão </p> </td> 
   <td colname="col1"> <p>Pelo menos uma característica de conversão deve ser atribuída a uma fonte de dados para que os relatórios de <span class="wintitle"> Conversão entre Canais</span> sejam executados. Consulte <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Informações básicas sobre características</a> para obter mais informações sobre características. </p> </td> 
  </tr>
  <tr> 
   <td> <p>Janela Atribuição </p> </td> 
   <td> <p> <b><span class="uicontrol"> A janela de atribuição AAM+Google Campaign Manager</span></b> é de 14 dias, o que significa que somente as características de conversão exibidas nas últimas duas semanas são consideradas. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Metodologia de último contato </p> </td> 
   <td> <p>O criativo que o usuário viu por último antes da conversão é o que recebeu a conversão. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Cliques versus impressões </p> </td> 
   <td> <p>Um clique tem precedência sobre uma impressão ao decidir a atribuição se eles ocorrem exatamente ao mesmo tempo. Por exemplo, em uma página em que várias criações são exibidas, a que está sendo clicada recebe a conversão. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Recenticidade de dados </p> </td> 
   <td> <p>Os relatórios são sempre calculados para dados disponíveis no dia anterior. </p> </td> 
  </tr> 
 </tbody> 
</table>
