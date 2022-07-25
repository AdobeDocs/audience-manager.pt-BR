---
description: Procure por um ou vários sinais, com base em seus respectivos pares de valores chave.
seo-description: Search for one or multiple signals, based on their respective key-value pairs.
seo-title: Search Signals by Key-Value Pairs
title: Pesquisar sinais por pares de valor-chave
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
exl-id: d598da6b-8dc0-47ce-8389-1973b1803711
source-git-commit: 6f8f82062403831e5b99525c4f3c3512c67d71bf
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 1%

---

# Pesquisar sinais por pares de valor-chave {#search-signals-by-key-value-pairs}

Procure por um ou vários sinais, com base em seus respectivos pares de valores chave.
Para procurar mais de um sinal, clique no botão ![Adicionar](assets/icon_add.png) botão. Insira os pares de valores chave que deseja pesquisar e use os seguintes filtros para limitar os resultados.

* **Status do sinal**: procurar sinais incluídos em características, sinais não utilizados ou ambos.
* **Exibir registros para**: selecione o intervalo de tempo no qual procurar sinais recebidos.
* **Contagens mínimas**: exibir apenas sinais com a contagem total mínima especificada no intervalo selecionado.

>[!IMPORTANT]
>
>Para obter uma experiência do usuário simplificada, os resultados de pesquisa de pares de valores-chave são baseados na amostragem de dados. Consulte [Amostragem de dados e taxas de erro](/help/using/reporting/report-sampling.md) para obter detalhes sobre como [!DNL Audience Manager] O usa a amostragem de dados e por que pequenas variações de resultados podem aparecer ao comparar a pesquisa de valor-chave a pesquisas gerais.

Ao procurar sinais usando vários pares de valores-chave, [!DNL Audience Manager] vincula os pares usando o **E** operador. Por exemplo, digamos que você esteja realizando uma pesquisa com os seguintes pares de valores chave:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Essa pesquisa retornará apenas resultados qualificados para todos os três filtros na mesma chamada: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Sinais excluídos da pesquisa de sinal {#excluded-signals}

Variáveis principais usadas pelo Audience Manager e prefixadas pelo `d_` e `h_` os prefixos não são revelados por [!UICONTROL Signals Search]. Consulte [Requisitos de prefixo para variáveis-chave](../../traits/trait-variable-prefixes.md) para obter detalhes.

## Distinção entre maiúsculas e minúsculas e autopreenchimento de pesquisa {#case-insensitivity}

Os campos de pesquisa de chave e valor distinguem maiúsculas de minúsculas. O campo de pesquisa principal inclui sugestões concluídas automaticamente.

![](assets/signal-search-suggestions.png)

Vamos dizer [!DNL Audience Manager] recebeu os seguintes sinais:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Ao inserir `product` no campo pesquisa principal, você recebe sugestões concluídas automaticamente para `productCategory` e `product`.

Da mesma forma, ao pesquisar por `product == PHONE`, [!UICONTROL Data Explorer] retorna resultados somente para `product == PHONE`.

As realizações de característica com preenchimento retroativo também diferenciam maiúsculas de minúsculas. Uma característica que contém o sinal com o par de valor-chave `PRODUCT == SMARTPHONE` não qualifica o sinal com o par de valor-chave `product == smartphone`.
