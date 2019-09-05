---
description: Comece aqui para obter informações sobre como fazer chamadas de /event para o DCS. Esta seção inclui informações sobre sintaxe de chamada, parâmetros, formatação e um exemplo de solicitação.
seo-description: Comece aqui para obter informações sobre como fazer chamadas de /event para o DCS. Esta seção inclui informações sobre sintaxe de chamada, parâmetros, formatação e um exemplo de solicitação.
seo-title: Enviar dados para o DCS
solution: Audience Manager
title: Enviar dados para o DCS
uuid: 024 e 307 d-bfcb -46 cf-ac 3 a-fc 71 df 0248 fe
translation-type: tm+mt
source-git-commit: bc2a9364b771436fe0191f9d69a8c291563f9229

---


# Enviar dados para o DCS {#send-data-to-the-dcs}

Comece aqui para obter informações sobre como fazer `/event` chamadas para o [!UICONTROL DCS]. Esta seção inclui informações sobre sintaxe de chamada, parâmetros, formatação e um exemplo de solicitação.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Substitua um valor real para o espaço reservado ao enviar dados para o método [!UICONTROL DCS] com este método.

## Sintaxe de chamada {#dcs-call-syntax}

Uma `URL` string básica que envia dados para o [!UICONTROL DCS] uso a sintaxe mostrada abaixo.

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>Também é possível enviar dados para o [!UICONTROL DCS] uso do `POST` método. A sintaxe de chamada é descrita em [Métodos de API DCS](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md).

## Parâmetros de chamada {#dcs-call-parameters}

A tabela a seguir define os componentes básicos de uma [!UICONTROL DCS] chamada simples.

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
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Seu alias de domínio atribuído pelo <span class="keyword"> Audience Manager</span> (por exemplo <code> , my_ domain. demdex. net</code>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">O domínio de destino, que é sempre <code> demdex. net</code>. Consulte <a href="../../../reference/demdex-calls.md">Compreender as chamadas para o domínio Demdex</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Esta parte da chamada: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifica a chamada como uma chamada de evento. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Define o início da sequência de caracteres de URL que contém os dados que você deseja enviar para o <span class="wintitle"> DCS</span>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>Um identificador exclusivo no par de valor chave. </p> <p>Esses pares de valor chave usam um prefixo específico para identificar o tipo de dados que você está enviando para o <span class="wintitle"> DCS</span>. For more information, see <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Supported Attributes for DCS API Calls</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>Um valor de variável que pertence a um conjunto definido por uma chave no par de valor chave. </p> <p>Ao trabalhar com valores: </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">Declose string os dados entre aspas duplas (por exemplo <code> , idade = "41 a 55"</code>). </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">Você pode passar várias teclas em um único valor (por exemplo <i><code>, key</i>=<i>val 1, val 2, val 3</i></code></i>). </i></li> 
     </ul> </p> <p>Consulte <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> Formatação de pares de valores chave em chamadas DCS</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_ dst = 1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_ rtbd = json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_ cb =<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>Parâmetros de resposta opcionais. </p> <p> Nenhum desses dados é necessário para enviar dados para <span class="wintitle"> o DCS</span>. No entanto, se você quiser que <span class="wintitle"> o DCS</span> retorne uma resposta, deverá incluir <code> d_ rtbd = json</code> em sua solicitação. </p> <p>Consulte <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> d_ Key-Value Pares definidos</a>. </p> </td> 
  </tr>
 </tbody>
</table>

## Chamada de exemplo {#dcs-sample-call}

Este exemplo mostra a empresa fictícia [!DNL Acme, Inc.] que envia dados para a [!UICONTROL DCS] chamada por meio de [!DNL HTTP] uma chamada. Observe que esta chamada inclui os parâmetros `d_dst=1`opcionais, `d_rtbd=json`e `d_cb=callback`. Eles indicam que [!DNL Acme] desejam receber [!DNL JSON] uma resposta da função [!UICONTROL DCS] de retorno de chamada. Lembre-se, isso é apenas um exemplo. Não recorte e cole esse código.

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```
## Próximas etapas {#dcs-next-steps}

Agora que você está familiarizado com o envio de dados para o [!UICONTROL DCS], é hora de saber como obter os dados de volta e analisar essas informações. Consulte [Receber dados do DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

>[!MORE_ LIKE_ THIS]
>
>* [Pares de valores chave explicados](../../../reference/key-value-pairs-explained.md)

