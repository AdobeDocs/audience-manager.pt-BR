---
description: Descreve a variação nos totais de usuários únicos entre relatórios para a mesma característica e período.
seo-description: Descreve a variação nos totais de usuário únicos entre relatórios para a mesma característica e período no Adobe Audience Manager
seo-title: Contagem de usuários únicos em sobreposição e relatórios gerais no AAM
solution: Audience Manager
title: Contagem de usuários únicos em sobreposição e relatórios gerais
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Reporting Reference
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 10%

---

# Contagem de usuários únicos em sobreposição e relatórios gerais{#counting-unique-users-in-overlap-and-general-reports}

Esta página descreve a variação nos totais de usuários únicos entre relatórios para a mesma característica e período de tempo.

<!-- 

c_unique_user_counts.xml

 -->

## Relatório de sobreposição: Contagem de usuários únicos

Os relatórios de sobreposição contam os usuários como exclusivos quando se qualificam para uma característica:

* Durante o intervalo de tempo selecionado para o relatório.
* Isso tem um valor [time-to-live](../features/traits/segment-ttl-explained.md) maior que o intervalo de tempo selecionado para o relatório.
* Se forem considerados ativos em nosso sistema (ou seja, se qualificarem para qualquer outra característica, tiverem uma sincronização de ID etc.) nos últimos 60 dias.

## Relatório geral: Contagem de usuários únicos

O relatório Geral conta os visitantes do site como exclusivos se eles se qualificarem para a característica durante o período de tempo selecionado.

>[!MORELIKETHIS]
>
>* [Relatórios interativos](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Relatórios gerais](../reporting/general-reports.md#general-reports-overview)

