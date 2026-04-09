---
description: Uma visão geral de como o Audience Manager executa uma troca assíncrona de dados em lote com um fornecedor terceirizado.
seo-description: A general overview of how Audience Manager performs an asynchronous batch data exchange with a third-party vendor.
seo-title: Batch Data Transfer Process Described
solution: Audience Manager
title: Descrição do processo de transferência de dados em lote
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: Inbound Data Transfers
exl-id: e02dcc9a-4010-4c01-bd6b-ad04b8029f18
TQID: https://experienceleague.adobe.com/HXA9Ql-ulLQ8itnnGnwMuk82nFRZnrFYaOGniGNDgn8
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 0%

---

# Descrição do processo de transferência de dados em lote {#batch-data-transfer-process-described}

Uma visão geral de como o [!DNL Audience Manager] executa uma troca assíncrona de dados em lote com um fornecedor terceirizado.

## Integração de dados em lote

<!-- c_async.xml -->

O processo de integração de dados em lote salva as informações do visitante em nossos servidores e sincroniza esse material com os dados enviados por um provedor em intervalos regulares. O processo de transferência de dados assíncrono é útil quando:

* Não são necessárias transferências imediatas de dados.
* Coleta de dados para criar um grande pool de usuários segmentados.
* Você deseja reduzir as discrepâncias de dados e `HTTP` chamadas do navegador.

![](assets/s2s_70.png)

## Etapas da integração de dados

1. Um usuário visita um site do cliente.
1. [!DNL Audience Manager] e o provedor de dados de terceiros atribuem ao visitante um identificador exclusivo (geralmente com um cookie).
1. [!DNL Audience Manager] chama o provedor de dados de terceiros para corresponder às IDs do visitante.
1. Uma solicitação agendada, geralmente em um intervalo diário, troca dados de segmento de visitante entre [!DNL Audience Manager] e seu provedor de dados de terceiros.
1. Sempre que um arquivo de entrada [!UICONTROL Server-to-Server] é processado, um recibo é enviado por email para soluções de parceiros e, se configurado, para o parceiro. Para obter mais informações, consulte [Mensagem de Exemplo para Parceiros após o Processamento de Entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).
