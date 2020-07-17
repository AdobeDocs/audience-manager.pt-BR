---
description: Este artigo fornece uma visão geral sobre como classificar características com uma taxonomia comum.
keywords: DIL
seo-description: Este artigo fornece uma visão geral sobre como classificar características com uma taxonomia comum.
seo-title: Classificação de características com uma taxonomia comum
solution: Audience Manager
title: Classificação de características com uma taxonomia comum
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 4%

---


# Classificação de características com uma taxonomia comum {#classifying-traits-with-a-common-taxonomy}

Este artigo fornece uma visão geral sobre como classificar características com uma taxonomia comum.

## A Taxonomia Audience Manager

<!-- c_common_taxonomy_about.xml -->

A [!DNL Audience Manager] taxonomia é um recurso opcional que classifica características usando convenções de nomenclatura uniformes, lógicas e comumente compreendidas. Ele opera no nível da plataforma para ajudar a garantir a consistência de nomenclatura em todo o [!DNL Audience Manager] ecossistema. Em última análise, a taxonomia comum foi projetada para tornar nosso produto mais alinhado com os padrões do setor em relação à privacidade do consumidor e aos processos de opção.

## Vantagens da classificação de características

Permitir que nossos clientes criem segmentos e modelos de dados personalizados é fundamental para o [!DNL Audience Manager] modelo e para sua capacidade de capturar valor de nossa plataforma. O que também é necessário, no entanto, é um meio robusto e escalonável para comunicar informações sobre segmentos aos seus clientes e parceiros. Além disso, essa comunicação exige que as informações do segmento sejam compartilhadas em um idioma fácil de entender e universalmente compreendido, além de proteger seus traços proprietários e nomes de segmentos. A taxonomia [!DNL Audience Manager] comum fornece essa linguagem e capacidade.

## A Taxonomia Usa Categorias De Classificação Padrão Da Indústria

A taxonomia comum se baseia nas classificações criadas pelo [!DNL Interactive Advertising Bureau (IAB)]. Consulte o [!DNL IAB]site [do](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines) para obter mais informações sobre as diretrizes de controle de qualidade para redes e trocas.

## Organização taxonômica

A [!DNL Audience Manager] taxonomia organiza dados em categorias aninhadas chamadas camadas. Cada categoria pode conter até 3 camadas separadas para a classificação de dados. No nível mais alto, uma categoria de nível 1 agrupa dados em seu formulário mais geral (por exemplo, geografia). Os níveis subsequentes fornecem maior especificidade ao nível superior, categoria geral (por exemplo, *geografia —> Estados Unidos —> Nova York*). No entanto, nem todas as categorias têm 3 níveis, alguns usam apenas 2.

## Classificar características em Categorias de dados

Você atribui classificações taxonômicas ao criar ou editar características no [!UICONTROL Add New Trait Wizard] (localizado em * **[!UICONTROL Audience Data > Traits]***). Consulte a [documentação sobre como criar características](../../features/traits/create-onboarded-rule-based-traits.md) para obter mais informações.

## Trabalhando com a taxonomia: Considerações adicionais

Se você decidir classificar os traços de acordo com nossa taxonomia comum, é importante lembrar:

* A classificação é *opcional*.
* As características não *são* atribuídas a uma categoria taxonômica por padrão (ou seja, as características não são classificadas como &quot;desconhecidas&quot; ou &quot;não categorizadas&quot; etc.).
* As características podem pertencer apenas a *uma* categoria taxonômica (classificações múltiplas e categorias múltiplas não são permitidas).