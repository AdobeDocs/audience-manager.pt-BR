---
seo-title: Efetuar chamadas de API do servidor para servidor DCS
solution: Audience Manager
title: Efetuar chamadas de API do servidor para servidor DCS
uuid: bdfe 3430-e 27 f -4 a 5 c -88 d 9-ae 164 d 28 f 601
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Efetuar chamadas de API do servidor para servidor DCS {#making-server-to-server-dcs-api-calls}

As chamadas exigem o nome de host do servidor DCS regional e da ID do usuário. Se você não tiver as IDs de usuário e região necessárias, consulte [Obter IDs de usuário e Regiões de uma Resposta](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) DCS e/ou [Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md). Depois de ter IDs de usuário e região, você pode fazer chamadas de servidor para servidor para o DCS. Consulte esta seção para sintaxe e exemplos.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Substitua um valor real para o espaço reservado quando você chamar as chamadas [!UICONTROL DCS]do servidor para o servidor.

## Sintaxe de chamada e exemplo {#call-syntax-example}

Uma solicitação básica de servidor para servidor que envia dados para o [!UICONTROL DCS] uso a sintaxe mostrada abaixo.

<pre><code>" Host:<i>domínio alias</i>. demdex. net "https://DCS<i>host name.demdex.net/event?d_rtbd=json&amp;d_jsonv=1&amp;d_uuid=user</i><i>ID</i>.</code></pre>

Uma chamada de amostra é semelhante ao exemplo a seguir.

```
"Host:foo.demdex.net" "https://usw2.demdex.net/event?d_rtbd=json&d_jsonv=1& d_uuid=123456789"`
```

## Parâmetros de chamada {#call-parameters}

<table id="table_3AF4466009B64F0C9CBE7904A4096E0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code><i>domínio alias</i>. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>Essa parte da chamada contém: </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Seu alias de domínio atribuído pelo <span class="keyword"> Audience Manager</span> (por exemplo <i><code> , my_ domain. demdex. net</code></i>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">O domínio de destino, que é sempre <i><code> demdex. net</code></i>. Consulte <a href="../../../reference/demdex-calls.md">Compreender as chamadas para o domínio Demdex</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>Nome de host DCS</i>. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>O parâmetro host do cabeçalho http, que mostra o nome do servidor <span class="wintitle"> DCS</span> regional. O nome do host está vinculado a uma ID de região, por isso é necessário fazer isso antes de fazer esses tipos de chamadas. Consulte <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">IDs da região do DCS, locais e nomes de host</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Esta parte da chamada: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifica a chamada como uma chamada de evento. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Define o início da sequência de caracteres de URL que contém os dados que você deseja enviar para o DCS. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_ uuid = <i>ID de usuário do Audience Manager</i></code> </p> </td> 
   <td colname="col2"> <p>Essa é a única chave de ID de usuário que contém o valor da ID de usuário <span class="keyword"> do Audience Manager</span> em um par de valor chave. </p> <p>Use <code><i>d_ uuid</i></code> se estiver passando a <span class="keyword"> ID</span> de usuário do Audience Manager. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_ mid =<i>ID de usuário da Experience Cloud</i></code> </p> </td> 
   <td colname="col2"> <p>Essa é a única chave de ID de usuário que contém o valor da ID de usuário <span class="keyword"> da Experience Cloud</span> em um par de valor chave. Consulte <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> também Obter a ID de usuário do cookie de serviço de ID</a>. </p> <p>Use <i><code> d_ mid</code></i> se estiver passando uma <span class="keyword"> Experience Cloud</span> ID capturada do serviço <span class="keyword"> da Experience Cloud</span> ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_ dst = 1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_ rtbd = json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_ cb =<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Parâmetros de resposta opcionais. </p> <p> Nenhum desses dados é necessário para enviar dados para <span class="wintitle"> o DCS</span>. No entanto, se você quiser que <span class="wintitle"> o DCS</span> retorne uma resposta, deverá incluir <i><code> d_ rtbd = json</code></i> em sua solicitação. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Resposta de exemplo {#sample-response}

Consulte [Receber dados do DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).
