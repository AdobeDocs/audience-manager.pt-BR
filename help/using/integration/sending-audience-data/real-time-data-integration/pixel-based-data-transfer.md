---
description: Os pixels simples (que podem ser usados para qualificar usuários para características) executam transferências de dados em tempo real. A interface Audience Manager permite que os clientes criem qualquer número de pixels em uma base de autoatendimento. As strings de pixels consistem em IDs simples ou pares de valores chave.
seo-description: Os pixels simples (que podem ser usados para qualificar usuários para características) executam transferências de dados em tempo real. A interface Audience Manager permite que os clientes criem qualquer número de pixels em uma base de autoatendimento. As strings de pixels consistem em IDs simples ou pares de valores chave.
seo-title: Transferências de dados com base em pixels
solution: Audience Manager
title: Transferências de dados com base em pixels
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 4%

---


# Transferências de dados com base em pixels {#pixel-based-data-transfers}

Os pixels simples (que podem ser usados para qualificar usuários para características) executam transferências de dados em tempo real. A interface Audience Manager permite que os clientes criem qualquer número de pixels em uma base de autoatendimento. As strings de pixels consistem em IDs simples ou pares de valores chave.

<!-- c_rt_inbound_pixel_transfers.xml -->

Para permitir transferências de dados de entrada, o fornecedor e o cliente:

1. Determine quais características deseja que o fornecedor ou parceiro seja acionado.
1. Obtenha o pixel para o traço. Na tela lista de características, passe o mouse sobre a **[!UICONTROL Actions]** coluna e clique no **[!UICONTROL Get trait URL]** símbolo da característica desejada.
1. Forneça o [!DNL URL] para o fornecedor ou parceiro.

## Exemplos

Esta chamada básica de evento envia a ID de característica 1234 para [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

Você pode serializar IDs de características em uma chamada de evento para ajudar a reduzir o `HTTP` tráfego da página. Anexar IDs de característica adicionais à string do URL, como mostrado no exemplo a seguir:

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
