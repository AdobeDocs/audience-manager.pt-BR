---
description: Um relatório de Tendência retorna dados de tendência em características e segmentos.
seo-description: Um relatório de Tendência retorna dados de tendência em características e segmentos.
seo-title: Relatórios de tendências
solution: Audience Manager
title: Relatórios de tendências
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
feature: Relatórios gerais e de tendências
exl-id: 3373f413-cc8f-49c7-9b4e-34b39e0efc38
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 1%

---

# Relatórios de tendências{#trend-reports}

Um relatório de Tendência retorna dados de tendência em características e segmentos.

## Visão geral {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] O usa  [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) para estender as permissões do grupo de usuários aos  [!UICONTROL Trend] relatórios. Os usuários podem ver somente as características e os segmentos nos relatórios que têm permissões para visualizar. [!UICONTROL RBAC] permite controlar quais dados de relatórios as equipes internas podem visualizar.

Por exemplo, uma agência que gerencia diferentes contas de anunciantes pode configurar permissões de grupo de usuários para que uma equipe que gerencia a conta do anunciante A não possa ver os dados de relatório do anunciante B.

Execute um relatório [!UICONTROL Trend] quando precisar:

* Analise os dados de tendência por características e segmentos.
* Acompanhe as tendências com intervalos de 1, 7, 14, 30, 60 e 90 dias.
* Compare as tendências de características e segmentos ao longo do tempo.
* Identificar características e segmentos de desempenho robustos ou inadequados.
* Exportar dados (formato .csv) para análise e compartilhamento adicionais.

A ilustração a seguir fornece uma visão geral de alto nível de elementos-chave no relatório [!UICONTROL Trend].

![](assets/trend_reports.png)

1. Configure as seguintes opções:
   **Tipo de relatório:** selecione o tipo de relatório desejado (Característica ou Segmento).
   **Intervalo de datas:** especifique o intervalo de datas do relatório (data inicial e data final).
   **Intervalo de exibição:** especifique o intervalo de exibição (intervalos de 1, 7, 14, 30, 60 e 90 dias).
1. Procure por uma característica ou segmento por nome ou ID.
1. Na lista de pastas, arraste e solte as características ou segmentos que deseja relatar no painel [!UICONTROL Selections] no lado direito.
1. Gere o relatório para exibir os dados em formato gráfico ou exporte-o para o formato CSV.

## Executar um Relatório de Tendência {#run-trend-report}

Este procedimento descreve como executar um relatório [!UICONTROL Trend].

<!-- 

t_working_with_trend_reports.xml

 -->

1. No painel **[!UICONTROL Analytics]**, clique em **[!UICONTROL Trend Reports]**.
1. Na lista suspensa **[!UICONTROL Report Type]**, selecione o tipo desejado: **[!UICONTROL Trait]** ou **[!UICONTROL Segment]**.
1. Clique nas caixas de datas para exibir um calendário e selecione as datas inicial e final para seu relatório.
1. Especifique o intervalo de exibição: por 1, 7, 14, 30, 60 ou 90 dias.
1. Procure por uma característica ou segmento por nome ou ID.
1. Na lista de pastas, arraste e solte as características ou segmentos que deseja relatar no painel [!UICONTROL Selections] no lado direito.
   * Para melhor desempenho, execute um relatório [!UICONTROL Trend] em menos de 20 características ou segmentos de cada vez.
1. Clique em **[!UICONTROL Graph Traits]** ou **[!UICONTROL Graph Segments]**, dependendo do tipo de relatório que você está visualizando (características ou segmentos). Essas opções ignoram todas as pastas e gráficos somente as características ou segmentos selecionados individualmente.

   Ou

   Clique em **[!UICONTROL Export to CSV]** para exportar os dados de característica ou segmento e todas as pastas no formato CSV para análise e compartilhamento adicionais. Isso exporta [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations] e [!UICONTROL Total Trait Population] para todos os intervalos de dia.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] são calculadas  [!UICONTROL Rule-based Traits] somente para .

1. (Opcional) Passe o mouse sobre características ou segmentos individuais para exibir o número de visitas e a data de cada ponto de dados. Você pode clicar nos cabeçalhos da coluna na tabela para classificar os resultados em ordem crescente ou decrescente.

## Resultados de relatório de tendência para características {#trend-report-results-traits}

Os filtros abaixo estão disponíveis quando você executa um [!UICONTROL Trend Report] e seleciona **[!UICONTROL Trait]** como o tipo de relatório.

Ao filtrar os resultados por [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] é o número de visitantes anônimos do dispositivo que adicionaram a característica ao perfil dentro do intervalo de tempo selecionado.
* [!UICONTROL Total Trait Realization] é o número total de realizações de característica do anonimato no intervalo de tempo selecionado.
* [!UICONTROL Total Trait Population] é o número de visitantes anônimos do seu dispositivo que têm essa característica no perfil.

Ao filtrar os resultados por [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] é o número de seus visitantes autenticados que adicionaram a característica ao perfil, dentro do intervalo de tempo selecionado.
* [!UICONTROL Total Trait Realization] é o número total de realizações de características autenticadas no intervalo de tempo selecionado.
* [!UICONTROL Total Trait Population] é o número de seus visitantes autenticados que têm essa característica em seu perfil.

![tendência-relatório-características](assets/trend-report-traits.png)

Zeroes indicam que [!DNL Audience Manager] não coletou dados do dia. As entradas em branco indicam que a característica não existia.

Assista ao vídeo abaixo para obter uma análise detalhada de como as métricas entre dispositivos funcionam.

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## Resultados de relatório de tendência para segmentos {#segment-report-results-traits}

Os filtros abaixo estão disponíveis quando você executa um [!UICONTROL Trend Report] e seleciona **[!UICONTROL Segments]** como o tipo de relatório.

* **[!UICONTROL Real-time Segment Population]**: o número de visitantes qualificados para o segmento dentro do intervalo de tempo selecionado.
* **[!UICONTROL Total Segment Population]**: o número total de visitantes qualificados para o segmento.

![segmentos de relatório de tendências](assets/trend-report-segments.png)
