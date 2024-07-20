---
description: O processo de assimilação de dados de entrada em tempo real usa uma série de solicitações HTTP do navegador de um usuário para transmitir dados para o Audience Manager.
seo-description: The real-time inbound data ingestion process uses a series of HTTP requests from a user's browser to pass in data to Audience Manager.
seo-title: Real-Time Inbound Data Ingestion
solution: Audience Manager
title: Assimilação de dados de entrada em tempo real
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Inbound Data Transfers
exl-id: d243c74c-3a29-4dbf-a4c7-43ea526a9d7b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 1%

---

# Assimilação de dados de entrada em tempo real {#real-time-inbound-data-ingestion}

O processo de assimilação de dados de entrada em tempo real usa uma série de `HTTP` solicitações do navegador de um usuário para enviar dados para o Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

Os dados de entrada devem ser formatados como pares de valores chave chamados sinais. Normalmente, cada sinal é mapeado para um segmento criado ou gerenciado através da interface de usuário ou [!DNL API].

## Parâmetros e sintaxe da string de URL {#url-string-syntax}

O [!DNL URL] para uma transferência de dados de entrada deve conter as variáveis descritas abaixo. Lembre-se de [criar características](../../../features/traits/create-onboarded-rule-based-traits.md) e uma [estrutura de pastas](../../../features/traits/trait-storage.md#create-trait-storage-folder) na interface do usuário do [!DNL Audience Manager] antes de configurar transferências de dados em tempo real.

>[!NOTE]
>
>Substitua o conteúdo em itálico pelos valores reais do parâmetro.

| Parâmetro | Descrição |
|---|---|
| `<KEY>` | Um identificador exclusivo em um par de valor-chave (por exemplo, gênero, cor, preço). |
| `<VAL>` | Uma variável que pertence ao conjunto de dados definido pela chave (por exemplo, gender=male, color=green, price=100) |

### Sintaxe do URL

Durante um processo de assimilação de dados de entrada em tempo real, uma cadeia de caracteres [!DNL URL] formatada corretamente usa a seguinte sintaxe:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
