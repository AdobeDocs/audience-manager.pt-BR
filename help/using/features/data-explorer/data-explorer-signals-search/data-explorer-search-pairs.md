---
description: Procure por um ou vários sinais, com base em seus respectivos pares de valores chave.
seo-description: Procure por um ou vários sinais, com base em seus respectivos pares de valores chave.
seo-title: Pesquisar sinais por pares de valor-chave
title: Pesquisar sinais por pares de valor-chave
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: 'Data Explorer '
exl-id: d598da6b-8dc0-47ce-8389-1973b1803711
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 5%

---

# Pesquisar sinais por pares de valor-chave {#search-signals-by-key-value-pairs}

Procure por um ou vários sinais, com base em seus respectivos pares de valores chave.
Para procurar mais de um sinal, clique no botão ![Add](assets/icon_add.png). Insira os pares de valores chave que deseja pesquisar e use os seguintes filtros para limitar os resultados.

* **Status** do sinal: procurar sinais incluídos em características, sinais não utilizados ou ambos.
* **Exibir registros para**: selecione o intervalo de tempo no qual procurar sinais recebidos.
* **Contagens** mínimas: exibir apenas sinais com a contagem total mínima especificada no intervalo selecionado.

>[!IMPORTANT]
>
>Para obter uma experiência do usuário simplificada, os resultados de pesquisa de pares de valores-chave são baseados na amostragem de dados. Consulte [Amostragem de dados e taxas de erro](/help/using/reporting/report-sampling.md) para obter detalhes sobre como [!DNL Audience Manager] usa a amostragem de dados e por que pequenas variações de resultado podem aparecer ao comparar a pesquisa de valor-chave a pesquisas gerais.

Ao pesquisar sinais usando vários pares de valores chave, [!DNL Audience Manager] vincula os pares usando o operador lógico **AND**. Por exemplo, digamos que você esteja realizando uma pesquisa com os seguintes pares de valores chave:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Essa pesquisa retornará apenas resultados qualificados para todos os três filtros na mesma chamada: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Sinais excluídos da pesquisa de sinal {#excluded-signals}

As variáveis-chave usadas pelo Audience Manager e prefixadas pelos prefixos `d_` e `h_` não são reveladas por [!UICONTROL Signals Search]. Consulte [Requisitos de prefixo para variáveis-chave](../../traits/trait-variable-prefixes.md) para obter detalhes.

## Insensibilidade a maiúsculas e minúsculas e autocompletar de pesquisa {#case-insensitivity}

Os campos de pesquisa de chave e valor não distinguem maiúsculas de minúsculas. O campo de pesquisa principal inclui sugestões concluídas automaticamente.

![](assets/signal-search-suggestions.png)

Digamos que [!DNL Audience Manager] recebeu os seguintes sinais:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Ao inserir `product` no campo de pesquisa principal, você recebe sugestões automaticamente concluídas para `productCategory`, `newProduct`, `PRODUCT` e `product`.

Da mesma forma, quando você pesquisa por `product == phone`, [!UICONTROL Data Explorer] retorna resultados para `PRODUCT == phone` e `product == PHONE`.
As realizações de características preenchidas retroativamente não distinguem maiúsculas de minúsculas. Uma característica que contém o sinal com o par de valor chave `PRODUCT == SMARTPHONE` também qualifica o sinal com o par de valor chave `product == smartphone`.
