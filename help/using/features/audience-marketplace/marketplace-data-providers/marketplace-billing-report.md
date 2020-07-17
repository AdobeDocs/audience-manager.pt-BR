---
description: Gere um relatório de faturamento de Audience Marketplace para a utilização do feed de dados de visualização para o mês anterior para cada um dos seus assinantes. Você pode criar um relatório para o mês anterior a qualquer momento. No entanto, o relatório é mais preciso quando você o gera no dia 10 do mês atual ou após ele.
seo-description: Gere um relatório de faturamento de Audience Marketplace para a utilização do feed de dados de visualização para o mês anterior para cada um dos seus assinantes. Você pode criar um relatório para o mês anterior a qualquer momento. No entanto, o relatório é mais preciso quando você o gera no dia 10 do mês atual ou após ele.
seo-title: Faturamento para provedores de feeds de dados
solution: Audience Manager
title: Faturamento para provedores de feeds de dados
topic: DIL API
uuid: 4e11dbd2-91fd-4b59-a66d-86a92e0de655
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 5%

---


# Faturamento para provedores de feeds de dados {#billing-for-data-feed-providers}

Gere um relatório de [!DNL Audience Marketplace] faturamento para a utilização do feed de dados de visualização para o mês anterior para cada um dos seus assinantes. Você pode criar um relatório para o mês anterior a qualquer momento. No entanto, o relatório é mais preciso quando você o gera no dia 10 do mês atual ou após ele.

## Download de um Relatório de cobrança {#download-billing-report}

Para baixar um relatório:

1. Vá para **[!UICONTROL Audience Marketplace > Receivables]**.
1. Clique em **[!UICONTROL Generate Billing Report]**.

## Campos de relatório definidos {#report-fields-defined}

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
   <td colname="col2"> <p>Nome da sua empresa ou organização. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> PID do comprador</span></b> </p> </td> 
   <td colname="col2"> <p>ID do comprador (assinante). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nome do comprador</span></b> </p> </td> 
   <td colname="col2"> <p>A empresa do comprador ou o nome da organização. </p> </td> 
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
    </ul> <p>Consulte <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types"> Tipos de plano para feeds</a>de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Unidade de Medida</span></b> </p> </td> 
   <td colname="col2"> <p>Indica cobranças de CPM ou de taxa fixa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Preço Lista</span></b> </p> </td> 
   <td colname="col2"> <p>A taxa de subscrição para cada feed de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Preço Descontado</span></b> </p> </td> 
   <td colname="col2"> <p>A taxa de subscrição para um feed de dados com desconto. Consulte <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> Descontos para provedores</a>de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Unidades</span></b> </p> </td> 
   <td colname="col2"> <p>Varia por tipo de preço do feed: </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">Feeds de dados de taxa fixa: Retorna apenas 1. </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">Feeds de dados do CPM: Retorna o valor de uso real para feeds de dados CPM. Se um assinante não tiver fornecido dados de impressão para um feed CPM, a célula Unidades estará vazia e a célula Sinalizar será definida como 1. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Custo total</span></b> </p> </td> 
   <td colname="col2"> <p>A quantia <span class="keyword"> de Audience Manager</span> paga um comprador. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Período de Faturamento</span></b> </p> </td> 
   <td colname="col2"> <p> No relatório, este é o último dia do mês anterior. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Data de entrada</span></b> </p> </td> 
   <td colname="col2"> <p>A data em que um comprador inseriu informações de subscrição/uso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Data do Start da Subscrição</span></b> </p> </td> 
   <td colname="col2"> <p>A data em que um comprador iniciou sua subscrição de feed de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Data final da Subscrição</span></b> </p> </td> 
   <td colname="col2"> <p>A data em que um comprador terminou sua subscrição de feed de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Sinalizador</span></b> </p> </td> 
   <td colname="col2"> <p> <i>Somente</i>para feeds CPM. As opções de sinalizador incluem: </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0: Indica que um assinante reportou informações de uso ao <span class="keyword"> Audience Manager</span>. </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1: Indica que um assinante não reportou informações de uso ao <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Alocação de Faturamento e Impressão para Feeds de Dados CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [Alocação de Faturamento e Impressão para Feeds de Dados de Taxa Simples](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [Como informar o uso do CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)

