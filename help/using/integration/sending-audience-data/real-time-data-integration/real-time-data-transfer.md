---
description: O processo de ingestão de dados em tempo real usa uma série de solicitações HTTP de um navegador do usuário para passar dados para o Audience Manager.
seo-description: O processo de ingestão de dados em tempo real usa uma série de solicitações HTTP de um navegador do usuário para passar dados para o Audience Manager.
seo-title: Ingestão de dados de entrada em tempo real
solution: Audience Manager
title: Ingestão de dados de entrada em tempo real
uuid: 43 cb 0 ebc -6 c 36-4391-bbfb -6 b 203 d 63 c 69 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Real-Time Inbound Data Ingestion {#real-time-inbound-data-ingestion}

The real-time inbound data ingestion process uses a series of `HTTP` requests from a user's browser to pass in data to Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

Os dados de entrada devem ser formatados como pares de valores chave chamados sinais. Typically, each signal is mapped to a segment created or managed through the user interface or [!DNL API].

## URL String Parameters and Syntax {#url-string-syntax}

The [!DNL URL] for an inbound data transfer should contain the variables described below. Remember to [create traits](../../../features/traits/create-onboarded-rule-based-traits.md) and a [folder structure](../../../features/traits/trait-storage.md#create-trait-storage-folder) in the [!DNL Audience Manager] UI before setting up real-time data transfers.

>[!NOTE]
>
>Substitua o conteúdo itálico por valores de parâmetro reais.

| Parâmetro | Descrição |
|---|---|
| `<KEY>` | Um identificador exclusivo em um par de valor chave (por exemplo, gênero, cor, preço). |
| `<VAL>` | Uma variável que pertence ao conjunto de dados definido pela chave (por exemplo, sexo = masculino, color = green, price = 100) |

### Sintaxe do URL

During a real-time inbound data ingestion process, a properly formatted [!DNL URL] string uses the following syntax:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
