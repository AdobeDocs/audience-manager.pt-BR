---
description: Uma visão geral do recurso Público-alvo endereçável e casos de uso.
keywords: DIL
seo-description: Uma visão geral do recurso Público-alvo endereçável e casos de uso.
seo-title: Públicos-alvo endereçáveis
solution: Audience Manager
title: Públicos-alvo endereçáveis
topic: API DIL
uuid: 3 eb 1335 a -6949-452 b-b 77 a -697 c 22856 cb 3
translation-type: tm+mt
source-git-commit: b213a1ecde4c85dc66dada24dec602ed1d9b0332

---


# Addressable Audience {#addressable-audiences}

Uma visão geral do recurso Público-alvo endereçável e casos de uso.

## What is an Addressable Audience? {#addressable-audience-description}

The [!UICONTROL Addressable Audiences] feature shows you the overlap between the audiences you see across all of your properties where [!DNL Audience Manager] collects data and your selected destination. Para ajudá-lo a entender este conceito, consulte a ilustração abaixo. A sobreposição entre cada círculo representa os diferentes tipos de públicos-alvo endereçáveis.

![](assets/addressableAudienceVenn.png)

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
    <tr> 
   <td colname="col1"> <p> <b>Público-alvo endereçável do Manager Manager para um destino</b> </p> </td> 
   <td colname="col2"> <p>Uma contagem de todos os dispositivos que interagiram com todos os clientes do Audience Manager no nível da plataforma durante o período de análise do relatório e que podem ser correspondidos com o destino escolhido. </p> <p>Essa métrica é útil porque mostra: </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> The size of the total addressable audience that <span class="keyword"> Audience Manager</span> can reach on a particular targeting destination. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">How big the <span class="keyword"> Audience Manager</span> profile pool is for a targeting platform and the size of their audiences. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Público-alvo total do cliente</b> </p> </td> 
   <td colname="col2"> <p>Uma contagem de dispositivos que perceberam uma característica baseada em regras em suas propriedades ou em uma característica incorporada dos arquivos offline durante a janela de look-back. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taxa de correspondência de público-alvo endereçável</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Uma contagem de sobreposição de dispositivos que tenha percebido uma característica baseada em regras ou um característica integrado durante a janela de retrospectiva e os dispositivos que temos uma sincronização de ID com o destino escolhido, independentemente do tempo de sincronizações. </p> 
    </draft-comment> <p>Esta métrica representa dispositivos que: 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Have realized either a rule-based or an onboarded trait during the look-back window <b>AND</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Tenha uma sincronização de ID com o destino escolhido, independentemente do tempo de sincronização. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taxa de correspondência do cliente</b> </p> </td> 
   <td colname="col2"> <p>Público-alvo do público-alvo endereçável do cliente ÷, expresso como um %. </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <b>População total de segmentos</b> </p> </td> 
   <td colname="col2"> <p>Uma contagem de todos os dispositivos que eram membros do seu segmento durante o período de retrospectiva do relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Público-alvo endereçável do segmento</b> </p> </td> 
   <td colname="col2"> <p>O número de usuários que pertenciam ao segmento durante o período de análise do relatório e têm uma sincronização de ID ativa no site. Segments can include your own first-party data and second party and third party data, via traits acquired in the <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>Dica: Quando usada com o período de retrospectiva de 1 dias, essa métrica pode ajudar você a entender o estado atual de seus segmentos. This is because the <span class="wintitle"> Segment Addressable Audience</span> metric represents the users who stayed in a segment throughout the previous day. Combine this with the fact that <span class="keyword"> Audience Manager</span> refreshes <span class="wintitle"> Addressable Audiences</span> daily, combining this metric and lookback period provides the most up-to-date snapshot of your segments. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taxa de correspondência do segmento</b> </p> </td> 
   <td colname="col2"> <p>Segmento de segmento total do público-alvo ÷, expresso como um %. </p> </td> 
  </tr>  
 </tbody> 
</table>

## Addressable Audience Interface {#addressable-audience-interface}

The [!UICONTROL Addressable Audience] feature turns this abstract concept into quantifiable data. In [!DNL Audience Manager], this feature displays audience overlap with data visualizations that provide at-a-glance information along with numeric data in tabular form.

[!UICONTROL Addressable Audiences] está localizado **[!UICONTROL Audience Data > Destinations]**. Select **[!UICONTROL Integrated Platforms > Device-Based]** to see addressable audiences metrics.

![](assets/addressable-audiences-landing.png)

As três métricas que podem ser visualizadas na página de aterrissagem Públicos-alvo endereçáveis representam:

| Métrica | Descrição |
---------|----------|
| **Público-alvo endereçável (dispositivos)** | This metric represents the Customer Addressable Audience (described in the table above) *for the last 30 days.* |
| **Taxa de correspondência** | This metric represents the Addressable Audience Match Rate (described in the table above) *for the last 30 days*. |
| **Público-alvo endereçável vitalício (dispositivos)** | Uma contagem de todos os dispositivos que interagiram com todos os clientes do Audience Manager no nível da plataforma durante o período de análise do relatório e que podem ser correspondidos com esse destino. See [Platform-Level Metrics](/help/using/features/addressable-audiences.md#platform-level-metrics) for more information. |

Clique no nome de um destino de servidor a servidor para exibir os dados de público-alvo endereçáveis. Observe que esse recurso retorna dados somente para destinos de servidor para servidor e o acesso requer permissões de administrador.

![](assets/addressableAudiences.png)

A revisão desses dados pode ajudá-lo a:

* **Previsão e planejamento:**[!UICONTROL Segment Addressable Audience] fornecem mais granularidade nos segmentos que você está planejando enviar para um destino para direcionamento e ativação do público-alvo.

* **Revisões de desempenho:** O [!UICONTROL Addressable Audiences] recurso também é uma ferramenta de solução de problemas. Ele permite analisar o desempenho da campanha, entender o alcance da campanha e permitir que você faça check-in cruzado com parceiros de definição de metas/ativação caso não veja os resultados esperados.

### Acessibilidade com dados de terceiros e implicações para taxas de correspondência

Antes de adquirir dados de terceiros para aquisição de público-alvo, os clientes podem validar a sobreposição com outros provedores de dados. Isso pode ajudar você a tomar uma decisão informada antes de comprar novos dados. The ID syncs for purchased third-party data rely not only on the overlap of your data but also on third-party providers’ footprints with all other [!DNL Audience Manager] customers. Your [!DNL Adobe] consultant can help you identify additional relevant data sources to optimize prospecting campaigns.

### Usuários móveis e taxas de correspondência

There are gaps when trying to connect [!DNL Safari] or mobile app users where there are no third-party cookies present. That makes it difficult to sync users with some partners because only those [!DNL Adobe] IDs for synced third-party cookies are provided in the media delivery logs. This is a reason why you might see [low match rates](../features/addressable-audiences.md#low-match-rates) for your destinations.

## Date Ranges in Addressable Audiences and Destinations {#date-ranges}

Read the sections below for available date ranges and how data ages out of each interval in the reports for an [!UICONTROL Addressable Audience] or [!UICONTROL Destination].

## Available Date Ranges and Time Zones {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Reports for your [!UICONTROL Addressable Audiences] and [Destinations](../features/destinations/destinations.md) use the same date range intervals. As opções de intervalo de datas incluem:

* [!UICONTROL Last 1 Day] (Esse intervalo é executado da Meia-noite à meia-noite do período de 24 horas anterior. Não é uma métrica de tempo atual ou atual.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

All dates and date ranges are set in the [!DNL UTC] time zone. See [Time Zones in Audience Manager](../reference/aam-time-zones.md).

## Data in Date Range Intervals {#date-range-intervals}

The [!UICONTROL Addressable Audience] and [!UICONTROL Destination] metrics return a count of unique users for the selected time interval. Por exemplo, um visitante é contado apenas uma vez, mesmo que eles cheguem ao site várias vezes. A primeira visita é uma visita única e é gravada. As visitas subsequentes retornas visitas e não são contadas, pois não são exclusivas.

Os intervalos de datas contêm dados para o intervalo de tempo selecionado ou mais recente. E os dados de cada intervalo de relatório com o passar do tempo passam. For example, let&#39;s assume you see 2 visitors after choosing the [!UICONTROL Last 30 Days] option. Nos relatórios, estes visitantes:

* *Será incluído* nos resultados retornados pelos intervalos de tempo mais longos (60 dias, 90 dias e duração).
* *Não será* incluído nos intervalos mais curtos que antecedem a [!UICONTROL Last 30 Day] opção (Atual, 7 dias e 14 dias).

And, on day 31, these visitors only show up in the 60 day, 90 day, and [!UICONTROL Lifetime] results. Eles excederam o intervalo de 30 dias. Visitors do not age out of the [!UICONTROL Lifetime] interval.

## Addressable Audience Metrics {#addressable-audience-metrics}

This section describes the types of metrics provided by [!UICONTROL Addressable Audiences].

### Customer-Level Metrics {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

These metrics return data for traits realized when visitors come to your site or when you send inbound data files to [!DNL Audience Manager]. Essas métricas fornecem uma exibição abrangente do tamanho do público-alvo para a sua conta.

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Público-alvo endereçável do cliente</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Uma contagem de sobreposição de dispositivos que tenha percebido uma característica baseada em regras ou um característica integrado durante a janela de retrospectiva e os dispositivos que temos uma sincronização de ID com o destino escolhido, independentemente do tempo de sincronizações. </p> 
    </draft-comment> <p>Esta métrica representa dispositivos que: 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Have realized either a rule-based or an onboarded trait during the look-back window <b>AND</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Tenha uma sincronização de ID com o destino escolhido, independentemente do tempo de sincronização. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Público-alvo total do cliente</b> </p> </td> 
   <td colname="col2"> <p>Uma contagem de dispositivos que perceberam uma característica baseada em regras em suas propriedades ou em uma característica incorporada dos arquivos offline durante a janela de look-back. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taxa de correspondência do cliente</b> </p> </td> 
   <td colname="col2"> <p>Público-alvo do público-alvo endereçável do cliente ÷, expresso como um %. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Segment-Level Match Metrics {#segment-level-metrics}

Essas métricas retornam dados sobre a associação de segmentos. Eles ajudam a fornecer uma visualização mais granular e precisa do tamanho do público-alvo para cada um dos seus segmentos.

>[!NOTE]
>
>A maneira como a janela de look-back é aplicada no nível do segmento é diferente daquela no nível do cliente. Os visitantes podem chegar ao site e perceber uma característica 10 dias atrás, e eles podem se qualificar para um segmento desde então e sair do segmento 2 dias atrás. Quando o retorno de 7 dia for aplicado, esses visitantes serão contados no nível do segmento, mas não no nível do cliente.

<table id="table_4185AA02CC774B6C93B02E45F88BBBD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Público-alvo endereçável do segmento</b> </p> </td> 
   <td colname="col2"> <p>O número de usuários que pertenciam ao segmento durante o período de análise do relatório e têm uma sincronização de ID ativa no site. Segments can include your own first-party data and second party and third party data, via traits acquired in the <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>Dica: Quando usada com o período de retrospectiva de 1 dias, essa métrica pode ajudar você a entender o estado atual de seus segmentos. This is because the <span class="wintitle"> Segment Addressable Audience</span> metric represents the users who stayed in a segment throughout the previous day. Combine this with the fact that <span class="keyword"> Audience Manager</span> refreshes <span class="wintitle"> Addressable Audiences</span> daily, combining this metric and lookback period provides the most up-to-date snapshot of your segments. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>População total de segmentos</b> </p> </td> 
   <td colname="col2"> <p>Uma contagem de todos os dispositivos que eram membros do seu segmento durante o período de retrospectiva do relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taxa de correspondência do segmento</b> </p> </td> 
   <td colname="col2"> <p>Segmento de segmento total do público-alvo ÷, expresso como um %. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Platform-Level Metrics {#platform-level-metrics}

Essa métrica retorna dados sobre atividades coletadas em todos os clientes do Audience Manager. Eles podem fornecer uma visão mais ampla do público-alvo do cliente em comparação aos clientes agregados do Audience Manager.

<table id="table_B6654D9858FF46AF95B1C181D4608D26"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Público-alvo endereçável do Audience Manager</b> </p> </td> 
   <td colname="col2"> <p>Uma contagem de todos os dispositivos que interagiram com todos os clientes do Audience Manager no nível da plataforma durante o período de análise do relatório e que podem ser correspondidos com o destino escolhido. </p> <p>Essa métrica é útil porque mostra: </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> The size of the total addressable audience that <span class="keyword"> Audience Manager</span> can reach on a particular targeting destination. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">How big the <span class="keyword"> Audience Manager</span> profile pool is for a targeting platform and the size of their audiences. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Comparing Customer and Segment Addressable Audiences{#comparing-metrics}

You shouldn&#39;t compare the [!UICONTROL Customer Addressable Audience] and [!UICONTROL Segment Addressable Audience] metrics to determine if one is more significant than the other. Essas são métricas diferentes, diferentes e independentes. Conforme descrito nas definições acima, cada um deles é derivado de diferentes conjuntos de dados. Com isso, você deve evitar obter quaisquer conclusões se uma métrica for maior que a outra. Tudo que você pode dizer ao compará-los é que:

* [!UICONTROL Customer Addressable Audiences] se baseia em experiências características *para seus próprios dados primários*. Essa métrica fornece uma visão ampla e abrangente da integração com um parceiro de dados.

* [!UICONTROL Segment Addressable Audiences] baseia-se em qualificações de segmento *para seus próprios dados primários, mais dados de segundo e terceiros*. Essa métrica fornece uma visualização granular e mais precisa dos públicos-alvo endereçáveis em uma plataforma de definição de metas.

## Causes of Low Match Rates for Addressable Audiences {#low-match-rates}

Common elements responsible for low [!UICONTROL Addressable Audience] match rates or discrepancies in reported numbers.

<!-- addressable-audiences.xml -->

<table id="table_895D536F69134330A4F13887ECAFD4F5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Causa </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Tráfego móvel</b> </p> </td> 
   <td colname="col2"> <p>A maioria das integrações do servidor para servidor depende de processos de sincronização facilitados por cookies de terceiros. No entanto, os ambientes móveis não usam cookies de terceiros. Como resultado, seus números de Público-alvo endereçáveis podem parecer baixos em comparação com o tamanho do segmento. </p> <p>A partir de janeiro de 2018, você pode ativar públicos móveis no mesmo destino do Google e da Adobe Advertising Cloud configurado para públicos-alvo baseados em cookies. Enquanto isso significa que você pode enviar segmentos com cookie combinado e associação de ID móvel aos destinos do Google e da Advertising Cloud, lembre-se de que Públicos-alvo endereçáveis só exibem a sobreposição entre IDs e destinos de cookies. O Audience Manager envia 100% dos públicos móveis para destinos, mas os públicos móveis não são medidos pela métrica Público-alvo endereçável. </p> <p> <p><b>Observação</b>: Por exemplo, utilize um segmento com uma população de 1,000,000. Se você mapear esse segmento para um destino do Google ou da Adobe Advertising Cloud, poderá ver um Público-alvo endereçável de devices 00,000 dispositivos e uma Taxa de correspondência de 70%. A associação de 700,000 consiste em IDs de cookie que têm uma sincronização de ID com o destino. O Público-alvo endereçável pode, na verdade, ser muito maior, pois as IDs móveis endereçáveis não aparecem nessa métrica. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tráfego do Safari</b> </p> </td> 
   <td colname="col2"> <p>O Safari bloqueia cookies de terceiros. Isso impede que o Audience Manager sincronize IDs com o destino. With the introduction of <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, you can expect your addressable audiences not to include Safari users. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Impressões de mídia rastreadas</b> </p> </td> 
   <td colname="col2"> <p>Devido às práticas recomendadas do servidor de anúncios, as sincronizações de ID não são feitas nas tags de anúncios. Os clientes que fazem uma grande quantidade de anúncios externos não sincronizam usuários a integrações de terceiros nesses ambientes. Além disso, uma grande quantidade de dados de impressão de mídia coletados pode reduzir números de público-alvo endereçáveis. </p> </td>
  </tr> 
 </tbody> 
</table>

## Troubleshooting with Addressable Audiences {#troubleshooting}

In addition to surfacing match rates, you can also use [!UICONTROL Addressable Audiences] as a troubleshooting tool.

<!-- addressable-audiences-troubleshooting.xml -->

Por exemplo, digamos que você envie um segmento para um destino e que o destino exiba números de relatório baixos. Checking the [!UICONTROL Addressable Audience] results will show you if this is a technical problem or just a case of low match rates. Uma taxa de correspondência baixa mostra que o destino não é ótimo para os segmentos selecionados. No entanto, uma diferença no número total de públicos-alvo endereçáveis entre o Audience Manager e o destino indica uma integração, sincronização ou outro problema técnico. Nesses casos, entre em contato com o gerente da conta.