---
description: Os clientes do serviço de ID devem consultar esta seção para obter informações sobre como ler o cookie do visitante para as IDs necessárias para fazer chamadas de API DCS.
seo-description: Os clientes do serviço de ID devem consultar esta seção para obter informações sobre como ler o cookie do visitante para as IDs necessárias para fazer chamadas de API DCS.
seo-title: Obter IDs de usuário e regiões por meio do serviço da Experience Cloud ID
solution: Audience Manager
title: Obter IDs de usuário e regiões por meio do serviço da Experience Cloud ID
uuid: 80 de 6 cf 2-5 d 9 e -4 ef 8-a 0 f 2-d 53 b 5 d 574 c 89
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Get User IDs and Regions Through the Experience Cloud ID Service {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

ID service customers should refer to this section for information on how to read the visitor cookie for the IDs required to make [!UICONTROL DCS] API calls.

## Get the User ID from the ID Service Cookie {#get-user-ids-from-service-cookie}

The [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/) assigns visitor and region IDs to users who come to your website. These IDs identify users across all the solutions in the [!DNL Experience Cloud] and they are required if you want to make [!UICONTROL DCS] calls.

* The [!UICONTROL user ID] is required to identify and associate data with a particular visitor.
* The [!UICONTROL region ID] is required because it is tied to a regional server name, which you need to send data to the [!UICONTROL DCS]. The [!UICONTROL DCS] stores information in data centers that are geographically closest to site visitors. Consulte [IDs da região do DCS, locais e nomes de host](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

Os clientes do serviço de ID podem extrair essas informações do cookie do serviço de ID ou chamando uma função. A tabela abaixo descreve as tarefas ou etapas que você precisa concluir para começar.

Code in *italics* represents a variable placeholder.

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tarefa </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. Check your <span class="keyword"> Experience Cloud</span> status</b> </p> </td> 
   <td colname="col2"> <p>You need a <span class="keyword"> Experience Cloud</span> account to use the ID service. If you have a <span class="keyword"> Experience Cloud</span> account, great! </p> <p> If you're not part of the <span class="keyword"> Experience Cloud</span>, then sign up. Adoraríamos tê-lo e há sempre espaço para mais. For instructions on how to set up an account, see <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=core_services.html" format="https" scope="external"> Core Services - Enabling Your Solutions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Set up the <span class="keyword"> ID service</span></b> </p> </td> 
   <td colname="col2"> <p>The <span class="keyword"> ID service</span> consists of JavaScript code that gets put on each page you want to use for data collection. See the ID service <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html" format="https" scope="external"> implementation guides</a> for more information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Read the <span class="keyword"> ID service</span> cookie</b> </p> </td> 
   <td colname="col2"> <p>The <span class="keyword"> ID service</span> stores the user and region ID in the AMCV cookie. The full cookie name is <code>AMCV_<i>###</i>@AdobeOrg</code>. The <code><i>###</i></code> elements are placeholders for your organization ID. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a> for details. </p> <p>Analise o cookie AMCV para estes pares de valor chave: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid =<i>ID do usuário</i></code>: Esse par de valor chave contém a ID de usuário <span class="keyword"> da Experience Cloud</span> . </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh =<i>ID da região</i></code>: Esse par de valor chave contém a ID da região (às vezes chamada de dica <span class="term"> de localização</span>) associada a um nome de servidor regional. </li> 
     </ul> </p> <p>You can make calls to the <span class="wintitle"> DCS</span> once you have the user and region IDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Retrieve the <span class="keyword"> Experience Cloud ID</span> with getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(Opcional)</i> Essa função retorna a <span class="keyword"> ID</span> de visitante da Experience Cloud. Ela foi projetada para soluções personalizadas e casos de uso específicos. See <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Working With getMarketingCloudVisitorID</a> below and the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-getmcvid.html" format="https" scope="external"> related ID service documentation</a>. </p> <p>Não é necessário usar isso se você obter IDs de usuário e local do cookie do serviço de ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Working With `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Another way to get the visitor ID is with the `getMarketingCloudVisitorID` function. When invoked, this function queries the [!DNL ID service] and returns an ID. `getMarketingCloudVisitorID` aceita `callback` o argumento opcional, como mostrado:

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Callback Usage and Purpose {#callback-usage}

`callback` é opcional. This function works without it, but returns an ID only when a visitor has a [!DNL Experience Cloud] cookie in their browser. If the visitor cookie is missing, or a visitor doesn't have an ID, the function returns an empty `()` object. Isso pode ocorrer mesmo depois que a página é carregada e o visitante recebe uma nova ID. To avoid this, `callback` forces this function to check for a visitor ID after the page loads. Without `callback`, the visitor ID function won't return an ID even if it's written to the visitor's browser later.

## Próximas etapas {#next-steps}

Once you have the user and region ID, you can start sending and receiving [!UICONTROL DCS] data. See [Making DCS API Calls](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).