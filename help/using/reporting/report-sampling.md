---
description: Um resumo da metodologia de amostragem utilizada para alguns relatórios, taxas de erro de amostragem e uma lista de relatórios que retornam informações com base em dados recolhidos.
seo-description: Um resumo da metodologia de amostragem utilizada para alguns relatórios, taxas de erro de amostragem e uma lista de relatórios que retornam informações com base em dados recolhidos.
seo-title: Amostragem de dados e taxas de erro em alguns relatórios do Audience Manager
solution: Audience Manager
title: Amostragem de dados e taxas de erro em alguns relatórios do Audience Manager
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: Referência de relatórios
exl-id: 0b7f9423-0859-4fa8-926b-e4858eed2294
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 7%

---

# Amostragem de dados e taxas de erro em alguns relatórios do Audience Manager{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

Um resumo da metodologia de amostragem utilizada para alguns relatórios, taxas de erro de amostragem e uma lista de relatórios que retornam informações com base em dados recolhidos.

## Proporção de amostragem de dados {#data-sampling-ratio}

Alguns relatórios [!DNL Audience Manager] exibem resultados com base em um conjunto amostrado da quantidade total de dados disponíveis. A proporção de dados amostrada é de 1:54. Para relatórios que usam dados de amostra, seus resultados são baseados em 1 registro de cada conjunto de 54 registros.

Esses relatórios usam dados estatísticos de amostra porque eles precisam de uma grande quantidade de poder de computação para gerar resultados. A amostragem ajuda a equilibrar as demandas computacionais reduzidas, mantendo o desempenho do sistema e fornecendo resultados precisos.

<!--

## Minimum Requirements {#minimum-requirements}

>[!NOTE]
>
>The minimum requirements listed below apply to Overlap reports only.

Overlap reports ([trait-to-trait](/help/using/reporting/dynamic-reports/trait-trait-overlap-report.md), [segment-to-trait](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md), and [segment-to-segment](/help/using/reporting/dynamic-reports/segment-segment-overlap-report.md)) exclude traits and segments when they do not meet the minimum unique visitor requirements. These minimum requirements are as follows:

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-and-segment-qualification-reference).
* Segments: 70,000 real-time users over a 14-day period.

-->

## Taxas de erro {#error-rates}

Erros podem ocorrer em relatórios que geram dados de sobreposição. Um erro é definido como a porcentagem de registros que:

* Não deveria ter sido incluído num relatório, mas sim adicionado.
* Deveria ter sido incluído em um relatório, mas foi deixado de fora.

É importante observar que nossos testes e modelos mostram que a taxa de erro *diminui* em uma proporção inversa ao número de registros no conjunto de dados. Conjuntos de dados com muitos registros geram menos erros que conjuntos com um pequeno número de registros. Vejamos essa afirmação de forma mais quantitativa. Como mostrado na tabela a seguir, para um número definido de registros, 95% dos resultados do relatório estarão abaixo de uma taxa de erro específica.

| Número de registros | Taxa de erro |
|--- |--- |
| 500 - 1.000 | 95% estão abaixo de uma taxa de erro de 42%. |
| 1.000 - 1.500 | 95% estão abaixo de uma taxa de erro de 34%. |
| 10.000 - 50.000 | 95% estão abaixo de uma taxa de erro de 14%. |
| 50.000 | 95% estão abaixo de uma taxa de erro de 6%. |
| 100.000 | 95% estão abaixo de uma taxa de erro de 4%. |
| 500.000 (ou mais) | 95% estão abaixo de uma taxa de erro de 2%. |

## Usando a metodologia de amostragem de minhash {#minhash}

Com base na metodologia de amostragem [Minhash](https://en.wikipedia.org/wiki/MinHash), o Audience Manager usa um novo método para calcular estimativas de características e segmentos sobre um rascunho de dados de hash de uma permutação. Esse novo método produz uma variação menor do que o estimador padrão da similaridade Jaccard. Consulte a seção abaixo para obter os relatórios que usam essa metodologia.

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## Relatórios que usam dados de amostra {#reports-using-sampled-data}

Os relatórios [!DNL Audience Manager] que usam dados estatísticos amostrados e a metodologia de amostragem de Minhash incluem:

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| Amostragem estatística | Metodologia de amostragem de minhash |
|--- |--- |
| [Dados de ](../features/addressable-audiences.md) público-alvo endereçáveis (dados a nível de cliente e segmento). | [Relatórios de sobreposição](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)  (característica, segmento para característica e segmento para segmento) |
| A métrica [Total de dispositivos](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) para um [!UICONTROL Profile Merge Rule]. | [Recomendações de característica](/help/using/features/segments/trait-recommendations.md) |
| [O Data ](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) Explorer usa dados de amostra na  [!UICONTROL Search] guia e em qualquer  [!UICONTROL Saved Searches] | [Audience Marketplace Recommendations](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |
