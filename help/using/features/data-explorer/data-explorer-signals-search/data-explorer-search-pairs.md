---
description: Pesquise por um ou vários sinais, com base em seus respectivos pares de valor chave.
seo-description: Pesquise por um ou vários sinais, com base em seus respectivos pares de valor chave.
seo-title: Sinais de pesquisa por pares de valores chave
title: Sinais de pesquisa por pares de valores chave
uuid: 2 a 38 d 0 d 4-4 a 2 e -4 ca 5-b 9 ec-af 9 d 4963 d 876
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# Search Signals by Key-Value Pairs {#search-signals-by-key-value-pairs}

Pesquise por um ou vários sinais, com base em seus respectivos pares de valor chave.
To search for more than one signal, click the ![Add](assets/icon_add.png) button. Insira os pares de valores chave que deseja pesquisar e use os seguintes filtros para limitar os resultados.

* **Status do sinal**: procurar sinais incluídos em características, sinais não usados ou ambos.
* **Exibir registros para**: selecione o intervalo de tempo no qual pesquisar os sinais recebidos.
* **Contagens mínimas**: exibir apenas sinais com a contagem mínima especificada especificada no intervalo selecionado.

>[!IMPORTANT]
>
>Para uma experiência de usuário simplificada, os resultados de pesquisa par de valores chave são baseados na amostragem de dados. See [Data Sampling and Error Rates](/help/using/reporting/report-sampling.md) for details on how [!DNL Audience Manager] uses data sampling and why slight result variations may appear when comparing key-value search to general searches.

When searching for signals using multiple key-value pairs, [!DNL Audience Manager] links the pairs using the logical **AND** operator. Por exemplo, digamos que você esteja realizando uma pesquisa com os seguintes pares chave-valor:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

This search will return only results that qualify for all three filters on the same call: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Case Insensitivity and Search Auto-Completion {#case-insensitivity}

Os campos de pesquisa de chave e valor não distinguem letras maiúsculas de minúsculas. O campo de pesquisa principal inclui sugestões concluídas automaticamente.

![](assets/signal-search-suggestions.png)

Let&#39;s say [!DNL Audience Manager] received the following signals:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

When you enter `product` in the key search field, you receive auto-completed suggestions for `productCategory`, `newProduct`, `PRODUCT`, and `product`.

Similarly, when you search for `product == phone`, [!UICONTROL Data Explorer] returns results for both `PRODUCT == phone` and `product == PHONE`.
As ações de característica retroativa não distinguem maiúsculas de minúsculas. A trait containing the signal with the key-value pair `PRODUCT == SMARTPHONE` also qualifies the signal with the key-value pair `product == smartphone`.