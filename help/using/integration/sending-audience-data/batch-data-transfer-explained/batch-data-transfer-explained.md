---
description: Uma visão geral de como o Audience Manager executa uma troca assíncrona de dados em lote com um fornecedor terceirizado.
seo-description: A general overview of how Audience Manager performs an asynchronous batch data exchange with a third-party vendor.
seo-title: Batch Data Transfer Process Described
solution: Audience Manager
title: Descrição do processo de transferência de dados em lote
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: Inbound Data Transfers
exl-id: e02dcc9a-4010-4c01-bd6b-ad04b8029f18
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 5%

---

# Descrição do processo de transferência de dados em lote {#batch-data-transfer-process-described}

Uma visão geral de como [!DNL Audience Manager] O realiza uma troca assíncrona de dados em lote com um fornecedor terceirizado.

## Integração de dados em lote

<!-- c_async.xml -->

O processo de integração de dados em lote salva as informações do visitante em nossos servidores e sincroniza esse material com os dados enviados por um provedor em intervalos regulares. O processo de transferência de dados assíncrono é útil quando:

* Não são necessárias transferências imediatas de dados.
* Coleta de dados para criar um grande pool de usuários segmentados.
* Você deseja reduzir as discrepâncias e `HTTP` chamadas do navegador.

![](assets/s2s_70.png)

## Etapas da integração de dados

1. Um usuário visita um site do cliente.
1. [!DNL Audience Manager] O e o provedor de dados de terceiros atribuem ao visitante um identificador exclusivo (geralmente com um cookie).
1. [!DNL Audience Manager] O chama o provedor de dados de terceiros para corresponder às IDs do visitante.
1. Uma solicitação agendada, geralmente em um intervalo diário, troca dados de segmento do visitante entre [!DNL Audience Manager] e seu provedor de dados de terceiros.
1. Sempre que uma entrada [!UICONTROL Server-to-Server] for processado, um recibo será enviado por email para soluções de parceiros e, se configurado, para o parceiro. Para obter mais informações, consulte [Mensagem de amostra para parceiros após o processamento de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).
