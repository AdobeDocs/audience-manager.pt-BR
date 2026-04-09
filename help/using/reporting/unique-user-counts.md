---
description: Descreve a variação em totais de usuários únicos entre relatórios para a mesma característica e período.
seo-description: Describes the variation in unique user totals between reports for the same trait and time period in Adobe Audience Manager
seo-title: Counting Unique Users in Overlap and General Reports in AAM
solution: Audience Manager
title: Contagem de usuários únicos em relatórios gerais e de sobreposição
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Reporting Reference
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
TQID: https://experienceleague.adobe.com/zQamEx1r5buK4Q4FN-meT3l-8-j3f9Q5Kw2RtO0iPQ8
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
subfeature_v2:
  - id: a49258d4-867f-4130-b875-d72c001bdf6c
  - id: ec0be1ae-7ea9-4f62-869a-963a97d2edc1
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 142
ht-degree: 1%

---

# Contagem de usuários únicos em relatórios gerais e de sobreposição{#counting-unique-users-in-overlap-and-general-reports}

Esta página descreve a variação nos totais de usuários únicos entre relatórios para a mesma característica e período.

<!-- 

c_unique_user_counts.xml

 -->

## Relatório de sobreposição: Contagem de usuários únicos

Os relatórios de sobreposição contam os usuários como exclusivos quando se qualificam para uma característica:

* Durante o intervalo selecionado para o relatório.
* Que tem um valor de [tempo de vida](../features/traits/segment-ttl-explained.md) mais longo que o intervalo selecionado para o relatório.
* Se forem vistas como ativas em nosso sistema (ou seja, qualificadas para qualquer outra característica, tinham uma sincronização de ID etc.) nos últimos 60 dias.

## Relatório Geral: Contagem de Usuários Únicos

O relatório Geral conta os visitantes do site como exclusivos se eles se qualificaram para a característica durante o período selecionado.

>[!MORELIKETHIS]
>
>* [Relatórios interativos](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Relatórios gerais](../reporting/general-reports.md#general-reports-overview)
