---
description: Uma visão geral do recurso de Público-alvo endereçável e casos de uso.
keywords: DIL
seo-description: An overview of the Addressable Audience feature and use cases.
seo-title: Addressable Audiences
solution: Audience Manager
title: Públicos-alvo endereçáveis
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Match Rates
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
source-git-commit: cecdc0b0f43a146e11f7d23eb21a06146496ac2d
workflow-type: tm+mt
source-wordcount: '1831'
ht-degree: 0%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Uma visão geral do recurso [!UICONTROL Addressable Audience] e casos de uso.

## O que é um [!UICONTROL Addressable Audience]? {#addressable-audience-description}

O recurso [!UICONTROL Addressable Audiences] mostra a sobreposição entre os públicos que você vê em todas as suas propriedades, onde o [!DNL Audience Manager] coleta dados e o destino selecionado. Para ajudar você a entender esse conceito, consulte a ilustração abaixo. A sobreposição entre cada círculo representa os diferentes tipos de públicos endereçáveis.

![](assets/addressableAudienceVenn.png)


| Métrica | Descrição |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] para [!UICONTROL Destination] | Uma contagem de todos os dispositivos que interagiram com todos os clientes do [!DNL Audience Manager] no nível da plataforma durante o período de análise do relatório e que podem corresponder ao [!UICONTROL destination] escolhido. <br><br>Esta métrica é útil porque mostra: <ul><li>O tamanho do total [!UICONTROL addressable audience] que [!DNL Audience Manager] pode atingir em um [!UICONTROL destination] de direcionamento específico.</li><li>O tamanho do pool de perfis [!DNL Audience Manager] para uma plataforma de direcionamento e o tamanho de seus públicos.</li></ul> |
| [!UICONTROL Customer Total Audience] | Uma contagem de dispositivos que perceberam um [!UICONTROL rule-based trait] em suas propriedades ou um [!UICONTROL onboarded trait] de seus arquivos offline durante a janela de retrospectiva. |
| [!UICONTROL Customer Addressable Audience] | Uma contagem de sobreposição de dispositivos que perceberam um [!UICONTROL rule-based trait] ou um [!UICONTROL onboarded trait] durante a janela de retrospectiva e dispositivos com os quais temos uma sincronização de ID com o [!UICONTROL destination] escolhido, independentemente do tempo de sincronização.<br><br>Esta métrica representa dispositivos que:<ul><li>Ter realizado um [!UICONTROL rule-based] ou um [!UICONTROL onboarded trait] durante a janela de retrospectiva `AND`</li><li>Ter uma sincronização de ID com o [!UICONTROL destination] escolhido, independentemente do tempo de sincronização.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] expresso como uma porcentagem. |
| [!UICONTROL Total Segment Population] | Uma contagem de todos os dispositivos que eram membros de seu [!UICONTROL segment] durante o período de análise do relatório. |
| [!UICONTROL Segment Addressable Audience] | O número de usuários que pertenceram a [!UICONTROL segment] durante o período de análise do relatório e que têm uma sincronização de ID ativa no site. O [!UICONTROL Segments] pode incluir seus próprios dados primários e dados secundários e de terceiros, via [!UICONTROL traits] adquiridos no [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Dica: quando usada com o período retroativo de um dia, essa métrica pode ajudá-lo a entender o estado atual do seu [!UICONTROL segments]. Isso ocorre porque a métrica [!UICONTROL Segment Addressable Audience] representa os usuários que permaneceram em um [!UICONTROL segment] durante o dia anterior. Combine isso com o fato de que o [!DNL Audience Manager] atualiza [!UICONTROL Addressable Audiences] diariamente, a combinação dessa métrica e do período de lookback fornece o instantâneo mais atualizado do seu [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] expresso como uma porcentagem. |

## Interface [!UICONTROL Addressable Audiences] {#addressable-audience-interface}

O recurso [!UICONTROL Addressable Audience] transforma esse conceito abstrato em dados quantificáveis. No [!DNL Audience Manager], esse recurso exibe a sobreposição de públicos-alvo com visualizações de dados que fornecem informações resumidas juntamente com dados numéricos em formato de tabela.

[!UICONTROL Addressable Audiences] está localizado em **[!UICONTROL Audience Data > Destinations]**. Selecione **[!UICONTROL Integrated Platforms > Device-Based]** para ver as métricas de públicos-alvo endereçáveis.

![](assets/addressable-audiences-landing.png)

As três métricas que você pode ver na página de aterrissagem do [!UICONTROL Addressable Audiences] representam:

| Métrica | Descrição |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Esta métrica representa o [!UICONTROL Customer Addressable Audience] (descrito na tabela acima) *dos últimos 30 dias.* |
| **[!UICONTROL Match Rate]** | Esta métrica representa o [!UICONTROL Addressable Audience Match Rate] (descrito na tabela acima) *dos últimos 30 dias*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Uma contagem de todos os dispositivos que interagiram com todos os clientes do [!DNL Audience Manager] no nível da plataforma durante o período de análise do relatório e que podem corresponder a este [!UICONTROL destination]. Consulte [Métricas de nível de plataforma](/help/using/features/addressable-audiences.md#platform-level-metrics) para obter mais informações. |

Clique no nome de um [!UICONTROL server-to-server destination] para ver seus dados de público-alvo endereçáveis. Observe que esse recurso retorna dados somente para [!UICONTROL server-to-server destinations] e o acesso exige permissões de administrador.

![](assets/addressableAudiences.png)

A análise desses dados pode ajudá-lo com:

* **Previsão e planejamento:** os dados de [!UICONTROL Segment Addressable Audience] fornecem mais granularidade aos segmentos que você pretende enviar para um destino de direcionamento e ativação de público-alvo.

* **Avaliações de desempenho:** o recurso [!UICONTROL Addressable Audiences] também é uma ferramenta de solução de problemas. Ele permite analisar o desempenho da campanha, entender seu alcance e cruzar com parceiros de direcionamento/ativação se você não encontrar os resultados esperados.

### Prospecção com dados de terceiros e implicações para taxas de correspondência

Antes de comprar dados de terceiros para aquisição de público-alvo, os clientes podem validar a sobreposição com outros provedores de dados. Isso pode ajudá-lo a tomar uma decisão informada antes de comprar novos dados. As sincronizações de ID para dados de terceiros comprados dependem não apenas da sobreposição de seus dados, mas também das pegadas de provedores de terceiros com todos os outros clientes do [!DNL Audience Manager]. O consultor do [!DNL Adobe] pode ajudá-lo a identificar outras fontes de dados relevantes para otimizar as campanhas de prospecção.

### Usuários móveis e taxas de correspondência

Há falhas ao tentar conectar [!DNL Safari] ou usuários do aplicativo móvel em que não há [!DNL cookies] de terceiros presentes. Isso dificulta a sincronização de usuários com alguns parceiros, pois somente essas [!DNL Adobe] IDs para terceiros sincronizados [!DNL cookies] são fornecidas nos logs de entrega de mídia. Esta é uma razão pela qual você pode ver [taxas de correspondência baixas](../features/addressable-audiences.md#low-match-rates) para seu [!UICONTROL destinations].

## Intervalos de Datas em [!UICONTROL Addressable Audiences] e [!UICONTROL Destinations] {#date-ranges}

Leia as seções abaixo para obter intervalos de datas disponíveis e saber como os dados envelhecem em cada intervalo nos relatórios para um [!UICONTROL Addressable Audience] ou [!UICONTROL Destination].

## Intervalos de datas e fusos horários disponíveis {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Os relatórios de seus [!UICONTROL Addressable Audiences] e [Destinos](../features/destinations/destinations.md) usam os mesmos intervalos de datas. As opções de intervalo de datas incluem:

* [!UICONTROL Last 1 Day] (Esse intervalo é executado da meia-noite à meia-noite do período de 24 horas anterior. Não é uma métrica em tempo real ou atual.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Todas as datas e intervalos de datas estão definidos no fuso horário [!DNL UTC]. Consulte [Fusos horários em Audience Manager](../reference/aam-time-zones.md).

## Dados em intervalos de datas {#date-range-intervals}

As métricas [!UICONTROL Addressable Audience] e [!UICONTROL Destination] retornam uma contagem de usuários únicos para o intervalo selecionado. Por exemplo, um visitante é contado apenas uma vez, mesmo que venha ao site várias vezes. A primeira visita é a visita única e é registrada. As visitas subsequentes são de retorno e não são contadas por não serem exclusivas.

Intervalos de datas contêm dados para o intervalo de tempo selecionado ou anterior. E os dados envelhecem de cada intervalo de relatório conforme o tempo passa. Por exemplo, vamos supor que você veja 2 visitantes depois de escolher a opção [!UICONTROL Last 30 Days]. Nos relatórios, esses visitantes:

* *Será* incluído nos resultados retornados pelos intervalos de tempo mais longos (60 dias, 90 dias e Duração).
* *Não será* incluído nos intervalos mais curtos que precedem a opção [!UICONTROL Last 30 Day] (Atual, 7 dias e 14 dias).

E, no dia 31, esses visitantes só aparecem nos resultados de 60 dias, 90 dias e [!UICONTROL Lifetime]. Eles envelheceram fora do intervalo de 30 dias. Os visitantes não envelhecem fora do intervalo [!UICONTROL Lifetime].

## [!UICONTROL Addressable Audiences] Métricas {#addressable-audience-metrics}

Esta seção descreve os tipos de métricas fornecidas por [!UICONTROL Addressable Audiences].

### Métricas no nível do cliente {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Essas métricas retornam dados para características percebidas quando os visitantes chegam ao seu site ou quando você envia arquivos de dados de entrada para [!DNL Audience Manager]. Essas métricas fornecem uma visualização abrangente do tamanho do público-alvo da sua conta.

| Métrica | Descrição |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Uma contagem de sobreposição de dispositivos que perceberam um [!UICONTROL rule-based trait] ou um [!UICONTROL onboarded trait] durante a janela de retrospectiva e dispositivos com os quais temos uma sincronização de ID com o destino escolhido, independentemente do tempo de sincronização.<br><br>Esta métrica representa dispositivos que:<ul><li>Ter realizado um [!UICONTROL rule-based] ou um [!UICONTROL onboarded trait] durante a janela de retrospectiva `AND`</li><li>Ter uma sincronização de ID com o [!UICONTROL destination] escolhido, independentemente do tempo de sincronização.</li></ul> |
| [!UICONTROL Customer Total Audience] | Uma contagem de dispositivos que perceberam um [!UICONTROL rule-based trait] em suas propriedades ou um [!UICONTROL onboarded trait] de seus arquivos offline durante a janela de retrospectiva. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] expresso como uma porcentagem. |

### Métricas de correspondência de nível de segmento {#segment-level-metrics}

Essas métricas retornam dados sobre a associação [!UICONTROL segment]. Eles ajudam a fornecer uma exibição mais granular e precisa do tamanho do público para cada um dos seus [!UICONTROL segments].

>[!NOTE]
>
>A forma como a janela de retrospectiva é aplicada no nível [!UICONTROL segment] é diferente daquela no nível do cliente. Os visitantes podem chegar ao site e perceber um [!UICONTROL trait] 10 dias atrás, e podem se qualificar para um [!UICONTROL segment] desde então e serem desconectados do [!UICONTROL segment] 2 dias atrás. Quando a retrospectiva de 7 dias for aplicada, esses visitantes serão contados no nível [!UICONTROL segment], mas não no nível do cliente.

| Métrica | Descrição |
|---|---|
| [!UICONTROL Segment Addressable Audience] | O número de usuários que pertenceram a [!UICONTROL segment] durante o período de análise do relatório e que têm uma sincronização de ID ativa no site. Os segmentos podem incluir seus próprios dados primários e dados secundários e de terceiros, via [!UICONTROL traits] adquiridos no [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Dica: quando usada com o período retroativo de um dia, essa métrica pode ajudá-lo a entender o estado atual do seu [!UICONTROL segments]. Isso ocorre porque a métrica [!UICONTROL Segment Addressable Audience] representa os usuários que permaneceram em um [!UICONTROL segment] durante o dia anterior. Combine isso com o fato de que o [!DNL Audience Manager] atualiza [!UICONTROL Addressable Audiences] diariamente, a combinação dessa métrica e do período de lookback fornece o instantâneo mais atualizado do seu [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Uma contagem de todos os dispositivos que eram membros de seu [!UICONTROL segment] durante o período de análise do relatório. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] expresso como uma porcentagem. |

### Métricas de nível de plataforma {#platform-level-metrics}

Essa métrica retorna dados sobre atividades coletadas em todos os clientes do [!DNL Audience Manager]. Eles podem fornecer uma visão mais ampla do público-alvo do cliente em comparação com os clientes agregados do [!DNL Audience Manager].

| Métrica | Descrição |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Uma contagem de todos os dispositivos que interagiram com todos os clientes do [!DNL Audience Manager] no nível da plataforma durante o período de análise do relatório e que podem corresponder ao [!UICONTROL destination] escolhido. <br><br>Esta métrica é útil porque mostra:<ul><li>O tamanho do [!UICONTROL total addressable audience] que [!DNL Audience Manager] pode alcançar em um destino de direcionamento específico.</li><li>O tamanho do pool de perfis [!DNL Audience Manager] para uma plataforma de direcionamento e o tamanho de seus públicos.</li></ul> |

## Comparando [!UICONTROL Customer] e [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

Você não deve comparar as métricas [!UICONTROL Customer Addressable Audience] e [!UICONTROL Segment Addressable Audience] para determinar se uma é mais significativa do que a outra. Essas são métricas separadas, diferentes e independentes. Conforme descrito nas definições acima, cada um deles é derivado de diferentes conjuntos de dados. Diante disso, você deve evitar tirar conclusões se uma métrica for maior que a outra. Tudo o que você pode dizer ao comparar isso é que:

* [!UICONTROL Customer Addressable Audiences] é baseado em [!UICONTROL trait] realizações *para seus próprios dados primários*. Essa métrica fornece uma visualização ampla e abrangente da sua integração com um parceiro de dados.

* [!UICONTROL Segment Addressable Audiences] é baseado nas qualificações de segmento *para seus próprios dados primários, além de dados secundários e de terceiros*. Essa métrica fornece uma exibição granular e mais precisa do seu [!UICONTROL addressable audiences] em uma plataforma de direcionamento.

## Causas de Taxas de Correspondência Baixas para [!UICONTROL Addressable Audiences] {#low-match-rates}

Elementos comuns responsáveis por baixas taxas de correspondência [!UICONTROL Addressable Audience] ou discrepâncias em números relatados.

| Causa | Descrição |
|---|---|
| Tráfego móvel | A maioria das [!UICONTROL server-to-server] integrações depende de processos de sincronização facilitados por [!DNL cookies] de terceiros. No entanto, os ambientes móveis não usam [!DNL cookies] de terceiros. Como resultado, os números [!UICONTROL Addressable Audiences] podem parecer baixos em comparação ao tamanho [!UICONTROL segment]. <br><br>A partir de janeiro de 2018, você poderá ativar públicos-alvo móveis nos mesmos [!DNL Google] e [!DNL Adobe Advertising Cloud] destinos configurados para [!UICONTROL cookie-based] públicos-alvo. Embora isso signifique que você possa enviar [!UICONTROL segments] com associação combinada de [!DNL cookie] e Mobile ID para seus destinos [!DNL Google] e [!DNL Advertising Cloud], lembre-se de que [!UICONTROL Addressable Audiences] exibe somente a sobreposição entre [!DNL cookie] IDs e destinos. [!DNL Audience Manager] envia 100% dos públicos-alvo móveis para [!UICONTROL destinations], mas os públicos-alvo móveis não são medidos pela métrica [!UICONTROL Addressable Audience]. <br><br>**Observação**: por exemplo, use um [!UICONTROL segment] com uma população de 1.000.000. Se você mapear este [!UICONTROL segment] para um destino [!DNL Google] ou [!DNL Adobe Advertising Cloud], poderá ver um [!UICONTROL Addressable Audience] de 700.000 dispositivos e um [!UICONTROL Match Rate] de 70%. A associação de 700.000 consiste em [!DNL cookie] IDs que têm uma sincronização de ID com o [!UICONTROL destination]. Seu [!UICONTROL Addressable Audience] pode, na verdade, ser muito maior, porque IDs de dispositivos móveis endereçáveis não aparecem nessa métrica. |
| Tráfego [!DNL Safari] | [!DNL Safari] bloqueia [!DNL cookies] de terceiros. Isso impede que o [!DNL Audience Manager] sincronize IDs com o [!UICONTROL destination]. Com a introdução da [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), você pode esperar que a [!UICONTROL addressable audiences] não inclua usuários do [!DNL Safari]. |
| Impressões de mídia rastreada | Devido às práticas recomendadas do servidor de anúncios, as sincronizações de ID não são feitas nas tags de anúncio. Os clientes que fazem uma grande quantidade de publicidade externa não sincronizarão os usuários com integrações de terceiros nesses ambientes. Além disso, uma grande quantidade de dados de impressão de mídia coletados pode reduzir [!UICONTROL addressable audience] números. |

## Solução de problemas com [!UICONTROL Addressable Audiences] {#troubleshooting}

Além de exibir as taxas de correspondência, você também pode usar [!UICONTROL Addressable Audiences] como uma ferramenta de solução de problemas.

Por exemplo, digamos que você envie um segmento para um [!UICONTROL destination] e que [!UICONTROL destination] mostra números de relatórios baixos. Verificar os resultados de [!UICONTROL Addressable Audience] mostrará se é um problema técnico ou apenas um caso de taxas de correspondência baixas. Uma baixa taxa de correspondência mostra que o [!UICONTROL destination] não é muito bom para os segmentos selecionados. No entanto, uma diferença nos números [!UICONTROL total addressable audience] entre [!DNL Audience Manager] e [!UICONTROL destination] indica uma integração, sincronização ou outro problema técnico. Nesses casos, entre em contato com seu gerente de conta.
