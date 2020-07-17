---
description: Com as Regras de mesclagem de Perfis, você obtém controle sobre os conjuntos de dados usados para segmentação e pode público alvo uma pessoa com precisão em vários dispositivos.
seo-description: Com as Regras de mesclagem de Perfis, você obtém controle sobre os conjuntos de dados usados para segmentação e pode público alvo uma pessoa com precisão em vários dispositivos.
seo-title: Visão geral das regras de mesclagem de perfis
solution: Audience Manager
title: Visão geral das regras de mesclagem de perfis
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 4%

---


# [!UICONTROL Profile Merge Rules] Visão geral {#profile-merge-rules-overview}

Com [!UICONTROL Profile Merge Rules] você pode controlar quais conjuntos de dados são usados para segmentação e público alvo os usuários com precisão em vários dispositivos.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## Coleta e segmentação de dados com perfis anônimos e autenticados {#data-collection-targeting}

Normalmente, a segmentação e a segmentação de audiências dependem dos dados coletados de todos os usuários em um dispositivo. A coleta e a segmentação de dados com base em dados no nível do dispositivo apresenta algumas desvantagens. Por exemplo, não é possível distinguir entre vários usuários que compartilham um dispositivo ou usuários públicos alvos com precisão em vários dispositivos. A coleta de dados centralizada no dispositivo não é mais suficiente para campanhas de marketing digital ou direcionamento entre dispositivos.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] fundamentalmente altera a forma como [!DNL Audience Manager] coleta dados e segmentos de usuários para definição de metas. Ele permite que você trabalhe com dois tipos distintos de perfis, um perfil de dispositivo e um perfil [](../../reference/visitor-authentication-states.md)autenticado.

| Tipo de Perfil | Descrição |
|---|---|
| [!UICONTROL Device Profile] | Uma ID [!UICONTROL device profile] está vinculada a uma ID de um determinado dispositivo, como uma [!UICONTROL cookie] ID ou uma ID de dispositivo móvel.<br><br> O serviço inclui:<ul><li>[!UICONTROL Rule-based traits] realizado quando um usuário não é autenticado.</li><li>[!UICONTROL Onboarded traits] vinculado a uma ID de dispositivo, como dados de [!UICONTROL cookie-based]terceiros.</li></ul> |
| [!UICONTROL Authenticated Profile] | O [!UICONTROL authenticated profile] está vinculado a uma ID de usuário transmitida quando uma pessoa faz logon no site.<br><br>O serviço inclui:<ul><li>[!UICONTROL Rule-based traits] coletado em dispositivos quando um usuário é autenticado.</li><li>[!UICONTROL Onboarded traits] em um arquivo offline vinculado à mesma ID de usuário.</li></ul> |

Esses perfis diferentes controlam os dados que você pode usar para segmentação. Por exemplo, com um perfil [](../../reference/visitor-authentication-states.md)autenticado, você pode criar com precisão [!UICONTROL segments] com base em dados de vários dispositivos para um único usuário. Isso significa que você pode oferecer uma experiência consistente com a marca aos clientes em vários dispositivos. [!DNL Audience Manager] Isso é feito armazenando o mapeamento dos diferentes dispositivos que uma pessoa usa para suas atividades online em seu perfil [](../../reference/visitor-authentication-states.md)autenticado. Esses mapeamentos são chamados de [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Benefícios {#advantages}

Com [!UICONTROL Profile Merge Rules] você pode:

* Usuários do Público alvo com base em perfis [](../../reference/visitor-authentication-states.md)autenticados, perfis anônimos ou combinações de ambos.
* Público alvo um cliente específico em seus dispositivos.
* Crie um gráfico de dispositivos com base em dados determinísticos.
* Ajuste os dados em seu sistema com [!UICONTROL segments] base em perfis diferentes.
* Obtenha informações adicionais sobre a sua audiência.
