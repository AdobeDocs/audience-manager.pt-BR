---
description: Os componentes de processamento de dados incluem Hadoop, Floco de neve, SOLR e Tableau.
seo-description: Os componentes de processamento de dados incluem Hadoop, Floco de neve, SOLR e Tableau.
seo-title: Componentes de processamento de dados
solution: Audience Manager
title: Componentes de processamento de dados
uuid: d458d869-7a23-4016-871d-0b994cf4af06
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Componentes de processamento de dados{#data-processing-components}

Os componentes de processamento de dados incluem Hadoop, Floco de neve, SOLR e Tableau.

<!-- 

c_comproc.xml

 -->

O Audience Manager usa os seguintes componentes para processar dados:

## Hadoop {#hadoop}

Em [!DNL Audience Manager], o Hadoop é o banco de dados mestre que contém tudo o que [!DNL Audience Manager] sabe sobre um usuário. Por exemplo, quando os Servidores [de cache de](../../reference/system-components/components-data-collection.md) perfil criam arquivos de log que contêm dados sobre seus usuários, eles enviam esses dados para o Hadoop para armazenamento. Outros elementos importantes do Hadoop incluem:

* **** Coloque: Um data warehouse para o Hadoop. Hive gerencia consultas ad hoc para os dados armazenados no Hadoop.

* **** HBase: Um banco de dados Hadoop muito grande. Ele processa e gerencia dados de entrada e saída, regras de características, informações de modelagem algorítmica e executa muitas outras funções relacionadas ao armazenamento e movimentação de dados para diferentes sistemas.

Os clientes não têm acesso direto a esses sistemas. No entanto, os clientes trabalham com eles indiretamente, já que esses componentes armazenam dados importantes sobre os visitantes do site.

## Floco de neve {#snowflake}

[Snowflake](https://www.snowflake.net/) é um enorme banco de dados de nuvens. Fornece dados para muitos dos gráficos de painel e suas caixas de texto relacionadas que exibem a % de alteração para cada item no gráfico. Se você usar [!DNL Audience Manager] e observar os relatórios de painel, estará interagindo com os dados fornecidos por [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

Essa não é de forma alguma uma lista abrangente, mas alguns relatórios comuns de painel que [!UICONTROL Snowflake] são responsáveis por incluir:

* [Relatório de variação de característica diária](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* [Relatório de entrega e desempenho](/help/using/reporting/dynamic-reports/delivery-performance-report.md)
* Todos os relatórios de sobreposição (consulte a seção Relatórios [](/help/using/reporting/dynamic-reports/dynamic-reports.md) interativos para obter informações sobre cada relatório de sobreposição).
* [Relatório de Sinais Não Utilizados](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

O SOLR é um banco de dados de código aberto e um sistema de servidor do Apache. Ele oferece recursos de pesquisa robustos e rápidos sobre nossos grandes conjuntos de dados. Como [!DNL Audience Manager] cliente, você pode ver a SOLR em ação ao criar segmentos. Fornece dados para o [!UICONTROL Estimated Historic Segment Size] relatório. O SOLR é ideal para esse papel por causa da sua velocidade. Por exemplo, o SOLR é capaz de atualizar os dados de tamanho histórico à medida que você cria regras e adiciona novas características a um segmento.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] usa o [Tableau](https://www.tableausoftware.com/) para exibir dados nos Relatórios [](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) interativos e nos Relatórios [de otimização de](../../reporting/audience-optimization-reports/audience-optimization-reports.md)público-alvo. Os relatórios interativos exibem dados de desempenho e sobreposição para características e segmentos. Em vez de usar números organizados em colunas e linhas, eles retornam dados usando diferentes formas, cores e tamanhos. Além disso, você pode escolher indivíduos ou grupos de pontos de dados e detalhar os resultados do relatório para obter mais detalhes. Essas técnicas de visualização e interatividade de relatório ajudam a facilitar a compreensão de grandes quantidades de dados numéricos.



![](assets/advertiser_analytics.png)

