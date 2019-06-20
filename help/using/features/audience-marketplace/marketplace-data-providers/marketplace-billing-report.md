---
description: Gere um relatório de cobrança do Audience Marketplace para exibir o uso do feed de dados do mês anterior para cada um dos assinantes. Você pode criar um relatório para o mês anterior a qualquer momento. No entanto, o relatório é mais preciso quando você o gera em ou após o 10 º dia do mês atual.
seo-description: Gere um relatório de cobrança do Audience Marketplace para exibir o uso do feed de dados do mês anterior para cada um dos assinantes. Você pode criar um relatório para o mês anterior a qualquer momento. No entanto, o relatório é mais preciso quando você o gera em ou após o 10 º dia do mês atual.
seo-title: Faturamento para provedores de feed de dados
solution: Audience Manager
title: Faturamento para provedores de feed de dados
topic: API DIL
uuid: 4 e 11 dbd 2-91 fd -4 b 59-a 66 d -86 a 92 e 0 de 655
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Billing for Data Feed Providers {#billing-for-data-feed-providers}

Generate an [!DNL Audience Marketplace] billing report to view data feed usage for the previous month for each of your subscribers. Você pode criar um relatório para o mês anterior a qualquer momento. No entanto, o relatório é mais preciso quando você o gera em ou após o 10 º dia do mês atual.

## Download a Billing Report {#download-billing-report}

Para baixar um relatório:

1. Go to **[!UICONTROL Audience Marketplace > Receivables]**.
1. Clique em **[!UICONTROL Generate Billing Report]**.

## Report Fields Defined {#report-fields-defined}

Um relatório de cobrança contém as seguintes informações.

<table id="table_B433D5059F6446068683E425B1D87520"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo de relatório </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> PID do provedor de dados</span></b> </p> </td> 
   <td colname="col2"> <p>Your <span class="keyword"> Audience Manager</span> data provider ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nome do provedor de dados</span></b> </p> </td> 
   <td colname="col2"> <p>Seu nome da empresa ou organização. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> PID do comprador</span></b> </p> </td> 
   <td colname="col2"> <p>ID do comprador (assinante). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nome do comprador</span></b> </p> </td> 
   <td colname="col2"> <p>O nome da empresa ou organização do comprador. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> ID do feed</span></b> </p> </td> 
   <td colname="col2"> <p>A ID do feed de dados </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nome do feed</span></b> </p> </td> 
   <td colname="col2"> <p>O nome do feed de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Casos de uso do plano</span></b> </p> </td> 
   <td colname="col2"> <p>Casos de uso permitem que os vendedores controlem como os compradores usam dados. As opções incluem: </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">Segmentos e sobreposição </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">Modelagem </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">Activation </li> 
    </ul> <p>See <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types"> Plan Types for Data Feeds</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Unidade de medida</span></b> </p> </td> 
   <td colname="col2"> <p>Indica o CPM ou cobrança fixa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Preço da lista</span></b> </p> </td> 
   <td colname="col2"> <p>A taxa de assinatura para cada feed de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Preço com desconto</span></b> </p> </td> 
   <td colname="col2"> <p>A taxa de assinatura para um feed de dados com desconto. See <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> Discounts for Data Providers</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Unidades</span></b> </p> </td> 
   <td colname="col2"> <p>Varia por tipo de preço do feed: </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">Feeds de dados de taxa simples: Retorna apenas 1. </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">Feeds de dados CPM: Retorna a quantia de uso real para feeds de dados CPM. Se um assinante não fornecer dados de impressão para um feed CPM, a célula Unidades estará vazia e a célula Sinalizar será definida como 1. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Custo total</span></b> </p> </td> 
   <td colname="col2"> <p>The amount <span class="keyword"> Audience Manager</span> bills a buyer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Período de faturamento</span></b> </p> </td> 
   <td colname="col2"> <p> No relatório, este é o último dia do mês anterior. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Data de entrada</span></b> </p> </td> 
   <td colname="col2"> <p>A data em que um comprador inseriu informações de assinatura/uso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Data de início da assinatura</span></b> </p> </td> 
   <td colname="col2"> <p>A data em que um comprador iniciou a assinatura do feed de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Data final da assinatura</span></b> </p> </td> 
   <td colname="col2"> <p>A data em que um comprador terminou a assinatura do feed de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Sinalizar</span></b> </p> </td> 
   <td colname="col2"> <p> <i>Apenas para feeds CPM</i>. As opções de sinalização incluem: </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0: Indicates a subscriber has reported usage information to <span class="keyword"> Audience Manager</span>. </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1: Indicates a subscriber has not reported usage information to <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Faturamento e alocação de impressão para feeds de dados CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [Faturamento e alocação de impressão para feeds de dados de taxa simples](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [Como relatar o uso de CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)

