---
description: Descreve a variação em totais exclusivos do usuário entre os relatórios para o mesmo tamanho e período de tempo.
seo-description: Descreve a variação em totais exclusivos do usuário entre os relatórios para o mesmo tamanho e período de tempo no Adobe Audience Manager
seo-title: Contagem de usuários únicos em sobreposição e relatórios gerais no AAM
solution: Audience Manager
title: Contagem de usuários únicos em sobreposição e relatórios gerais
uuid: 450 f 6 a 8 c-f 363-43 de-b 2 d 8-0 a 156 f 14 ecae
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Counting Unique Users in Overlap and General Reports{#counting-unique-users-in-overlap-and-general-reports}

Essa página descreve a variação em totais exclusivos do usuário entre os relatórios para o mesmo tamanho e período de tempo.

<!-- 

c_unique_user_counts.xml

 -->

## Relatório de sobreposição: Contagem exclusiva de usuários

Os relatórios de sobreposição contam os usuários como exclusivos quando se qualificam para uma característica:

* Durante o intervalo de tempo selecionado para o relatório.
* That has a [time-to-live](../features/traits/segment-ttl-explained.md) value longer than the selected time interval for the report.
* Se forem vistos como ativos em nosso sistema (ou seja, qualificados para qualquer outra característica, tinham uma sincronização de ID, etc.) nos últimos 60 dias.

## Relatório Geral: Contagem exclusiva de usuários

O relatório Geral conta os visitantes do site como únicos se eles estiverem qualificados para a característica durante o período selecionado.

>[!MORE_ LIKE_ THIS]
>
>* [Relatórios interativos](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Relatórios gerais](../reporting/general-reports.md#general-reports-overview)

