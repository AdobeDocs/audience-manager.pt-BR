---
description: Este artigo fornece uma visão geral sobre a classificação de características com uma taxonomia comum.
keywords: DIL
seo-description: This article provides general overview about classifying traits with a common taxonomy.
seo-title: Classifying Traits with a Common Taxonomy
solution: Audience Manager
title: Classificação de características com uma taxonomia comum
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
feature: Traits
exl-id: 59000dc7-66cf-4e7e-8e9b-9d48157203bd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 0%

---

# Classificação de características com uma taxonomia comum {#classifying-traits-with-a-common-taxonomy}

Este artigo fornece uma visão geral sobre a classificação de características com uma taxonomia comum.

## A taxonomia do Audience Manager

<!-- c_common_taxonomy_about.xml -->

A taxonomia [!DNL Audience Manager] é um recurso opcional que classifica características usando convenções de nomenclatura uniformes, lógicas e geralmente compreendidas. Ela opera no nível da plataforma para ajudar a garantir a consistência da nomenclatura em todo o ecossistema do [!DNL Audience Manager]. Em última análise, a taxonomia comum foi projetada para alinhar melhor nosso produto aos padrões do setor em relação à privacidade do consumidor e aos processos de recusa.

## Vantagens da classificação de características

Permitir que nossos clientes criem segmentos e modelos de dados personalizados é fundamental para o modelo [!DNL Audience Manager] e para sua capacidade de capturar valor de nossa plataforma. No entanto, também é necessário um meio robusto e escalável para transmitir informações sobre segmentos aos seus clientes e parceiros. Além disso, essa comunicação exige que as informações do segmento sejam compartilhadas em um idioma fácil de entender e compreendido universalmente, protegendo suas características e nomes de segmentos proprietários. A taxonomia comum [!DNL Audience Manager] fornece essa linguagem e esse recurso.

## A Taxonomia Usa Categorias De Classificação Padrão Do Setor

A taxonomia comum é baseada nas classificações criadas pelo [!DNL Interactive Advertising Bureau (IAB)]. Consulte o [site](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines) do [!DNL IAB] para obter mais informações sobre diretrizes de controle de qualidade para redes e trocas.

## Organização taxonômica

A taxonomia [!DNL Audience Manager] organiza os dados em categorias aninhadas chamadas camadas. Cada categoria pode conter até três camadas separadas para a classificação de dados. No nível mais alto, uma categoria de Nível 1 agrupa os dados em sua forma mais geral (por exemplo, geografia). Os níveis subsequentes fornecem maior especificidade para a categoria geral de nível mais alto (por exemplo, *geografia —> Estados Unidos —> Nova York*). No entanto, nem todas as categorias têm três níveis, alguns usam apenas dois.

## Classificar características em categorias de dados

Você atribui classificações taxonômicas ao criar ou editar características no [!UICONTROL Add New Trait Wizard] (localizado em * **[!UICONTROL Audience Data > Traits]***). Consulte a [documentação sobre criação de características](../../features/traits/create-onboarded-rule-based-traits.md) para obter mais informações.

## Trabalhar com a taxonomia: considerações adicionais

Se você decidir classificar características de acordo com nossa taxonomia comum, é importante lembrar:

* Classificação *opcional*.
* As características *não* são atribuídas a uma categoria taxonômica por padrão (ou seja, as características não são classificadas como &quot;desconhecidas&quot; ou &quot;não categorizadas&quot; etc.).
* As características podem pertencer somente a *uma* categoria taxonômica (classificações múltiplas e entre categorias não são permitidas).
