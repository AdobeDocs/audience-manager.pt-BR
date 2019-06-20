---
description: Uma visão geral geral de como o Audience Manager executa transferências de dados em tempo real com um provedor de conteúdo de terceiros.
seo-description: Uma visão geral geral de como o Audience Manager executa transferências de dados em tempo real com um provedor de conteúdo de terceiros.
seo-title: Descrição do processo de transferência de dados em tempo real
solution: Audience Manager
title: Descrição do processo de transferência de dados em tempo real
uuid: b 68781 b 3-0 b 7 a -442 d -8 e 34-2 db 2474849 a 4
translation-type: tm+mt
source-git-commit: ea95df8531c00c183f22b09a4a78fc6b35ee279d

---


# Real-Time Data Transfer Process Described{#real-time-data-transfer-process-described}

Uma visão geral geral de como o Audience Manager executa transferências de dados em tempo real com um provedor de conteúdo de terceiros.

<!-- real-time-data-transfer-explained.xml -->

## Transferências de dados em tempo real

As transferências de dados em tempo real enviam e recebem IDs de segmento enquanto um usuário visita ou executa ações em seu site. Normalmente, transferências de dados síncronos são úteis quando você precisa qualificar ou segmentar os usuários imediatamente, à medida que navegam pelo inventário.

## Etapas de integração de dados

O processo de integração de dados em tempo real funciona da seguinte maneira:

1. Um usuário visita o site de um cliente que contém o código do Audience Manager.
1. Audience Manager loads an iframe and makes a call to our [!UICONTROL Data Collection Server] ( [!UICONTROL DCS]).
1. [!UICONTROL DCS] A chamada do servidor de terceiros (em tempo real) para verificar se o fornecedor tem informações de segmento sobre o usuário.
1. O provedor de conteúdo retorna informações de segmento sobre esse usuário para o Audience Manager.
1. O Audience Manager recebe essas informações de segmento e o torna disponível para definição de metas e criação de novos traços e segmentos.

![](assets/rt_reduce70.png)