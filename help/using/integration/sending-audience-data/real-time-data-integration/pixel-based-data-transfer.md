---
description: Os pixels simples (que podem ser usados para qualificar usuários para características) executam transferências de dados em tempo real. A interface do Audience Manager permite que os clientes criem qualquer número de pixels com base em autoatendimento. As cadeias de caracteres de pixels consistem em IDs simples ou pares de valores chave.
seo-description: Os pixels simples (que podem ser usados para qualificar usuários para características) executam transferências de dados em tempo real. A interface do Audience Manager permite que os clientes criem qualquer número de pixels com base em autoatendimento. As cadeias de caracteres de pixels consistem em IDs simples ou pares de valores chave.
seo-title: Transferências de dados com base em pixels
solution: Audience Manager
title: Transferências de dados com base em pixels
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Transferências de dados de entrada
exl-id: fe9ecb97-4a45-4fbb-855e-01df007144cf
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 4%

---

# Transferências de dados com base em pixels {#pixel-based-data-transfers}

Os pixels simples (que podem ser usados para qualificar usuários para características) executam transferências de dados em tempo real. A interface do Audience Manager permite que os clientes criem qualquer número de pixels com base em autoatendimento. As cadeias de caracteres de pixels consistem em IDs simples ou pares de valores chave.

<!-- c_rt_inbound_pixel_transfers.xml -->

Para permitir transferências de dados de entrada, o fornecedor e o cliente:

1. Determine quais características você deseja que o fornecedor ou parceiro seja acionado.
1. Obtenha o pixel da característica. Na tela da lista de características, passe o mouse sobre a coluna **[!UICONTROL Actions]** e clique no símbolo **[!UICONTROL Get trait URL]** para a característica desejada.
1. Forneça o [!DNL URL] ao fornecedor ou parceiro.

## Exemplos

Essa chamada de evento básica envia a ID de característica 1234 para [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

Você pode serializar IDs de características em uma chamada de evento para ajudar a reduzir o tráfego `HTTP` da página. Anexe IDs de característica adicionais à cadeia de caracteres do URL, conforme mostrado no exemplo a seguir:

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
