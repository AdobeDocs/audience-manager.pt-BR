---
description: O status de autenticação do visitante no Audience Manager determina se as novas informações de característica são gravadas no perfil autenticado do visitante ou no perfil do dispositivo, onde os dados foram coletados. O Audience Manager lida com os status de autenticação da ID de visitante UNKNOWN e LOGGED_OUT em chamadas de evento da mesma maneira.
keywords: dpm.demdex.net
seo-description: O status de autenticação do visitante no Audience Manager determina se as novas informações de característica são gravadas no perfil autenticado do visitante ou no perfil do dispositivo, onde os dados foram coletados. O Audience Manager lida com os status de autenticação da ID de visitante UNKNOWN e LOGGED_OUT em chamadas de evento da mesma maneira.
seo-title: Estados de autenticação de visitante no Audience Manager
solution: Audience Manager
title: Estados de autenticação de visitante no Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: 'Referência '
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 5%

---

# Estados de autenticação de visitante no Audience Manager{#visitor-authentication-states-in-audience-manager}

O status de autenticação do visitante no Audience Manager determina se as novas informações de característica são gravadas no perfil autenticado do visitante ou no perfil do dispositivo, onde os dados foram coletados. O Audience Manager lida com os status de autenticação da ID de visitante UNKNOWN e LOGGED_OUT em chamadas de evento da mesma maneira.

A partir de [!DNL Experience Cloud] serviço de ID v1.5+, o método `setCustomerID` inclui o objeto `AuthState` opcional. `AuthState` O identifica visitantes de acordo com seu status  [de autenticação](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] O lida com as características realizadas de forma diferente, dependendo do status de autenticação passado na chamada e da Regra de mesclagem de  [perfis ](../features/profile-merge-rules/merge-rules-dashboard.md) usada para segmentação.

## Status de autenticação: DESCONHECIDO {#auth-status-unknown}

<table id="table_E1EA51533FAE4BBFB338D6F6116BC1F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valor da solicitação </p> </th> 
   <th colname="col2" class="entry"> <p> <b></b> Ler informações do perfil autenticado </p> </th> 
   <th colname="col3" class="entry"> <p> <b></b> Gravar novas características no perfil autenticado </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 0 </code> </p> </td> 
   <td colname="col2"> <p>Sim, se a Regra de mesclagem de opções autenticadas = "Últimos perfis autenticados". </p> </td> 
   <td colname="col3" morerows="1"> <p>Não, os dados de característica são adicionados ao perfil do dispositivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Não, se a Regra de mesclagem de opções autenticadas = "Perfis atuais autenticados" ou "Sem perfil autenticado". </p> </td> 
  </tr> 
 </tbody> 
</table>

Exemplo de chamada (o valor da solicitação correspondente ao status de autenticação é destacado):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Status de autenticação: AUTENTICADO {#auth-status-authenticated}

<table id="table_956ABF96024744308F7773E1F96482B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valor da solicitação </p> </th> 
   <th colname="col2" class="entry"> <p> <b></b> Ler informações do perfil autenticado </p> </th> 
   <th colname="col3" class="entry"> <p> <b></b> Gravar novas características no perfil autenticado </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 1 </code> </p> </td> 
   <td colname="col2"> <p>Sim, se a Regra de mesclagem de opções autenticadas = "Perfis atuais autenticados" ou "Últimos perfis autenticados". </p> </td> 
   <td colname="col3" morerows="1"> <p>Sim, os dados de característica são adicionados ao perfil autenticado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Não, se a Regra de mesclagem de opções autenticadas = "Sem perfil autenticado". </p> </td> 
  </tr> 
 </tbody> 
</table>

Exemplo de chamada (o valor da solicitação correspondente ao status de autenticação é destacado):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Status de autenticação: LOGGED_OUT {#auth-status-logged-out}

<table id="table_783F0CBB0431482AA49F41468FA65B19"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valor da solicitação </p> </th> 
   <th colname="col2" class="entry"> <p> <b></b> Ler informações do perfil autenticado </p> </th> 
   <th colname="col3" class="entry"> <p> <b></b> Gravar novas características no perfil autenticado </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 2 </code> </p> </td> 
   <td colname="col2"> Sim, se a Regra de mesclagem de opções autenticadas = "Últimos perfis autenticados" </td> 
   <td colname="col3" morerows="1"> <p>Não, os dados de características são gravados no perfil do dispositivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Não, se a Regra de mesclagem de opções autenticadas = "Perfis atuais autenticados" ou "Sem perfil autenticado" </td> 
  </tr> 
 </tbody> 
</table>

Exemplo de chamada (o valor da solicitação correspondente ao status de autenticação é destacado):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] O executa uma sincronização de ID entre  [CID e ](../reference/ids-in-aam.md) UUIDnos três casos.

>[!MORELIKETHIS]
>
>* [Estados de autenticação e IDs do cliente](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

