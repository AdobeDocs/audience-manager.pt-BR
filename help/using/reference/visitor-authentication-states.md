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
source-git-commit: c3c829ef1335d1e073b719f8252103fa578bb4e6
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 7%

---

# Estados de autenticação de visitante no Audience Manager{#visitor-authentication-states-in-audience-manager}

O status de autenticação do visitante no Audience Manager determina se as novas informações de característica são gravadas no perfil autenticado do visitante ou no perfil do dispositivo, onde os dados foram coletados. O Audience Manager lida com os status de autenticação da ID de visitante UNKNOWN e LOGGED_OUT em chamadas de evento da mesma maneira.

A partir de [!DNL Experience Cloud] serviço de ID v1.5+, o método `setCustomerID` inclui o objeto `AuthState` opcional. `AuthState` O identifica visitantes de acordo com seu status  [de autenticação](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] O lida com as características realizadas de forma diferente, dependendo do status de autenticação passado na chamada e da Regra de mesclagem de  [perfis ](../features/profile-merge-rules/merge-rules-dashboard.md) usada para segmentação.

## Status de autenticação: DESCONHECIDO {#auth-status-unknown}

| Valor da solicitação | Ler informações do perfil autenticado | Gravar novas características no perfil autenticado |
|---|---|---|
| 0 | <ul><li>Sim, se o [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>Não, se o [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] ou [!UICONTROL No Authenticated Profile].</li></ul> | Não, os dados de característica são adicionados ao perfil do dispositivo. |

Exemplo de chamada (o valor da solicitação correspondente ao status de autenticação é destacado):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Status de autenticação: AUTENTICADO {#auth-status-authenticated}

| Valor da solicitação | Ler informações do perfil autenticado | Gravar novas características no perfil autenticado |
|---|---|---|
| 1 | <ul><li>Sim, se [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] ou [!UICONTROL Last Authenticated Profiles].</li><li>Não, se o [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL No Authenticated Profile].</li></ul> | Sim, os dados de característica são adicionados ao perfil autenticado. |

Exemplo de chamada (o valor da solicitação correspondente ao status de autenticação é destacado):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Status de autenticação: LOGGED_OUT {#auth-status-logged-out}

| Valor da solicitação | Ler informações do perfil autenticado | Gravar novas características no perfil autenticado |
|---|---|---|
| 2 | <ul><li>Sim, se o [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>Não, se o [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] ou [!UICONTROL No Authenticated Profile].</li></ul> | Não, os dados de características são gravados no perfil do dispositivo. |

Exemplo de chamada (o valor da solicitação correspondente ao status de autenticação é destacado):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] O executa uma sincronização de ID entre  [CID e ](../reference/ids-in-aam.md) UUIDnos três casos.

>[!MORELIKETHIS]
>
>* [Estados de autenticação e IDs do cliente](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

