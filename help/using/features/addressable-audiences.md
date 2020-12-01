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

Uma visão geral do recurso [!UICONTROL Addressable Audience] e dos casos de uso.

## O que é uma [!UICONTROL Addressable Audience]? {#addressable-audience-description}

O recurso [!UICONTROL Addressable Audiences] mostra a sobreposição entre as audiências que você vê em todas as suas propriedades, onde [!DNL Audience Manager] coleta dados e o destino selecionado. Para ajudá-lo a entender esse conceito, dê uma olhada na ilustração abaixo. A sobreposição entre cada círculo representa os diferentes tipos de audiências endereçáveis.

![](assets/addressableAudienceVenn.png)


| Métrica | Descrição |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] para um  [!UICONTROL Destination] | Uma contagem de todos os dispositivos que interagiram com todos os [!DNL Audience Manager] clientes no nível da plataforma durante o período de análise do relatório e que podem ser combinados com o [!UICONTROL destination] escolhido. <br><br>Essa métrica é útil porque mostra: <ul><li>O tamanho do total [!UICONTROL addressable audience] que [!DNL Audience Manager] pode atingir em um direcionamento específico [!UICONTROL destination].</li><li>O tamanho do pool de perfis [!DNL Audience Manager] é para uma plataforma de definição de metas e o tamanho de suas audiências.</li></ul> |
| [!UICONTROL Customer Total Audience] | Uma contagem de dispositivos que perceberam [!UICONTROL rule-based trait] em suas propriedades ou um [!UICONTROL onboarded trait] em seus arquivos offline durante a janela de retrospectiva. |
| [!UICONTROL Addressable Audience Match Rate] | Uma contagem de sobreposições de dispositivos que perceberam [!UICONTROL rule-based trait] ou [!UICONTROL onboarded trait] durante a janela de retrospectiva e os dispositivos que temos uma sincronização de ID com o [!UICONTROL destination] escolhido, independentemente do tempo de sincronização.<br><br>Essa métrica representa dispositivos que:<ul><li>Percebemos que [!UICONTROL rule-based] ou [!UICONTROL onboarded trait] durante a janela de retrospectiva `AND`</li><li>Tenha uma sincronização de ID com o [!UICONTROL destination] escolhido, independentemente do tempo de sincronização.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] / [!UICONTROL Customer Total Audience] expresso em percentagem. |
| [!UICONTROL Total Segment Population] | Uma contagem de todos os dispositivos que eram membros de seu [!UICONTROL segment] durante o período de análise do relatório. |
| [!UICONTROL Segment Addressable Audience] | O número de usuários que pertenceram a [!UICONTROL segment] durante o período de análise do relatório e que têm uma sincronização de ID ativa no site. [!UICONTROL Segments] pode incluir seus próprios dados primários e dados de terceiros e segundos, por meio dos  [!UICONTROL traits] adquiridos no  [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Dica: Quando usada com o período de análise de 1 dia, essa métrica pode ajudá-lo a entender o estado atual do seu  [!UICONTROL segments]. Isso ocorre porque a métrica [!UICONTROL Segment Addressable Audience] representa os usuários que permaneceram em [!UICONTROL segment] no dia anterior. Combine isso com o fato de que [!DNL Audience Manager] atualiza [!UICONTROL Addressable Audiences] diariamente, combinando essa métrica e o período de pesquisa fornece o instantâneo mais atualizado de seu [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] / [!UICONTROL Total Segment Population] expresso em percentagem. |

## [!UICONTROL Addressable Audiences] Interface {#addressable-audience-interface}

O recurso [!UICONTROL Addressable Audience] transforma esse conceito abstrato em dados quantificáveis. Em [!DNL Audience Manager], esse recurso exibe a sobreposição de audiência com visualizações de dados que fornecem informações instantâneas juntamente com dados numéricos em forma de tabela.

[!UICONTROL Addressable Audiences] está localizado em  **[!UICONTROL Audience Data > Destinations]**. Selecione **[!UICONTROL Integrated Platforms > Device-Based]** para ver métricas de audiências endereçáveis.

![](assets/addressable-audiences-landing.png)

As três métricas que você pode ver na landing page [!UICONTROL Addressable Audiences] representam:

| Métrica | Descrição |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Essa métrica representa [!UICONTROL Customer Addressable Audience] (descrita na tabela acima) *nos últimos 30 dias.* |
| **[!UICONTROL Match Rate]** | Essa métrica representa [!UICONTROL Addressable Audience Match Rate] (descrita na tabela acima) *nos últimos 30 dias*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Uma contagem de todos os dispositivos que interagiram com todos os [!DNL Audience Manager] clientes no nível da plataforma durante o período de análise do relatório e que podem ser combinados com este [!UICONTROL destination]. Consulte [Métricas de nível de plataforma](/help/using/features/addressable-audiences.md#platform-level-metrics) para obter mais informações. |

Clique no nome de [!UICONTROL server-to-server destination] para visualização dos dados de audiência endereçáveis. Observe que esse recurso retorna dados somente para [!UICONTROL server-to-server destinations] e o acesso requer permissões de administrador.

![](assets/addressableAudiences.png)

A revisão desses dados pode ajudá-lo com:

* **Previsão e planejamento:** [!UICONTROL Segment Addressable Audience] os dados fornecem mais granularidade aos segmentos que você está planejando enviar para um destino para direcionamento de audiência e ativação.

* **Análises de desempenho:** O  [!UICONTROL Addressable Audiences] recurso também é uma ferramenta de solução de problemas. Ele permite que você analise o desempenho da campanha, entenda o alcance da campanha e faça uma verificação cruzada com parceiros de definição de metas/ativações se você não encontrar os resultados esperados.

### Prospecção com dados de terceiros e implicações para taxas de correspondência

Antes de adquirir dados de terceiros para aquisição de audiências, os clientes podem validar a sobreposição com outros provedores de dados. Isso pode ajudá-lo a tomar uma decisão informada antes de comprar novos dados. As sincronizações de ID para dados de terceiros adquiridos dependem não apenas da sobreposição de seus dados, mas também de pegadas de provedores de terceiros com todos os outros [!DNL Audience Manager] clientes. Seu consultor [!DNL Adobe] pode ajudá-lo a identificar fontes de dados relevantes adicionais para otimizar campanhas de prospecção.

### Usuários móveis e taxas de correspondência

Há lacunas ao tentar conectar [!DNL Safari] ou usuários de aplicativos móveis nos quais não há [!DNL cookies] terceiros presentes. Isso dificulta a sincronização de usuários com alguns parceiros, pois apenas as [!DNL Adobe] IDs de terceiros sincronizadas [!DNL cookies] são fornecidas nos logs do delivery de mídia. Esse é um motivo pelo qual você pode ver [taxas de correspondência baixas](../features/addressable-audiences.md#low-match-rates) para seu [!UICONTROL destinations].

## Intervalos de datas em [!UICONTROL Addressable Audiences] e [!UICONTROL Destinations] {#date-ranges}

Leia as seções abaixo para ver os intervalos de datas disponíveis e como os dados expiram em cada intervalo nos relatórios de [!UICONTROL Addressable Audience] ou [!UICONTROL Destination].

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

Todas as datas e intervalos de datas são definidos no fuso horário [!DNL UTC]. Consulte [Fusos Horários em Audience Manager](../reference/aam-time-zones.md).

## Dados em Intervalos de Intervalo de Datas {#date-range-intervals}

As métricas [!UICONTROL Addressable Audience] e [!UICONTROL Destination] retornam uma contagem de usuários únicos para o intervalo de tempo selecionado. Por exemplo, um visitante é contado apenas uma vez, mesmo se ele vier ao seu site várias vezes. A primeira visita é a única e é registrada. As visitas subsequentes são visitas recorrentes e não são contadas porque não são exclusivas.

Os intervalos de datas contêm dados para o intervalo de tempo selecionado ou anterior. Além disso, os dados envelhecem fora de cada intervalo de relatório conforme o tempo passa. Por exemplo, vamos supor que você veja 2 visitantes depois de escolher a opção [!UICONTROL Last 30 Days]. Nos relatórios, estes visitantes:

* *Serão* incluídos nos resultados retornados pelos intervalos de tempo mais longos (60 dias, 90 dias e Duração).
* *Não será* incluído nos intervalos mais curtos que precedem a  [!UICONTROL Last 30 Day] opção (Atual, 7 dias e 14 dias).

E, no dia 31, esses visitantes só aparecem nos resultados de 60 dias, 90 dias e [!UICONTROL Lifetime]. Eles envelheceram fora do intervalo de 30 dias. Os visitantes não envelhecem fora do intervalo [!UICONTROL Lifetime].

## [!UICONTROL Addressable Audiences] Métricas {#addressable-audience-metrics}

Esta seção descreve os tipos de métricas fornecidas por [!UICONTROL Addressable Audiences].

### Métricas no nível do cliente {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Essas métricas retornam dados de características realizadas quando os visitantes chegam ao seu site ou quando você envia arquivos de dados de entrada para [!DNL Audience Manager]. Essas métricas fornecem uma visualização abrangente do tamanho da audiência para sua conta.

| Métrica | Descrição |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Uma contagem de sobreposições de dispositivos que perceberam [!UICONTROL rule-based trait] ou [!UICONTROL onboarded trait] durante a janela de retrospectiva e os dispositivos que temos uma sincronização de ID com o destino escolhido, independentemente do tempo de sincronização.<br><br>Essa métrica representa dispositivos que:<ul><li>Percebemos que [!UICONTROL rule-based] ou [!UICONTROL onboarded trait] durante a janela de retrospectiva `AND`</li><li>Tenha uma sincronização de ID com o [!UICONTROL destination] escolhido, independentemente do tempo de sincronização.</li></ul> |
| [!UICONTROL Customer Total Audience] | Uma contagem de dispositivos que perceberam [!UICONTROL rule-based trait] em suas propriedades ou um [!UICONTROL onboarded trait] em seus arquivos offline durante a janela de retrospectiva. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] / [!UICONTROL Customer Total Audience] expresso em percentagem. |

### Métricas de correspondência no nível do segmento {#segment-level-metrics}

Essas métricas retornam dados em [!UICONTROL segment] associação. Eles ajudam a fornecer uma visualização mais granular e precisa do tamanho da audiência para cada [!UICONTROL segments].

>[!NOTE]
>
>A forma como a janela de retrospectiva é aplicada no nível [!UICONTROL segment] é diferente daquela no nível do cliente. Os visitantes podem vir ao site e perceber há [!UICONTROL trait] 10 dias, e podem se qualificar para [!UICONTROL segment] desde então e sair do [!UICONTROL segment] há 2 dias. Quando a análise de sete dias for aplicada, esses visitantes serão contados no nível [!UICONTROL segment], mas não no nível do cliente.

| Métrica | Descrição |
|---|---|
| [!UICONTROL Segment Addressable Audience] | O número de usuários que pertenceram a [!UICONTROL segment] durante o período de análise do relatório e que têm uma sincronização de ID ativa no site. Os segmentos podem incluir seus próprios dados primários e dados de terceiros e de terceiros, por meio de [!UICONTROL traits] adquiridos no [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Dica: Quando usada com o período de análise de 1 dia, essa métrica pode ajudá-lo a entender o estado atual do seu  [!UICONTROL segments]. Isso ocorre porque a métrica [!UICONTROL Segment Addressable Audience] representa os usuários que permaneceram em [!UICONTROL segment] no dia anterior. Combine isso com o fato de que [!DNL Audience Manager] atualiza [!UICONTROL Addressable Audiences] diariamente, combinando essa métrica e o período de pesquisa fornece o instantâneo mais atualizado de seu [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Uma contagem de todos os dispositivos que eram membros de seu [!UICONTROL segment] durante o período de análise do relatório. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] / [!UICONTROL Total Segment Population] expresso em percentagem. |

### Métricas de nível de plataforma {#platform-level-metrics}

Essa métrica retorna dados em atividades coletados em todos os [!DNL Audience Manager] clientes. Eles podem fornecer uma visualização mais ampla da audiência do cliente em comparação aos clientes agregados [!DNL Audience Manager].

| Métrica | Descrição |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Uma contagem de todos os dispositivos que interagiram com todos os [!DNL Audience Manager] clientes no nível da plataforma durante o período de análise do relatório e que podem ser combinados com o [!UICONTROL destination] escolhido. <br><br>Essa métrica é útil porque mostra:<ul><li>O tamanho de [!UICONTROL total addressable audience] que [!DNL Audience Manager] pode alcançar em um destino de definição de metas específico.</li><li>O tamanho do pool de perfis [!DNL Audience Manager] é para uma plataforma de definição de metas e o tamanho de suas audiências.</li></ul> |

## Comparar [!UICONTROL Customer] e [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

Você não deve comparar as métricas [!UICONTROL Customer Addressable Audience] e [!UICONTROL Segment Addressable Audience] para determinar se uma é mais significativa do que a outra. Essas são métricas separadas, diferentes e independentes. Conforme descrito nas definições acima, cada uma destas é derivada de diferentes conjuntos de dados. Considerando isso, você deve evitar tirar conclusões se uma métrica for maior que a outra. Tudo o que você pode dizer ao comparar isso é que:

* [!UICONTROL Customer Addressable Audiences] é baseado em  [!UICONTROL trait] realizações  *para seus próprios dados* primários. Essa métrica fornece uma visualização abrangente e abrangente da sua integração com um parceiro de dados.

* [!UICONTROL Segment Addressable Audiences] é baseado em qualificações de segmento  *para seus próprios dados primários, além de dados* secundários e de terceiros. Essa métrica fornece uma visualização granular e mais precisa do [!UICONTROL addressable audiences] em uma plataforma de definição de metas.

## Causas de taxas de correspondência baixas para [!UICONTROL Addressable Audiences] {#low-match-rates}

Elementos comuns responsáveis por taxas de correspondência baixas ou discrepâncias nos números relatados.[!UICONTROL Addressable Audience]

| Causa | Descrição |
|---|---|
| Tráfego móvel | A maioria das integrações [!UICONTROL server-to-server] depende de processos de sincronização facilitados por [!DNL cookies] terceiros. No entanto, ambientes móveis não usam [!DNL cookies] de terceiros. Como resultado, seus números de [!UICONTROL Addressable Audiences] podem parecer baixos quando comparados com o tamanho de [!UICONTROL segment]. <br><br>A partir de janeiro de 2018, você poderá ativar audiências móveis nos mesmos  [!DNL Google] e  [!DNL Adobe Advertising Cloud] destinos configurados para  [!UICONTROL cookie-based] audiência. Embora isso signifique que você pode enviar [!UICONTROL segments] com a associação combinada [!DNL cookie] e ID móvel para seus destinos [!DNL Google] e [!DNL Advertising Cloud], lembre-se de que [!UICONTROL Addressable Audiences] só exibe a sobreposição entre [!DNL cookie] IDs e destinos. [!DNL Audience Manager] envia 100% das audiências móveis para  [!UICONTROL destinations], mas as audiências móveis não são medidas pela  [!UICONTROL Addressable Audience] métrica. <br><br>**Observação**: Por exemplo, pegue uma amostra  [!UICONTROL segment] com uma população de 1.000.000 pessoas. Se mapear [!UICONTROL segment] para um destino [!DNL Google] ou [!DNL Adobe Advertising Cloud], você poderá ver um [!UICONTROL Addressable Audience] de 700.000 dispositivos e um [!UICONTROL Match Rate] de 70%. A associação de 700.000 consiste em [!DNL cookie] IDs que têm uma sincronização de ID com [!UICONTROL destination]. Seu [!UICONTROL Addressable Audience] pode, na verdade, ser muito maior, pois as IDs móveis endereçáveis não aparecem nessa métrica. |
| [!DNL Safari] Tráfego | [!DNL Safari] bloqueia terceiros  [!DNL cookies]. Isso impede que [!DNL Audience Manager] sincronize IDs com [!UICONTROL destination]. Com a introdução de [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), você pode esperar que [!UICONTROL addressable audiences] não inclua [!DNL Safari] usuários. |
| Impressões de mídia rastreadas | Devido às práticas recomendadas do servidor de publicidade, as sincronizações de ID não são feitas em tags de publicidade. Os clientes que fazem uma grande quantidade de anúncios externos não sincronizarão os usuários às integrações de terceiros nesses ambientes. Além disso, uma grande quantidade de dados coletados de impressão de mídia pode reduzir os números [!UICONTROL addressable audience]. |

## Solução de problemas com [!UICONTROL Addressable Audiences] {#troubleshooting}

Além de encontrar as taxas de correspondência, você também pode usar [!UICONTROL Addressable Audiences] como uma ferramenta de solução de problemas.

Por exemplo, digamos que você envie um segmento para [!UICONTROL destination] e que [!UICONTROL destination] mostra números de relatórios baixos. Marcar os resultados de [!UICONTROL Addressable Audience] mostrará se isso é um problema técnico ou apenas um caso de taxas de correspondência baixas. Uma taxa de correspondência baixa mostra que seu [!UICONTROL destination] não é tão bom para seus segmentos selecionados. No entanto, uma diferença nos números [!UICONTROL total addressable audience] entre [!DNL Audience Manager] e [!UICONTROL destination] indica um problema de integração, sincronização ou outro problema técnico. Nesses casos, entre em contato com seu gerente de conta.
