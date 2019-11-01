---
description: Comece aqui para obter informações sobre como fazer chamadas /event para o DCS. Esta seção inclui informações sobre sintaxe de chamada, parâmetros, formatação e um exemplo de solicitação.
seo-description: Comece aqui para obter informações sobre como fazer chamadas /event para o DCS. Esta seção inclui informações sobre sintaxe de chamada, parâmetros, formatação e um exemplo de solicitação.
seo-title: Enviar dados para o DCS
solution: Audience Manager
title: Enviar dados para o DCS
uuid: 024e307d-bfcb-46cf-ac3a-fc71df0248fe
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Enviar dados para o DCS {#send-data-to-the-dcs}

Comece aqui para obter informações sobre como fazer `/event` chamadas para o [!UICONTROL DCS]. Esta seção inclui informações sobre sintaxe de chamada, parâmetros, formatação e um exemplo de solicitação.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Substitua um valor real do espaço reservado quando você envia dados para o [!UICONTROL DCS] com este método.

## Sintaxe de chamada {#dcs-call-syntax}

Uma `URL` string básica que envia dados para o [!UICONTROL DCS] usuário usa a sintaxe mostrada abaixo.

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>Também é possível enviar dados para o [!UICONTROL DCS] usando o `POST` método. A sintaxe de chamada é descrita em Métodos [de API](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)DCS.

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
   <td colname="col1"> <p> <code> domain alias.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Esta parte da chamada contém: </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Seu alias de domínio atribuído pelo <span class="keyword"> Audience Manager</span> (por exemplo, <code> my_domain.demdex.net</code>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">O domínio de destino, que é sempre <code> demdex.net</code>. Consulte <a href="../../../reference/demdex-calls.md">Compreender as chamadas para o domínio Demdex</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Esta parte da chamada: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifica a chamada como uma chamada de evento. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Define o início da string de URL que contém os dados que você deseja enviar para o <span class="wintitle"> DCS</span>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>Um identificador exclusivo no par de chave-valor. </p> <p>Esses pares de valores chave usam um prefixo específico para identificar o tipo de dados que você está enviando ao <span class="wintitle"> DCS</span>. For more information, see <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Supported Attributes for DCS API Calls</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>Um valor de variável que pertence a um conjunto definido por uma chave no par de valores chave. </p> <p>Ao trabalhar com valores: </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">Inclua dados de sequência de caracteres entre aspas duplas (por exemplo, <code> age="41 to 55"</code>). </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">Você pode passar várias teclas em um único valor (por exemplo, <i><code>key</i>=<i>val1,val2,val3</i></code></i>). </li> 
     </ul> </p> <p>Consulte <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> Formatação de pares de valores chave em chamadas</a>DCS. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_cb=<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>Parâmetros de resposta opcionais. </p> <p> Nenhum deles é necessário para enviar dados para o <span class="wintitle"> DCS</span>. No entanto, se você quiser que o <span class="wintitle"> DCS</span> retorne uma resposta, é necessário incluir <code> d_rtbd=json</code> na solicitação. </p> <p>Consulte <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> d_ Key-Value Pairs Definidos</a>. </p> </td> 
  </tr>
 </tbody>
</table>

## Chamada de exemplo {#dcs-sample-call}

Este exemplo mostra a empresa ficcional [!DNL Acme, Inc.] enviando dados para o [!UICONTROL DCS] por meio de uma [!DNL HTTP] chamada. Observe que esta chamada inclui os parâmetros opcionais `d_dst=1`, `d_rtbd=json`e `d_cb=callback`. Isso indica que [!DNL Acme] deseja receber uma [!DNL JSON] resposta do [!UICONTROL DCS] com uma função de retorno de chamada. Lembrem-se, isto é apenas um exemplo. Não recorte e cole este código.

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## Próximas etapas {#dcs-next-steps}

Agora que vocês estão familiarizados com o envio de dados para o [!UICONTROL DCS], é hora de olhar como obter dados de volta e analisar essa informação. Consulte [Receber dados do DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

>[!MORELIKETHIS]
>
>* [Explicação dos pares de valor-chave](../../../reference/key-value-pairs-explained.md)

