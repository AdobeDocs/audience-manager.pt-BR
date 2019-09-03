---
description: Um relatório Geral retorna dados de desempenho em características, segmentos e destinos.
seo-description: Um relatório Geral no Audience Manager retorna dados de desempenho em características, segmentos e destinos.
seo-title: Relatórios gerais no Audience Manager
solution: Audience Manager
title: Relatórios gerais
uuid: 0 cea 75 a 0-969 e -4 ee 3-971 a -60 b 911711 e 52
translation-type: tm+mt
source-git-commit: 1c626c770208150d209d93f666b581113ada8de9

---


# Relatórios gerais{#general-reports}

Um [!UICONTROL General] relatório retorna os dados de desempenho em características, segmentos e destinos.

## Visão geral {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] usa [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) para estender permissões de grupo do usuário para [!UICONTROL General] os relatórios. Os usuários podem ver apenas essas características e segmentos no relatório que têm permissão para visualizar. [!UICONTROL RBAC] permite controlar quais equipes internas de dados de relatório podem exibir. Por exemplo, uma agência que gerencia diferentes contas de anunciante pode configurar permissões de grupo do usuário para que uma equipe que gerencia a conta do anunciante A não possa ver os dados de relatório do anunciante B.

Execute [!UICONTROL General] um relatório quando precisar:

* Analise o desempenho por características, segmentos ou destino.
* Rastrear impressões (total e único) em intervalos 1, 7, 14, 30, 60 e 90 dias.
* Analise contagens de carga totais e únicas.
* Compare o desempenho de características e segmentos.
* Identifique características e segmentos de desempenho forte ou ruim, analise demanda ou compare dados de carregamento/acionamento com relatórios de terceiros.
* Exportar dados (formato. csv) para análise e compartilhamento mais recentes.

A ilustração a seguir fornece uma visão geral de alto nível dos elementos-chave no [!UICONTROL General] relatório.

![](assets/general_reports.png)

1. Configure as seguintes opções:

   * **Tipo de relatório:** Selecione o tipo de relatório desejado (Característica, Segmento ou Destino).

   * **Para Datas por:** Especifique o intervalo de datas para o relatório.

2. Pesquise por uma característica, segmento ou destino por nome ou ID.
3. Na lista de pastas, arraste e solte as características, os segmentos ou os destinos que deseja relatar ao [!UICONTROL Selections] painel no lado direito.
4. Gere o relatório para exibição em uma tabela exportável.

## Executar um relatório geral {#run-general-report}

Esta seção descreve como executar um [!UICONTROL General] relatório e definir tempo e outras opções de desempenho.

<!-- 

t_run_general_report.xml

 -->

1. In the **[!UICONTROL Analytics]** dashboard, click **[!UICONTROL General Reports]**.
1. Na lista **[!UICONTROL Report Type]** suspensa, selecione o tipo desejado: Característica, segmento ou destino.
1. *Clique na* caixa de datas condicional para exibir um calendário e, em seguida, selecione a data final do seu relatório se desejar especificar uma data diferente de hoje.
1. Pesquise por uma característica, segmento ou destino por nome ou ID.
1. Na lista de pastas, arraste e solte as características, os segmentos ou os destinos que deseja relatar ao [!UICONTROL Selections] painel no lado direito.
1. Clique em **[!UICONTROL Run Report]**.

   Os resultados são exibidos em uma tabela exportável. Clique nos cabeçalhos das colunas para classificar os resultados em ordem crescente ou decrescente.
1. Selecione o botão de opção desejado na parte superior do relatório para filtrar os dados por desempenho ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]ou [!UICONTROL Total Trait Population]) ou por hora (1, 7, 14, 30, 60 ou intervalo de 90 dias).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] são calculadas apenas [!UICONTROL Rule-based Traits] para.

1. *Clique opcional***[!UICONTROL Export to CSV]**. Isso exporta o [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]e [!UICONTROL Total Trait Population] todos os intervalos de dia.

## Explicação dos resultados dos relatórios gerais {#general-reports-explained}

Os números nos [!UICONTROL General Reports] são gerados diretamente de nosso [!UICONTROL User Profile Store]. Os resultados refletem o número de usuários que [!DNL Audience Manager] contém o backend no momento em que estes números de relatório foram gerados.

* Esses números não incluem IDs de visitantes com tráfego excessivo. O tráfego de bots é filtrado antes de chegar ao sistema de backend. Além disso, alguns tráfegos de bot são descartados durante uma execução de limpeza semanal no backend.
* Se os dados do quadro por meio do processamento de entrada não estiverem ativados para o [!DNL Audience Manager] UUID, e essas IDs incluírem usuários que não estão mais ativos em nosso sistema, esses [!DNL Audience Manager] uuids inativos nunca chegam ao [!UICONTROL User Profile Store] e não são relatados.
* [!UICONTROL Total Trait Realizations] são calculadas apenas [!UICONTROL Rule-based Traits] para.

## Resultados gerais dos relatórios para características {#general-report-results-traits}

As métricas abaixo estão disponíveis quando você executa um relatório Geral e seleciona **[!UICONTROL Trait]** o tipo de relatório:

**Análise de característica exclusiva**

Essa métrica representa o número exclusivo de [IDs de usuário único do Audience Manager (UUID)](../reference/ids-in-aam.md) que se qualifica para a característica no intervalo de tempo selecionado. Por exemplo, se um usuário visitou sua página inicial três vezes em 10/1, você veria uma Realização de característica exclusiva.

**Total de experiências de característica**

Essa métrica representa a quantidade total de acionamentos de características para a característica no intervalo de tempo selecionado. Por exemplo, se um usuário visitou sua página inicial e, em seguida, navegou para suas notícias técnicas e suas seções de notícias esportivas, elas apareceriam no Relatório geral como três totais de características e uma realização de característica exclusiva.

**População de característica total**

Essa métrica representa a quantidade total de uuids do Audience Manager que estão qualificados atualmente para a característica. Use esse número para entender a quantidade total de usuários que você pode usar para segmentação e direcionamento. Normalmente, os usuários permanecem fazendo parte de uma característica por [120 dias](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). Por exemplo, um usuário que visita sua página inicial três vezes hoje e nunca retorna depois, permaneceria como um usuário nesta população todos os dias até 120 dias de agora. Na marca de 120 dias, eles seriam removidos da população. Leia a [Referência de Qualificação de Característica](../features/traits/trait-qualification-reference.md) para obter mais exemplos sobre a diferença entre as Análises de característica exclusivas e a População total de características.

A ilustração abaixo mostra os resultados da execução de um relatório geral para o tipo de relatório Característica.

![](assets/general_reports_metrics.png)

## Resultados gerais dos relatórios para segmentos {#general-report-results-segments}

As métricas abaixo estão disponíveis quando você executa um relatório Geral e seleciona **[!UICONTROL Segment]** o tipo de relatório:

**Preenchimento de segmentos em tempo real**

Essa métrica representa o número real de visitantes únicos vistos em tempo real para o intervalo de tempo especificado e que foram qualificados para o segmento no momento em que foram vistos pelo Audience Manager.

**População total de segmentos**

Essa métrica representa o número total de uuids do Audience Manager que são qualificados para o segmento no período de análise selecionado. Sua população de segmento total de 1 dias representa a base de usuários mais precisa para direcionamento.

>[!NOTE]
>
>Selecione **[!UICONTROL Include Destination Mappings]** um detalhamento da população de segmentos para destinos ativados.

A ilustração abaixo mostra os resultados da execução de um relatório geral para o tipo de relatório Segmento.

![](assets/general_reports_segment_metrics.png)

## Resultados gerais dos relatórios para destinos {#general-report-results-destinations}

As métricas abaixo estão disponíveis quando você executa um relatório Geral e seleciona **[!UICONTROL Destination]** o tipo de relatório:

**Preenchimento de segmentos em tempo real**

Essa métrica representa o número real de visitantes únicos vistos em tempo real para o intervalo de tempo especificado e que foram qualificados para o segmento no momento em que foram vistos pelo Audience Manager.

**População total de segmentos**

Essa métrica representa o número total de uuids do Audience Manager pertencentes a um segmento no período de análise, que foi enviado para um destino.

A ilustração abaixo mostra os resultados da execução de um relatório geral para o tipo de relatório de Destinos.

![](assets/general_reports_destinations.png)
