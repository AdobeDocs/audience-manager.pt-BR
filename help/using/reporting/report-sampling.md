---
description: Um resumo da metodologia de amostragem usada para alguns relatórios, taxas de erro de amostra e uma lista de relatórios que retornam informações com base em dados de amostra.
seo-description: Um resumo da metodologia de amostragem usada para alguns relatórios, taxas de erro de amostra e uma lista de relatórios que retornam informações com base em dados de amostra.
seo-title: Amostras de dados e taxas de erro nos relatórios do Audience Manager selecionados
solution: Audience Manager
title: Amostras de dados e taxas de erro nos relatórios do Audience Manager selecionados
uuid: 3 d 8 bd 764-a 9 da -40 f 1-8794-54304457 bb 9 a
translation-type: tm+mt
source-git-commit: d96182b0741dd31cc5ec0ffb68182ed5f8445c03

---


# Data Sampling and Error Rates in Selected Audience Manager Reports{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

Um resumo da metodologia de amostragem usada para alguns relatórios, taxas de erro de amostra e uma lista de relatórios que retornam informações com base em dados de amostra.

## Data Sampling Ratio and Minimum Requirements {#data-sampling-ratio}

Some [!DNL Audience Manager] reports display results based on a sampled set of the total amount of available data. A taxa de dados de amostra é 1:54. Para relatórios que usam dados de amostra, isso significa que os resultados são baseados em 1 registro de cada conjunto de 54 registros.

Esses relatórios usam dados de amostra porque eles precisam de uma grande quantidade de energia computacional para gerar resultados. A amostragem ajuda a atingir um equilíbrio entre as exigências computacionais reduzidas, manter o desempenho do sistema e fornecer resultados precisos.

Relatórios que usam amostras excluem características e segmentos quando eles não atendem aos requisitos mínimos do visitante único. Esses requisitos mínimos são os seguintes:

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-qualification-reference.md#unique-trait-realizations) over a 14-day period.
* Segmentos: 70,000 usuários em tempo real ao longo de um período de 14 dias.

## Error Rates {#error-rates}

Podem ocorrer erros nos relatórios que geram dados de sobreposição. Um erro é definido como a porcentagem de registros que:

* Não deve ter sido incluído em um relatório, mas foi adicionado.
* Deveria ter sido incluído em um relatório, mas foi omitido.

It's important to note that our tests and models show that the error rate *decreases* in an inverse proportion to the number of records in your data set. Os conjuntos de dados que possuem muitos registros geram menos erros que os conjuntos com um pequeno número de registros. Vejamos essa asserção de forma mais quantitativa. Como mostrado na tabela a seguir, para um número definido de registros, 95% dos resultados do relatório estarão abaixo de uma taxa de erros específica.

| Número de registros | Taxa de erro |
|--- |--- |
| 500 - 1,000 | 95% estão abaixo de uma taxa de erro de 42%. |
| 1,000 - 1,500 | 95% estão abaixo de uma taxa de erro de 34%. |
| 10,000 - 50,000 | 95% estão abaixo de uma taxa de erro de 14%. |
| 50.000 | 95% estão abaixo de uma taxa de erro de 6%. |
| 100,000 | 95% estão abaixo de uma taxa de erro de 4%. |
| 500,000 (ou mais) | 95% estão abaixo de uma taxa de erro de 2%. |

## Reports That Use Sampled Data {#reports-using-sampled-data}

The [!DNL Audience Manager] reports that use sampled data include:

* [Sobreposição de relatórios](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (característica a característica, segmento-a-característica e segmento a segmento).
* [Dados de público-alvo](../features/addressable-audiences.md) endereçáveis (dados do cliente e do segmento).
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
