---
description: Um relatório Geral retorna dados de desempenho sobre características, segmentos e destinos.
seo-description: Um relatório Geral no Gerenciador de Audiências retorna dados de desempenho sobre características, segmentos e destinos.
seo-title: Relatórios gerais no Gerenciador de Audiências
solution: Audience Manager
title: Relatórios gerais
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
translation-type: tm+mt
source-git-commit: 8493705b0f200b5b43d937dfd452210403a52b33

---


# Relatórios gerais{#general-reports}

Um [!UICONTROL General] relatório retorna dados de desempenho sobre características, segmentos e destinos.

## Visão geral {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] usa [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) para estender permissões do grupo de usuários aos [!UICONTROL General] relatórios. Os usuários podem ver apenas as características e os segmentos no relatórios com permissões para a visualização. [!UICONTROL RBAC] permite controlar quais equipes internas de dados de relatórios são capazes de visualização. Por exemplo, uma agência que gerencia diferentes contas de anunciantes pode configurar permissões de grupo de usuários para que uma equipe que gerencia a conta do anunciante A não possa ver os dados de relatórios do anunciante B.

Execute um [!UICONTROL General] relatório quando precisar:

* Analise o desempenho por característica, segmento ou destino.
* Rastreie impressões (total e exclusiva) em intervalos de 1, 7, 14, 30, 60 e 90 dias.
* Analise a contagem total e exclusiva de cargas.
* Compare características e desempenho de segmentos.
* Identifique características e segmentos de desempenho fortes ou ruins, analise a demanda ou compare os dados de carga/fogo com relatórios de terceiros.
* Exporte dados (formato .csv) para análise e compartilhamento adicionais.

A ilustração a seguir fornece uma visão geral de alto nível dos elementos-chave no [!UICONTROL General] relatório.

![](assets/general_reports.png)

1. Configure as seguintes opções:

   * **Tipo de relatório:** Selecione o tipo de relatório desejado (Características, Segmento ou Destino).

   * **Para datas até:** Especifique o intervalo de datas do relatório.

2. Procure uma característica, um segmento ou um destino por nome ou ID.
3. Na lista da pasta, arraste e solte as características, os segmentos ou os destinos que você deseja reportar para o [!UICONTROL Selections] painel no lado direito.
4. Gere o relatório a ser exibido em uma tabela exportável.

## Executar um relatório geral {#run-general-report}

Esta seção descreve como executar um [!UICONTROL General] relatório e definir o tempo e outras opções de desempenho.

<!-- 

t_run_general_report.xml

 -->

1. In the **[!UICONTROL Analytics]** dashboard, click **[!UICONTROL General Reports]**.
1. Na lista **[!UICONTROL Report Type]** suspensa, selecione o tipo desejado: Característica, segmento ou destino.
1. *Condicional* Clique na caixa de data para exibir um calendário e, em seguida, selecione a data de término do seu relatório se desejar especificar uma data diferente de hoje.
1. Procure uma característica, um segmento ou um destino por nome ou ID.
1. Na lista da pasta, arraste e solte as características, os segmentos ou os destinos que você deseja reportar para o [!UICONTROL Selections] painel no lado direito.
1. Clique em **[!UICONTROL Run Report]**.

   Os resultados são exibidos em uma tabela exportável. Clique nos cabeçalhos da coluna para classificar os resultados em ordem crescente ou decrescente.
1. Selecione o botão de opção desejado na parte superior do relatório para filtrar dados por desempenho ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]ou [!UICONTROL Total Trait Population]) ou por tempo (1, 7, 14, 30, 60 ou intervalo de 90 dias).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] são calculados [!UICONTROL Rule-based Traits] apenas para.

1. *Clique opcional* **[!UICONTROL Export to CSV]**. Isso exporta os intervalos [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]e [!UICONTROL Total Trait Population] para todos os intervalos do dia.

## Explicação dos resultados gerais dos relatórios {#general-reports-explained}

Os números no [!UICONTROL General Reports] são gerados diretamente do nosso [!UICONTROL User Profile Store]. Os resultados refletem o número de usuários [!DNL Audience Manager] contidos no backend no momento em que esses números de relatórios foram gerados.

* Esses números não incluem IDs de visitante com tráfego excessivo. O tráfego dos bots é filtrado antes de chegar ao nosso sistema de backend. Além disso, algum tráfego de robô é descartado durante uma execução semanal de limpeza no backend.
* Se os dados onboard por meio do processamento de entrada forem desconectados do [!DNL Audience Manager] UUID e essas IDs incluírem usuários que não estão mais ativos no sistema, essas [!DNL Audience Manager] UIDs inativas nunca chegam ao [!UICONTROL User Profile Store] e não são reportadas.
* [!UICONTROL Total Trait Realizations] são calculados [!UICONTROL Rule-based Traits] apenas para.

## Resultados gerais de relatórios para características {#general-report-results-traits}

As métricas abaixo estão disponíveis quando você executa um relatório Geral e seleciona **[!UICONTROL Trait]** como o tipo de relatório:

**Realizações de características únicas**

Essa métrica representa o número exclusivo de IDs de usuário exclusivas (UUID) [do Gerenciador de](../reference/ids-in-aam.md) Audiências qualificadas para a característica no intervalo de tempo selecionado. Por exemplo, se um usuário visitasse sua página inicial três vezes em 10/1, você veria uma Realização de características únicas.

**Total de Realizações de Características**

Essa métrica representa a quantidade total de características acionadas para a característica no intervalo de tempo selecionado. Por exemplo, se um usuário visitasse sua página inicial e navegasse até suas notícias de tecnologia e suas seções de notícias de esportes, elas apareceriam no Relatório Geral como três realizações de características totais e uma realização de características únicas.

**População total do traço**

Essa métrica representa a quantidade total de UUIDs do Gerenciador de Audiências que estão qualificados para a característica no momento. Use esse número para entender a quantidade total de usuários que você pode usar para segmentação e direcionamento. Normalmente, os usuários permanecem como parte de uma característica por [120 dias](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). Por exemplo, um usuário visitando sua página inicial três vezes hoje e nunca mais voltando depois, permaneceria como usuário nessa população todos os dias até daqui a 120 dias. Na marca dos 120 dias, eles seriam removidos da população. Leia nossa [Referência](../features/traits/trait-and-segment-qualification-reference.md) de qualificação de características e segmentos para obter mais exemplos sobre a diferença entre as Realizações de características únicas e a População de características totais.

A ilustração abaixo mostra os resultados da execução de um relatório geral para o tipo de relatório Características.

![](assets/general_reports_metrics.png)

## Resultados gerais de relatórios para segmentos {#general-report-results-segments}

As métricas abaixo estão disponíveis quando você executa um relatório Geral e seleciona **[!UICONTROL Segment]** como o tipo de relatório:

**População de segmentos em tempo real**

Essa métrica representa o número real de visitantes únicos vistos em tempo real para o intervalo de tempo especificado e que estavam qualificados para o segmento no momento em que foram vistos pelo Gerenciador de Audiências.

**População total de segmentos**

Essa métrica representa o número total de UUIDs do Gerenciador de Audiências qualificadas para o segmento no período de análise selecionado. Sua População total de segmentos de 1 dia representa a base de usuários mais precisa para definição de metas.

>[!NOTE]
>
>Selecione **[!UICONTROL Include Destination Mappings]** para ver um detalhamento da população de segmentos para destinos ativados.

A ilustração abaixo mostra os resultados da execução de um relatório geral para o tipo de relatório Segmento.

![](assets/general_reports_segment_metrics.png)

## Resultados gerais de relatórios para destinos {#general-report-results-destinations}

As métricas abaixo estão disponíveis quando você executa um relatório Geral e seleciona **[!UICONTROL Destination]** como o tipo de relatório:

**População de segmentos em tempo real**

Essa métrica representa o número real de visitantes únicos vistos em tempo real para o intervalo de tempo especificado e que estavam qualificados para o segmento no momento em que foram vistos pelo Gerenciador de Audiências.

**População total de segmentos**

Essa métrica representa o número total de UUIDs do Gerenciador de Audiências pertencentes a um segmento dentro do período de análise, que foram enviados para um destino.

A ilustração abaixo mostra os resultados da execução de um relatório geral para o tipo de relatório Destinos.

![](assets/general_reports_destinations.png)
