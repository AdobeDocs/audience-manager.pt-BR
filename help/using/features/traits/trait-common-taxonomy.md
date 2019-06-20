---
description: Este artigo fornece visão geral geral sobre a classificação de características com uma taxonomia comum.
keywords: DIL
seo-description: Este artigo fornece visão geral geral sobre a classificação de características com uma taxonomia comum.
seo-title: Classificação de características com uma taxonomia comum
solution: Audience Manager
title: Classificação de características com uma taxonomia comum
uuid: 2 e 177344-07 d 9-40 a 7-8 c 99-c 6 c 6518 b 9 d 97
translation-type: tm+mt
source-git-commit: 44bb4d511215a7bbc8889cc9518b3b5ffcb79a2a

---


# Classifying Traits with a Common Taxonomy {#classifying-traits-with-a-common-taxonomy}

Este artigo fornece visão geral geral sobre a classificação de características com uma taxonomia comum.

## A taxonomia do Audience Manager

<!-- c_common_taxonomy_about.xml -->

[!DNL Audience Manager] A taxonomia é um recurso opcional que classifica as características usando convenções de nomeação uniformes, lógicas e comumente compreensíveis. It operates at the platform level to help ensure naming consistency throughout the [!DNL Audience Manager] ecosystem. Em última análise, a taxonomia comum foi projetada para aproximar o produto com padrões do setor em relação à privacidade do consumidor e processos de não participação.

## Vantagens da classificação de características

Enabling our customers to build custom segments and data models is core to the [!DNL Audience Manager] model and to your ability to capture value from our platform. O que também é necessário, contudo, é um meio robusto e escalonável de comunicar informações sobre segmentos aos seus clientes e parceiros. Além disso, essa comunicação exige que as informações do segmento sejam compartilhadas com uma linguagem fácil de entender e universalmente entendida, ao mesmo tempo em que protegem seus nomes de características e segmentos proprietários. The [!DNL Audience Manager] common taxonomy provides this language and capability.

## A Taxonomia usa Categorias de classificação padrão do setor

The common taxonomy is based on the classifications created by the [!DNL Interactive Advertising Bureau (IAB)]. Refer to the [!DNL IAB]&#39;s [website](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines) for more information about quality assurance guidelines for networks and exchanges.

## Organização taxonomia

The [!DNL Audience Manager] taxonomy organizes data into nested categories called tiers. Cada categoria pode conter até 3 níveis separados para classificação de dados. No nível mais alto, uma categoria de Camada 1 agrupa dados em seu formulário mais geral (por exemplo, geografia). Subsequent tiers provide greater specificity to the higher level, general category (e.g., *geography --&gt; United States --&gt; New York*). No entanto, nem toda categoria tem 3 níveis, sendo que alguns usam apenas 2.

## Classificar características em categorias de dados

You assign taxonomic classifications when creating or editing traits in the [!UICONTROL Add New Trait Wizard] (located in * **[!UICONTROL Audience Data > Traits]***). Refer to the [documentation on creating traits](../../features/traits/create-onboarded-rule-based-traits.md) for more information.

## Trabalhar com a Taxonomia: Considerações adicionais

Se você decidir classificar características de acordo com a taxonomia comum, é importante lembrar:

* Classification is *optional*.
* Traits *are not* assigned to a taxonomic category by default (i.e., traits are not classified as &quot;unknown&quot; or &quot;uncategorized&quot; etc.).
* Traits can belong to *one* taxonomic category only (multiple and cross-category classifications are not allowed).