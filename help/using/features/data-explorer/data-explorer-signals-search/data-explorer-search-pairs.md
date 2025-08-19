---
description: Procure um ou vários sinais, com base nos respectivos pares de valores chave.
seo-description: Search for one or multiple signals, based on their respective key-value pairs.
seo-title: Search Signals by Key-Value Pairs
title: Pesquisar sinais por pares de valor-chave
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
exl-id: d598da6b-8dc0-47ce-8389-1973b1803711
source-git-commit: 6f8f82062403831e5b99525c4f3c3512c67d71bf
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---

# Pesquisar sinais por pares de valores chave {#search-signals-by-key-value-pairs}

Procure um ou vários sinais, com base nos respectivos pares de valores chave.
Para procurar mais de um sinal, clique no botão ![Adicionar](assets/icon_add.png). Insira os pares de valor-chave que deseja pesquisar e use os filtros a seguir para restringir os resultados.

* **Status do sinal**: procure sinais incluídos em características, sinais não utilizados ou ambos.
* **Exibir registros para**: selecione o intervalo de tempo no qual procurar sinais recebidos.
* **Contagens mínimas**: exibir apenas sinais com a contagem total mínima especificada no intervalo selecionado.

>[!IMPORTANT]
>
>Para uma experiência do usuário simplificada, os resultados de pesquisa do par de valores-chave se baseiam na amostragem de dados. Consulte [Amostragem de Dados e Taxas de Erro](/help/using/reporting/report-sampling.md) para obter detalhes sobre como o [!DNL Audience Manager] usa a amostragem de dados e por que pequenas variações de resultado podem aparecer ao comparar a pesquisa de valor chave com pesquisas gerais.

Ao pesquisar sinais usando vários pares de valores chave, [!DNL Audience Manager] vincula os pares usando o operador lógico **AND**. Por exemplo, digamos que você esteja fazendo uma pesquisa com os seguintes pares de valores chave:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Esta pesquisa retornará apenas resultados qualificados para todos os três filtros na mesma chamada: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Sinais excluídos da pesquisa de sinal {#excluded-signals}

As variáveis principais usadas pelo Audience Manager e prefixadas pelos prefixos `d_` e `h_` não são exibidas por [!UICONTROL Signals Search]. Consulte [Requisitos de prefixo para variáveis-chave](../../traits/trait-variable-prefixes.md) para obter detalhes.

## Distinção entre maiúsculas e minúsculas e preenchimento automático de pesquisa {#case-insensitivity}

Os campos de pesquisa de chave e valor fazem distinção entre maiúsculas e minúsculas. O campo de pesquisa principal inclui sugestões preenchidas automaticamente.

![](assets/signal-search-suggestions.png)

Digamos que [!DNL Audience Manager] recebeu os seguintes sinais:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Ao inserir `product` no campo de pesquisa por chave, você receberá sugestões preenchidas automaticamente para `productCategory` e `product`.

Da mesma forma, quando você pesquisa por `product == PHONE`, [!UICONTROL Data Explorer] retorna resultados somente para `product == PHONE`.

As realizações de características com preenchimento retroativo também fazem distinção entre maiúsculas e minúsculas. Uma característica que contém o sinal com o par de valores chave `PRODUCT == SMARTPHONE` não qualifica o sinal com o par de valores chave `product == smartphone`.
