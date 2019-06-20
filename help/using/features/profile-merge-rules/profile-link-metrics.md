---
description: As métricas de Link de perfil fornecem dados sobre pessoas e dispositivos que se autenticam em seu site. Os dados e os gráficos no Link do perfil são atualizados dinamicamente à medida que você cria uma regra de mesclagem ou quando você clica em uma regra existente do painel Regras de mesclagem de perfis. Essas métricas podem incluir um gráfico de dispositivo na Cooperativa de dispositivo da Adobe Experience Cloud ou em outras fontes de gráficos de dispositivo de terceiros.
seo-description: As métricas de Link de perfil fornecem dados sobre pessoas e dispositivos que se autenticam em seu site. Os dados e os gráficos no Link do perfil são atualizados dinamicamente à medida que você cria uma regra de mesclagem ou quando você clica em uma regra existente do painel Regras de mesclagem de perfis. Essas métricas podem incluir um gráfico de dispositivo na Cooperativa de dispositivo da Adobe Experience Cloud ou em outras fontes de gráficos de dispositivo de terceiros.
seo-title: Métricas de relatório para Regras de mesclagem de perfil
solution: Audience Manager
title: Métricas de relatório para Regras de mesclagem de perfil
uuid: 76 a 86 ff 0-4 c 64-4734-ae0-0 a 8828942096
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Report Metrics for Profile Merge Rules {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Link] fornecem dados sobre pessoas e dispositivos que se autenticam em seu site. The data and graphs in [!UICONTROL Profile Link] update dynamically as you create a merge rules or when you click an existing rule from the [!UICONTROL Profile Merge Rules] dashboard. These metrics can include device graph from the [!DNL Adobe Experience Cloud Device Co-op] or other third-party device graph sources.

## Merge Rule Metrics {#merge-rule-metrics}

Reports return data in side-by-side bar graphs when your merge rules use data from the [Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/) or other, third-party device graphs you may have access to in [!DNL Audience Manager]. This lets you compare your authenticated, first-party data with cross-device data provided by the [!UICONTROL Experience Cloud Device Co-op] or another, third-party device graph. For information about data returned by the [!UICONTROL Device Co-op], see [The Device Graph: Internal Processes and Output](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html). Esses dados são atualizados diariamente.

<table id="table_A7FB2F9804F84AC8A6DD05C0E6EE7555"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Atividade autenticada</span></b> </p> </td> 
   <td colname="col2"> <p>Mostra: </p> 
    <ul id="ul_7F7373919A4A49028EF4BF7B28D9F8E9"> 
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> Pessoas ativas</span>: O número de pessoas que se autenticaram no site nos últimos 60 dias. </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> Dispositivo</span>cruzado: O número total de <a href="../../features/profile-merge-rules/merge-rules-start.md#create-data-source"> IDs de dispositivo cruzado</a> armazenadas na Fonte <a href="../../features/manage-datasources.md#create-data-source"> de Dados</a> do Perfil <a href="../../features/profile-merge-rules/merge-rule-definitions.md"> autenticado selecionado</a> durante a vida útil da fonte de dados. </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> % Ativas Pessoas</span>: Mostra <span class="wintitle"> Pessoas ativas</span> como %. </li> 
    </ul> <p> <span class="wintitle"> A atividade autenticada</span> permite comparar fontes de dados por atividade, volume e porcentagem. Ele pode ajudá-lo a encontrar uma fonte de dados com muitas pessoas e uma grande porcentagem de usuários ativos. Ou você pode encontrar um valor na comparação das fontes de dados com alta proporção de usuários ativos em comparação com o tamanho total do público-alvo. Por exemplo, às vezes uma fonte de dados com números de duração total baixos e alta atividade são mais valiosos do que aqueles com resultados de duração alta e números de atividade baixos. </p> <p> <p>Note: The <span class="wintitle"> Authenticated Activity</span> metrics contain <span class="wintitle"> Profile Link</span> data only. This report does not include <span class="wintitle"> Device Graph</span> data. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Média de dispositivos por pessoa</span></b> </p> </td> 
   <td colname="col2"> <p> Mostra o número médio de dispositivos usados por visitantes que foram autenticados em seu site para a fonte de dados selecionada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Total de dispositivos</span></b> </p> </td> 
   <td colname="col2"> <p>Mostra o número total de dispositivos que as pessoas usaram para autenticar no site para a fonte de dados selecionada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Total de pessoas</span></b> </p> </td> 
   <td colname="col2"> <p>Mostra o número total de pessoas que foram identificadas determinalmente para a fonte de dados selecionada. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Device Graph Metrics {#device-graph-metrics}

The [!UICONTROL Merge Rules] reports also show data on the total number of people and devices who have visited your site for the selected data source and device graph. Essas métricas retornam dados com base em intervalos de tempo pré-definidos (o período de retrospectiva) que variam dependendo da opção de dispositivo selecionada ao criar uma regra. A tabela a seguir lista esses intervalos de relatório para cada uma das opções de gráfico de dispositivos.

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opção de gráfico de dispositivo </th> 
   <th colname="col2" class="entry"> Intervalo de consulta do relatório </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Link de perfil</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_B2FF2341573840549FFB96579F537082"> 
      <li id="li_B37323C2F2434F41B407500AC5C15447">Total de pessoas: 60 dias </li> 
      <li id="li_08D911224A60418BBB3CFB4E70CE73D4">Total de dispositivos: 120 dias </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Gráfico de dispositivos de cooperação</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_64AD1DD89DF64703B70B973A463BA020"> 
      <li id="li_D7D3A3871F434CBFA71BE8929EB41648">Total de pessoas: 180 dias </li> 
      <li id="li_125D387986B2463EB310203CE5857EDA">Total de dispositivos: 180 dias </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Liveramp</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_2772F3AD7E1440789B635794ECDE8DFB"> 
      <li id="li_1432363829D64615B1D349A3722D6268">Total de pessoas: 180 dias </li> 
      <li id="li_D5C0E3CE92524B54BBD36C73A326292B">Total de dispositivos: 180 dias </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Tapad</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_274529DB58E6442E95C6AD89BECB1362"> 
      <li id="li_67102211A72A4E47AACFE5E369793C17">Total de pessoas: 60 dias </li> 
      <li id="li_3E8F3DA6A7B5487895A626674DA363A5">Total de dispositivos 60 dias </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sample Reports {#sample-reports}

### Relatório de link padrão de perfil

A standard [!UICONTROL Profile Link] report looks like the following example. Unir regras que usam várias fontes de dados (até 3, máximo) mostra os gráficos em guias separadas para cada fonte de dados. This merge rule does not include [!UICONTROL Device Co-op] data.

![](assets/coop-metrics1.png)

### Relatório de link de perfil com dados de gráfico de dispositivo

A [!UICONTROL Profile Link] report that includes device graph data from the [!UICONTROL Adobe Experience Cloud Device Co-op] or a third-party device graph shows [!UICONTROL Profile Link] and device graph data with side-by-side bar graphs. Placing these graphs adjacent to each other lets you evaluate the benefits of using the [!UICONTROL Experience Cloud Device Co-op] compared to [!UICONTROL Profile Link] by itself. Unir regras que usam várias fontes de dados (até 3, máximo) mostra os gráficos em guias separadas para cada fonte de dados. As a reminder, the [!UICONTROL Authenticated Activity] graph and metrics do not return data from the [!DNL Adobe] device graph or other, third-party device graphs you may have access to in [!DNL Audience Manager].

![](assets/coop-metrics2.png)

## Profile Link Trend Graphs {#profile-link-trend}

In addition to the other data visualizations, [!UICONTROL Profile Link] reports include a line graph. O gráfico de linha foi projetado para mostrar tendências ao longo do tempo para suas regras de perfil. Trend graphs (and the other reports) are available when you click a rule from the [!UICONTROL Profile Merge Rules] landing page ( **[!UICONTROL Audience Data > Profile Merge Rules]**). These graphs include device graph data if you&#39;re a member of the [!UICONTROL Device Co-op] or other, third-party device graphs you may have access to in [!DNL Audience Manager]. Clique em uma linha de tendência para ver os dados subjacentes.

![](assets/authenticated_trends.png)

>[!MORE_ LIKE_ THIS]
>
>* [Perguntas frequentes sobre regras de mesclagem de perfil](../../faq/faq-profile-merge.md)

