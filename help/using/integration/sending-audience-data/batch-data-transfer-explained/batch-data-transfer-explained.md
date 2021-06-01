---
description: Uma visão geral de como o Audience Manager executa uma troca assíncrona de dados em lote com um fornecedor terceirizado.
seo-description: Uma visão geral de como o Audience Manager executa uma troca assíncrona de dados em lote com um fornecedor terceirizado.
seo-title: Descrição do processo de transferência de dados em lote
solution: Audience Manager
title: Descrição do processo de transferência de dados em lote
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: Transferência de dados de entrada
exl-id: e02dcc9a-4010-4c01-bd6b-ad04b8029f18
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 8%

---

# Descrição do processo de transferência de dados em lote {#batch-data-transfer-process-described}

Uma visão geral de como o [!DNL Audience Manager] executa uma troca de dados em lote assíncrona com um fornecedor terceirizado.

## Integração de dados em lote

<!-- c_async.xml -->

O processo de integração de dados em lote salva as informações do visitante em nossos servidores e sincroniza esse material com os dados enviados por um provedor em intervalos regulares. O processo assíncrono de transferência de dados é útil quando:

* Não são necessárias transferências de dados imediatas.
* Coleta de dados para criar um grande pool de usuários segmentados.
* Você deseja reduzir as discrepâncias de dados e as chamadas `HTTP` do navegador.

![](assets/s2s_70.png)

## Etapas da integração de dados

1. Um usuário visita um site de cliente.
1. [!DNL Audience Manager] e o provedor de dados de terceiros atribui ao visitante uma ID exclusiva (geralmente com um cookie).
1. [!DNL Audience Manager] O chama o provedor de dados de terceiros para corresponder às IDs do visitante.
1. Uma solicitação programada, normalmente em um intervalo diário, troca dados do segmento de visitante entre [!DNL Audience Manager] e seu provedor de dados de terceiros.
1. Sempre que um arquivo de entrada [!UICONTROL Server-to-Server] é processado, um recebimento é enviado por email para soluções de parceiros e, se configurado, para o parceiro. Para obter mais informações, consulte [Mensagem de amostra para parceiros após o processamento de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).
