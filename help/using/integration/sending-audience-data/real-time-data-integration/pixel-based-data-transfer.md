---
description: Os pixels simples (que podem ser usados para qualificar usuários para características) executam transferências de dados em tempo real. A interface do Audience Manager permite que os clientes criem qualquer número de pixels com base em autoatendimento. As strings de pixel consistem em IDs simples ou pares de valores chave.
seo-description: Os pixels simples (que podem ser usados para qualificar usuários para características) executam transferências de dados em tempo real. A interface do Audience Manager permite que os clientes criem qualquer número de pixels com base em autoatendimento. As strings de pixel consistem em IDs simples ou pares de valores chave.
seo-title: Transferências de dados baseadas em pixel
solution: Audience Manager
title: Transferências de dados baseadas em pixel
uuid: 8773 bfc 0-6 b 8 d -4 a 6 a-a 8 b 7-e 043744486 ab
translation-type: tm+mt
source-git-commit: 3fb90da3be8f50fe670c1193600f5e3a027be52c

---


# Pixel-based Data Transfers {#pixel-based-data-transfers}

Os pixels simples (que podem ser usados para qualificar usuários para características) executam transferências de dados em tempo real. A interface do Audience Manager permite que os clientes criem qualquer número de pixels com base em autoatendimento. As strings de pixel consistem em IDs simples ou pares de valores chave.

<!-- c_rt_inbound_pixel_transfers.xml -->

Para ativar transferências de dados de entrada, o fornecedor e o cliente seriam:

1. Determine quais características você deseja que o fornecedor ou parceiro acione.
1. Obtenha o pixel da característica. In the traits list screen, hover over the **[!UICONTROL Actions]** column and click the **[!UICONTROL Get trait URL]** symbol for the desired trait.
1. Provide the [!DNL URL] to the vendor or partner.

## Exemplos

This basic event call sends trait ID 1234 to [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

You can serialize trait IDs in an event call to help reduce `HTTP` traffic from the page. Anexe IDs de característica adicionais à sequência de caracteres de URL, como mostrado no exemplo a seguir:

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
