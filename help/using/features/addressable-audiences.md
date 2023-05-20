---
description: Uma visão geral do recurso de Público-alvo endereçável e casos de uso.
keywords: DIL
seo-description: An overview of the Addressable Audience feature and use cases.
seo-title: Addressable Audiences
solution: Audience Manager
title: Públicos endereçáveis
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Match Rates
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
source-git-commit: cecdc0b0f43a146e11f7d23eb21a06146496ac2d
workflow-type: tm+mt
source-wordcount: '1813'
ht-degree: 1%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Uma visão geral do [!UICONTROL Addressable Audience] recursos e casos de uso.

## O que é uma [!UICONTROL Addressable Audience]? {#addressable-audience-description}

A variável [!UICONTROL Addressable Audiences] mostra a sobreposição entre os públicos que você vê em todas as propriedades, onde [!DNL Audience Manager] O coleta dados e o destino selecionado. Para ajudar você a entender esse conceito, consulte a ilustração abaixo. A sobreposição entre cada círculo representa os diferentes tipos de públicos endereçáveis.

![](assets/addressableAudienceVenn.png)


| Métrica | Descrição |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] para um [!UICONTROL Destination] | Uma contagem de todos os dispositivos que interagiram com todos [!DNL Audience Manager] clientes no nível da plataforma durante o período de análise do relatório e que podem corresponder ao [!UICONTROL destination]. <br><br>Essa métrica é útil porque mostra: <ul><li>O tamanho do total [!UICONTROL addressable audience] que [!DNL Audience Manager] podem alcançar um direcionamento específico [!UICONTROL destination].</li><li>Quão grande é a [!DNL Audience Manager] o pool de perfis é para uma plataforma de direcionamento e o tamanho de seus públicos-alvo.</li></ul> |
| [!UICONTROL Customer Total Audience] | Uma contagem de dispositivos que realizaram uma [!UICONTROL rule-based trait] em suas propriedades ou em um [!UICONTROL onboarded trait] dos arquivos offline durante a janela de retrospectiva. |
| [!UICONTROL Customer Addressable Audience] | Uma contagem de sobreposição de dispositivos que realizaram uma [!UICONTROL rule-based trait] ou um [!UICONTROL onboarded trait] durante a janela de retrospectiva e os dispositivos com os quais temos uma sincronização de ID [!UICONTROL destination] independentemente do tempo de sincronização.<br><br>Essa métrica representa dispositivos que:<ul><li>Ter realizado um [!UICONTROL rule-based] ou um [!UICONTROL onboarded trait] durante a janela de retrospectiva `AND`</li><li>Ter uma sincronização de ID com o escolhido [!UICONTROL destination] independentemente do tempo de sincronização.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] expresso como uma porcentagem. |
| [!UICONTROL Total Segment Population] | Uma contagem de todos os dispositivos que eram membros de sua [!UICONTROL segment] durante o período de análise do relatório. |
| [!UICONTROL Segment Addressable Audience] | O número de usuários que pertenceram a [!UICONTROL segment] durante o período de análise do relatório e tiver uma sincronização de ID ativa no site. [!UICONTROL Segments] pode incluir seus próprios dados primários e dados secundários e de terceiros, por meio de [!UICONTROL traits] adquirido na [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Dica: Quando usada com o período retroativo de um dia, essa métrica pode ajudar você a entender o estado atual do [!UICONTROL segments]. Isso ocorre porque a variável [!UICONTROL Segment Addressable Audience] representa os usuários que permaneceram em uma [!UICONTROL segment] durante o dia anterior. Combinar esta situação com o fato de que [!DNL Audience Manager] atualiza [!UICONTROL Addressable Audiences] diariamente, a combinação dessa métrica com o período de lookback fornece o instantâneo mais atualizado do seu [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] expresso como uma porcentagem. |

## [!UICONTROL Addressable Audiences] Interface {#addressable-audience-interface}

A variável [!UICONTROL Addressable Audience] esse conceito abstrato se transforma em dados quantificáveis. Entrada [!DNL Audience Manager]Além disso, esse recurso exibe a sobreposição de público-alvo com visualizações de dados que fornecem informações instantâneas junto com dados numéricos em formato de tabela.

[!UICONTROL Addressable Audiences] está localizado em **[!UICONTROL Audience Data > Destinations]**. Selecionar **[!UICONTROL Integrated Platforms > Device-Based]** para ver as métricas de públicos-alvo endereçáveis.

![](assets/addressable-audiences-landing.png)

As três métricas que você pode ver na [!UICONTROL Addressable Audiences] A página de aterrissagem representa:

| Métrica | Descrição |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Essa métrica representa o [!UICONTROL Customer Addressable Audience] (descrito no quadro acima) *nos últimos 30 dias.* |
| **[!UICONTROL Match Rate]** | Essa métrica representa o [!UICONTROL Addressable Audience Match Rate] (descrito no quadro acima) *nos últimos 30 dias*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Uma contagem de todos os dispositivos que interagiram com todos [!DNL Audience Manager] clientes no nível da plataforma durante o período de análise do relatório e que podem ser combinados com esse [!UICONTROL destination]. Consulte [Métricas de nível de plataforma](/help/using/features/addressable-audiences.md#platform-level-metrics) para obter mais informações. |

Clique no nome de um [!UICONTROL server-to-server destination] para visualizar os dados do público-alvo endereçável. Observe que esse recurso retorna dados para [!UICONTROL server-to-server destinations] somente o acesso e exige permissões de administrador.

![](assets/addressableAudiences.png)

A análise desses dados pode ajudá-lo com:

* **Previsão e planejamento:** [!UICONTROL Segment Addressable Audience] Os dados do fornecem mais granularidade aos segmentos que você planeja enviar para um destino para direcionamento e ativação de público-alvo.

* **Revisões de desempenho:** A variável [!UICONTROL Addressable Audiences] O recurso também é uma ferramenta de solução de problemas. Ele permite analisar o desempenho da campanha, entender seu alcance e cruzar com parceiros de direcionamento/ativação se você não encontrar os resultados esperados.

### Prospecção com dados de terceiros e implicações para taxas de correspondência

Antes de comprar dados de terceiros para aquisição de público-alvo, os clientes podem validar a sobreposição com outros provedores de dados. Isso pode ajudá-lo a tomar uma decisão informada antes de comprar novos dados. As sincronizações de ID para dados de terceiros comprados dependem não apenas da sobreposição de seus dados, mas também das pegadas de provedores de terceiros com todos os outros [!DNL Audience Manager] clientes. Seu [!DNL Adobe] O consultor da pode ajudar você a identificar outras fontes de dados relevantes para otimizar as campanhas de prospecção.

### Usuários móveis e taxas de correspondência

Há lacunas ao tentar se conectar [!DNL Safari] ou usuários de aplicativos móveis onde não há terceiros [!DNL cookies] presente. Isso dificulta a sincronização de usuários com alguns parceiros, pois somente esses [!DNL Adobe] IDs para terceiros sincronizados [!DNL cookies] são fornecidos nos logs de delivery de mídia. Essa é uma razão pela qual você pode ver [baixas taxas de correspondência](../features/addressable-audiences.md#low-match-rates) para seu [!UICONTROL destinations].

## Intervalos de datas em [!UICONTROL Addressable Audiences] e [!UICONTROL Destinations] {#date-ranges}

Leia as seções abaixo para obter intervalos de datas disponíveis e saber como os dados envelhecem em cada intervalo nos relatórios para um [!UICONTROL Addressable Audience] ou [!UICONTROL Destination].

## Intervalos de datas e fusos horários disponíveis {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Relatórios para o seu [!UICONTROL Addressable Audiences] e [Destinos](../features/destinations/destinations.md) usar os mesmos intervalos de intervalo de datas. As opções de intervalo de datas incluem:

* [!UICONTROL Last 1 Day] (Esse intervalo é executado da meia-noite para a meia-noite do período de 24 horas anterior. Não é uma métrica em tempo real ou atual.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Todas as datas e intervalos de datas estão definidos no [!DNL UTC] fuso horário. Consulte [Fusos horários em Audience Manager](../reference/aam-time-zones.md).

## Dados em intervalos de datas {#date-range-intervals}

A variável [!UICONTROL Addressable Audience] e [!UICONTROL Destination] as métricas retornam uma contagem de usuários únicos para o intervalo selecionado. Por exemplo, um visitante é contado apenas uma vez, mesmo que venha ao site várias vezes. A primeira visita é a visita única e é registrada. As visitas subsequentes são de retorno e não são contadas por não serem exclusivas.

Intervalos de datas contêm dados para o intervalo de tempo selecionado ou anterior. E os dados envelhecem de cada intervalo de relatório conforme o tempo passa. Por exemplo, vamos supor que você veja 2 visitantes depois de escolher a variável [!UICONTROL Last 30 Days] opção. Nos relatórios, esses visitantes:

* *Será* incluídos nos resultados retornados pelos intervalos de tempo mais longos (60 dias, 90 dias e Duração).
* *Não será* incluídos nos intervalos mais curtos que precedem o [!UICONTROL Last 30 Day] (Atual, 7 dias e 14 dias).

E, no dia 31, esses visitantes só aparecem nos dias 60, 90 e [!UICONTROL Lifetime] resultados. Eles envelheceram fora do intervalo de 30 dias. Os visitantes não envelhecem fora do [!UICONTROL Lifetime] intervalo.

## [!UICONTROL Addressable Audiences] Métricas {#addressable-audience-metrics}

Esta seção descreve os tipos de métricas fornecidas pelo [!UICONTROL Addressable Audiences].

### Métricas no nível do cliente {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Essas métricas retornam dados para características realizadas quando os visitantes chegam ao site ou quando você envia arquivos de dados de entrada para o [!DNL Audience Manager]. Essas métricas fornecem uma visualização abrangente do tamanho do público-alvo da sua conta.

| Métrica | Descrição |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Uma contagem de sobreposição de dispositivos que realizaram uma [!UICONTROL rule-based trait] ou um [!UICONTROL onboarded trait] durante a janela de retrospectiva e os dispositivos, temos uma sincronização de ID com o destino escolhido, independentemente do tempo de sincronização.<br><br>Essa métrica representa dispositivos que:<ul><li>Ter realizado um [!UICONTROL rule-based] ou um [!UICONTROL onboarded trait] durante a janela de retrospectiva `AND`</li><li>Ter uma sincronização de ID com o escolhido [!UICONTROL destination] independentemente do tempo de sincronização.</li></ul> |
| [!UICONTROL Customer Total Audience] | Uma contagem de dispositivos que realizaram uma [!UICONTROL rule-based trait] em suas propriedades ou em um [!UICONTROL onboarded trait] dos arquivos offline durante a janela de retrospectiva. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] expresso como uma porcentagem. |

### Métricas de correspondência de nível de segmento {#segment-level-metrics}

Essas métricas retornam dados sobre [!UICONTROL segment] associação. Eles ajudam a fornecer uma visualização mais granular e precisa do tamanho do público-alvo para cada um dos seus [!UICONTROL segments].

>[!NOTE]
>
>A forma como a janela de retrospectiva é aplicada na [!UICONTROL segment] é diferente do nível do cliente. Os visitantes podem chegar ao site e realizar uma [!UICONTROL trait] 10 dias atrás, e eles poderiam se qualificar para um [!UICONTROL segment] desde então e saiu do [!UICONTROL segment] 2 dias atrás. Quando a retrospectiva de 7 dias for aplicada, esses visitantes serão contados no [!UICONTROL segment] mas não no nível do cliente.

| Métrica | Descrição |
|---|---|
| [!UICONTROL Segment Addressable Audience] | O número de usuários que pertenceram a [!UICONTROL segment] durante o período de análise do relatório e tiver uma sincronização de ID ativa no site. Os segmentos podem incluir seus próprios dados primários e dados secundários e de terceiros, por meio de [!UICONTROL traits] adquirido na [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Dica: Quando usada com o período retroativo de um dia, essa métrica pode ajudar você a entender o estado atual do [!UICONTROL segments]. Isso ocorre porque a variável [!UICONTROL Segment Addressable Audience] representa os usuários que permaneceram em uma [!UICONTROL segment] durante o dia anterior. Combinar esta situação com o fato de que [!DNL Audience Manager] atualiza [!UICONTROL Addressable Audiences] diariamente, a combinação dessa métrica com o período de lookback fornece o instantâneo mais atualizado do seu [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Uma contagem de todos os dispositivos que eram membros de sua [!UICONTROL segment] durante o período de análise do relatório. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] expresso como uma porcentagem. |

### Métricas de nível de plataforma {#platform-level-metrics}

Essa métrica retorna dados sobre atividades coletadas em todos os [!DNL Audience Manager] clientes. Eles podem fornecer uma visão mais ampla do público-alvo do cliente em comparação com o [!DNL Audience Manager] clientes.

| Métrica | Descrição |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Uma contagem de todos os dispositivos que interagiram com todos [!DNL Audience Manager] clientes no nível da plataforma durante o período de análise do relatório e que podem corresponder ao [!UICONTROL destination]. <br><br>Essa métrica é útil porque mostra:<ul><li>O tamanho do [!UICONTROL total addressable audience] que [!DNL Audience Manager] podem alcançar um destino de direcionamento específico.</li><li>Quão grande é a [!DNL Audience Manager] o pool de perfis é para uma plataforma de direcionamento e o tamanho de seus públicos-alvo.</li></ul> |

## Comparação [!UICONTROL Customer] e [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

Você não deve comparar as [!UICONTROL Customer Addressable Audience] e [!UICONTROL Segment Addressable Audience] para determinar se uma é mais significativa do que a outra. Essas são métricas separadas, diferentes e independentes. Conforme descrito nas definições acima, cada um deles é derivado de diferentes conjuntos de dados. Diante disso, você deve evitar tirar conclusões se uma métrica for maior que a outra. Tudo o que você pode dizer ao comparar isso é que:

* [!UICONTROL Customer Addressable Audiences] é baseado em [!UICONTROL trait] realizações *para seus próprios dados primários*. Essa métrica fornece uma visualização ampla e abrangente da sua integração com um parceiro de dados.

* [!UICONTROL Segment Addressable Audiences] é baseado nas qualificações do segmento *para seus próprios dados primários, além de dados secundários e de terceiros*. Essa métrica fornece uma visualização granular e mais precisa dos [!UICONTROL addressable audiences] em uma plataforma de direcionamento.

## Causas de taxas de correspondência baixas para [!UICONTROL Addressable Audiences] {#low-match-rates}

Elementos comuns responsáveis por baixa [!UICONTROL Addressable Audience] taxas de correspondência ou discrepâncias em números relatados.

| Causa | Descrição |
|---|---|
| Tráfego móvel | Mais [!UICONTROL server-to-server] integrações dependem de processos de sincronização facilitados por terceiros [!DNL cookies]. No entanto, os ambientes móveis não usam serviços de terceiros [!DNL cookies]. Como resultado, seu [!UICONTROL Addressable Audiences] Os números podem parecer baixos em comparação com [!UICONTROL segment] tamanho. <br><br>A partir de janeiro de 2018, você poderá ativar públicos-alvo móveis na mesma [!DNL Google] e [!DNL Adobe Advertising Cloud] destinos configurados para [!UICONTROL cookie-based] públicos-alvo. Embora isso signifique que você pode enviar [!UICONTROL segments] com combinado [!DNL cookie] e a associação da ID móvel à sua [!DNL Google] e [!DNL Advertising Cloud] destinos, lembre-se de que [!UICONTROL Addressable Audiences] exibir somente a sobreposição entre [!DNL cookie] IDs e destinos [!DNL Audience Manager] envia 100% dos públicos-alvo móveis para [!UICONTROL destinations], mas os públicos-alvo móveis não são medidos pelo [!UICONTROL Addressable Audience] métrica. <br><br>**Nota**: por exemplo, use uma [!UICONTROL segment] com uma população de 1.000.000. Se você mapear isto [!UICONTROL segment] para um [!DNL Google] ou [!DNL Adobe Advertising Cloud] destino, você poderá ver um [!UICONTROL Addressable Audience] de 700 mil dispositivos e uma [!UICONTROL Match Rate] de 70%. Os 700 000 membros consistem em [!DNL cookie] IDs que têm uma sincronização de ID com o [!UICONTROL destination]. Seu [!UICONTROL Addressable Audience] pode, na verdade, ser muito maior, porque as IDs móveis endereçáveis não aparecem nessa métrica. |
| [!DNL Safari] Tráfego | [!DNL Safari] bloqueia terceiros [!DNL cookies]. Isso evita [!DNL Audience Manager] da sincronização de IDs com o [!UICONTROL destination]. Com a introdução do [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), você pode esperar seu [!UICONTROL addressable audiences] não incluir [!DNL Safari] usuários. |
| Impressões de mídia rastreada | Devido às práticas recomendadas do servidor de anúncios, as sincronizações de ID não são feitas nas tags de anúncio. Os clientes que fazem uma grande quantidade de publicidade externa não sincronizarão os usuários com integrações de terceiros nesses ambientes. Além disso, uma grande quantidade de dados de impressão de mídia coletados pode reduzir [!UICONTROL addressable audience] números. |

## Solução de problemas com o [!UICONTROL Addressable Audiences] {#troubleshooting}

Além de superar as taxas de correspondência, você também pode usar [!UICONTROL Addressable Audiences] como uma ferramenta de solução de problemas.

Por exemplo, digamos que você envie um segmento para um [!UICONTROL destination] e que [!UICONTROL destination] mostra números de relatórios baixos. Verificar a [!UICONTROL Addressable Audience] os resultados mostrarão se é um problema técnico ou apenas um caso de taxas de correspondência baixas. Uma baixa taxa de correspondência mostra o [!UICONTROL destination] O não é muito bom para os segmentos selecionados. No entanto, uma diferença na [!UICONTROL total addressable audience] números entre [!DNL Audience Manager] e a variável [!UICONTROL destination] indica uma integração, sincronização ou outro problema técnico. Nesses casos, entre em contato com seu gerente de conta.
