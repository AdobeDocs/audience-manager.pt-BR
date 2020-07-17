---
description: O status de autenticação do visitante determina se as novas informações de característica são gravadas no perfil autenticado do visitante ou no perfil do dispositivo, de onde os dados foram coletados. O Audience Manager trata os status de autenticação da ID do visitante UNKNOWN e LOGGED_OUT nas chamadas do evento da mesma maneira.
keywords: dpm.demdex.net
seo-description: O status de autenticação do visitante determina se as novas informações de característica são gravadas no perfil autenticado do visitante ou no perfil do dispositivo, de onde os dados foram coletados. O Audience Manager trata os status de autenticação da ID do visitante UNKNOWN e LOGGED_OUT nas chamadas do evento da mesma maneira.
seo-title: Estados de autenticação de visitante no Audience Manager
solution: Audience Manager
title: Estados de autenticação de visitante no Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 5%

---


# Estados de autenticação de visitante no Audience Manager{#visitor-authentication-states-in-audience-manager}

O status de autenticação do visitante determina se as novas informações de característica são gravadas no perfil autenticado do visitante ou no perfil do dispositivo, de onde os dados foram coletados. O Audience Manager trata os status de autenticação da ID do visitante UNKNOWN e LOGGED_OUT nas chamadas do evento da mesma maneira.

A partir do serviço [!DNL Experience Cloud] de ID v1.5+, o `setCustomerID` método inclui o `AuthState` objeto opcional. `AuthState` identifica visitantes de acordo com seu status [de](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)autenticação. [!DNL Audience Manager] lida com as características realizadas de forma diferente, dependendo do status de autenticação transmitido na chamada e da Regra [de mesclagem de](../features/profile-merge-rules/merge-rules-dashboard.md) Perfis usada para segmentação.

## Status da autenticação: DESCONHECIDO {#auth-status-unknown}

<table id="table_E1EA51533FAE4BBFB338D6F6116BC1F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valor da solicitação </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Leia</b> informações do perfil autenticado </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Gravar</b> novas características no perfil autenticado </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 0 </code> </p> </td> 
   <td colname="col2"> <p>Sim, se a Regra de mesclagem de opções autenticadas = "Últimos Perfis autenticados". </p> </td> 
   <td colname="col3" morerows="1"> <p>Não, os dados de características são adicionados ao perfil do dispositivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Não, se a Regra de mesclagem de opções autenticadas = "Perfis autenticados atuais" ou "Nenhum Perfil autenticado". </p> </td> 
  </tr> 
 </tbody> 
</table>

Chamada de amostra (o valor da solicitação correspondente ao status de autenticação é destacado):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Status da autenticação: AUTENTICADO {#auth-status-authenticated}

<table id="table_956ABF96024744308F7773E1F96482B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valor da solicitação </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Leia</b> informações do perfil autenticado </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Gravar</b> novas características no perfil autenticado </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 1 </code> </p> </td> 
   <td colname="col2"> <p>Sim, se a regra de mesclagem de opções autenticadas = "Perfis autenticados atuais" ou "Perfis autenticados pela última vez". </p> </td> 
   <td colname="col3" morerows="1"> <p>Sim, os dados de características são adicionados ao perfil autenticado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Não, se a Regra de mesclagem de opções autenticadas = "Nenhum Perfil autenticado". </p> </td> 
  </tr> 
 </tbody> 
</table>

Chamada de amostra (o valor da solicitação correspondente ao status de autenticação é destacado):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Status da autenticação: LOGGED_OUT {#auth-status-logged-out}

<table id="table_783F0CBB0431482AA49F41468FA65B19"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valor da solicitação </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Leia</b> informações do perfil autenticado </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Gravar</b> novas características no perfil autenticado </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 2 </code> </p> </td> 
   <td colname="col2"> Sim, se a Regra de mesclagem de opções autenticadas = "Últimos Perfis autenticados" </td> 
   <td colname="col3" morerows="1"> <p>Não, os dados de características são gravados no perfil do dispositivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Não, se a Regra de mesclagem de opções autenticadas = "Perfis autenticados atuais" ou "Nenhum Perfil autenticado" </td> 
  </tr> 
 </tbody> 
</table>

Chamada de amostra (o valor da solicitação correspondente ao status de autenticação é destacado):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] executa uma sincronização de ID entre [CID e UUID](../reference/ids-in-aam.md) em todos os três casos.

>[!MORELIKETHIS]
>
>* [Estados de autenticação e IDs do cliente](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

