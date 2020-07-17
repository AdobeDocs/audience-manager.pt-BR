---
description: As métricas de Link de Perfil fornecem dados sobre pessoas e dispositivos que se autenticam em seu site. Os dados e gráficos no Link do Perfil são atualizados dinamicamente à medida que você cria regras de mesclagem ou quando cla em uma regra existente no painel Regras de mesclagem de Perfis. Essas métricas podem incluir gráficos de dispositivos do Adobe Experience Cloud Device Co-op ou de outras fontes de gráficos de dispositivos de terceiros.
seo-description: As métricas de Link de Perfil fornecem dados sobre pessoas e dispositivos que se autenticam em seu site. Os dados e gráficos no Link do Perfil são atualizados dinamicamente à medida que você cria regras de mesclagem ou quando cla em uma regra existente no painel Regras de mesclagem de Perfis. Essas métricas podem incluir gráficos de dispositivos do Adobe Experience Cloud Device Co-op ou de outras fontes de gráficos de dispositivos de terceiros.
seo-title: Métricas de relatório para regras de mesclagem de perfis
solution: Audience Manager
title: Métricas de relatório para regras de mesclagem de perfis
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 2%

---


# Métricas de relatório para regras de mesclagem de perfis {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Merge Rule] as métricas fornecem dados sobre pessoas e dispositivos que se autenticam em seu site. Os dados e gráficos em [!UICONTROL Profile Merge Rule Reports] atualização dinamicamente à medida que você cria uma regra de mesclagem ou ao clicar em uma regra existente do [!UICONTROL Profile Merge Rules] painel. Essas métricas podem incluir gráficos de dispositivos de fontes de gráficos de dispositivos [!DNL Adobe Experience Cloud Device Co-op] ou de outras fontes de gráficos de dispositivos de terceiros.

## Mesclar métricas de regras {#merge-rule-metrics}

Os relatórios retornam dados em gráficos de barras lado a lado quando suas regras de mesclagem usam dados do [Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html) ou outros gráficos de dispositivos de terceiros aos quais você pode ter acesso [!DNL Audience Manager]. Isso permite que você compare seus dados autenticados e primários com os dados entre dispositivos fornecidos pelo gráfico de dispositivos [!UICONTROL Experience Cloud Device Co-op] ou por outro, de terceiros. Para obter informações sobre os dados retornados pelo [!UICONTROL Device Co-op], consulte [O Gráfico de dispositivos: Processos internos e saída](https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html). Estes dados são atualizados diariamente.

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
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> Pessoas</span>ativas: O número de pessoas que se autenticaram no site nos últimos 60 dias. </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> Entre dispositivos</span>: O número total de IDs <a href="merge-rules-start.md#create-data-source"> entre dispositivos armazenados na Fonte</a> de <a href="https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html"> dados do Perfil</a> <a href="merge-rule-definitions.md"></a> Autenticado selecionado pelo tempo de vida útil que a fonte de dados possui. </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> % de Pessoas</span>Ativas: Mostra Pessoas <span class="wintitle"></span> ativas como um %. </li> 
    </ul> <p> <span class="wintitle"> A Atividade</span> autenticada permite comparar fontes de dados por atividade, volume e porcentagem. Ele pode ajudá-lo a encontrar uma fonte de dados que tenha muitas pessoas e uma alta porcentagem de usuários ativos. Ou você pode encontrar valor ao comparar fontes de dados com a alta proporção de usuários ativos em comparação ao tamanho total da audiência. Por exemplo, às vezes uma fonte de dados com números de vida útil total baixos e atividade alta são mais valiosos do que aquelas com resultados de vida útil alta e números baixos de atividades. </p> <p> <p>Observação: As métricas de Atividade <span class="wintitle"> Autenticada contêm apenas dados de Link</span> de <span class="wintitle"></span> Perfil. Este relatório não inclui <span class="wintitle"> dados do Gráfico</span> de dispositivos. </p> </p> </td> 
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
   <td colname="col1"> <p> <b><span class="wintitle"> Total de Pessoas</span></b> </p> </td> 
   <td colname="col2"> <p>Mostra o número total de pessoas que foram identificadas deterministicamente para a fonte de dados selecionada. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Métricas do Gráfico de dispositivos {#device-graph-metrics}

Os [!UICONTROL Merge Rules] relatórios também mostram dados sobre o número total de pessoas e dispositivos que visitaram seu site para a fonte de dados e o gráfico de dispositivos selecionados. Essas métricas retornam dados com base em intervalos de tempo predefinidos (o período de análise) que variam dependendo da opção de dispositivo selecionada ao criar uma regra. A tabela a seguir lista esses intervalos de relatório para cada uma das opções de gráfico do dispositivo.

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opção de Gráfico de dispositivos </th> 
   <th colname="col2" class="entry"> Intervalo de retorno do relatório </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Link de perfil</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_B2FF2341573840549FFB96579F537082"> 
      <li id="li_B37323C2F2434F41B407500AC5C15447">Total de Pessoas: 60 dias </li> 
      <li id="li_08D911224A60418BBB3CFB4E70CE73D4">Total de dispositivos: 120 dias </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Gráfico de dispositivos cooperativos</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_64AD1DD89DF64703B70B973A463BA020"> 
      <li id="li_D7D3A3871F434CBFA71BE8929EB41648">Total de Pessoas: 180 dias </li> 
      <li id="li_125D387986B2463EB310203CE5857EDA">Total de dispositivos: 180 dias </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LiveRamp</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_2772F3AD7E1440789B635794ECDE8DFB"> 
      <li id="li_1432363829D64615B1D349A3722D6268">Total de Pessoas: 180 dias </li> 
      <li id="li_D5C0E3CE92524B54BBD36C73A326292B">Total de dispositivos: 180 dias </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Tapad</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_274529DB58E6442E95C6AD89BECB1362"> 
      <li id="li_67102211A72A4E47AACFE5E369793C17">Total de Pessoas: 60 dias </li> 
      <li id="li_3E8F3DA6A7B5487895A626674DA363A5">Total de dispositivos 60 dias </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Relatórios de exemplo {#sample-reports}

### Relatório de link de Perfil padrão

Um [!UICONTROL Profile Link] relatório padrão se parece com o exemplo a seguir. As regras de mesclagem que usam várias fontes de dados (até 3, no máximo) mostram gráficos em guias separadas para cada fonte de dados. Essa regra de mesclagem não inclui [!UICONTROL Device Co-op] dados.

![](assets/profile-link-metrics.png)

### Relatório De Link De Perfil Com Dados De Gráfico De Dispositivo

Um [!UICONTROL Profile Link Device Graph] relatório que inclui dados de gráficos de dispositivos do [!UICONTROL Adobe Experience Cloud Device Co-op] ou de um gráfico de dispositivos de terceiros mostra [!UICONTROL Profile Link] e dados de gráficos de dispositivos com gráficos lado a lado. Colocar esses gráficos adjacentes permite avaliar os benefícios de usar os gráficos [!UICONTROL Experience Cloud Device Co-op] em comparação com [!UICONTROL Profile Link] eles mesmos. As regras de mesclagem que usam várias fontes de dados (até 3, no máximo) mostram gráficos em guias separadas para cada fonte de dados. Como lembrete, o [!UICONTROL Authenticated Activity] gráfico e as métricas não retornam dados do gráfico do [!DNL Adobe] dispositivo ou de outros gráficos de dispositivos de terceiros aos quais você pode ter acesso [!DNL Audience Manager].

![](assets/profile-link-graph.png)

## Gráficos de Tendência de Link de Perfil {#profile-link-trend}

Além das outras visualizações de dados, [!UICONTROL Profile Link] os relatórios incluem um gráfico de linha. O gráfico de linhas foi projetado para mostrar tendências ao longo do tempo para suas regras de perfil. Os gráficos de tendência (e os outros relatórios) estão disponíveis quando você clica em uma regra da [!UICONTROL Profile Merge Rules] landing page ( **[!UICONTROL Audience Data > Profile Merge Rules]**). Esses gráficos incluem dados de gráficos de dispositivos se você for membro dos gráficos de dispositivos de terceiros [!UICONTROL Device Co-op] aos quais você pode ter acesso [!DNL Audience Manager]. Clique em uma linha de tendência para ver os dados subjacentes.

>[!MORELIKETHIS]
>
>* [Perguntas frequentes sobre as regras de mesclagem de Perfis](../../faq/faq-profile-merge.md)

