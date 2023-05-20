---
description: Descreve a variação em totais de usuários únicos entre relatórios para a mesma característica e período.
seo-description: Describes the variation in unique user totals between reports for the same trait and time period in Adobe Audience Manager
seo-title: Counting Unique Users in Overlap and General Reports in AAM
solution: Audience Manager
title: Contagem de usuários únicos em sobreposição e relatórios gerais
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Reporting Reference
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 12%

---

# Contagem de usuários únicos em sobreposição e relatórios gerais{#counting-unique-users-in-overlap-and-general-reports}

Esta página descreve a variação nos totais de usuários únicos entre relatórios para a mesma característica e período.

<!-- 

c_unique_user_counts.xml

 -->

## Relatório de sobreposição: Contagem de usuários únicos

Os relatórios de sobreposição contam os usuários como exclusivos quando se qualificam para uma característica:

* Durante o intervalo selecionado para o relatório.
* Isso tem um [tempo de vida](../features/traits/segment-ttl-explained.md) valor mais longo que o intervalo de tempo selecionado para o relatório.
* Se forem vistas como ativas em nosso sistema (ou seja, qualificadas para qualquer outra característica, tinham uma sincronização de ID etc.) nos últimos 60 dias.

## Relatório Geral: Contagem de Usuários Únicos

O relatório Geral conta os visitantes do site como exclusivos se eles se qualificaram para a característica durante o período selecionado.

>[!MORELIKETHIS]
>
>* [Relatórios interativos](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Relatórios gerais](../reporting/general-reports.md#general-reports-overview)

