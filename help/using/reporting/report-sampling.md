---
description: Um resumo da metodologia de amostragem utilizada para alguns relatórios, taxas de erro de amostragem e uma lista de relatórios que retornam informações com base em dados recolhidos.
seo-description: Um resumo da metodologia de amostragem utilizada para alguns relatórios, taxas de erro de amostragem e uma lista de relatórios que retornam informações com base em dados recolhidos.
seo-title: Amostragem de dados e taxas de erro em alguns relatórios do Audience Manager
solution: Audience Manager
title: Amostragem de dados e taxas de erro em alguns relatórios do Audience Manager
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: reporting reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 8%

---


# Amostragem de dados e taxas de erro em alguns relatórios do Audience Manager{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

Um resumo da metodologia de amostragem utilizada para alguns relatórios, taxas de erro de amostragem e uma lista de relatórios que retornam informações com base em dados recolhidos.

## Rácio de amostragem de dados e requisitos mínimos {#data-sampling-ratio}

Alguns [!DNL Audience Manager] relatórios exibem resultados com base em um conjunto de amostras da quantidade total de dados disponíveis. A proporção de dados amostrados é de 1:54. Para relatórios que usam dados de amostra, isso significa que seus resultados se baseiam em 1 registro de cada conjunto de 54 registros.

Esses relatórios usam dados de amostra porque precisam de uma grande quantidade de poder de computação para gerar resultados. A amostragem ajuda a equilibrar as demandas computacionais reduzidas, mantendo o desempenho do sistema e fornecendo resultados precisos.

Os relatórios que usam a amostragem excluem características e segmentos quando não atendem aos requisitos mínimos de visitante único. Estes requisitos mínimos são os seguintes:

* Características: 28.000 realização de características [únicas](/help/using/features/traits/trait-and-segment-qualification-reference.md#unique-trait-realizations) em um período de 14 dias.
* Segmentos: 70.000 usuários em tempo real em um período de 14 dias.

## Taxas de erro {#error-rates}

Erros podem ocorrer em relatórios que geram dados de sobreposição. Um erro é definido como a porcentagem de registros que:

* Não deveria ter sido incluído em um relatório, mas sim adicionado mesmo assim.
* Deveria ter sido incluído em um relatório, mas foi deixado de fora.

É importante observar que nossos testes e modelos mostram que a taxa de erro *diminui* em uma proporção inversa ao número de registros no conjunto de dados. Os conjuntos de dados com muitos registros geram menos erros do que os conjuntos com um pequeno número de registros. Vejamos essa afirmação de forma mais quantitativa. Conforme mostrado na tabela a seguir, para um número definido de registros, 95% dos resultados do relatório estarão abaixo de uma taxa de erro específica.

| Número de registros | Taxa de erro |
|--- |--- |
| 500 - 1,000 | 95% estão abaixo de uma taxa de erro de 42%. |
| 1,000 - 1,500 | 95% estão abaixo de uma taxa de erro de 34%. |
| 10,000 - 50,000 | 95% estão abaixo de uma taxa de erro de 14%. |
| 50.000 | 95% estão abaixo de uma taxa de erro de 6%. |
| 100,000 | 95% estão abaixo de uma taxa de erro de 4%. |
| 500.000 (ou mais) | 95% estão abaixo de uma taxa de erro de 2%. |

## Relatórios que usam dados de amostra {#reports-using-sampled-data}

Os [!DNL Audience Manager] relatórios que usam dados de amostra incluem:

* [Relatórios](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) de sobreposição (característica a característica, segmento a característica e segmento a segmento).
* [Dados de Audiência](../features/addressable-audiences.md) endereçáveis (dados no nível do cliente e do segmento).
* A métrica [Total de dispositivos](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) para um [!UICONTROL Profile Merge Rule].
* [O Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) usa dados de amostra na [!UICONTROL Search] guia e em qualquer [!UICONTROL Saved Searches].