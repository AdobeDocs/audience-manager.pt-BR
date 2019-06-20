---
description: Um relatório Geral retorna dados de desempenho em características, segmentos e destinos.
seo-description: Um relatório Geral no Audience Manager retorna dados de desempenho em características, segmentos e destinos.
seo-title: Relatórios gerais no Audience Manager
solution: Audience Manager
title: Relatórios gerais
uuid: 0 cea 75 a 0-969 e -4 ee 3-971 a -60 b 911711 e 52
translation-type: tm+mt
source-git-commit: 18bb00d494d44d7028dcc51dcb2fc57b23420142

---


# General Reports{#general-reports}

A [!UICONTROL General] report returns performance data on traits, segments, and destinations.

## Visão geral {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] usa [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) para estender permissões de grupo do usuário para [!UICONTROL General] os relatórios. Os usuários podem ver apenas essas características e segmentos no relatório que têm permissão para visualizar. [!UICONTROL RBAC] permite controlar quais equipes internas de dados de relatório podem exibir. Por exemplo, uma agência que gerencia diferentes contas de anunciante pode configurar permissões de grupo do usuário para que uma equipe que gerencia a conta do anunciante A não possa ver os dados de relatório do anunciante B.

Run a [!UICONTROL General] report when you need to:

* Analise o desempenho por características, segmentos ou destino.
* Rastrear impressões (total e único) em intervals, 7, 14, 30, 60, 90 dias e intervalos de tempo de vida.
* Analise contagens de carga totais e únicas.
* Compare o desempenho de características e segmentos.
* Identifique características e segmentos de desempenho forte ou ruim, analise demanda ou compare dados de carregamento/acionamento com relatórios de terceiros.
* Exportar dados (formato. csv) para análise e compartilhamento mais recentes.

The following illustration provides a high-level overview of key elements in the [!UICONTROL General] report.

![](assets/general_reports.png)

1. Configure as seguintes opções:

   * **Tipo de relatório:** Selecione o tipo de relatório desejado (Característica, Segmento ou Destino).

   * **Para Datas por:** Especifique o intervalo de datas para o relatório.

2. Pesquise por uma característica, segmento ou destino por nome ou ID.
3. From the folder list, drag and drop the traits, segments, or destinations you want to report to the [!UICONTROL Selections] panel on the right side.
4. Gere o relatório para exibição em uma tabela exportável.

## Run a General Report {#run-general-report}

This section describes how to run a [!UICONTROL General] report and set time and other performance options.

<!-- 

t_run_general_report.xml

 -->

1. In the **[!UICONTROL Analytics]** dashboard, click **[!UICONTROL General Reports]**.
1. From the **[!UICONTROL Report Type]** drop-down list, select the desired type: Trait, Segment, or Destination.
1. *Clique na* caixa de datas condicional para exibir um calendário e, em seguida, selecione a data final do seu relatório se desejar especificar uma data diferente de hoje.
1. Pesquise por uma característica, segmento ou destino por nome ou ID.
1. From the folder list, drag and drop the traits, segments, or destinations you want to report to the [!UICONTROL Selections] panel on the right side.
1. Clique em **[!UICONTROL Run Report]**.

   Os resultados são exibidos em uma tabela exportável. Clique nos cabeçalhos das colunas para classificar os resultados em ordem crescente ou decrescente.
1. Select the desired option button at the top of the report to filter data by performance ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], or [!UICONTROL Total Trait Population]) or by time (1, 7, 14, 30, 60, 90-day range or lifetime).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] são calculadas apenas [!UICONTROL Rule-based Traits] para.

1. *Clique opcional***[!UICONTROL Export to CSV]**. This exports the [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], and [!UICONTROL Total Trait Population] for all day ranges.

## General Reports Results Explained {#general-reports-explained}

The numbers in the [!UICONTROL General Reports] are generated directly from our [!UICONTROL User Profile Store]. The results reflect the number of users that [!DNL Audience Manager] contained in the backend at the time these reporting numbers were generated.

* Esses números não incluem IDs de visitantes com tráfego excessivo. O tráfego de bots é filtrado antes de chegar ao sistema de backend. Além disso, alguns tráfegos de bot são descartados durante uma execução de limpeza semanal no backend.
* If you onboard data via inbound processing keyed off the [!DNL Audience Manager] UUID, and these IDs include users that are no longer active in our system, these inactive [!DNL Audience Manager] UUIDs never reach the [!UICONTROL User Profile Store] and are not reported.
* [!UICONTROL Total Trait Realizations] são calculadas apenas [!UICONTROL Rule-based Traits] para.

## General Reports Results for Traits {#general-report-results-traits}

The metrics below are available when you run a General report and select **[!UICONTROL Trait]** as the report type:

**Análise de característica exclusiva**

This metric represents the unique number of [Audience Manager Unique User IDs (UUID)](../reference/ids-in-aam.md) that qualified for the trait in your selected time range. Por exemplo, se um usuário visitou sua página inicial três vezes em 10/1, você veria uma Realização de característica exclusiva.

**Total de experiências de característica**

Essa métrica representa a quantidade total de acionamentos de características para a característica no intervalo de tempo selecionado. Por exemplo, se um usuário visitou sua página inicial e, em seguida, navegou para suas notícias técnicas e suas seções de notícias esportivas, elas apareceriam no Relatório geral como três totais de características e uma realização de característica exclusiva.

**População de característica total**

Essa métrica representa a quantidade total de uuids do Audience Manager que estão qualificados atualmente para a característica. Use esse número para entender a quantidade total de usuários que você pode usar para segmentação e direcionamento. Typically, users remain part of a trait for [120 days](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). Por exemplo, um usuário que visita sua página inicial três vezes hoje e nunca retorna depois, permaneceria como um usuário nesta população todos os dias até 120 dias de agora. Na marca de 120 dias, eles seriam removidos da população. Read our [Trait Qualification Reference](../features/traits/trait-qualification-reference.md) for more examples on the difference between Unique Trait Realizations and Total Trait Population.

A ilustração abaixo mostra os resultados da execução de um relatório geral para o tipo de relatório Característica.

![](assets/general_reports_metrics.png)

## General Reports Results for Segments {#general-report-results-segments}

The metrics below are available when you run a General report and select **[!UICONTROL Segment]** as the report type:

**Preenchimento de segmentos em tempo real**

Essa métrica representa o número real de visitantes únicos vistos em tempo real para o intervalo de tempo especificado e que foram qualificados para o segmento no momento em que foram vistos pelo Audience Manager.

**População total de segmentos**

Essa métrica representa o número total de uuids do Audience Manager que são qualificados para o segmento no período de análise selecionado. Sua população de segmento total de 1 dias representa a base de usuários mais precisa para direcionamento.

>[!NOTE]
>
>Select **[!UICONTROL Include Destination Mappings]** to see a breakdown of segment population for activated destinations.

A ilustração abaixo mostra os resultados da execução de um relatório geral para o tipo de relatório Segmento.

![](assets/general_reports_segment_metrics.png)

## General Reports Results for Destinations {#general-report-results-destinations}

The metrics below are available when you run a General report and select **[!UICONTROL Destination]** as the report type:

**Preenchimento de segmentos em tempo real**

Essa métrica representa o número real de visitantes únicos vistos em tempo real para o intervalo de tempo especificado e que foram qualificados para o segmento no momento em que foram vistos pelo Audience Manager.

**População total de segmentos**

Essa métrica representa o número total de uuids do Audience Manager pertencentes a um segmento no período de análise, que foi enviado para um destino.

A ilustração abaixo mostra os resultados da execução de um relatório geral para o tipo de relatório de Destinos.

![](assets/general_reports_destinations.png)
