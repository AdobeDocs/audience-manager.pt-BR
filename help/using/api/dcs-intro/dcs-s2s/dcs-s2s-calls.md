---
seo-title: Making Server-to-Server DCS API Calls
solution: Audience Manager
title: Como fazer chamadas de DCS API de servidor para servidor
uuid: bdfe3430-e27f-4a5c-88d9-ae164d28f601
feature: DCS
description: Sintaxe de chamada, exemplo e parâmetros ao fazer chamadas de DCS API de servidor para servidor
exl-id: 977f4dfe-0beb-43c8-b64e-df4042427474
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 1%

---

# Como fazer chamadas de DCS API de servidor para servidor {#making-server-to-server-dcs-api-calls}

As chamadas exigem o nome de host do servidor DCS regional e a ID de usuário. Se você não tiver as IDs de usuário e região necessárias, consulte [Obter IDs de usuário e regiões de uma resposta de DCS](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) e/ou [Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md). Depois de ter IDs de usuário e região, você pode fazer chamadas de servidor para servidor para o DCS. Consulte esta seção para obter sintaxe e exemplos.

>[!NOTE]
>
>No código e em exemplos, *itálico* representa um espaço reservado para variável. Substitua um valor real para o espaço reservado quando você chamar de servidor para servidor o [!DNL DCS].

## Sintaxe de chamada e exemplo {#call-syntax-example}

Uma solicitação básica de servidor para servidor que envia dados para o [!DNL DCS] usa a sintaxe mostrada abaixo.

```js
"Host:domain_alias.demdex.net" "https://DCS_host_name.demdex.net/event?d_rtbd=json&d_jsonv=1&d_uuid=userID
```

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
   <td colname="col1"> <p><code> <i>domain alias</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Esta parte da chamada contém: </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Seu alias de domínio atribuído por <span class="keyword"> Audience Manager</span> (por exemplo, <i><code> my_domain.demdex.net</code></i>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">O domínio de destino, que é sempre <i><code> demdex.net</code></i>. Consulte <a href="../../../reference/demdex-calls.md"> Compreendendo as chamadas para o domínio Demdex</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> <i>DCS host name</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>O parâmetro de host do cabeçalho http que mostra o nome do servidor <span class="wintitle"> DCS</span> regional. O nome do host está vinculado a uma ID de região, por isso você precisa disso antes de fazer esses tipos de chamadas. Consulte <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md"> IDs da região do DCS, locais e nomes de host</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Esta parte da chamada: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifica a chamada como uma chamada de evento. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Define o início da cadeia de caracteres do URL que contém os dados que você deseja enviar para o DCS. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_uuid= <i>Audience Manager user ID</i></code> </p> </td> 
   <td colname="col2"> <p>Esta é a chave de ID de usuário exclusiva que contém o valor de ID de usuário Audience Manager<span class="keyword"></span> em um par de valor-chave. </p> <p>Use <code><i>d_uuid</i></code> se estiver transmitindo a ID de usuário do Audience Manager <span class="keyword"></span>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_mid=<i>Experience Cloud user ID</i></code> </p> </td> 
   <td colname="col2"> <p>Esta é a chave de ID de usuário exclusiva que contém o valor de ID de usuário Experience Cloud<span class="keyword"></span> em um par de valor-chave. Consulte também <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> Obter a ID de usuário do cookie do serviço de ID</a>. </p> <p>Use <i><code> d_mid</code></i> se estiver transmitindo uma ID de Experience Cloud</span> <span class="keyword"> capturada do serviço de ID Experience Cloud</span> do <span class="keyword">. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_cb=<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Parâmetros de resposta opcionais. </p> <p> Nenhum deles é necessário para enviar dados ao <span class="wintitle"> DCS</span>. No entanto, se você quiser que o <span class="wintitle"> DCS</span> retorne uma resposta, você deve incluir <i><code> d_rtbd=json</code></i> em sua solicitação. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Resposta de exemplo {#sample-response}

Consulte [Receber dados do DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).
