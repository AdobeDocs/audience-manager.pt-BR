---
description: Gere um relatório de faturamento Audience Marketplace para exibir o uso do feed de dados do mês anterior para cada um dos assinantes. Você pode criar um relatório para o mês anterior a qualquer momento. No entanto, o relatório é mais preciso ao gerá-lo no dia 10 ou depois do mês atual.
seo-description: Generate an Audience Marketplace billing report to view data feed usage for the previous month for each of your subscribers. You can create a report for the previous month at any time. However, the report is more accurate when you generate it on or after the 10th day of the current month.
seo-title: Billing for Data Feed Providers
solution: Audience Manager
title: Faturamento para provedores de feeds de dados
uuid: 4e11dbd2-91fd-4b59-a66d-86a92e0de655
feature: Audience Marketplace
exl-id: aca2cec1-d3a0-421c-83ca-1c11e9e7d4c7
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 5%

---

# Faturamento para provedores de feeds de dados {#billing-for-data-feed-providers}

Gerar um [!DNL Audience Marketplace] relatório de faturamento para visualizar o uso do feed de dados do mês anterior para cada um de seus assinantes. Você pode criar um relatório para o mês anterior a qualquer momento. No entanto, o relatório é mais preciso ao gerá-lo no dia 10 ou depois do mês atual.

## Baixar um relatório de faturamento {#download-billing-report}

Para baixar um relatório:

1. Ir para **[!UICONTROL Audience Marketplace > Receivables]**.
1. Clique em **[!UICONTROL Generate Billing Report]**.

## Campos de Relatório Definidos {#report-fields-defined}

Um relatório de faturamento contém as informações a seguir.

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
   <td colname="col2"> <p>Seu <span class="keyword"> Audience Manager</span> ID do provedor de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nome do provedor de dados</span></b> </p> </td> 
   <td colname="col2"> <p>O nome da sua empresa ou organização. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> PID do comprador</span></b> </p> </td> 
   <td colname="col2"> <p>ID do comprador (assinante). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nome do Comprador</span></b> </p> </td> 
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
   <td colname="col1"> <p><b><span class="uicontrol"> Planejar casos de uso</span></b> </p> </td> 
   <td colname="col2"> <p>Os casos de uso permitem que os vendedores controlem como os compradores usam os dados. As opções incluem: </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">Segmentos e sobreposição </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">Modelagem </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">Ativação </li> 
    </ul> <p>Consulte <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types"> Tipos de plano para feeds de dados</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Unidade de Medida</span></b> </p> </td> 
   <td colname="col2"> <p>Indica o CPM ou faturamento de taxa fixa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Preço de Lista</span></b> </p> </td> 
   <td colname="col2"> <p>A taxa de subscrição para cada feed de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Preço com desconto</span></b> </p> </td> 
   <td colname="col2"> <p>A taxa de subscrição de um feed de dados com desconto. Consulte <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> Descontos para provedores de dados</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Unidades</span></b> </p> </td> 
   <td colname="col2"> <p>Varia por tipo de preço de feed: </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">Feeds de dados de taxa fixa: retorna apenas 1. </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">Feeds de dados do CPM: retorna a quantidade de uso real dos feeds de dados do CPM. Se um assinante não tiver fornecido dados de impressão para um feed do CPM, a célula Unidades estará vazia e a célula Sinalizador será definida como 1. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Custo Total</span></b> </p> </td> 
   <td colname="col2"> <p>O valor <span class="keyword"> Audience Manager</span> fatura um comprador. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Período de Cobrança</span></b> </p> </td> 
   <td colname="col2"> <p> No relatório, este é o último dia do mês anterior. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Data de entrada</span></b> </p> </td> 
   <td colname="col2"> <p>A data em que um comprador inseriu informações de uso/subscrição. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Data de início da assinatura</span></b> </p> </td> 
   <td colname="col2"> <p>A data em que um comprador iniciou sua assinatura do feed de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Data de término da assinatura</span></b> </p> </td> 
   <td colname="col2"> <p>A data em que um comprador encerrou a assinatura do feed de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Sinalizador</span></b> </p> </td> 
   <td colname="col2"> <p> <i>Somente para feeds CPM</i>. As opções de sinalizador incluem: </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0: Indica que um assinante relatou informações de uso a <span class="keyword"> Audience Manager</span>. </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1: Indica que um assinante não relatou informações de uso a <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Alocação de impressão e cobrança para feeds de dados do CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [Alocação de impressão e cobrança para feeds de dados de taxa fixa](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [Como relatar o uso do CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)

