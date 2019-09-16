---
description: Uma visão geral de como o Audience Manager realiza transferências de dados em tempo real com um provedor de conteúdo de terceiros.
seo-description: Uma visão geral de como o Audience Manager realiza transferências de dados em tempo real com um provedor de conteúdo de terceiros.
seo-title: Processo de transferência de dados em tempo real descrito
solution: Audience Manager
title: Processo de transferência de dados em tempo real descrito
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
translation-type: tm+mt
source-git-commit: ea95df8531c00c183f22b09a4a78fc6b35ee279d

---


# Processo de transferência de dados em tempo real descrito{#real-time-data-transfer-process-described}

Uma visão geral de como o Audience Manager realiza transferências de dados em tempo real com um provedor de conteúdo de terceiros.

<!-- real-time-data-transfer-explained.xml -->

## Transferências de dados em tempo real

As transferências de dados em tempo real enviam e recebem IDs de segmento quando um usuário visita ou age em seu site. Normalmente, as transferências de dados síncronas são úteis quando você precisa qualificar ou segmentar os usuários imediatamente, à medida que eles navegam pelo seu inventário.

## Etapas da integração de dados

O processo de integração de dados em tempo real funciona da seguinte maneira:

1. Um usuário visita o site de um cliente que contém o código do Audience Manager.
1. O Audience Manager carrega um iframe e faz uma chamada para nosso [!UICONTROL Data Collection Server] ( [!UICONTROL DCS]).
1. O [!UICONTROL DCS] chama o servidor de terceiros (em tempo real) para verificar se o fornecedor tem alguma informação de segmento sobre o usuário.
1. O provedor de conteúdo retorna informações de segmento sobre esse usuário ao Audience Manager.
1. O Audience Manager recebe essas informações de segmento e as disponibiliza para segmentação e criação de novas características e segmentos.

![](assets/rt_reduce70.png)