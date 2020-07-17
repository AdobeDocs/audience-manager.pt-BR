---
description: Procure um ou vários sinais, com base em seus respectivos pares de valores chave.
seo-description: Procure um ou vários sinais, com base em seus respectivos pares de valores chave.
seo-title: Pesquisar sinais por pares de valor-chave
title: Pesquisar sinais por pares de valor-chave
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 4%

---


# Pesquisar sinais por pares de valor-chave {#search-signals-by-key-value-pairs}

Procure um ou vários sinais, com base em seus respectivos pares de valores chave.
Para procurar mais de um sinal, clique no botão ![Adicionar](assets/icon_add.png) . Insira os pares de valores chave que deseja pesquisar e use os seguintes filtros para restringir seus resultados.

* **Estado** do sinal: procurar sinais incluídos em características, sinais não utilizados ou ambos.
* **Registros de Visualização para**: selecione o intervalo de tempo no qual procurar sinais recebidos.
* **Contagens** mínimas: exibir somente sinais com a contagem total mínima especificada no intervalo selecionado.

>[!IMPORTANT]
>
>Para uma experiência de usuário otimizada, os resultados de pesquisa de pares de valores chave são baseados na amostragem de dados. Consulte Amostragem de [dados e Taxas](/help/using/reporting/report-sampling.md) de erro para obter detalhes sobre como [!DNL Audience Manager] usa a amostragem de dados e por que pequenas variações de resultado podem aparecer ao comparar a pesquisa de valor chave com pesquisas gerais.

Ao procurar sinais usando vários pares de valores chave, [!DNL Audience Manager] vincula os pares usando o operador lógico **AND** . Por exemplo, digamos que você esteja realizando uma pesquisa com os seguintes pares de valor chave:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Essa pesquisa retornará somente os resultados que se qualificam para os três filtros na mesma chamada: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Sinais excluídos da pesquisa de sinal {#excluded-signals}

As variáveis-chave usadas pelo Audience Manager e prefixadas pelos prefixos `d_` e `h_` não são reveladas [!UICONTROL Signals Search]. Consulte Requisitos de [prefixo para variáveis](../../traits/trait-variable-prefixes.md) -chave para obter detalhes.

## Insensibilidade a maiúsculas e minúsculas e autocompletar a pesquisa {#case-insensitivity}

Os campos de pesquisa de chave e valor não distinguem maiúsculas de minúsculas. O campo de pesquisa principal inclui sugestões completadas automaticamente.

![](assets/signal-search-suggestions.png)

Digamos que [!DNL Audience Manager] recebam os seguintes sinais:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Ao digitar `product` no campo de pesquisa principal, você recebe sugestões completadas automaticamente para `productCategory`, `newProduct`, `PRODUCT`e `product`.

Da mesma forma, quando você pesquisa por `product == phone`, [!UICONTROL Data Explorer] retorna os resultados tanto `PRODUCT == phone` quanto `product == PHONE`.
Realizações de características preenchidas retroativamente não distinguem maiúsculas de minúsculas. Uma característica que contém o sinal com o par de valor chave também `PRODUCT == SMARTPHONE` qualifica o sinal com o par de valor chave `product == smartphone`.