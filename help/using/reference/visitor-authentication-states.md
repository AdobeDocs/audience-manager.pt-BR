---
description: O status de autenticação do visitante no Audience Manager determina se as novas informações de característica são gravadas no perfil autenticado do visitante ou no perfil do dispositivo, onde os dados foram coletados. O Audience Manager trata os status de autenticação da ID de visitante DESCONHECIDO e LOGGED_ OUT em chamadas de evento da mesma forma.
keywords: dpm.demdex.net
seo-description: O status de autenticação do visitante no Audience Manager determina se as novas informações de característica são gravadas no perfil autenticado do visitante ou no perfil do dispositivo, onde os dados foram coletados. O Audience Manager trata os status de autenticação da ID de visitante DESCONHECIDO e LOGGED_ OUT em chamadas de evento da mesma forma.
seo-title: Estados de autenticação do visitante no Audience Manager
solution: Audience Manager
title: Estados de autenticação do visitante no Audience Manager
uuid: d 748 c 0 c 3-5833-4 fb 9-ab 3 e -793 f 5 f 252 e 47
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Visitor Authentication States in Audience Manager{#visitor-authentication-states-in-audience-manager}

O status de autenticação do visitante no Audience Manager determina se as novas informações de característica são gravadas no perfil autenticado do visitante ou no perfil do dispositivo, onde os dados foram coletados. O Audience Manager trata os status de autenticação da ID de visitante DESCONHECIDO e LOGGED_ OUT em chamadas de evento da mesma forma.

Beginning with [!DNL Experience Cloud] ID service v1.5+, the `setCustomerID` method includes the optional `AuthState` object. `AuthState` identifica os visitantes de acordo com o [status de autenticação](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). [!DNL Audience Manager] trata as características percebidas de forma diferente, dependendo do status de autenticação passado na chamada e da [Regra](../features/profile-merge-rules/merge-rules-dashboard.md) de mesclagem de perfil usada para segmentação.

## Authentication Status: UNKNOWN {#auth-status-unknown}

<table id="table_E1EA51533FAE4BBFB338D6F6116BC1F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valor da solicitação </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Ler</b> informações do perfil autenticado </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Gravar</b> novas características no perfil autenticado </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 0 </code> </p> </td> 
   <td colname="col2"> <p>Sim, se a opção de mesclagem de opção autenticada = "Perfis autenticados finais". </p> </td> 
   <td colname="col3" morerows="1"> <p>Não, os dados características são adicionados ao perfil do dispositivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Não, se a opção Mesclar opção de mesclagem = "Perfis autenticados atuais" ou "Não houver perfil autenticado". </p> </td> 
  </tr> 
 </tbody> 
</table>

Chamada de amostra (o valor da solicitação correspondente ao status de autenticação é destacado):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Authentication Status: AUTHENTICATED {#auth-status-authenticated}

<table id="table_956ABF96024744308F7773E1F96482B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valor da solicitação </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Ler</b> informações do perfil autenticado </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Gravar</b> novas características no perfil autenticado </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 1 </code> </p> </td> 
   <td colname="col2"> <p>Sim, se a opção Mesclar opção de mesclagem = "Perfis autenticados atuais" ou "Perfis autenticados finais" for usada. </p> </td> 
   <td colname="col3" morerows="1"> <p>Sim, os dados características são adicionados ao perfil autenticado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Não, se a opção de mesclagem de opção autenticada = "Sem perfil autenticado". </p> </td> 
  </tr> 
 </tbody> 
</table>

Chamada de amostra (o valor da solicitação correspondente ao status de autenticação é destacado):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Authentication Status: LOGGED_OUT {#auth-status-logged-out}

<table id="table_783F0CBB0431482AA49F41468FA65B19"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valor da solicitação </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Ler</b> informações do perfil autenticado </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Gravar</b> novas características no perfil autenticado </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code>2</code> </p> </td> 
   <td colname="col2"> Sim, se a opção de mesclagem de opção autenticada = "Perfis autenticados últimos" </td> 
   <td colname="col3" morerows="1"> <p>Não, os dados características são gravados no perfil do dispositivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Não, se a opção Mesclar opção de mesclagem = "Perfis autenticados atuais" ou "Nenhum perfil autenticado" </td> 
  </tr> 
 </tbody> 
</table>

Chamada de amostra (o valor da solicitação correspondente ao status de autenticação é destacado):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] realiza uma sincronização de ID entre [CID e UUID](../reference/ids-in-aam.md) nos três casos.

>[!MORE_ LIKE_ THIS]
>
>* [Estados de autenticação e IDs do cliente](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html)

