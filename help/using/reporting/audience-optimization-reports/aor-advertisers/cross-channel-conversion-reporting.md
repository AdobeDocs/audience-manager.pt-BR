---
description: A opção Conversão entre Canais nos relatórios de Otimização de Audiência permite que você atribua conversões offline a impressões ou cliques online oferecidos.
seo-description: A opção Conversão entre Canais nos relatórios de Otimização de Audiência permite que você atribua conversões offline a impressões ou cliques online oferecidos.
seo-title: Conversão entre canais
solution: Audience Manager
title: Conversão entre canais
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 4%

---


# Conversão entre canais{#cross-channel-conversion}

A opção Conversão entre Canais nos relatórios de Otimização de Audiência permite que você atribua conversões offline a impressões ou cliques online oferecidos.

Os [!UICONTROL Cross Channel Conversion] relatórios combinam os resultados da plataforma [!DNL DoubleClick Campaign Manager] (DCM) com as características de [!DNL Audience Manager] conversão. Isso permite vincular conversões offline a impressões ou cliques online.

Você pode usar o [!UICONTROL Cross Channel Conversion] para os relatórios Desempenho [do](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) segmento e Frequência [](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) ideal.

Para visualização dos [!UICONTROL Cross Channel Conversion] relatórios, selecione o **[!UICONTROL AAM+DCM]** item na lista **[!UICONTROL Platform]** suspensa.

A tabela a seguir lista considerações importantes ao configurar [!UICONTROL Cross Channel Conversion]:

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
   <td colname="col1"> <p>Pelo menos uma característica de conversão deve ser atribuída a uma fonte de dados para que os relatórios de Conversão <span class="wintitle"></span> entre Canais sejam executados. Consulte Informações <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> básicas sobre características</a> para obter mais informações sobre características. </p> </td> 
  </tr>
  <tr> 
   <td> <p>Janela de atribuição </p> </td> 
   <td> <p> <b><span class="uicontrol"> A janela de atribuição AAM+DCM</span></b> é de 14 dias, o que significa que somente as características de conversão exibidas nas últimas duas semanas são consideradas. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Metodologia de último toque </p> </td> 
   <td> <p>O anúncio que o usuário viu por último antes da conversão é aquele que recebeu a conversão. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Cliques versus impressões </p> </td> 
   <td> <p>Um clique tem precedência sobre uma impressão ao decidir a atribuição se ela ocorrer ao mesmo tempo. Por exemplo, em uma página onde várias criações são exibidas, a que está sendo clicada recebe a conversão. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Recência de dados </p> </td> 
   <td> <p>Os relatórios são sempre calculados para os dados disponíveis no dia anterior. </p> </td> 
  </tr> 
 </tbody> 
</table>
