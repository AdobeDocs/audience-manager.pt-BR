---
description: A opção Conversão entre canais nos relatórios de Otimização de público-alvo permite atribuir conversões offline para impressões online ou cliques.
seo-description: A opção Conversão entre canais nos relatórios de Otimização de público-alvo permite atribuir conversões offline para impressões online ou cliques.
seo-title: Conversão entre canais
solution: Audience Manager
title: Conversão entre canais
uuid: 0 fecec 23-e 502-490 b-b 7 dd -47 a 3753 a 3 f 75
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Conversão entre canais{#cross-channel-conversion}

A opção Conversão entre canais nos relatórios de Otimização de público-alvo permite atribuir conversões offline para impressões online ou cliques.

[!UICONTROL Cross Channel Conversion] Os relatórios combinam resultados da plataforma [!DNL DoubleClick Campaign Manager] (DCM) com características [!DNL Audience Manager] de conversão. Isso permite vincular conversões offline a impressões online ou cliques.

You can use the [!UICONTROL Cross Channel Conversion] for the [Segment Performance](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) and [Optimal Frequency](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) reports.

To view the [!UICONTROL Cross Channel Conversion] reports, select the **[!UICONTROL AAM+DCM]** item in the **[!UICONTROL Platform]** drop-down list.

The following table lists important considerations when setting up [!UICONTROL Cross Channel Conversion]:

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
   <td colname="col1"> <p>At least one conversion trait must be assigned to a data source in order for the <span class="wintitle"> Cross Channel Conversion</span> reports to run. See <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Basic Information for Traits</a> for more information on traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>Número máximo de características de conversão </p> </td> 
   <td colname="col1"> <p>The reports pull in a <i>maximum</i> of 50 conversion traits from the user. Se você atingir o máximo, os relatórios usarão as primeiras 50 características de conversão com base na ID de característica, em ordem crescente. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Janela de atribuição </p> </td> 
   <td> <p> <b><span class="uicontrol"> A janela</span></b> de atribuição AAM + DCM é de 14 dias, o que significa que apenas as características de conversão exibidas nas últimas duas semanas são consideradas. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Metodologia do último toque </p> </td> 
   <td> <p>O anúncio visto por último pelo usuário antes da conversão é aquele que recebe a conversão. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Cliques versus impressões </p> </td> 
   <td> <p>Um clique tem precedência sobre uma impressão ao decidir a atribuição se ocorrer ao mesmo tempo. Por exemplo, em uma página em que várias criações são exibidas, a conversão clicada recebe a conversão. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Idade dos dados </p> </td> 
   <td> <p>Os relatórios são sempre calculados para dados disponíveis no dia anterior. </p> </td> 
  </tr> 
 </tbody> 
</table>
