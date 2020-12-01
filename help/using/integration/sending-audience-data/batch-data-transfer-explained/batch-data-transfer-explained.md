---
description: Uma visão geral de como o Audience Manager executa uma troca assíncrona de dados em lote com um fornecedor terceirizado.
seo-description: Uma visão geral de como o Audience Manager executa uma troca assíncrona de dados em lote com um fornecedor terceirizado.
seo-title: Descrição do processo de transferência de dados em lote
solution: Audience Manager
title: Descrição do processo de transferência de dados em lote
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: 231d8e537cf5b4f29b1c4f284fe1b3ffe6d187a9
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 7%

---


# Descrição do processo de transferência de dados em lote {#batch-data-transfer-process-described}

Uma visão geral de como [!DNL Audience Manager] executa uma troca assíncrona de dados em lote com um fornecedor terceirizado.

## Integração de dados em lote

<!-- c_async.xml -->

O processo de integração de dados em lote salva as informações do visitante em nossos servidores e sincroniza esse material com os dados enviados por um provedor em intervalos regulares. O processo de transferência de dados assíncrono é útil quando:

* Não são necessárias transferências de dados imediatas.
* Coleta de dados para criar um grande pool de usuários segmentados.
* Você deseja reduzir as discrepâncias de dados e as chamadas `HTTP` do navegador.

![](assets/s2s_70.png)

## Etapas da integração de dados

1. Um usuário visita um site de cliente.
1. [!DNL Audience Manager] e o provedor de dados de terceiros atribui ao visitante uma ID exclusiva (normalmente com um cookie).
1. [!DNL Audience Manager] chama o provedor de dados de terceiros para corresponder às IDs de visitante.
1. Uma solicitação programada, normalmente em um intervalo diário, troca dados de segmentos de visitantes entre [!DNL Audience Manager] e o provedor de dados de terceiros.
1. Sempre que um arquivo [!UICONTROL Server-to-Server] de entrada for processado, um recibo será enviado por email para as soluções do parceiro e, se configurado, para o parceiro. Para obter mais informações, consulte [Exemplo de mensagem para parceiros após o processamento de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).
