---
description: Um relatório de tendência retorna dados de tendências em características e segmentos.
seo-description: Um relatório de tendência retorna dados de tendências em características e segmentos.
seo-title: Relatórios de tendência
solution: Audience Manager
title: Relatórios de tendência
uuid: bedbe 7 d 4-7 cbb -4403-9104-312 f 9230 aea 1
translation-type: tm+mt
source-git-commit: 18bb00d494d44d7028dcc51dcb2fc57b23420142

---


# Trend Reports{#trend-reports}

Um relatório de tendência retorna dados de tendências em características e segmentos.

## Visão geral {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] usa [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) para estender permissões de grupo do usuário para [!UICONTROL Trend] os relatórios. Os usuários podem ver apenas essas características e segmentos no relatório que têm permissão para visualizar. [!UICONTROL RBAC] permite controlar quais equipes internas de dados de relatório podem exibir.

Por exemplo, uma agência que gerencia diferentes contas de anunciante pode configurar permissões de grupo do usuário para que uma equipe que gerencia a conta do anunciante A não possa ver os dados de relatório do anunciante B.

Run a [!UICONTROL Trend] report when you need to:

* Analise os dados de tendências por características e segmentos.
* Acompanhe as tendências por intervalos de 1, 7, 14, 30, 60 e 90 dias.
* Compare as tendências de características e segmentos ao longo do tempo.
* Identifique características e segmentos de desempenho forte ou ruim.
* Exportar dados (formato. csv) para análise e compartilhamento mais recentes.

The following illustration provides a high-level overview of key elements in the [!UICONTROL Trend] report.

![](assets/trend_reports.png)

1. Configure as seguintes opções:

   **Tipo de relatório:** Selecione o tipo de relatório desejado (Característica ou Segmento).

   **Intervalo de datas:** Especifique o intervalo de datas para o relatório (data de início e data de término).

   **Intervalo de exibição:** Especifique os intervalos de exibição (1, 7, 14, 30, 60 e 90 dias).

2. Pesquise por uma característica ou segmento por nome ou ID.
3. From the folder list, drag and drop the traits or segments you want to report to the [!UICONTROL Selections] panel on the right side.
4. Gere o relatório para exibir nos dados em formato gráfico ou exporte o relatório para o formato CSV.

## Run a Trend Report {#run-trend-report}

This procedure describes how to run a [!UICONTROL Trend] report.

<!-- 

t_working_with_trend_reports.xml

 -->

1. In the **[!UICONTROL Analytics]** dashboard, click **[!UICONTROL Trend Reports]**.
1. From the **[!UICONTROL Report Type]** drop-down list, select the desired type: **[!UICONTROL Trait]** or **[!UICONTROL Segment]**.
1. Clique nas caixas de datas para exibir um calendário e, em seguida, selecione as datas inicial e final do seu relatório.
1. Especifique o intervalo de exibição: por 1, 7, 14, 30, 60 ou 90 dias.
1. Pesquise por uma característica ou segmento por nome ou ID.
1. From the folder list, drag and drop the traits or segments you want to report to the [!UICONTROL Selections] panel on the right side.

   For best performance, run a [!UICONTROL Trend] report on fewer than 20 traits or segments at a time.
1. Click **[!UICONTROL Graph Traits]** or **[!UICONTROL Graph Segments]**, depending on which type of report you are viewing (Traits or Segments).

   Essas opções ignoram todas as pastas e gráficos somente selecionados individualmente ou segmentos.

   Ou

   Click **[!UICONTROL Export to CSV]** to export the trait or segment data and all folders in CSV format for further analysis and sharing. This exports the [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], and [!UICONTROL Total Trait Population] for all day ranges.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] são calculadas apenas [!UICONTROL Rule-based Traits] para.

1. (Opcional) Passe o mouse sobre características individuais ou segmentos para exibir o número de visitas e a data de cada ponto de dados.

   Você pode clicar nos cabeçalhos das colunas na tabela para classificar os resultados em ordem crescente ou decrescente.

For [!UICONTROL Trended Trait] reports, zeroes indicate that [!DNL Audience Manager] did not collect data for that day. Entradas em branco indicam que a característica não existia. O exemplo a seguir mostra exemplos de ambos os tipos de entradas:

![](assets/trended_data.png)
