---
description: Um relatório de Tendência retorna dados de tendência sobre características e segmentos.
seo-description: Um relatório de Tendência retorna dados de tendência sobre características e segmentos.
seo-title: Relatórios de tendências
solution: Audience Manager
title: Relatórios de tendências
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
feature: general & trend reports
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 1%

---


# Relatórios de tendências{#trend-reports}

Um relatório de Tendência retorna dados de tendência sobre características e segmentos.

## Visão geral {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] usa  [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) para estender permissões de grupo de usuários aos  [!UICONTROL Trend] relatórios. Os usuários podem ver apenas as características e os segmentos no relatórios com permissões para a visualização. [!UICONTROL RBAC] permite controlar quais equipes internas de dados de relatórios são capazes de visualização.

Por exemplo, uma agência que gerencia diferentes contas de anunciantes pode configurar permissões de grupo de usuários para que uma equipe que gerencia a conta do anunciante A não possa ver os dados de relatórios do anunciante B.

Execute um relatório [!UICONTROL Trend] quando precisar:

* Analise os dados de tendências por características e segmentos.
* Acompanhe as tendências em intervalos de 1, 7, 14, 30, 60 e 90 dias.
* Compare características e tendências de segmentos ao longo do tempo.
* Identifique traços e segmentos de desempenho fortes ou ruins.
* Exporte dados (formato .csv) para análise e compartilhamento adicionais.

A ilustração a seguir fornece uma visão geral de alto nível dos elementos principais no relatório [!UICONTROL Trend].

![](assets/trend_reports.png)

1. Configure as seguintes opções:
   **Tipo de relatório:** selecione o tipo de relatório desejado (Característica ou Segmento).
   **Intervalo de datas:** especifique o intervalo de datas do relatório (data do start e data final).
   **Intervalo de exibição:** especifique o intervalo de exibição (intervalos de 1, 7, 14, 30, 60 e 90 dias).
1. Procure por uma característica ou segmento por nome ou ID.
1. Na lista da pasta, arraste e solte as características ou segmentos que deseja reportar para o painel [!UICONTROL Selections] no lado direito.
1. Gere o relatório para exibi-lo em formato gráfico ou exporte-o para o formato CSV.

## Executar um Relatório de Tendência {#run-trend-report}

Este procedimento descreve como executar um relatório [!UICONTROL Trend].

<!-- 

t_working_with_trend_reports.xml

 -->

1. No painel **[!UICONTROL Analytics]**, clique em **[!UICONTROL Trend Reports]**.
1. Na lista suspensa **[!UICONTROL Report Type]**, selecione o tipo desejado: **[!UICONTROL Trait]** ou **[!UICONTROL Segment]**.
1. Clique nas caixas de datas para exibir um calendário e selecione as datas inicial e final do seu relatório.
1. Especifique o intervalo de exibição: por 1, 7, 14, 30, 60 ou 90 dias.
1. Procure por uma característica ou segmento por nome ou ID.
1. Na lista da pasta, arraste e solte as características ou segmentos que deseja reportar para o painel [!UICONTROL Selections] no lado direito.
   * Para obter melhor desempenho, execute um relatório [!UICONTROL Trend] em menos de 20 características ou segmentos de cada vez.
1. Clique em **[!UICONTROL Graph Traits]** ou **[!UICONTROL Graph Segments]**, dependendo do tipo de relatório que você está visualizando (Características ou Segmentos). Essas opções ignoram todas as pastas e gráficos somente os traços ou segmentos selecionados individualmente.

   Ou

   Clique em **[!UICONTROL Export to CSV]** para exportar os dados de características ou segmentos e todas as pastas no formato CSV para análise e compartilhamento adicionais. Isso exporta [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations] e [!UICONTROL Total Trait Population] para todos os intervalos de dias.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] são calculados  [!UICONTROL Rule-based Traits] apenas para.

1. (Opcional) Passe o mouse sobre características individuais ou segmentos para exibir o número de visitas e a data de cada ponto de dados. Você pode clicar nos cabeçalhos de coluna na tabela para classificar os resultados em ordem crescente ou decrescente.

## Resultados de relatório de tendência para características {#trend-report-results-traits}

Os filtros abaixo estão disponíveis quando você executa um [!UICONTROL Trend Report] e seleciona **[!UICONTROL Trait]** como o tipo de relatório.

Ao filtrar os resultados por [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] é o número de visitantes de dispositivo anônimos que adicionaram a característica ao perfil dentro do intervalo de tempo selecionado.
* [!UICONTROL Total Trait Realization] é o número total de realizações de características anônimas dentro do intervalo de tempo selecionado.
* [!UICONTROL Total Trait Population] é o número de visitantes anônimos do dispositivo que têm esta característica no perfil.

Ao filtrar os resultados por [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] é o número de visitantes autenticados que adicionaram a característica ao perfil, dentro do intervalo de tempo selecionado.
* [!UICONTROL Total Trait Realization] é o número total de realizações de características autenticadas dentro do intervalo de tempo selecionado.
* [!UICONTROL Total Trait Population] é o número de visitantes autenticados que têm esta característica no perfil.

![tendência-características-do-relatório](assets/trend-report-traits.png)

Zeroes indicam que [!DNL Audience Manager] não coletou dados desse dia. Entradas em branco indicam que o traço não existia.

Assista ao vídeo abaixo para ver detalhadamente como as métricas entre dispositivos funcionam.

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## Resultados de relatório de tendência para segmentos {#segment-report-results-traits}

Os filtros abaixo estão disponíveis quando você executa um [!UICONTROL Trend Report] e seleciona **[!UICONTROL Segments]** como o tipo de relatório.

* **[!UICONTROL Real-time Segment Population]**: o número de visitantes qualificados para o segmento dentro do intervalo de tempo selecionado.
* **[!UICONTROL Total Segment Population]**: o número total de visitantes qualificados para o segmento.

![segmentos de relatórios de tendências](assets/trend-report-segments.png)