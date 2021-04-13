---
description: O processo de assimilação de dados de entrada em tempo real usa uma série de solicitações HTTP do navegador de um usuário para transmitir dados para o Audience Manager.
seo-description: O processo de assimilação de dados de entrada em tempo real usa uma série de solicitações HTTP do navegador de um usuário para transmitir dados para o Audience Manager.
seo-title: Assimilação de dados de entrada em tempo real
solution: Audience Manager
title: Assimilação de dados de entrada em tempo real
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Transferências de dados de entrada
exl-id: d243c74c-3a29-4dbf-a4c7-43ea526a9d7b
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 7%

---

# Assimilação de dados de entrada em tempo real {#real-time-inbound-data-ingestion}

O processo de assimilação de dados de entrada em tempo real usa uma série de solicitações `HTTP` do navegador de um usuário para transmitir dados para o Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

Os dados de entrada devem ser formatados como pares de valores chave chamados de sinais. Normalmente, cada sinal é mapeado para um segmento criado ou gerenciado pela interface do usuário ou [!DNL API].

## Parâmetros da string de URL e sintaxe {#url-string-syntax}

O [!DNL URL] para uma transferência de dados de entrada deve conter as variáveis descritas abaixo. Lembre-se de [criar características](../../../features/traits/create-onboarded-rule-based-traits.md) e uma [estrutura de pastas](../../../features/traits/trait-storage.md#create-trait-storage-folder) na interface do usuário [!DNL Audience Manager] antes de configurar transferências de dados em tempo real.

>[!NOTE]
>
>Substitua o conteúdo em itálico por valores de parâmetro reais.

| Parâmetro | Descrição |
|---|---|
| `<KEY>` | Um identificador exclusivo em um par de valor principal (por exemplo, gênero, cor, preço). |
| `<VAL>` | Uma variável que pertence ao conjunto de dados definido pela chave (por exemplo, gênero=masculino, cor=verde, preço=100) |

### Sintaxe do URL

Durante um processo de assimilação de dados de entrada em tempo real, uma sequência de caracteres [!DNL URL] formatada corretamente usa a seguinte sintaxe:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
