---
description: Uma visão geral geral de como o Audience Manager realiza uma troca assíncrona de dados em lote com um fornecedor terceirizado.
seo-description: Uma visão geral geral de como o Audience Manager realiza uma troca assíncrona de dados em lote com um fornecedor terceirizado.
seo-title: Descrição do processo de transferência de dados em lote
solution: Audience Manager
title: Descrição do processo de transferência de dados em lote
uuid: a 9 eee 940-151 c -44 f 8-9 fe 9-8 ab 47 d 8 fa 45 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Batch Data Transfer Process Described {#batch-data-transfer-process-described}

Uma visão geral geral de como o Audience Manager realiza uma troca assíncrona de dados em lote com um fornecedor terceirizado.

## Integração de dados em lote

<!-- c_async.xml -->

O processo de integração de dados em lote salva as informações do visitante nos nossos servidores e sincroniza esse material com dados enviados por um provedor a intervalos regulares. O processo assíncrono de transferência de dados é útil quando:

* Transferências de dados imediatas não são necessárias.
* Coleta de dados para criar um grande conjunto de usuários segmentados.
* You want to reduce data discrepancies and `HTTP` calls from the browser.

![](assets/s2s_70.png)

## Etapas de integração de dados

1. Um usuário visita um site do cliente.
1. O Audience Manager e o provedor de dados de terceiros atribuem o visitante uma ID exclusiva (geralmente com um cookie).
1. O Audience Manager chama o provedor de dados de terceiros para corresponder às IDs do visitante.
1. Uma solicitação programada, normalmente em um intervalo diário, envia os dados de segmento do visitante entre o Audience Manager e seu provedor de dados de terceiros.
1. Whenever an inbound [!UICONTROL Server-to-Server] file is processed, a receipt is sent via email to partner solutions and, if configured, to the partner. For more information, see [Sample Message to Partners after Inbound Processing](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).