---
description: Uma visão geral de como o Audience Manager executa transferências de dados em tempo real com um provedor de conteúdo de terceiros.
seo-description: Uma visão geral de como o Audience Manager executa transferências de dados em tempo real com um provedor de conteúdo de terceiros.
seo-title: Processo de transferência de dados em tempo real descrito
solution: Audience Manager
title: Processo de transferência de dados em tempo real descrito
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---


# Real-Time Data Transfer Process Described{#real-time-data-transfer-process-described}

Uma visão geral de como o Audience Manager executa transferências de dados em tempo real com um provedor de conteúdo de terceiros.

<!-- real-time-data-transfer-explained.xml -->

## Transferências de dados em tempo real

As transferências de dados em tempo real enviam e recebem IDs de segmento quando um usuário visita ou age em seu site. Normalmente, as transferências de dados síncronas são úteis quando você precisa qualificar ou segmentar os usuários imediatamente, à medida que eles navegam pelo seu inventário.

## Etapas da integração de dados

O processo de integração de dados em tempo real funciona da seguinte maneira:

1. Um usuário visita o site de um cliente que contém o código de Audience Manager.
1. Audience Manager carrega um iframe e faz uma chamada para nosso [!UICONTROL Data Collection Server] ( [!DNL DCS]).
1. O [!DNL DCS] chama o servidor de terceiros (em tempo real) para verificar se o fornecedor tem alguma informação de segmento sobre o usuário.
1. O provedor de conteúdo retorna as informações do segmento para o Audience Manager.
1. A Audience Manager recebe essas informações de segmento e as disponibiliza para segmentação e criação de novas características e segmentos.

![](assets/rt_reduce70.png)