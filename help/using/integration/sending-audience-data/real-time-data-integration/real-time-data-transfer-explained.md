---
description: Uma visão geral de como o Audience Manager executa transferências de dados em tempo real com um provedor de conteúdo de terceiros.
seo-description: Uma visão geral de como o Audience Manager executa transferências de dados em tempo real com um provedor de conteúdo de terceiros.
seo-title: Descrição do processo de transferência de dados em tempo real
solution: Audience Manager
title: Descrição do processo de transferência de dados em tempo real
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 1%

---


# Descrição do processo de transferência de dados em tempo real{#real-time-data-transfer-process-described}

Uma visão geral de como o Audience Manager executa transferências de dados em tempo real com um provedor de conteúdo de terceiros.

<!-- real-time-data-transfer-explained.xml -->

## Transferências de dados em tempo real

As transferências de dados em tempo real enviam e recebem IDs de segmento conforme um usuário visita ou toma medidas no site. Normalmente, as transferências de dados síncronas são úteis quando é necessário qualificar ou segmentar os usuários imediatamente, conforme eles navegam pelo inventário.

## Etapas da integração de dados

O processo de integração de dados em tempo real funciona da seguinte maneira:

1. Um usuário visita o site de um cliente que contém código Audience Manager.
1. O Audience Manager carrega um iframe e faz uma chamada para nosso [!UICONTROL Data Collection Server] ( [!DNL DCS]).
1. O [!DNL DCS] chama o servidor de terceiros (em tempo real) para verificar se o fornecedor tem alguma informação de segmento sobre o usuário.
1. O provedor de conteúdo retorna informações do segmento sobre esse usuário para o Audience Manager.
1. O Audience Manager recebe essas informações de segmento e as disponibiliza para direcionamento e criação de novas características e segmentos.

![](assets/rt_reduce70.png)