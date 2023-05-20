---
description: Um relatório Geral retorna dados de desempenho sobre características, segmentos e destinos.
seo-description: A General report in Audience Manager returns performance data on traits, segments, and destinations.
seo-title: General Reports in Audience Manager
solution: Audience Manager
title: Relatórios gerais
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
feature: General & Trend Reports
exl-id: dc16a821-b776-4a04-af60-4b8c914253dd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 1%

---

# Relatórios gerais{#general-reports}

A [!UICONTROL General] O relatório do retorna dados de desempenho sobre características, segmentos e destinos.

## Visão geral {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] usos [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) para estender permissões de grupo de usuários para o [!UICONTROL General] relatórios. Os usuários podem ver somente essas características e segmentos nos relatórios que têm permissão para visualizar. [!UICONTROL RBAC] A funcionalidade permite controlar quais dados de relatório as equipes internas podem visualizar. Por exemplo, uma agência que gerencia diferentes contas de anunciante pode configurar permissões de grupo de usuários para que uma equipe que gerencia a conta do Anunciante A não possa ver os dados de relatório do Anunciante B.

Executar um [!UICONTROL General] relatar quando for necessário:

* Revise o desempenho por característica, segmento ou destino.
* Rastrear impressões (total e exclusivas) em intervalos de 1, 7, 14, 30, 60 e 90 dias.
* Revisar contagens de carga total e exclusiva.
* Compare o desempenho de características e segmentos.
* Identifique características e segmentos de desempenho fortes ou ruins, analise a demanda ou compare dados de carga/disparo com relatórios de terceiros.
* Exporte dados (formato .csv) para análise e compartilhamento adicional.

A ilustração a seguir fornece uma visão geral de alto nível dos principais elementos da [!UICONTROL General] relatório.

![](assets/general_reports.png)

1. Configure as seguintes opções:

   * **Tipo de relatório:** Selecione o tipo de relatório desejado (Característica, Segmento ou Destino).

   * **Para Datas Até:** Especifique o intervalo de datas do relatório.

2. Procure uma característica, segmento ou destino por nome ou ID.
3. Na lista de pastas, arraste e solte as características, os segmentos ou os destinos que deseja relatar na [!UICONTROL Selections] no lado direito.
4. Gere o relatório a ser exibido em uma tabela exportável.

## Executar um Relatório Geral {#run-general-report}

Esta seção descreve como executar uma [!UICONTROL General] relatar e definir tempo e outras opções de desempenho.

<!-- 

t_run_general_report.xml

 -->

1. No **[!UICONTROL Analytics]** painel, clique em **[!UICONTROL General Reports]**.
1. No **[!UICONTROL Report Type]** selecione o tipo desejado: Característica, Segmento ou Destino.
1. *Condicional* Clique na caixa de data para exibir um calendário e, em seguida, selecione a data de término do relatório se desejar especificar uma data diferente de hoje.
1. Procure uma característica, segmento ou destino por nome ou ID.
1. Na lista de pastas, arraste e solte as características, os segmentos ou os destinos que deseja relatar na [!UICONTROL Selections] no lado direito.
1. Clique em **[!UICONTROL Run Report]**.

   Os resultados são exibidos em uma tabela exportável. Clique nos cabeçalhos da coluna para classificar os resultados em ordem crescente ou decrescente.
1. Selecione o botão de opção desejado na parte superior do relatório para filtrar dados por desempenho ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]ou [!UICONTROL Total Trait Population]) ou por hora (intervalo de 1, 7, 14, 30, 60 ou 90 dias).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] são calculados para [!UICONTROL Rule-based Traits] somente.

1. *Opcional* Clique em **[!UICONTROL Export to CSV]**. Isso exporta o [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], e [!UICONTROL Total Trait Population] para todos os intervalos de dias.

## Explicação dos resultados de relatórios gerais {#general-reports-explained}

Os números no [!UICONTROL General Reports] são gerados diretamente de nosso [!UICONTROL User Profile Store]. Os resultados refletem o número de usuários que [!DNL Audience Manager] contido no back-end no momento em que esses números de relatório foram gerados.

* Esses números não incluem IDs de visitante com tráfego excessivo. O tráfego de bots é filtrado antes de chegar ao nosso sistema de back-end. Além disso, parte do tráfego de bot é descartada durante uma execução de trabalho de limpeza semanal no back-end.
* Se você integrar os dados por meio do processamento de entrada, desativou o [!DNL Audience Manager] UUID e essas IDs incluem usuários que não estão mais ativos em nosso sistema, esses usuários inativos [!DNL Audience Manager] Os UUIDs nunca alcançam o [!UICONTROL User Profile Store] e não são relatados.
* [!UICONTROL Total Trait Realizations] são calculados para [!UICONTROL Rule-based Traits] somente.

## Resultados de relatórios gerais para características {#general-report-results-traits}

Os filtros abaixo estão disponíveis ao executar um relatório Geral e selecionar **[!UICONTROL Trait]** como o tipo de relatório.

Ao filtrar os resultados por [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] é o número de visitantes de dispositivos anônimos que adicionaram a característica aos perfis dentro do intervalo de tempo selecionado.
* [!UICONTROL Total Trait Realization] é o número total de realizações de características anônimas no intervalo de tempo selecionado.
* [!UICONTROL Total Trait Population] é o número de visitantes de dispositivos anônimos que têm essa característica em seus perfis.

![geral-relatório-características-dispositivo](assets/general-report-traits-deviceid.png)

Ao filtrar os resultados por [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] é o número de visitantes autenticados que adicionaram a característica ao perfil, dentro do intervalo de tempo selecionado.
* [!UICONTROL Total Trait Realization] é o número total de realizações de características autenticadas dentro do intervalo de tempo selecionado.
* [!UICONTROL Total Trait Population] é o número de visitantes autenticados que têm essa característica no perfil.

![geral-relatório-características-entre-dispositivos](assets/general-report-traits-cross-device.png)

<!-- 
### Unique Trait Realizations

This metric represents the unique number of [Audience Manager Unique User IDs (UUID)](../reference/ids-in-aam.md) that qualified for the trait in your selected time range. For example, if a user visited your homepage three times on 10/1, you would see one Unique Trait Realization.

### Total Trait Realizations

This metric represents the total amount of trait fires for the trait in your selected time range. For example, if a user visited your homepage, then navigated to your tech news and your sports news sections, they would appear in the General Report as three total trait realizations, and one unique trait realization.

### Total Trait Population

This metric represents the total amount of Audience Manager UUIDs that are currently qualified for the trait. Use this number to understand the total amount of users you could use for segmentation and targeting. Typically, users remain part of a trait for [120 days](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). For example, a user visiting your homepage three times today and never returning afterwards, would remain as a user in this population every day until 120 days from now. At the 120 day mark, they would be removed from the population. Read our [Trait and Segment Qualification Reference](../features/traits/trait-and-segment-qualification-reference.md) for more examples on the difference between Unique Trait Realizations and Total Trait Population.

The illustration below shows the results of running a general report for the Trait report type. -->
<!-- 
![](assets/general_reports_metrics.png) -->


## Resultados de relatórios gerais para segmentos {#general-report-results-segments}

As métricas abaixo estão disponíveis ao executar um relatório Geral e selecionar **[!UICONTROL Segment]** como o tipo de relatório:

### Preenchimento de segmentos em tempo real

Essa métrica representa o número real de visitantes únicos vistos em tempo real pelo intervalo de tempo especificado e que foram qualificados para o segmento no momento em que foram vistos pelo Audience Manager.

### População total do segmento

Essa métrica representa o número total de UUIDs de Audience Manager qualificados para o segmento dentro do período de análise selecionado. A População total de segmentos de 1 dia representa a base de usuários mais precisa para direcionamento.

>[!NOTE]
>
>Selecionar **[!UICONTROL Include Destination Mappings]** para ver um detalhamento da população do segmento para destinos ativados.

A ilustração abaixo mostra os resultados da execução de um relatório geral para o tipo de relatório Segmento.

![](assets/general_reports_segment_metrics.png)

## Resultados de relatórios gerais para destinos {#general-report-results-destinations}

As métricas abaixo estão disponíveis ao executar um relatório Geral e selecionar **[!UICONTROL Destination]** como o tipo de relatório:

**Preenchimento de segmentos em tempo real**

Essa métrica representa o número real de visitantes únicos vistos em tempo real pelo intervalo de tempo especificado e que foram qualificados para o segmento no momento em que foram vistos pelo Audience Manager.

**População total do segmento**

Essa métrica representa o número total de UUIDs de Audience Manager pertencentes a um segmento dentro do período de retrospectiva, que foram enviados para um destino.

A ilustração abaixo mostra os resultados da execução de um relatório geral para o tipo de relatório Destinos.

![](assets/general_reports_destinations.png)
