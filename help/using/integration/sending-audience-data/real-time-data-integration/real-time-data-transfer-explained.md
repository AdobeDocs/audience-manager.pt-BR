---
description: Uma visão geral de como o Audience Manager executa transferências de dados em tempo real com um provedor de conteúdo de terceiros.
seo-description: A general overview of how Audience Manager performs real-time data transfers with a third-party content provider.
seo-title: Real-Time Data Transfer Process Described
solution: Audience Manager
title: Descrição do processo de transferência de dados em tempo real
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
    internal-label: Integrations
subfeature_v2:
  - id: a03b8192-8410-479f-a326-4cddf10757f6
    internal-label: Inbound data transfers
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 0%
---

# Descrição do processo de transferência de dados em tempo real{#real-time-data-transfer-process-described}

Uma visão geral de como o Audience Manager executa transferências de dados em tempo real com um provedor de conteúdo de terceiros.

<!-- real-time-data-transfer-explained.xml -->

## Transferências de dados em tempo real

As transferências de dados em tempo real enviam e recebem IDs de segmento como visitas de usuários ou ações em seu site. Normalmente, as transferências de dados síncronas são úteis quando você precisa qualificar ou segmentar os usuários imediatamente, à medida que eles navegam pelo inventário.

## Etapas da integração de dados

O processo de integração de dados em tempo real funciona da seguinte maneira:

1. Um usuário visita o site de um cliente que contém o código Audience Manager.
1. O Audience Manager carrega um iframe e faz uma chamada para o nosso [!UICONTROL Data Collection Server] ( [!DNL DCS]).
1. O [!DNL DCS] chama o servidor de terceiros (em tempo real) para verificar se o fornecedor tem alguma informação de segmento sobre o usuário.
1. O provedor de conteúdo retorna informações de segmento sobre esse usuário para o Audience Manager.
1. O Audience Manager recebe essas informações de segmento e as disponibiliza para direcionar e criar novas características e segmentos.

![](assets/rt_reduce70.png)