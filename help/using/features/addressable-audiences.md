---
description: Uma visão geral do recurso Audiência endereçável e dos casos de uso.
keywords: DIL
seo-description: Uma visão geral do recurso Audiência endereçável e dos casos de uso.
seo-title: Públicos endereçáveis
solution: Audience Manager
title: Públicos endereçáveis
topic: DIL API
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Match Rates
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1824'
ht-degree: 1%

---


# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Uma visão geral do [!UICONTROL Addressable Audience] recurso e dos casos de uso.

## O que é uma [!UICONTROL Addressable Audience]? {#addressable-audience-description}

O [!UICONTROL Addressable Audiences] recurso mostra a sobreposição entre as audiências que você vê em todas as suas propriedades, onde [!DNL Audience Manager] coleta dados e o destino selecionado. Para ajudá-lo a entender esse conceito, dê uma olhada na ilustração abaixo. A sobreposição entre cada círculo representa os diferentes tipos de audiências endereçáveis.

![](assets/addressableAudienceVenn.png)


| Métrica | Descrição |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] para um [!UICONTROL Destination] | Uma contagem de todos os dispositivos que interagiram com todos os [!DNL Audience Manager] clientes no nível da plataforma durante o período de análise do relatório e que pode ser correspondida com a sua escolha [!UICONTROL destination]. <br><br>Essa métrica é útil porque mostra: <ul><li>O tamanho do total [!UICONTROL addressable audience] que [!DNL Audience Manager] pode atingir em uma definição de metas específica [!UICONTROL destination].</li><li>O tamanho do pool de [!DNL Audience Manager] perfis para uma plataforma de definição de metas e o tamanho de suas audiências.</li></ul> |
| [!UICONTROL Customer Total Audience] | Uma contagem de dispositivos que perceberam um erro [!UICONTROL rule-based trait] em suas propriedades ou um erro [!UICONTROL onboarded trait] em seus arquivos offline durante a janela de retrospectiva. |
| [!UICONTROL Addressable Audience Match Rate] | Uma contagem de sobreposições de dispositivos que perceberam uma [!UICONTROL rule-based trait] ou uma [!UICONTROL onboarded trait] durante a janela de retrospectiva e os dispositivos que temos uma sincronização de ID com a escolhida, [!UICONTROL destination] independentemente do tempo de sincronização.<br><br>Essa métrica representa dispositivos que:<ul><li>Have realized either a [!UICONTROL rule-based] or an [!UICONTROL onboarded trait] during the look-back window `AND`</li><li>Have an ID sync with the chosen [!UICONTROL destination] regardless of the time of syncs.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] / [!UICONTROL Customer Total Audience] expresso em percentagem. |
| [!UICONTROL Total Segment Population] | Uma contagem de todos os dispositivos que eram membros de seu relatório [!UICONTROL segment] durante o período de análise do relatório. |
| [!UICONTROL Segment Addressable Audience] | The number of users who have belonged to the [!UICONTROL segment] during the report look-back period and have an active ID sync on your site. [!UICONTROL Segments] pode incluir seus próprios dados primários e dados de terceiros e segundos, por meio dos [!UICONTROL traits] adquiridos no [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Dica: Quando usada com o período de análise de 1 dia, essa métrica pode ajudá-lo a entender o estado atual do seu [!UICONTROL segments]. Isso ocorre porque a [!UICONTROL Segment Addressable Audience] métrica representa os usuários que permaneceram em um [!UICONTROL segment] dia anterior. Combine isso com o fato de que [!DNL Audience Manager] a atualização é feita [!UICONTROL Addressable Audiences] diariamente, combinando essa métrica e o período de pesquisa fornece o instantâneo mais atualizado do seu [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] / [!UICONTROL Total Segment Population] expresso em percentagem. |

## [!UICONTROL Addressable Audiences] Interface {#addressable-audience-interface}

O [!UICONTROL Addressable Audience] recurso transforma esse conceito abstrato em dados quantificáveis. Em [!DNL Audience Manager]geral, esse recurso exibe sobreposição de audiência com visualizações de dados que fornecem informações instantâneas juntamente com dados numéricos em forma de tabela.

[!UICONTROL Addressable Audiences] está localizado em **[!UICONTROL Audience Data > Destinations]**. Selecione **[!UICONTROL Integrated Platforms > Device-Based]** para ver métricas de audiências endereçáveis.

![](assets/addressable-audiences-landing.png)

As três métricas que você pode ver na [!UICONTROL Addressable Audiences] landing page representam:

| Métrica | Descrição |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Essa métrica representa a métrica [!UICONTROL Customer Addressable Audience] (descrita na tabela acima) *dos últimos 30 dias.* |
| **[!UICONTROL Match Rate]** | Essa métrica representa a métrica [!UICONTROL Addressable Audience Match Rate] (descrita na tabela acima) *dos últimos 30 dias*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Uma contagem de todos os dispositivos que interagiram com todos os [!DNL Audience Manager] clientes no nível da plataforma durante o período de análise do relatório e que podem ser combinados com isso [!UICONTROL destination]. Consulte Métricas [de nível](/help/using/features/addressable-audiences.md#platform-level-metrics) Platform para obter mais informações. |

Clique no nome de uma visualização [!UICONTROL server-to-server destination] para  seus dados de audiência endereçáveis. Observe que esse recurso retorna dados somente para [!UICONTROL server-to-server destinations] e o acesso requer permissões de administrador.

![](assets/addressableAudiences.png)

A revisão desses dados pode ajudá-lo com:

* **Previsão e planejamento:** [!UICONTROL Segment Addressable Audience] os dados fornecem mais granularidade aos segmentos que você planeja enviar para um destino para direcionamento e ativação de audiências.

* **Análises de desempenho:** O [!UICONTROL Addressable Audiences] recurso também é uma ferramenta de solução de problemas. Ele permite que você analise o desempenho da campanha, entenda o alcance da campanha e faça uma verificação cruzada com parceiros de definição de metas/ativações se você não encontrar os resultados esperados.

### Prospecção com dados de terceiros e implicações para taxas de correspondência

Antes de adquirir dados de terceiros para aquisição de audiências, os clientes podem validar a sobreposição com outros provedores de dados. Isso pode ajudá-lo a tomar uma decisão informada antes de comprar novos dados. As sincronizações de ID para dados de terceiros adquiridos dependem não apenas da sobreposição de seus dados, mas também de pegadas de provedores de terceiros com todos os outros [!DNL Audience Manager] clientes. Seu [!DNL Adobe] consultor pode ajudá-lo a identificar outras fontes de dados relevantes para otimizar as campanhas de prospecção.

### Usuários móveis e taxas de correspondência

Há lacunas ao tentar conectar [!DNL Safari] ou usuários de aplicativos móveis nos quais não há terceiros [!DNL cookies] presentes. Isso dificulta a sincronização de usuários com alguns parceiros, pois somente essas [!DNL Adobe] IDs de terceiros sincronizadas [!DNL cookies] são fornecidas nos logs do delivery de mídia. Esta é uma razão pela qual você pode ver taxas [de correspondência](../features/addressable-audiences.md#low-match-rates) baixas para seu [!UICONTROL destinations].

## Intervalos de datas em [!UICONTROL Addressable Audiences] e [!UICONTROL Destinations] {#date-ranges}

Leia as seções abaixo para ver os intervalos de datas disponíveis e como os dados expiram em cada intervalo nos relatórios de um [!UICONTROL Addressable Audience] ou [!UICONTROL Destination].

## Intervalos de datas e fusos horários disponíveis {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Os relatórios para seus [!UICONTROL Addressable Audiences] e [Destinos](../features/destinations/destinations.md) usam os mesmos intervalos de intervalo de datas. As opções de intervalo de datas incluem:

* [!UICONTROL Last 1 Day] (Esse intervalo é executado da meia-noite à meia-noite do período de 24 horas anterior. Não é uma métrica em tempo real ou atual.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Todas as datas e intervalos de datas são definidos no [!DNL UTC] fuso horário. See [Time Zones in Audience Manager](../reference/aam-time-zones.md).

## Dados em intervalos de datas {#date-range-intervals}

As métricas [!UICONTROL Addressable Audience] e [!UICONTROL Destination] retornam uma contagem de usuários únicos para o intervalo de tempo selecionado. Por exemplo, um visitante é contado apenas uma vez, mesmo se ele vier ao seu site várias vezes. A primeira visita é a única e é registrada. As visitas subsequentes são visitas recorrentes e não são contadas porque não são exclusivas.

Os intervalos de datas contêm dados para o intervalo de tempo selecionado ou anterior. Além disso, os dados envelhecem fora de cada intervalo de relatório conforme o tempo passa. Por exemplo, vamos supor que você veja dois visitantes depois de escolher a [!UICONTROL Last 30 Days] opção. Nos relatórios, estes visitantes:

* *Serão* incluídos nos resultados retornados pelos intervalos de tempo mais longos (60 dias, 90 dias e Duração).
* *Não será* incluído nos intervalos mais curtos que precedem a [!UICONTROL Last 30 Day] opção (Atual, 7 dias e 14 dias).

E, no dia 31, esses visitantes só aparecem nos 60 dias, 90 dias, e [!UICONTROL Lifetime] resultados. Eles envelheceram fora do intervalo de 30 dias. Os Visitantes não envelhecem fora do [!UICONTROL Lifetime] intervalo.

## [!UICONTROL Addressable Audiences] Métricas {#addressable-audience-metrics}

Esta seção descreve os tipos de métricas fornecidas por [!UICONTROL Addressable Audiences].

### Métricas no nível do cliente {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Essas métricas retornam dados para características realizadas quando visitantes chegam ao seu site ou quando você envia arquivos de dados de entrada para [!DNL Audience Manager]. Essas métricas fornecem uma visualização abrangente do tamanho da audiência para sua conta.

| Métrica | Descrição |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Uma contagem de sobreposições de dispositivos que perceberam uma [!UICONTROL rule-based trait] ou uma [!UICONTROL onboarded trait] durante a janela de retrospectiva e os dispositivos com os quais temos uma sincronização de ID com o destino escolhido, independentemente do tempo de sincronização.<br><br>Essa métrica representa dispositivos que:<ul><li>Have realized either a [!UICONTROL rule-based] or an [!UICONTROL onboarded trait] during the look-back window `AND`</li><li>Have an ID sync with the chosen [!UICONTROL destination] regardless of the time of syncs.</li></ul> |
| [!UICONTROL Customer Total Audience] | Uma contagem de dispositivos que perceberam um erro [!UICONTROL rule-based trait] em suas propriedades ou um erro [!UICONTROL onboarded trait] em seus arquivos offline durante a janela de retrospectiva. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] / [!UICONTROL Customer Total Audience] expresso em percentagem. |

### Métricas de correspondência no nível do segmento {#segment-level-metrics}

Essas métricas retornam dados sobre a [!UICONTROL segment] associação. Eles ajudam a fornecer uma visualização mais granular e precisa do tamanho da audiência para cada um de seus [!UICONTROL segments].

>[!NOTE]
>
>A forma como a janela de retrospectiva é aplicada no [!UICONTROL segment] nível é diferente daquela no nível do cliente. Os Visitantes podem vir ao site e perceber há [!UICONTROL trait] 10 dias, e eles podem se qualificar para uma visita [!UICONTROL segment] desde então e desistir dos [!UICONTROL segment] 2 dias atrás. Quando a análise de sete dias for aplicada, esses visitantes serão contados no nível, mas não no nível do [!UICONTROL segment] cliente.

| Métrica | Descrição |
|---|---|
| [!UICONTROL Segment Addressable Audience] | The number of users who have belonged to the [!UICONTROL segment] during the report look-back period and have an active ID sync on your site. Segments can include your own first-party data and second party and third party data, via [!UICONTROL traits] acquired in the [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Dica: Quando usada com o período de análise de 1 dia, essa métrica pode ajudá-lo a entender o estado atual do seu [!UICONTROL segments]. Isso ocorre porque a [!UICONTROL Segment Addressable Audience] métrica representa os usuários que permaneceram em um [!UICONTROL segment] dia anterior. Combine isso com o fato de que [!DNL Audience Manager] a atualização é feita [!UICONTROL Addressable Audiences] diariamente, combinando essa métrica e o período de pesquisa fornece o instantâneo mais atualizado do seu [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Uma contagem de todos os dispositivos que eram membros de seu relatório [!UICONTROL segment] durante o período de análise do relatório. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] / [!UICONTROL Total Segment Population] expresso em percentagem. |

### Métricas de nível Platform {#platform-level-metrics}

Essa métrica retorna dados sobre atividades coletadas em todos os [!DNL Audience Manager] clientes. Eles podem fornecer uma visualização mais ampla da audiência do cliente em comparação aos [!DNL Audience Manager] clientes agregados.

| Métrica | Descrição |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Uma contagem de todos os dispositivos que interagiram com todos os [!DNL Audience Manager] clientes no nível da plataforma durante o período de análise do relatório e que pode ser correspondida com a sua escolha [!UICONTROL destination]. <br><br>Essa métrica é útil porque mostra:<ul><li>O tamanho do destino [!UICONTROL total addressable audience] que [!DNL Audience Manager] pode ser atingido em um destino de direcionamento específico.</li><li>O tamanho do pool de [!DNL Audience Manager] perfis para uma plataforma de definição de metas e o tamanho de suas audiências.</li></ul> |

## Comparar [!UICONTROL Customer] e [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

Você não deve comparar as métricas [!UICONTROL Customer Addressable Audience] e [!UICONTROL Segment Addressable Audience] para determinar se uma é mais significativa do que a outra. Essas são métricas separadas, diferentes e independentes. Conforme descrito nas definições acima, cada uma destas é derivada de diferentes conjuntos de dados. Considerando isso, você deve evitar tirar conclusões se uma métrica for maior que a outra. Tudo o que você pode dizer ao comparar isso é que:

* [!UICONTROL Customer Addressable Audiences] é baseado em [!UICONTROL trait] realizações *para seus próprios dados* primários. Essa métrica fornece uma visualização abrangente e abrangente da sua integração com um parceiro de dados.

* [!UICONTROL Segment Addressable Audiences] é baseado em qualificações de segmento *para seus próprios dados primários, além de dados* secundários e de terceiros. Essa métrica fornece uma visualização granular e mais precisa de sua empresa [!UICONTROL addressable audiences] em uma plataforma de definição de metas.

## Causas de taxas de correspondência baixas para [!UICONTROL Addressable Audiences] {#low-match-rates}

Elementos comuns responsáveis por baixas taxas de [!UICONTROL Addressable Audience] correspondência ou discrepâncias nos números reportados.

| Causa | Descrição |
|---|---|
| Tráfego móvel | A maioria das [!UICONTROL server-to-server] integrações depende de processos de sincronização facilitados por terceiros [!DNL cookies]. No entanto, ambientes móveis não usam terceiros [!DNL cookies]. Como resultado, seus [!UICONTROL Addressable Audiences] números podem parecer baixos quando comparados ao [!UICONTROL segment] tamanho. <br><br>A partir de janeiro de 2018, você poderá ativar audiências móveis nos mesmos [!DNL Google] e [!DNL Adobe Advertising Cloud] destinos configurados para [!UICONTROL cookie-based] audiência. Embora isso signifique que você pode enviar [!UICONTROL segments] com associação de IDs combinadas [!DNL cookie] e móveis para seus [!DNL Google] e [!DNL Advertising Cloud] destinos, lembre-se de que [!UICONTROL Addressable Audiences] só exibe a sobreposição entre [!DNL cookie] IDs e destinos. [!DNL Audience Manager] envia 100% das audiências móveis para [!UICONTROL destinations], mas as audiências móveis não são medidas pela [!UICONTROL Addressable Audience] métrica. <br><br>**Observação **: Por exemplo, pegue um[!UICONTROL segment]com uma população de 1.000.000. Se você mapear isso[!UICONTROL segment]para um[!DNL Google]ou[!DNL Adobe Advertising Cloud]destino, você poderá ver um[!UICONTROL Addressable Audience]de 700.000 dispositivos e um[!UICONTROL Match Rate]de 70%. A associação de 700.000 consiste em[!DNL cookie]IDs que têm uma sincronização de ID com o[!UICONTROL destination]. Sua[!UICONTROL Addressable Audience]opção pode, na verdade, ser muito maior, pois as IDs móveis endereçáveis não aparecem nessa métrica. |
| [!DNL Safari] Tráfego | [!DNL Safari] bloqueia terceiros [!DNL cookies]. Isso impede [!DNL Audience Manager] a sincronização de IDs com o [!UICONTROL destination]. Com a introdução do [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), você pode esperar que [!UICONTROL addressable audiences] não inclua [!DNL Safari] usuários. |
| Impressões de mídia rastreadas | Devido às práticas recomendadas do servidor de publicidade, as sincronizações de ID não são feitas em tags de publicidade. Os clientes que fazem uma grande quantidade de anúncios externos não sincronizarão os usuários às integrações de terceiros nesses ambientes. Além disso, uma grande quantidade de dados coletados de impressão de mídia poderia reduzir [!UICONTROL addressable audience] os números. |

## Solução de problemas com [!UICONTROL Addressable Audiences] {#troubleshooting}

Além de encontrar as taxas de correspondência, você também pode usar [!UICONTROL Addressable Audiences] como uma ferramenta de solução de problemas.

Por exemplo, digamos que você envie um segmento para um segmento [!UICONTROL destination] que [!UICONTROL destination] mostra números baixos de relatórios. A verificação dos [!UICONTROL Addressable Audience] resultados mostrará se isso é um problema técnico ou apenas um caso de taxas de correspondência baixas. Uma taxa de correspondência baixa mostra que seus segmentos selecionados [!UICONTROL destination] não são tão excelentes. No entanto, uma diferença nos [!UICONTROL total addressable audience] números entre [!DNL Audience Manager] e o [!UICONTROL destination] indica um problema de integração, sincronização ou outro problema técnico. Nesses casos, entre em contato com seu gerente de conta.
