---
description: O status de autenticação do visitante no Audience Manager determina se as novas informações de característica são gravadas no perfil autenticado do visitante ou no perfil do dispositivo, de onde os dados foram coletados. O Audience Manager lida da mesma forma com os status de autenticação de ID de visitante UNKNOWN e LOGGED_OUT em chamadas de evento.
keywords: dpm.demdex.net
seo-description: The visitor authentication status in Audience Manager determines if the new trait information is written to the visitor's authenticated profile or to the device profile, where the data was collected from. Audience Manager handles the visitor ID authentication statuses UNKNOWN and LOGGED_OUT in event calls in the same way.
seo-title: Visitor Authentication States in Audience Manager
solution: Audience Manager
title: Estados de autenticação de visitante no Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: Reference
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 6%

---

# Estados de autenticação de visitante no Audience Manager{#visitor-authentication-states-in-audience-manager}

O status de autenticação do visitante no Audience Manager determina se as novas informações de característica são gravadas no perfil autenticado do visitante ou no perfil do dispositivo, de onde os dados foram coletados. O Audience Manager lida da mesma forma com os status de autenticação de ID de visitante UNKNOWN e LOGGED_OUT em chamadas de evento.

Começando com [!DNL Experience Cloud] serviço de ID v1.5+, o `setCustomerID` inclui a variável opcional `AuthState` objeto. `AuthState` O identifica visitantes de acordo com seus [status de autenticação](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] O lida com as características realizadas de forma diferente, dependendo do status de autenticação transmitido na chamada e do [Regra de mesclagem de perfis](../features/profile-merge-rules/merge-rules-dashboard.md) é usada para segmentação.

## Status de autenticação: DESCONHECIDO {#auth-status-unknown}

| Valor da solicitação | Ler informações do perfil autenticado | Gravar novas características no perfil autenticado |
|---|---|---|
| 0 | <ul><li>Sim, se a variável [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>Não, se a variável [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] ou [!UICONTROL No Authenticated Profile].</li></ul> | Não, os dados de características são adicionados ao perfil do dispositivo. |

Exemplo de chamada (o valor da solicitação correspondente ao status de autenticação é realçado):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Status de autenticação: AUTENTICADO {#auth-status-authenticated}

| Valor da solicitação | Ler informações do perfil autenticado | Gravar novas características no perfil autenticado |
|---|---|---|
| 1 | <ul><li>Sim, se a variável [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] ou [!UICONTROL Last Authenticated Profiles].</li><li>Não, se a variável [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL No Authenticated Profile].</li></ul> | Sim, os dados de características são adicionados ao perfil autenticado. |

Exemplo de chamada (o valor da solicitação correspondente ao status de autenticação é realçado):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Status de Autenticação: LOGGED_OUT {#auth-status-logged-out}

| Valor da solicitação | Ler informações do perfil autenticado | Gravar novas características no perfil autenticado |
|---|---|---|
| 2 | <ul><li>Sim, se a variável [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>Não, se a variável [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] ou [!UICONTROL No Authenticated Profile].</li></ul> | Não, os dados de características são gravados no perfil do dispositivo. |

Exemplo de chamada (o valor da solicitação correspondente ao status de autenticação é realçado):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] O executa uma sincronização de ID entre [CID e UUID](../reference/ids-in-aam.md) nos três casos.

>[!MORELIKETHIS]
>
>* [Estados de autenticação e IDs do cliente](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html)

