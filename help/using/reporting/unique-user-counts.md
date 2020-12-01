---
description: Descreve a variação nos totais de usuário únicos entre relatórios para a mesma característica e período.
seo-description: Descreve a variação nos totais de usuário únicos entre relatórios para a mesma característica e período no Adobe Audience Manager
seo-title: Contagem de usuários únicos em sobreposição e relatórios gerais em AAM
solution: Audience Manager
title: Contagem de usuários únicos em sobreposição e relatórios gerais
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: reporting reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 10%

---


# Contagem de usuários únicos em sobreposição e relatórios gerais{#counting-unique-users-in-overlap-and-general-reports}

Esta página descreve a variação dos totais de usuário únicos entre relatórios para a mesma característica e período de tempo.

<!-- 

c_unique_user_counts.xml

 -->

## Relatório de sobreposição: Contagem de usuários únicos

Os relatórios de sobreposição contam os usuários como únicos quando eles se qualificam para uma característica:

* Durante o intervalo de tempo selecionado para o relatório.
* Isso tem um valor [time-to-live](../features/traits/segment-ttl-explained.md) maior que o intervalo de tempo selecionado para o relatório.
* Se eles forem vistos como ativos em nosso sistema (isto é, qualificados para qualquer outra característica, tiverem uma sincronização de ID etc.) nos últimos 60 dias.

## Relatório geral: Contagem de usuários únicos

O relatório Geral conta os visitantes do site como exclusivos se eles se qualificaram para a característica durante o período selecionado.

>[!MORELIKETHIS]
>
>* [Relatórios interativos](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Relatórios gerais](../reporting/general-reports.md#general-reports-overview)

