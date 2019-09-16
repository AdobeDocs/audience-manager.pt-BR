---
description: Os pixels simples (que podem ser usados para qualificar usuários para características) executam transferências de dados em tempo real. A interface do Audience Manager permite que os clientes criem qualquer número de pixels em uma base de autoatendimento. As strings de pixels consistem em IDs simples ou pares de valores chave.
seo-description: Os pixels simples (que podem ser usados para qualificar usuários para características) executam transferências de dados em tempo real. A interface do Audience Manager permite que os clientes criem qualquer número de pixels em uma base de autoatendimento. As strings de pixels consistem em IDs simples ou pares de valores chave.
seo-title: Transferências de dados baseadas em pixels
solution: Audience Manager
title: Transferências de dados baseadas em pixels
uuid: 8773bfc0-6b8d-4a6a-a8b7-e04374486ab
translation-type: tm+mt
source-git-commit: 3fb90da3be8f50fe670c1193600f5e3a027be52c

---


# Transferências de dados baseadas em pixels {#pixel-based-data-transfers}

Os pixels simples (que podem ser usados para qualificar usuários para características) executam transferências de dados em tempo real. A interface do Audience Manager permite que os clientes criem qualquer número de pixels em uma base de autoatendimento. As strings de pixels consistem em IDs simples ou pares de valores chave.

<!-- c_rt_inbound_pixel_transfers.xml -->

Para permitir transferências de dados de entrada, o fornecedor e o cliente:

1. Determine quais características deseja que o fornecedor ou parceiro seja acionado.
1. Obtenha o pixel para o traço. Na tela da lista de características, passe o mouse sobre a **[!UICONTROL Actions]** coluna e clique no **[!UICONTROL Get trait URL]** símbolo da característica desejada.
1. Forneça o relatório [!DNL URL] ao fornecedor ou parceiro.

## Exemplos

Esta chamada de evento básica envia a ID de característica 1234 para [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

Você pode serializar IDs de características em uma chamada de evento para ajudar a reduzir o `HTTP` tráfego da página. Anexar IDs de característica adicionais à string do URL, como mostrado no exemplo a seguir:

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
