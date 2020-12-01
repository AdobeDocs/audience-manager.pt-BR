---
description: Os componentes de processamento de dados incluem Hadoop, Snowflake, SOLR e Tableau.
seo-description: Os componentes de processamento de dados incluem Hadoop, Snowflake, SOLR e Tableau.
seo-title: Componentes de processamento de dados
solution: Audience Manager
title: Componentes de processamento de dados
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 3%

---


# Componentes de processamento de dados{#data-processing-components}

Os componentes de processamento de dados incluem Hadoop, Snowflake, SOLR e Tableau.

<!-- 

c_comproc.xml

 -->

O Audience Manager usa os seguintes componentes para processar dados:

## Hadoop {#hadoop}

Em [!DNL Audience Manager], a Hadoop é o banco de dados principal que contém tudo o que [!DNL Audience Manager] conhece sobre um usuário. Por exemplo, quando os [Servidores de cache de Perfil](../../reference/system-components/components-data-collection.md) criam arquivos de log que contêm dados sobre seus usuários, eles enviam esses dados para a Hadoop para armazenamento. Outros elementos importantes do Hadoop incluem:

* **Colmeia:** um data warehouse para Hadoop. Hive gerencia query ad hoc para os dados armazenados no Hadoop.

* **HBase:** Um banco de dados Hadoop muito grande. Ele processa e gerencia dados de entrada e saída, regras de características, informações de modelagem algorítmica e executa muitas outras funções relacionadas ao armazenamento e movimentação de dados para diferentes sistemas.

Os clientes não têm acesso direto a esses sistemas. No entanto, os clientes trabalham com eles indiretamente, já que esses componentes armazenam dados importantes sobre os visitantes do site.

## Snowflake {#snowflake}

[](https://www.snowflake.net/) Snowflakeis é um enorme banco de dados de nuvens. Fornece dados para muitos gráficos de painéis e suas caixas de texto relacionadas que exibem a % de alteração para cada item no gráfico. Se você usar [!DNL Audience Manager] e observar os relatórios de painel, você interagirá com os dados fornecidos por [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

Esta não é de forma alguma uma lista abrangente, mas alguns relatórios de painel comuns que [!UICONTROL Snowflake] são responsáveis por incluem:

* [Relatório de variação diária de características](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* Todos os relatórios de sobreposição (consulte a seção [Relatórios interativos](/help/using/reporting/dynamic-reports/dynamic-reports.md) para obter informações sobre cada relatório de sobreposição).
* [Relatório de sinais não usados](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

O SOLR é um banco de dados de código aberto e um sistema de servidor do Apache. Ele oferece recursos de pesquisa robustos e rápidos sobre nossos grandes conjuntos de dados. Como um cliente [!DNL Audience Manager], você pode ver a SOLR em ação ao criar segmentos. Fornece dados para o relatório [!UICONTROL Estimated Historic Segment Size]. O SOLR é ideal para esse papel por causa da sua velocidade. Por exemplo, o SOLR é capaz de atualizar os dados de tamanho histórico à medida que você cria regras e adiciona novas características a um segmento.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] usa os dados de exibição  [](https://www.tableausoftware.com/) Tableauto nos Relatórios  [interativos ](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) e nos Relatórios [ de ](../../reporting/audience-optimization-reports/audience-optimization-reports.md)Audience Optimization. Os relatórios interativos exibem dados de desempenho e sobreposição para características e segmentos. Em vez de usar números organizados em colunas e linhas, eles retornam dados usando diferentes formas, cores e tamanhos. Além disso, você pode escolher indivíduos ou grupos de pontos de dados e detalhar os resultados do relatório para obter mais detalhes. Essas técnicas de visualização e interatividade de relatório ajudam a facilitar a compreensão de grandes quantidades de dados numéricos.



![](assets/advertiser_analytics.png)

