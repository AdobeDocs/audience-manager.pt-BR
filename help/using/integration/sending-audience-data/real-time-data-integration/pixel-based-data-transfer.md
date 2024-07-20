---
description: Pixels simples (que podem ser usados para qualificar usuários para características) executam transferências de dados em tempo real. A interface Audience Manager permite que os clientes criem qualquer número de pixels com base no autoatendimento. As sequências de pixels consistem em IDs simples ou pares de valores chave.
seo-description: Simple pixels (that can be used to qualify users for traits) perform real-time data transfers. The Audience Manager interface lets clients create any number of pixels on a self-service basis. Pixel strings consist of simple IDs or key-value pairs.
seo-title: Pixel-based Data Transfers
solution: Audience Manager
title: Transferências de dados com base em pixels
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Inbound Data Transfers
exl-id: fe9ecb97-4a45-4fbb-855e-01df007144cf
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 0%

---

# Transferências de dados com base em pixels {#pixel-based-data-transfers}

Pixels simples (que podem ser usados para qualificar usuários para características) executam transferências de dados em tempo real. A interface Audience Manager permite que os clientes criem qualquer número de pixels com base no autoatendimento. As sequências de pixels consistem em IDs simples ou pares de valores chave.

<!-- c_rt_inbound_pixel_transfers.xml -->

Para habilitar transferências de dados de entrada, o fornecedor e o cliente devem:

1. Determine quais características você deseja que o fornecedor ou parceiro acione.
1. Obtenha o pixel para a característica. Na tela da lista de características, passe o mouse sobre a coluna **[!UICONTROL Actions]** e clique no símbolo **[!UICONTROL Get trait URL]** para a característica desejada.
1. Forneça o [!DNL URL] ao fornecedor ou parceiro.

## Exemplos

Esta chamada de evento básica envia a ID de característica 1234 para [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

Você pode serializar IDs de características em uma chamada de evento para ajudar a reduzir o tráfego de `HTTP` da página. Anexe IDs de característica adicionais à string do URL, como mostrado no exemplo a seguir:

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
