---
description: Um relatório de Tendência retorna dados de tendência sobre características e segmentos.
seo-description: Um relatório de Tendência retorna dados de tendência sobre características e segmentos.
seo-title: Relatórios de tendências
solution: Audience Manager
title: Relatórios de tendências
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
translation-type: tm+mt
source-git-commit: 18bb00d494d44d7028dcc51dcb2fc57b23420142

---


# Relatórios de tendências{#trend-reports}

Um relatório de Tendência retorna dados de tendência sobre características e segmentos.

## Visão geral {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] usa [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) para estender permissões do grupo de usuários aos [!UICONTROL Trend] relatórios. Os usuários podem ver apenas as características e os segmentos nos relatórios que têm permissões para visualizar. [!UICONTROL RBAC] permite controlar quais dados de relatório as equipes internas podem visualizar.

Por exemplo, uma agência que gerencia diferentes contas de anunciante pode configurar permissões de grupo de usuários para que uma equipe que gerencia a conta do anunciante A não possa ver os dados de relatório do anunciante B.

Execute um [!UICONTROL Trend] relatório quando precisar:

* Analise os dados de tendências por características e segmentos.
* Acompanhe as tendências em intervalos de 1, 7, 14, 30, 60 e 90 dias.
* Compare características e tendências de segmentos ao longo do tempo.
* Identifique traços e segmentos de desempenho fortes ou ruins.
* Exporte dados (formato .csv) para análise e compartilhamento adicionais.

A ilustração a seguir fornece uma visão geral de alto nível dos elementos-chave no [!UICONTROL Trend] relatório.

![](assets/trend_reports.png)

1. Configure as seguintes opções:

   **** Tipo de relatório: Selecione o tipo de relatório desejado (característica ou segmento).

   **** Intervalo de datas: Especifique o intervalo de datas do relatório (data de início e data de término).

   **** Intervalo de exibição: Especifique o intervalo de exibição (intervalos de 1, 7, 14, 30, 60 e 90 dias).

2. Procure por uma característica ou segmento por nome ou ID.
3. Na lista de pastas, arraste e solte as características ou segmentos que deseja reportar para o [!UICONTROL Selections] painel no lado direito.
4. Gere o relatório para exibir os dados no formato gráfico ou exporte-o para o formato CSV.

## Executar um relatório de tendências {#run-trend-report}

Este procedimento descreve como executar um [!UICONTROL Trend] relatório.

<!-- 

t_working_with_trend_reports.xml

 -->

1. In the **[!UICONTROL Analytics]** dashboard, click **[!UICONTROL Trend Reports]**.
1. Na lista **[!UICONTROL Report Type]** suspensa, selecione o tipo desejado: **[!UICONTROL Trait]** ou **[!UICONTROL Segment]**.
1. Clique nas caixas de datas para exibir um calendário e selecione as datas inicial e final do seu relatório.
1. Especifique o intervalo de exibição: por 1, 7, 14, 30, 60 ou 90 dias.
1. Procure por uma característica ou segmento por nome ou ID.
1. Na lista de pastas, arraste e solte as características ou segmentos que deseja reportar para o [!UICONTROL Selections] painel no lado direito.

   Para obter melhor desempenho, execute um [!UICONTROL Trend] relatório com menos de 20 características ou segmentos de cada vez.
1. Clique **[!UICONTROL Graph Traits]** ou **[!UICONTROL Graph Segments]**, dependendo do tipo de relatório que você está visualizando (características ou segmentos).

   Essas opções ignoram todas as pastas e gráficos somente os traços ou segmentos selecionados individualmente.

   Ou

   Clique em **[!UICONTROL Export to CSV]** para exportar os dados de características ou segmentos e todas as pastas no formato CSV para análise e compartilhamento adicionais. Isso exporta os intervalos [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]e [!UICONTROL Total Trait Population] para todos os intervalos do dia.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] são calculados [!UICONTROL Rule-based Traits] apenas para.

1. (Opcional) Passe o mouse sobre características individuais ou segmentos para exibir o número de visitas e a data de cada ponto de dados.

   Você pode clicar nos cabeçalhos de coluna na tabela para classificar os resultados em ordem crescente ou decrescente.

Para [!UICONTROL Trended Trait] relatórios, os zeros indicam que [!DNL Audience Manager] não coletou dados desse dia. Entradas em branco indicam que o traço não existia. O exemplo a seguir mostra exemplos de ambos os tipos de entradas:

![](assets/trended_data.png)
