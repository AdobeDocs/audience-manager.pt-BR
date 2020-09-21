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
source-git-commit: a41f0beffba686f283a2933ad7066cb124e4d380
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 5%

---


# Estados de autenticação de visitante no Audience Manager{#visitor-authentication-states-in-audience-manager}

O status de autenticação do visitante determina se as novas informações de característica são gravadas no perfil autenticado do visitante ou no perfil do dispositivo, de onde os dados foram coletados. O Audience Manager trata os status de autenticação da ID do visitante UNKNOWN e LOGGED_OUT nas chamadas do evento da mesma maneira.

A partir do serviço [!DNL Experience Cloud] de ID v1.5+, o `setCustomerID` método inclui o `AuthState` objeto opcional. `AuthState` identifica visitantes de acordo com seu status [de](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)autenticação. [!DNL Audience Manager] lida com as características realizadas de forma diferente, dependendo do status de autenticação transmitido na chamada e da Regra [de mesclagem de](../features/profile-merge-rules/merge-rules-dashboard.md) Perfis usada para segmentação.

## Status da autenticação: DESCONHECIDO {#auth-status-unknown}

| Valor da solicitação | **Leia** informações do perfil autenticado | **Gravar** novas características no perfil autenticado |
---------|----------|---------
| 0 | <ul><li>Sim, se a Regra de mesclagem de opções autenticadas = &quot;Últimos Perfis autenticados&quot;.</li><li>Não, se a Regra de mesclagem de opções autenticadas = &quot;Perfis autenticados atuais&quot; ou &quot;Nenhum Perfil autenticado&quot;.</li></ul> | Não, os dados de características são adicionados ao perfil do dispositivo. |


Chamada de amostra (o valor da solicitação correspondente ao status de autenticação é destacado):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Status da autenticação: AUTENTICADO {#auth-status-authenticated}

| Valor da solicitação | **Leia** informações do perfil autenticado | **Gravar** novas características no perfil autenticado |
---------|----------|---------
| 1 | <ul><li>Sim, se a regra de mesclagem de opções autenticadas = &quot;Perfis autenticados atuais&quot; ou &quot;Perfis autenticados pela última vez&quot;.</li><li>Não, se a Regra de mesclagem de opções autenticadas = &quot;Nenhum Perfil autenticado&quot;.</li></ul> | Sim, os dados de características são adicionados ao perfil autenticado. |

Chamada de amostra (o valor da solicitação correspondente ao status de autenticação é destacado):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Status da autenticação: LOGGED_OUT {#auth-status-logged-out}

| Valor da solicitação | **Leia** informações do perfil autenticado | **Gravar** novas características no perfil autenticado |
---------|----------|---------
| 2 | <ul><li>Sim, se a Regra de mesclagem de opções autenticadas = &quot;Últimos Perfis autenticados&quot;</li><li>Não, se a Regra de mesclagem de opções autenticadas = &quot;Perfis autenticados atuais&quot; ou &quot;Nenhum Perfil autenticado&quot;</li></ul> | Não, os dados de características são gravados no perfil do dispositivo. |

Chamada de amostra (o valor da solicitação correspondente ao status de autenticação é destacado):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] executa uma sincronização de ID entre [CID e UUID](../reference/ids-in-aam.md) em todos os três casos.

>[!MORELIKETHIS]
>
>* [Estados de autenticação e IDs do cliente](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

