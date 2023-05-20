---
description: Os componentes de processamento de dados incluem Hadoop, Snowflake, SOLR e Tableau.
seo-description: Data processing components include Hadoop, Snowflake, SOLR, and Tableau.
seo-title: Data Processing Components
solution: Audience Manager
title: Componentes de processamento de dados
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: System Components
exl-id: 9ff2b82b-aad0-4d24-96e6-230763019311
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 3%

---

# Componentes de processamento de dados{#data-processing-components}

Os componentes de processamento de dados incluem Hadoop, Snowflake, SOLR e Tableau.

<!-- 

c_comproc.xml

 -->

O Audience Manager usa os seguintes componentes para processar dados:

## Hadoop {#hadoop}

Entrada [!DNL Audience Manager], o Hadoop é o banco de dados principal que contém tudo [!DNL Audience Manager] O sabe sobre um usuário. Por exemplo, quando a variável [Servidores de cache de perfil](../../reference/system-components/components-data-collection.md) criar arquivos de log que contenham dados sobre os usuários; esses dados são enviados ao Hadoop para armazenamento. Outros elementos importantes do Hadoop incluem:

* **Hive:** Um data warehouse para Hadoop. O Hive gerencia consultas ad hoc aos dados armazenados no Hadoop.

* **HBase** Um banco de dados Hadoop muito grande. Ele processa e gerencia dados de entrada e saída, regras de características, informações de modelagem algorítmica e executa muitas outras funções relacionadas ao armazenamento e à movimentação de dados para diferentes sistemas.

Os clientes não têm acesso direto a esses sistemas. No entanto, os clientes trabalham indiretamente com eles, pois esses componentes armazenam dados importantes sobre os visitantes do site.

## Snowflake {#snowflake}

[Snowflake](https://www.snowflake.net/) O é um banco de dados em nuvem massivo. Ele fornece dados para muitos dos gráficos do painel e suas caixas de texto relacionadas que exibem a % de alteração para cada item no gráfico. Se você usar [!DNL Audience Manager] e olhe os relatórios do painel de controle, você está interagindo com os dados fornecidos pelo [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

Não se trata de uma lista abrangente, mas de alguns relatórios de painel comuns que [!UICONTROL Snowflake] O é responsável por incluir:

* [Relatório de variação diária de características](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* Todos os relatórios de sobreposição (consulte [Relatórios interativos](/help/using/reporting/dynamic-reports/dynamic-reports.md) para obter informações sobre cada relatório de sobreposição).
* [Relatório de sinais não usados](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR é um sistema de servidor e banco de dados de código aberto do Apache. Ele oferece recursos de pesquisa robustos e rápidos em nossos grandes conjuntos de dados. Como um [!DNL Audience Manager] cliente, você pode ver a SOLR em ação ao criar segmentos. Ele fornece dados para o [!UICONTROL Estimated Historic Segment Size] relatório. SOLR é ideal para este papel por causa de sua velocidade. Por exemplo, o SOLR pode atualizar os dados de tamanho do histórico à medida que você cria regras e adiciona novas características a um segmento.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] usos [Tableau](https://www.tableausoftware.com/) para exibir dados na [Relatórios interativos](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) e a variável [Relatórios Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md). Os relatórios interativos exibem dados de desempenho e sobreposição para características e segmentos. Em vez de usar números organizados em colunas e linhas, eles retornam dados usando diferentes formas, cores e tamanhos. Além disso, você pode escolher pontos de dados individuais ou grupos de e detalhar os resultados do relatório para obter mais detalhes. Essas técnicas de visualização e interatividade de relatórios ajudam a facilitar a compreensão de grandes quantidades de dados numéricos.



![](assets/advertiser_analytics.png)
