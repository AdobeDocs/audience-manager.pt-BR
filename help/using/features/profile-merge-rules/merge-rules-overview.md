---
description: Com as Regras de mesclagem de perfis, você obtém controle sobre os conjuntos de dados usados para segmentação e pode direcionar uma pessoa com precisão em vários dispositivos.
seo-description: Com as Regras de mesclagem de perfis, você obtém controle sobre os conjuntos de dados usados para segmentação e pode direcionar uma pessoa com precisão em vários dispositivos.
seo-title: Visão geral das regras de mesclagem de perfis
solution: Audience Manager
title: Visão geral das regras de mesclagem de perfis
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: Mesclar perfis
exl-id: 5d1f5bea-0fca-4684-a2b4-585d9e38d9ef
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 4%

---

# [!UICONTROL Profile Merge Rules] Visão geral {#profile-merge-rules-overview}

Com [!UICONTROL Profile Merge Rules] você pode controlar quais conjuntos de dados são usados para segmentação e pode direcionar usuários com precisão em vários dispositivos.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## Coleta de dados e direcionamento com perfis anônimos e autenticados {#data-collection-targeting}

Normalmente, a segmentação e o direcionamento do público-alvo dependem dos dados coletados de todos os usuários em um dispositivo. A coleta e o direcionamento de dados com base em dados no nível do dispositivo apresenta algumas desvantagens. Por exemplo, não é possível distinguir entre vários usuários que compartilham um dispositivo ou direcionam usuários com precisão em vários dispositivos. A coleta de dados centralizada no dispositivo não é mais suficiente para campanhas de marketing digital ou direcionamento entre dispositivos.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] fundamentalmente altera a forma como o  [!DNL Audience Manager] coleta dados e segmentos usuários para direcionamento. Ele permite trabalhar com dois tipos distintos de perfis, um perfil de dispositivo e um [perfil autenticado](../../reference/visitor-authentication-states.md).

| Tipo de perfil | Descrição |
|---|---|
| [!UICONTROL Device Profile] | Um [!UICONTROL device profile] é vinculado a uma ID de um determinado dispositivo, como uma ID [!UICONTROL cookie] ou ID de dispositivo móvel.<br><br> O serviço inclui:<ul><li>[!UICONTROL Rule-based traits] percebido quando um usuário não é autenticado.</li><li>[!UICONTROL Onboarded traits] vinculado a uma ID do dispositivo, como dados de terceiros  [!UICONTROL cookie-based].</li></ul> |
| [!UICONTROL Authenticated Profile] | O [!UICONTROL authenticated profile] é vinculado a uma ID de usuário transmitida quando uma pessoa faz logon no site.<br><br>O serviço inclui:<ul><li>[!UICONTROL Rule-based traits] coletado em vários dispositivos quando um usuário é autenticado.</li><li>[!UICONTROL Onboarded traits] em um arquivo offline vinculado à mesma ID de usuário.</li></ul> |

Esses perfis diferentes controlam os dados que você pode usar para segmentação. Por exemplo, com um [perfil autenticado](../../reference/visitor-authentication-states.md), você pode criar [!UICONTROL segments] preciso com base em dados de vários dispositivos para um único usuário. Isso significa que você pode fornecer uma experiência de marca consistente para os clientes em vários dispositivos. [!DNL Audience Manager] Isso é feito armazenando o mapeamento dos diferentes dispositivos que uma pessoa usa para suas atividades online em seu perfil  [autenticado](../../reference/visitor-authentication-states.md). Esses mapeamentos são chamados de [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Benefícios {#advantages}

Com [!UICONTROL Profile Merge Rules] você pode:

* Direcione usuários com base em [perfil autenticado](../../reference/visitor-authentication-states.md), perfis anônimos ou combinações de ambos.
* Direcione um cliente específico em seus dispositivos.
* Crie um gráfico de dispositivos com base em dados determinísticos.
* Ajuste os dados em seu [!UICONTROL segments] com base em perfis diferentes.
* Obtenha informações adicionais sobre seu público-alvo.
