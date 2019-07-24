---
description: Comece aqui para obter informações sobre como fazer chamadas de /event para o DCS. Esta seção inclui informações sobre sintaxe de chamada, parâmetros, formatação e um exemplo de solicitação.
seo-description: Comece aqui para obter informações sobre como fazer chamadas de /event para o DCS. Esta seção inclui informações sobre sintaxe de chamada, parâmetros, formatação e um exemplo de solicitação.
seo-title: Enviar dados para o DCS
solution: Audience Manager
title: Enviar dados para o DCS
uuid: 024 e 307 d-bfcb -46 cf-ac 3 a-fc 71 df 0248 fe
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Send Data to the DCS {#send-data-to-the-dcs}

Start here for information about making `/event` calls to the [!UICONTROL DCS]. Esta seção inclui informações sobre sintaxe de chamada, parâmetros, formatação e um exemplo de solicitação.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Substitute a real value for the placeholder when you send data to the [!UICONTROL DCS] with this method.

## Call Syntax {#dcs-call-syntax}

A basic `URL` string that sends data to the [!UICONTROL DCS] uses the syntax shown below.

<pre><code>https://domain alias.demdex.net/event<i></i>?<i>key 1</i>=<i>val 1</i>, &amp;<i>key 2</i>=<i>val 2</i>&amp; d_ dst = 1 &amp; d_ rtbd = json &amp; d_ cb =<i>callback</i></code>
</pre>

>[!NOTE]
>
>You can also send data to the [!UICONTROL DCS] by using the `POST` method. The call syntax is described in [DCS API Methods](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md).

## Call Parameters {#dcs-call-parameters}

The following table defines the basic components of a simple [!UICONTROL DCS] call.

<table id="table_5F6A5B324EB848168543386516FBF384"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Componente </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> domínio alias. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>Essa parte da chamada contém: </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Your domain alias assigned by <span class="keyword"> Audience Manager</span> (e.g., <code> my_domain.demdex.net</code>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">The destination domain, which is always <code> demdex.net</code>. Consulte <a href="../../../reference/demdex-calls.md">Compreender as chamadas para o domínio Demdex</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Esta parte da chamada: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifica a chamada como uma chamada de evento. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Defines the start of the URL string that contains the data you want to send to the <span class="wintitle"> DCS</span>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>Um identificador exclusivo no par de valor chave. </p> <p>These key-value pairs use a specific prefix to identify the type of data you're sending to the <span class="wintitle"> DCS</span>. For more information, see <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Supported Attributes for DCS API Calls</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>Um valor de variável que pertence a um conjunto definido por uma chave no par de valor chave. </p> <p>Ao trabalhar com valores: </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">Enclose string data in double quotes (e.g., <code> age="41 to 55"</code>). </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">You can pass multiple keys in on a single value (e.g., <i><code>key</i>=<i>val1,val2,val3</i></code></i>). </i></li> 
     </ul> </p> <p>See <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> Formatting Key-Value Pairs in DCS Calls</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_ dst = 1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_ rtbd = json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_ cb =<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>Parâmetros de resposta opcionais. </p> <p> None of these are required to send data to the <span class="wintitle"> DCS</span>. However, if you want the <span class="wintitle"> DCS</span> to return a response, you must include <code> d_rtbd=json</code> in your request. </p> <p>See <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> d_ Key-Value Pairs Defined</a>. </p> </td> 
  </tr>
 </tbody>
</table>

## Sample Call {#dcs-sample-call}

This example shows the fictional company [!DNL Acme, Inc.] sending data to the [!UICONTROL DCS] via an HTTP call. Note that this call includes the optional parameters `d_dst=1`, `d_rtbd=json`, and `d_cb=callback`. These indicate that [!DNL Acme] wants to receive a [!DNL JSON] response from the [!UICONTROL DCS] with a call back function. Lembre-se, isso é apenas um exemplo. Não recorte e cole esse código.

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

## Próximas etapas {#dcs-next-steps}

Now that you're familiar with sending data to the [!UICONTROL DCS], it's time to look at how to get data back from it and parse that information. See [Receive Data From the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

>[!MORE_ LIKE_ THIS]
>
>* [Pares de valores chave explicados](../../../reference/key-value-pairs-explained.md)

