---
description: Com as Regras de mesclagem de perfis, você tem controle sobre os conjuntos de dados usados para segmentação e pode direcionar uma pessoa com precisão em vários dispositivos.
seo-description: With Profile Merge Rules you get control over the data sets used for segmentation and can target a person accurately across multiple devices.
seo-title: Profile Merge Rules Overview
solution: Audience Manager
title: Visão geral das regras de mesclagem de perfis
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: Profile Merge
exl-id: 5d1f5bea-0fca-4684-a2b4-585d9e38d9ef
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 3%

---

# [!UICONTROL Profile Merge Rules] Visão geral {#profile-merge-rules-overview}

Com [!UICONTROL Profile Merge Rules] você pode controlar quais conjuntos de dados são usados para segmentação e direcionar os usuários com precisão em vários dispositivos.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## Coleta e direcionamento de dados com perfis anônimos e autenticados {#data-collection-targeting}

Normalmente, a segmentação e o direcionamento do público-alvo dependem dos dados coletados de todos os usuários em um dispositivo. A coleta e o direcionamento de dados com base nos dados no nível do dispositivo têm algumas desvantagens. Por exemplo, não é possível distinguir entre vários usuários que compartilham um dispositivo ou direcionam com precisão os usuários em vários dispositivos. A coleta de dados centrada em dispositivos não é mais suficiente para campanhas de marketing digital ou direcionamento entre dispositivos.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] muda fundamentalmente como [!DNL Audience Manager] coleta dados e segmenta usuários para direcionamento. Ele permite trabalhar com dois tipos distintos de perfis, um perfil de dispositivo e um [perfil autenticado](../../reference/visitor-authentication-states.md).

| Tipo de perfil | Descrição |
|---|---|
| [!UICONTROL Device Profile] | A [!UICONTROL device profile] está vinculado a uma ID para um determinado dispositivo, como uma [!UICONTROL cookie] ID do dispositivo móvel.<br><br> O serviço inclui:<ul><li>[!UICONTROL Rule-based traits] realizado quando um usuário não está autenticado.</li><li>[!UICONTROL Onboarded traits] vinculado a uma ID de dispositivo, como [!UICONTROL cookie-based], dados de terceiros.</li></ul> |
| [!UICONTROL Authenticated Profile] | A variável [!UICONTROL authenticated profile] está vinculado a uma ID de usuário transmitida quando uma pessoa faz logon no site.<br><br>O serviço inclui:<ul><li>[!UICONTROL Rule-based traits] coletado em dispositivos quando um usuário é autenticado.</li><li>[!UICONTROL Onboarded traits] em um arquivo offline vinculado à mesma ID de usuário.</li></ul> |

Esses perfis diferentes controlam os dados que podem ser usados para segmentação. Por exemplo, com um [perfil autenticado](../../reference/visitor-authentication-states.md), você pode criar dados precisos [!UICONTROL segments] com base em dados de vários dispositivos para um único usuário. Isso significa que você pode fornecer uma experiência de marca consistente aos clientes em vários dispositivos. [!DNL Audience Manager] consegue isso armazenando o mapeamento dos diferentes dispositivos que uma pessoa usa para suas atividades online em seus [perfil autenticado](../../reference/visitor-authentication-states.md). Esses mapeamentos são chamados de [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Benefícios {#advantages}

Com [!UICONTROL Profile Merge Rules] você pode:

* Direcionar usuários com base em [perfil autenticado](../../reference/visitor-authentication-states.md), perfis anônimos ou combinações de ambos.
* Direcione um cliente específico em seus dispositivos.
* Crie um gráfico de dispositivos com base em dados determinísticos.
* Ajuste os dados em sua [!UICONTROL segments] com base em perfis diferentes.
* Obtenha insights adicionais sobre seu público-alvo.
