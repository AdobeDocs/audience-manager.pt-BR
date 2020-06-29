---
description: O processo de ingestão de dados de entrada em tempo real usa uma série de solicitações HTTP do navegador de um usuário para passar os dados para o Audience Manager.
seo-description: O processo de ingestão de dados de entrada em tempo real usa uma série de solicitações HTTP do navegador de um usuário para passar os dados para o Audience Manager.
seo-title: Ingestão de dados de entrada em tempo real
solution: Audience Manager
title: Ingestão de dados de entrada em tempo real
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 1%

---


# Ingestão de dados de entrada em tempo real {#real-time-inbound-data-ingestion}

O processo de ingestão de dados de entrada em tempo real usa uma série de `HTTP` solicitações do navegador de um usuário para passar os dados para o Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

Os dados de entrada devem ser formatados como pares de valores chave chamados sinais. Normalmente, cada sinal é mapeado para um segmento criado ou gerenciado pela interface do usuário ou [!DNL API].

## Parâmetros e sintaxe da string de URL {#url-string-syntax}

O [!DNL URL] para uma transferência de dados de entrada deve conter as variáveis descritas abaixo. Lembre-se de [criar características](../../../features/traits/create-onboarded-rule-based-traits.md) e uma estrutura [de](../../../features/traits/trait-storage.md#create-trait-storage-folder) [!DNL Audience Manager] pasta na interface do usuário antes de configurar transferências de dados em tempo real.

>[!NOTE]
>
>Substitua o conteúdo em itálico por valores de parâmetro reais.

| Parâmetro | Descrição |
|---|---|
| `<KEY>` | Um identificador exclusivo em um par de valor chave (por exemplo, gênero, cor, preço). |
| `<VAL>` | Uma variável que pertence ao conjunto de dados definido pela chave (por exemplo, gênero=masculino, cor=verde, preço=100) |

### Sintaxe de URL

Durante um processo de ingestão de dados de entrada em tempo real, uma sequência de [!DNL URL] caracteres formatada corretamente usa a seguinte sintaxe:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
