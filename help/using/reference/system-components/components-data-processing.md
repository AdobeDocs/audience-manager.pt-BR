---
description: Os componentes de processamento de dados incluem Hadoop, Snowflake, SOLR e Tableau.
seo-description: Os componentes de processamento de dados incluem Hadoop, Snowflake, SOLR e Tableau.
seo-title: Componentes de processamento de dados
solution: Audience Manager
title: Componentes de processamento de dados
uuid: d 458 d 869-7 a 23-4016-871 d -0 b 994 cf 4 af 06
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Processing Components{#data-processing-components}

Os componentes de processamento de dados incluem Hadoop, Snowflake, SOLR e Tableau.

<!-- 

c_comproc.xml

 -->

O Audience Manager usa os seguintes componentes para processar dados:

## Hadoop {#hadoop}

In [!DNL Audience Manager], Hadoop is the master database that contains everything [!DNL Audience Manager] knows about a user. For example, when the [Profile Cache Servers](../../reference/system-components/components-data-collection.md) create log files that contain data about your users, it sends that data to Hadoop for storage. Outros elementos importantes do Hadoop incluem:

* **Hive:** Um data warehouse para Hadoop. O hive gerencia consultas ad hoc aos dados armazenados no Hadoop.

* **Hbase:** Um banco de dados Hadoop muito grande. Ele processa e gerencia dados de entrada e saída, regras de características, informações de modelagem algorítmica e executa muitas outras funções relacionadas ao armazenamento e movimentação de dados para sistemas diferentes.

Os clientes não têm acesso direto a esses sistemas. No entanto, os clientes trabalham com eles indiretamente, pois esses componentes armazenam dados importantes sobre os visitantes do site.

## Snowflake {#snowflake}

[Floco de neve](https://www.snowflake.net/) é um banco de dados em nuvem massivo. Ele fornece dados a muitos dos gráficos do painel e suas caixas de texto relacionadas que exibem a % de alteração de cada item no gráfico. If you use [!DNL Audience Manager] and look at the dashboard reports, you're interacting with data provided by [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

This is by no means a comprehensive list, but some common dashboard reports that [!UICONTROL Snowflake] is responsible for include:

* [Relatório de variação de característica diária](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* [Relatório de entrega e desempenho](/help/using/reporting/dynamic-reports/delivery-performance-report.md)
* All the overlap reports (see the [Interactive Reports](/help/using/reporting/dynamic-reports/dynamic-reports.md) section for information about each overlap report).
* [Relatório de Sinais não usados](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR é um banco de dados de código aberto e um sistema de servidor do Apache. Ele oferece recursos de pesquisa robustos e rápidos sobre nossos grandes conjuntos de dados. As an [!DNL Audience Manager] customer, you can see SOLR in action when you build segments. It provides data to the [!UICONTROL Estimated Historic Segment Size] report. SOLR é ideal para essa função devido à sua velocidade. Por exemplo, SOLR é capaz de atualizar os dados de tamanho histórico à medida que você cria regras e adiciona novas características a um segmento.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] usa [o Tableau](https://www.tableausoftware.com/) para exibir dados nos Relatórios [interativos](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) e nos Relatórios de otimização [de público-alvo](../../reporting/audience-optimization-reports/audience-optimization-reports.md). Os relatórios interativos exibem dados de desempenho e sobreposição para características e segmentos. Em vez de usar números organizados em colunas e linhas, retornam dados usando diferentes formas, cores e tamanhos. Além disso, você pode escolher indivíduos ou grupos de pontos de dados e detalhar os resultados do relatório para obter mais detalhes. Essas técnicas de visualização e a interatividade do relatório ajudam a facilitar a compreensão de grandes quantidades de dados numéricos.



![](assets/advertiser_analytics.png)

