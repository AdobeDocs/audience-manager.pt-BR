---
description: Uma visão geral do recurso Audiência endereçável e dos casos de uso.
keywords: DIL
seo-description: Uma visão geral do recurso Audiência endereçável e dos casos de uso.
seo-title: Públicos-alvo endereçáveis
solution: Audience Manager
title: Públicos-alvo endereçáveis
topic: DIL API
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '2059'
ht-degree: 0%

---


# Audiência endereçável {#addressable-audiences}

Uma visão geral do [!UICONTROL Addressable Audience] recurso e dos casos de uso.

## O que é uma Audiência endereçável? {#addressable-audience-description}

O [!UICONTROL Addressable Audiences] recurso mostra a sobreposição entre as audiências que você vê em todas as suas propriedades, onde [!DNL Audience Manager] coleta dados e o destino selecionado. Para ajudá-lo a entender esse conceito, dê uma olhada na ilustração abaixo. A sobreposição entre cada círculo representa os diferentes tipos de audiências endereçáveis.

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
   <td colname="col1"> <p> <b>Audience Manager endereçável</b> </p> </td> 
   <td colname="col2"> <p>Uma contagem de todos os dispositivos que interagiram com todos os clientes do Audience Manager no nível da plataforma durante o período de análise do relatório e que podem ser combinados com o destino escolhido. </p> <p>Essa métrica é útil porque mostra: </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> O tamanho da audiência endereçável total que o <span class="keyword"> Audience Manager</span> pode atingir em um destino de direcionamento específico. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">O tamanho do pool de perfis <span class="keyword"> Audience Manager</span> para uma plataforma de definição de metas e o tamanho de suas audiências. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audiência total do cliente</b> </p> </td> 
   <td colname="col2"> <p>Uma contagem de dispositivos que perceberam uma característica baseada em regras em suas propriedades ou uma característica integrada de seus arquivos offline durante a janela de retrospectiva. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taxa de correspondência de Audiência endereçável</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Uma contagem de sobreposição de dispositivos que perceberam uma característica baseada em regras ou uma característica integrada durante a janela de retrospectiva e dispositivos que possuem uma sincronização de ID com o destino escolhido independentemente do tempo de sincronização. </p> 
    </draft-comment> <p>Essa métrica representa dispositivos que: 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Tenham percebido uma característica baseada em regras ou integrada durante a janela de retrospectiva <b>E</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Ter uma sincronização de ID com o destino escolhido, independentemente do tempo de sincronização. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taxa de correspondência do cliente</b> </p> </td> 
   <td colname="col2"> <p>Audiência endereçável do cliente /Audiência total do cliente expressa como %. </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <b>População total de segmentos</b> </p> </td> 
   <td colname="col2"> <p>Uma contagem de todos os dispositivos que eram membros do seu segmento durante o período de análise do relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audiência endereçável do segmento</b> </p> </td> 
   <td colname="col2"> <p>O número de usuários que pertenceram ao segmento durante o período de análise do relatório e que têm uma sincronização de ID ativa no site. Os segmentos podem incluir seus próprios dados primários e dados de terceiros e de terceiros, por meio de características adquiridas no <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>Dica: Quando usada com o período de análise de 1 dia, essa métrica pode ajudá-lo a entender o estado atual de seus segmentos. Isso ocorre porque a <span class="wintitle"> métrica Audiência</span> endereçável de segmento representa os usuários que permaneceram em um segmento durante o dia anterior. Combine isso com o fato de que o Audience Manager <span class="keyword"> atualiza</span> Audiências <span class="wintitle"></span> endereçáveis diariamente, combinando essa métrica e o período de pesquisa fornece o instantâneo mais atualizado de seus segmentos. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taxa de correspondência do segmento</b> </p> </td> 
   <td colname="col2"> <p>Audiência endereçável do segmento /População total do segmento expressa como %. </p> </td> 
  </tr>  
 </tbody> 
</table>

## Interface de Audiência endereçável {#addressable-audience-interface}

O [!UICONTROL Addressable Audience] recurso transforma esse conceito abstrato em dados quantificáveis. Em [!DNL Audience Manager]geral, esse recurso exibe sobreposição de audiência com visualizações de dados que fornecem informações instantâneas juntamente com dados numéricos em forma de tabela.

[!UICONTROL Addressable Audiences] está localizado em **[!UICONTROL Audience Data > Destinations]**. Selecione **[!UICONTROL Integrated Platforms > Device-Based]** para ver métricas de audiências endereçáveis.

![](assets/addressable-audiences-landing.png)

As três métricas que você pode ver na [!UICONTROL Addressable Audiences] landing page representam:

| Métrica | Descrição |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Essa métrica representa a métrica [!UICONTROL Customer Addressable Audience] (descrita na tabela acima) *dos últimos 30 dias.* |
| **[!UICONTROL Match Rate]** | Essa métrica representa a métrica [!UICONTROL Addressable Audience Match Rate] (descrita na tabela acima) *dos últimos 30 dias*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Uma contagem de todos os dispositivos que interagiram com todos os [!DNL Audience Manager] clientes no nível da plataforma durante o período de análise do relatório e que podem ser combinados com esse destino. Consulte Métricas [de nível](/help/using/features/addressable-audiences.md#platform-level-metrics) Platform para obter mais informações. |

Clique no nome de um destino servidor a servidor para visualização dos dados de audiência endereçáveis. Observe que esse recurso retorna dados somente para destinos de servidor para servidor e o acesso requer permissões de administrador.

![](assets/addressableAudiences.png)

A revisão desses dados pode ajudá-lo com:

* **Previsão e planejamento:** [!UICONTROL Segment Addressable Audience] os dados fornecem mais granularidade aos segmentos que você planeja enviar para um destino para direcionamento e ativação de audiências.

* **Análises de desempenho:** O [!UICONTROL Addressable Audiences] recurso também é uma ferramenta de solução de problemas. Ele permite que você analise o desempenho da campanha, entenda o alcance da campanha e faça uma verificação cruzada com parceiros de definição de metas/ativações se você não encontrar os resultados esperados.

### Prospecção com dados de terceiros e implicações para taxas de correspondência

Antes de adquirir dados de terceiros para aquisição de audiências, os clientes podem validar a sobreposição com outros provedores de dados. Isso pode ajudá-lo a tomar uma decisão informada antes de comprar novos dados. As sincronizações de ID para dados de terceiros adquiridos dependem não apenas da sobreposição de seus dados, mas também de pegadas de provedores de terceiros com todos os outros [!DNL Audience Manager] clientes. Seu [!DNL Adobe] consultor pode ajudá-lo a identificar outras fontes de dados relevantes para otimizar as campanhas de prospecção.

### Usuários móveis e taxas de correspondência

Há lacunas ao tentar conectar usuários de aplicativos móveis [!DNL Safari] nos quais não há cookies de terceiros presentes. Isso dificulta a sincronização de usuários com alguns parceiros, pois somente essas [!DNL Adobe] IDs de cookies de terceiros sincronizados são fornecidas nos logs do delivery de mídia. Esta é uma razão pela qual você pode ver taxas [de correspondência](../features/addressable-audiences.md#low-match-rates) baixas para seus destinos.

## Intervalos de datas em Audiências e destinos endereçáveis {#date-ranges}

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

Todas as datas e intervalos de datas são definidos no [!DNL UTC] fuso horário. Consulte Fusos [horários em Audience Manager](../reference/aam-time-zones.md).

## Dados em intervalos de datas {#date-range-intervals}

As métricas [!UICONTROL Addressable Audience] e [!UICONTROL Destination] retornam uma contagem de usuários únicos para o intervalo de tempo selecionado. Por exemplo, um visitante é contado apenas uma vez, mesmo se ele vier ao seu site várias vezes. A primeira visita é a única e é registrada. As visitas subsequentes são visitas recorrentes e não são contadas porque não são exclusivas.

Os intervalos de datas contêm dados para o intervalo de tempo selecionado ou anterior. Além disso, os dados envelhecem fora de cada intervalo de relatório conforme o tempo passa. Por exemplo, vamos supor que você veja dois visitantes depois de escolher a [!UICONTROL Last 30 Days] opção. Nos relatórios, estes visitantes:

* *Serão* incluídos nos resultados retornados pelos intervalos de tempo mais longos (60 dias, 90 dias e Duração).
* *Não será* incluído nos intervalos mais curtos que precedem a [!UICONTROL Last 30 Day] opção (Atual, 7 dias e 14 dias).

E, no dia 31, esses visitantes só aparecem nos 60 dias, 90 dias, e [!UICONTROL Lifetime] resultados. Eles envelheceram fora do intervalo de 30 dias. Os Visitantes não envelhecem fora do [!UICONTROL Lifetime] intervalo.

## Métricas de Audiência endereçáveis {#addressable-audience-metrics}

Esta seção descreve os tipos de métricas fornecidas por [!UICONTROL Addressable Audiences].

### Métricas no nível do cliente {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Essas métricas retornam dados para características realizadas quando visitantes chegam ao seu site ou quando você envia arquivos de dados de entrada para [!DNL Audience Manager]. Essas métricas fornecem uma visualização abrangente do tamanho da audiência para sua conta.

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Audiência endereçável do cliente</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Uma contagem de sobreposição de dispositivos que perceberam uma característica baseada em regras ou uma característica integrada durante a janela de retrospectiva e dispositivos que possuem uma sincronização de ID com o destino escolhido independentemente do tempo de sincronização. </p> 
    </draft-comment> <p>Essa métrica representa dispositivos que: 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Tenham percebido uma característica baseada em regras ou integrada durante a janela de retrospectiva <b>E</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Ter uma sincronização de ID com o destino escolhido, independentemente do tempo de sincronização. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audiência total do cliente</b> </p> </td> 
   <td colname="col2"> <p>Uma contagem de dispositivos que perceberam uma característica baseada em regras em suas propriedades ou uma característica integrada de seus arquivos offline durante a janela de retrospectiva. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taxa de correspondência do cliente</b> </p> </td> 
   <td colname="col2"> <p>Audiência endereçável do cliente /Audiência total do cliente expressa como %. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Métricas de correspondência no nível do segmento {#segment-level-metrics}

Essas métricas retornam dados sobre a associação a segmentos. Eles ajudam a fornecer uma visualização mais granular e precisa do tamanho da audiência para cada um dos segmentos.

>[!NOTE]
>
>A forma como a janela de retrospectiva é aplicada no nível do segmento é diferente daquela no nível do cliente. Os Visitantes podem vir ao site e perceber uma característica há 10 dias, e podem se qualificar para um segmento desde então e sair do segmento há 2 dias. Quando a análise de sete dias for aplicada, esses visitantes serão contados no nível do segmento, mas não no nível do cliente.

<table id="table_4185AA02CC774B6C93B02E45F88BBBD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Audiência endereçável do segmento</b> </p> </td> 
   <td colname="col2"> <p>O número de usuários que pertenceram ao segmento durante o período de análise do relatório e que têm uma sincronização de ID ativa no site. Os segmentos podem incluir seus próprios dados primários e dados de terceiros e de terceiros, por meio de características adquiridas no <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>Dica: Quando usada com o período de análise de 1 dia, essa métrica pode ajudá-lo a entender o estado atual de seus segmentos. Isso ocorre porque a <span class="wintitle"> métrica Audiência</span> endereçável de segmento representa os usuários que permaneceram em um segmento durante o dia anterior. Combine isso com o fato de que o Audience Manager <span class="keyword"> atualiza</span> Audiências <span class="wintitle"></span> endereçáveis diariamente, combinando essa métrica e o período de pesquisa fornece o instantâneo mais atualizado de seus segmentos. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>População total de segmentos</b> </p> </td> 
   <td colname="col2"> <p>Uma contagem de todos os dispositivos que eram membros do seu segmento durante o período de análise do relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taxa de correspondência do segmento</b> </p> </td> 
   <td colname="col2"> <p>Audiência endereçável do segmento /População total do segmento expressa como %. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Métricas de nível Platform {#platform-level-metrics}

Essa métrica retorna dados sobre atividades coletadas em todos os [!DNL Audience Manager] clientes. Eles podem fornecer uma visualização mais ampla da audiência do cliente em comparação aos [!DNL Audience Manager] clientes agregados.

<table id="table_B6654D9858FF46AF95B1C181D4608D26"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Audiência endereçável</b> </p> </td> 
   <td colname="col2"> <p>Uma contagem de todos os dispositivos que interagiram com todos os clientes do Audience Manager no nível da plataforma durante o período de análise do relatório e que podem ser combinados com o destino escolhido. </p> <p>Essa métrica é útil porque mostra: </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> O tamanho da audiência endereçável total que o <span class="keyword"> Audience Manager</span> pode atingir em um destino de direcionamento específico. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">O tamanho do pool de perfis <span class="keyword"> Audience Manager</span> para uma plataforma de definição de metas e o tamanho de suas audiências. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Comparação de Audiências endereçáveis de segmentos e clientes{#comparing-metrics}

Você não deve comparar as métricas [!UICONTROL Customer Addressable Audience] e [!UICONTROL Segment Addressable Audience] para determinar se uma é mais significativa do que a outra. Essas são métricas separadas, diferentes e independentes. Conforme descrito nas definições acima, cada uma destas é derivada de diferentes conjuntos de dados. Considerando isso, você deve evitar tirar conclusões se uma métrica for maior que a outra. Tudo o que você pode dizer ao comparar isso é que:

* [!UICONTROL Customer Addressable Audiences] é baseado em realizações características *para seus próprios dados* primários. Essa métrica fornece uma visualização abrangente e abrangente da sua integração com um parceiro de dados.

* [!UICONTROL Segment Addressable Audiences] é baseado em qualificações de segmento *para seus próprios dados primários, além de dados* secundários e de terceiros. Essa métrica fornece uma visualização granular e mais precisa de suas audiências endereçáveis em uma plataforma de definição de metas.

## Causas de baixas taxas de correspondência para Audiências endereçáveis {#low-match-rates}

Elementos comuns responsáveis por baixas taxas de [!UICONTROL Addressable Audience] correspondência ou discrepâncias nos números reportados.

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
   <td colname="col2"> <p>A maioria das integrações servidor a servidor depende de processos de sincronização facilitados por cookies de terceiros. No entanto, ambientes móveis não usam cookies de terceiros. Como resultado, seus números de Audiência endereçáveis podem parecer baixos em comparação ao tamanho do segmento. </p> <p>A partir de janeiro de 2018, você poderá ativar audiências móveis nos mesmos destinos do Google e Adobe Advertising Cloud configurados para audiências baseadas em cookies. Embora isso signifique que você pode enviar segmentos com cookie combinado e associação de ID móvel para seus destinos do Google e Advertising Cloud, tenha em mente que as Audiências endereçáveis exibem apenas a sobreposição entre IDs de cookie e destinos. O Audience Manager envia 100% das audiências móveis para destinos, mas as audiências móveis não são medidas pela métrica Audiência endereçável. </p> <p> <p><b>Observação</b>:  Por exemplo, pegue um segmento com uma população de 1.000.000. Se mapear esse segmento para um destino do Google ou Adobe Advertising Cloud, você poderá ver uma Audiência endereçável de 700.000 dispositivos e uma Taxa de correspondência de 70%. A associação de 700.000 consiste em IDs de cookie que têm uma sincronização de ID com o destino. Sua Audiência endereçável pode, na verdade, ser muito maior, pois as IDs móveis endereçáveis não aparecem nessa métrica. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tráfego Safari</b> </p> </td> 
   <td colname="col2"> <p>O Safari bloqueia cookies de terceiros. Isso impede que o Audience Manager sincronize IDs com o destino. Com a introdução do <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, você pode esperar que suas audiências endereçáveis não incluam usuários do Safari. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Impressões de mídia rastreadas</b> </p> </td> 
   <td colname="col2"> <p>Devido às práticas recomendadas do servidor de publicidade, as sincronizações de ID não são feitas em tags de publicidade. Os clientes que fazem uma grande quantidade de anúncios externos não sincronizarão os usuários às integrações de terceiros nesses ambientes. Além disso, uma grande quantidade de dados coletados de impressão de mídia poderia reduzir os números de audiências endereçáveis. </p> </td>
  </tr> 
 </tbody> 
</table>

## Solução de problemas com Audiências endereçáveis {#troubleshooting}

Além de encontrar as taxas de correspondência, você também pode usar [!UICONTROL Addressable Audiences] como uma ferramenta de solução de problemas.

<!-- addressable-audiences-troubleshooting.xml -->

Por exemplo, digamos que você envie um segmento para um destino e esse destino mostra números baixos de relatórios. A verificação dos [!UICONTROL Addressable Audience] resultados mostrará se isso é um problema técnico ou apenas um caso de taxas de correspondência baixas. Uma taxa de correspondência baixa mostra que seu destino não é tão bom para seus segmentos selecionados. No entanto, uma diferença nos números totais de audiência endereçáveis entre [!DNL Audience Manager] e o destino indica um problema de integração, sincronização ou outro problema técnico. Nesses casos, entre em contato com seu gerente de conta.