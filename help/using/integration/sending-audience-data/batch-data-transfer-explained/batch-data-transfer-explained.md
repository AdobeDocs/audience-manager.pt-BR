---
description: Uma visão geral de como o Audience Manager executa uma troca assíncrona de dados em lote com um fornecedor terceirizado.
seo-description: Uma visão geral de como o Audience Manager executa uma troca assíncrona de dados em lote com um fornecedor terceirizado.
seo-title: Processo de transferência de dados em lote descrito
solution: Audience Manager
title: Processo de transferência de dados em lote descrito
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Processo de transferência de dados em lote descrito {#batch-data-transfer-process-described}

Uma visão geral de como o Audience Manager executa uma troca assíncrona de dados em lote com um fornecedor terceirizado.

## Integração de dados em lote

<!-- c_async.xml -->

O processo de integração de dados em lote salva as informações do visitante em nossos servidores e sincroniza esse material com os dados enviados por um provedor em intervalos regulares. O processo de transferência de dados assíncrono é útil quando:

* Não são necessárias transferências de dados imediatas.
* Coleta de dados para criar um grande pool de usuários segmentados.
* Você deseja reduzir as discrepâncias de dados e `HTTP` chamadas do navegador.

![](assets/s2s_70.png)

## Etapas da integração de dados

1. Um usuário visita um site de cliente.
1. O Audience Manager e o provedor de dados de terceiros atribuem ao visitante uma ID exclusiva (normalmente com um cookie).
1. O Audience Manager chama o provedor de dados de terceiros para corresponder às IDs do visitante.
1. Uma solicitação programada, normalmente em um intervalo diário, troca dados de segmentos de visitantes entre o Audience Manager e o provedor de dados de terceiros.
1. Sempre que um [!UICONTROL Server-to-Server] arquivo de entrada é processado, um recibo é enviado por email para soluções de parceiros e, se configurado, para o parceiro. Para obter mais informações, consulte Mensagem de [amostra para parceiros após o processamento](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md)de entrada.