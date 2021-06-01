---
description: Este artigo fornece uma visão geral sobre como classificar características com uma taxonomia comum.
keywords: DIL
seo-description: Este artigo fornece uma visão geral sobre como classificar características com uma taxonomia comum.
seo-title: Classificação de características com uma taxonomia comum
solution: Audience Manager
title: Classificação de características com uma taxonomia comum
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
feature: 'Características '
exl-id: 59000dc7-66cf-4e7e-8e9b-9d48157203bd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 5%

---

# Classificação de características com uma taxonomia comum {#classifying-traits-with-a-common-taxonomy}

Este artigo fornece uma visão geral sobre como classificar características com uma taxonomia comum.

## A taxonomia Audience Manager

<!-- c_common_taxonomy_about.xml -->

A taxonomia [!DNL Audience Manager] é um recurso opcional que classifica características usando convenções de nomenclatura uniformes, lógicas e comumente compreendidas. Ela opera no nível da plataforma para ajudar a garantir a consistência de nomeação em todo o ecossistema [!DNL Audience Manager]. Em última análise, a taxonomia comum foi projetada para alinhar melhor nosso produto com os padrões do setor em relação à privacidade do consumidor e aos processos de recusa.

## Vantagens da classificação de características

Permitir que nossos clientes criem segmentos e modelos de dados personalizados é essencial para o modelo [!DNL Audience Manager] e para sua capacidade de capturar valor de nossa plataforma. O que também é necessário, no entanto, é um meio robusto e escalável para comunicar informações sobre segmentos aos clientes e parceiros. Além disso, essa comunicação exige que as informações do segmento sejam compartilhadas em um idioma fácil de entender e universalmente compreendido, além de proteger seus nomes de características e segmentos proprietários. A taxonomia comum [!DNL Audience Manager] fornece esse idioma e esse recurso.

## A Taxonomia Usa Categorias De Classificação Padrão Do Setor

A taxonomia comum é baseada nas classificações criadas pelo [!DNL Interactive Advertising Bureau (IAB)]. Consulte o [!DNL IAB] site [do ](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines) para obter mais informações sobre as diretrizes de controle de qualidade para redes e trocas.

## Organização taxonômica

A taxonomia [!DNL Audience Manager] organiza os dados em categorias aninhadas chamadas camadas. Cada categoria pode conter até 3 camadas separadas para classificação de dados. No nível mais alto, uma categoria de Nível 1 agrupa dados em seu formulário mais geral (por exemplo, geografia). Os níveis subsequentes fornecem maior especificidade ao nível mais alto, categoria geral (por exemplo, *geografia —> Estados Unidos —> Nova York*). No entanto, nem todas as categorias têm 3 camadas, algumas usam apenas 2.

## Classificar características em categorias de dados

Você atribui classificações taxonômicas ao criar ou editar características no [!UICONTROL Add New Trait Wizard] (localizado em * **[!UICONTROL Audience Data > Traits]***). Consulte a [documentação sobre como criar características](../../features/traits/create-onboarded-rule-based-traits.md) para obter mais informações.

## Trabalhando com a taxonomia: Considerações adicionais

Se você decidir classificar as características de acordo com nossa taxonomia comum, é importante lembrar:

* A classificação é *opcional*.
* As características *não são* atribuídas a uma categoria taxonômica por padrão (ou seja, as características não são classificadas como &quot;desconhecidas&quot; ou &quot;não categorizadas&quot; etc.).
* As características podem pertencer somente a *uma* categoria taxonômica (classificações múltiplas e entre categorias não são permitidas).
