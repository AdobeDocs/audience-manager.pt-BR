---
description: Os componentes de processamento de dados incluem Hadoop, Snowflake, SOLR e Tableau.
seo-description: Os componentes de processamento de dados incluem Hadoop, Snowflake, SOLR e Tableau.
seo-title: Componentes de processamento de dados
solution: Audience Manager
title: Componentes de processamento de dados
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: 'Componentes do sistema '
exl-id: 9ff2b82b-aad0-4d24-96e6-230763019311
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 4%

---

# Componentes de processamento de dados{#data-processing-components}

Os componentes de processamento de dados incluem Hadoop, Snowflake, SOLR e Tableau.

<!-- 

c_comproc.xml

 -->

O Audience Manager usa os seguintes componentes para processar dados:

## Hadoop {#hadoop}

Em [!DNL Audience Manager], o Hadoop é o banco de dados principal que contém tudo o que [!DNL Audience Manager] sabe sobre um usuário. Por exemplo, quando os [Servidores de Cache de Perfil](../../reference/system-components/components-data-collection.md) criam arquivos de log que contêm dados sobre seus usuários, ele envia esses dados ao Hadoop para armazenamento. Outros elementos importantes do Hadoop incluem:

* **Hive:** um data warehouse para o Hadoop. O Hive gerencia consultas ad hoc para os dados armazenados no Hadoop.

* **HBase:** um banco de dados de Hadoops muito grande. Ele processa e gerencia dados de entrada e saída, regras de características, informações de modelagem algorítmica e executa muitas outras funções relacionadas ao armazenamento e movimentação de dados para diferentes sistemas.

Os clientes não têm acesso direto a esses sistemas. No entanto, os clientes trabalham com eles indiretamente, já que esses componentes armazenam dados importantes sobre os visitantes do site.

## Snowflake {#snowflake}

[](https://www.snowflake.net/) O Snowflakeis é um enorme banco de dados de nuvem. Ele fornece dados para muitos dos gráficos de painel e suas caixas de texto relacionadas que exibem a % de alteração para cada item no gráfico. Se você usar [!DNL Audience Manager] e examinar os relatórios do painel, estará interagindo com os dados fornecidos por [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

Essa não é de forma alguma uma lista abrangente, mas alguns relatórios comuns de painel indicam que [!UICONTROL Snowflake] é responsável por incluir:

* [Relatório de variação diária de características](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* Todos os relatórios de sobreposição (consulte a seção [Relatórios interativos](/help/using/reporting/dynamic-reports/dynamic-reports.md) para obter informações sobre cada relatório de sobreposição).
* [Relatório de sinais não usados](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

O SOLR é um sistema de servidor e banco de dados de código aberto do Apache. Ele fornece recursos de pesquisa robustos e rápidos em nossos grandes conjuntos de dados. Como cliente [!DNL Audience Manager], você pode ver a SOLR em ação ao criar segmentos. Ele fornece dados para o relatório [!UICONTROL Estimated Historic Segment Size]. O SOLR é ideal para esse papel por causa da velocidade. Por exemplo, o SOLR é capaz de atualizar os dados de tamanho histórico à medida que você cria regras e adiciona novas características a um segmento.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] O usa  [](https://www.tableausoftware.com/) Tableauto para exibir dados nos Relatórios  [interativos ](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) e nos Relatórios do  [Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md). Os relatórios interativos exibem dados de desempenho e sobreposição para características e segmentos. Em vez de usar números organizados em colunas e linhas, eles retornam dados usando diferentes formas, cores e tamanhos. Além disso, você pode escolher pontos de dados individuais ou grupos e detalhar os resultados do relatório para obter mais detalhes. Essas técnicas de visualização e a interatividade de relatórios ajudam a entender grandes quantidades de dados numéricos.



![](assets/advertiser_analytics.png)
