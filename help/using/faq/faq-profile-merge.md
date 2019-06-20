---
description: Respostas a Perguntas comuns sobre a Regra de mesclagem de perfis e a gráficos de dispositivo.
keywords: ID da organização
seo-description: Respostas a Perguntas comuns sobre a Regra de mesclagem de perfis e a gráficos de dispositivo.
seo-title: Regras de mesclagem de perfil e perguntas frequentes sobre o gráfico de dispositivos
solution: Audience Manager
title: Regras de mesclagem de perfil e perguntas frequentes sobre o gráfico de dispositivos
uuid: ba 7986 f 1-078 f -4162-aef 3-b 5 c 8740 cebf 4
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Merge Rules and Device Graph FAQ{#profile-merge-rules-and-device-graph-faq}

Respostas a Perguntas comuns sobre a Regra de mesclagem de perfis e a gráficos de dispositivo.

<!-- 

profile-merge-faq.xml

 -->

## Device Graph Basics {#device-graph-basics}

**O que é um gráfico de dispositivos?**

Um gráfico de dispositivos é um conjunto de mapeamentos de ID que define grupos de dispositivos anônimos. Ele associa esses dispositivos a uma pessoa ou residência com base em elementos comuns nos sinais coletados de cada dispositivo. Esses sinais ajudam a identificar dispositivos no nível individual ou doméstico.

<br> 

**O que é um gráfico de dispositivos externo?**

An external device graph is any device graph in [!DNL Audience Manager] that has not been created exclusively from your own cross-device data sources. For example, when you create a [Profile Merge Rule](../features/profile-merge-rules/merge-rules-start.md) and choose the [!UICONTROL Co-op Device Graph] or third-party device graph options, you&#39;re working with an external device graph. See [Device Options](../features/profile-merge-rules/merge-rule-definitions.md#device-options).

<br> 

**Quais são alguns casos de uso comuns para usar um gráfico de dispositivo externo em um[!UICONTROL Profile Merge Rule]?**

The main objective of using a device graph in a [!UICONTROL Profile Merge Rule] is to evaluate and qualify multiple devices belonging to a single person or household for a specific segment. O próprio segmento pode ter vários usos, por exemplo, direcionar um público-alvo de prospetos e anúncios veiculados por um DSP ou personalizar a experiência no site de um cliente por meio de uma plataforma de personalização no site. See [External Device Graph Use Cases](../features/profile-merge-rules/external-graph-use-cases.md).

<br> 

**O Audience Manager oferece suporte global para gráficos de dispositivos externos?**

Não. Gráficos de dispositivos externos estão disponíveis apenas nos Estados Unidos e Canadá.

<br> 

**Com que frequência[!DNL Audience Manager]atualizar os dados de gráfico de dispositivos externos?**

Uma vez por semana.

<br> 

## Device Graphs and Profile Merge Rules {#device-graph-profile-merge-rules}

**Como[!DNL Audience Manager]usar um gráfico de dispositivos?**

In [!DNL Audience Manager], device graphs appear as configuration options when you [create a Profile Merge Rule](../features/profile-merge-rules/merge-rules-start.md). Through your [!UICONTROL Profile Merge Rules], these device graphs help [!DNL Audience Manager]:

* Mesclar vários perfis de dispositivo. Isso cria um único superconjunto de características.
* Avalie o superconjunto de características para qualificação de segmentos (em vez de avaliar cada perfil de dispositivo individualmente).
* Adicionar dispositivos qualificados aos segmentos disponíveis.

<br> 

**Quantos[!UICONTROL Profile Merge Rules]posso criar?**

Currently, you can create a maximum of 3 [!UICONTROL Profile Merge Rules].

<br> 

**Quantos perfis de dispositivo[!DNL Audience Manager]são mesclados e lidos ao usar um gráfico de dispositivos em um[!UICONTROL Profile Merge Rule]?**

When qualifying a device for a segment using a [!UICONTROL Profile Merge Rule], Audience Manager merges and reads the current device profile and a maximum of 3 additional device profiles linked by your selected device graph option.

<br> 

**Quais dispositivos se qualificam para um segmento ao usar um gráfico de dispositivos em um[!UICONTROL Profile Merge Rule]?**

The devices [!DNL Audience Manager] merges and reads are the same devices that are qualified for a segment.

>[!NOTE]
>
>For external device graphs, [!DNL Audience Manager] stores the mapping between devices at the platform level and selects 3 without evaluating their relationship to the devices seen in your instance of [!DNL Audience Manager].

<br> 

**Quais dispositivos**podem ser qualificados para um segmento usando um[!UICONTROL Profile Merge Rule]gráfico de dispositivos?**

To qualify for a segment, devices must have been seen by Audience Manager on our [edge data servers](../reference/system-components/components-edge.md) after the segment was created. Além disso, os servidores de borda:

* Armazene dados de perfil de um máximo de 14 dias.
* Exclua um perfil de dispositivo se ele estiver inativo por mais de 14 dias. Observação: Essa ação remove apenas os dados da borda. Outros sistemas manterão registros para intervalos de tempo mais longos. See the [Privacy and Data Retention FAQ](../faq/faq-privacy.md).
* Reset the 14-day interval if [!DNL Audience Manager] records any activity for that profile across the entire platform.

See also, [Data Collection Components](../reference/system-components/components-data-collection.md).

<br> 

**Onde[!DNL Audience Manager]pode enviar segmentos que foram qualificados por um[!UICONTROL Profile Merge Rule]gráfico de dispositivos?**

[!DNL Audience Manager] pode enviar segmentos para um destino em arquivos em lote ou em tempo real. And, as noted in the FAQ entry above, To qualify for a segment, devices must have been seen by [!DNL Audience Manager] on our [edge data servers](../reference/system-components/components-edge.md) after the segment was created.

<br> 

## Segments, Device Graphs, and Profile Merge Rules {#segments-device-graphs-rules}

**Como[!DNL Audience Manager]um dispositivo não é mais qualificado para um segmento com um[!UICONTROL Profile Merge Rule]gráfico de dispositivo?**

Audience Manager merges up to four devices when evaluating segments with a [!UICONTROL Profile Merge Rule] that uses a device graph. Se o sinal de dessegmento for emitido, o dispositivo atual e três dispositivos adicionais vistos em tempo real serão removidos do segmento no destino. Por exemplo, em um cluster de seis dispositivos, até quatro dispositivos são mesclados, avaliados e qualificados para um segmento. Da mesma forma, até quatro dispositivos são mesclados, avaliados e não segmentados.

<br> 

**Se um destino não conseguir segmentar dispositivos, os dispositivos serão removidos de segmentos por[!UICONTROL Profile Merge Rules]meio de um gráfico de dispositivos?**

Sim. Consulte a explicação acima.

<br> 

**Se eu criar um segmento com um[!UICONTROL Profile Merge Rule]gráfico de dispositivo que usa um gráfico de dispositivo e o segmento estiver usando dados em tempo real e integrados, o meu segmento será atualizado conforme os dados internos forem alterados?**

Não. Currently, [!DNL Audience Manager] evaluates segments with a [!UICONTROL Profile Merge Rule] that uses a device graph in real-time only. Updates made to on-boarded traits after the segment has been evaluated will be used to qualify the segment when the device is next seen by our [edge data servers](../reference/system-components/components-edge.md). Isso parte do princípio de que o perfil do dispositivo ainda está ativo nos servidores de borda, e os dados em andamento foram disponibilizados para esses sistemas. See also, the [Privacy and Data Retention FAQ](../faq/faq-privacy.md).

<br> 

**As estimativas de tamanho do segmento incluem dispositivos qualificados para um segmento com base em conexões fornecidas por um[!UICONTROL Profile Merge Rule]que usa uma opção de gráfico de dispositivo?**

Não. See the definitions for the [!UICONTROL Estimated Real-Time Population] and [!UICONTROL Estimated Total Population] in [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

<br> 

**[!UICONTROL Addressable Audiences]Inclui dispositivos qualificados para um segmento com base em conexões fornecidas por um[!UICONTROL Profile Merge Rule]que usa uma opção de gráfico de dispositivo?**

Sim.

<br> 

**Se um segmento usar uma[!UICONTROL Profile Merge Rule]com[!UICONTROL No Authenticated Profile]e as características que qualificam os dispositivos para o segmento são armazenadas apenas em relação ao perfil autenticado, a população total do segmento será 0?**

Não. Hoje, o Audience Manager conta os dispositivos mapeados para o perfil autenticado como qualificado para o segmento.

<br> 

## Trait Frequency, Device Graphs, and Profile Merge Rules {#trait-freq-device-rules}

**Como[!DNL Audience Manager]calcular a frequência de característica com um[!UICONTROL Profile Merge Rule]gráfico de dispositivos?**

A frequência de característica é definida pela soma do número de qualificações para uma característica específica em vários dispositivos. Para ajudá-lo a entender isso, consulte o caso de uso a seguir.

<table id="table_DE7A308705C84B93B3089CAD2228569E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso de uso </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Condições</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_52EA0F142E3F488CAAC7CF541E7F3472"> 
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">O dispositivo A e o Dispositivo B são vinculados por um gráfico de dispositivo. </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">You have a <span class="wintitle"> Profile Merge Rule</span> that uses a device graph option. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">Um único segmento (Segmento 1) composto de uma única característica (Característica 1), onde Traço 1 tem uma frequência de 8. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ações</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> O Audience Manager</span> lê e mescla os perfis de dispositivo para Dispositivo A e Dispositivo B. A partir disso, consulte o seguinte: </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">O Device A foi qualificado para Características 1 três vezes. Ela tem uma frequência de 3 para Característica 1. </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">O dispositivo B foi qualificado para Característica 1 cinco vezes. Tem uma frequência de 5 para Característica 1. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> O Audience Manager</span> contabiliza a frequência da Característica 1 e usa 8 (3 + 5 = 8) para decidir a qualificação de segmentos. O dispositivo A e o Dispositivo B qualificam-se para o Segmento 1, pois ele tem uma frequência de 8. </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

## Reports, Device Graphs, and Profile Merge Rules {#reports-device-graphs-rules}

**É possível ver o número de dispositivos que podem ser atingidos por um[!UICONTROL Profile Merge Rule]gráfico de dispositivos?**

Sim. Reports return data at the [!UICONTROL Profile Merge Rule] level. Os dados do relatório são atualizados diariamente. Os dados são baseados nos dispositivos vistos em sua conta, e não aqueles vinculados por um gráfico de dispositivos. See [Report Metrics for Profile Merge Rules](../features/profile-merge-rules/profile-link-metrics.md).

<br> 

**É possível ver o número de dispositivos qualificados para um segmento específico em*tempo real*com[!UICONTROL Profile Merge Rules]o uso de um gráfico de dispositivos?**

Sim. A métrica de população em tempo real captura as qualificações de segmento para o dispositivo atual (o dispositivo visto em tempo real) usando os perfis de todos os dispositivos vinculados por um gráfico de dispositivos.

<table id="table_D37A51E99B314C04A96A084491A5FEC7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento do caso de uso </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Condições</b> </p> </td> 
   <td colname="col2"> <p>Suponha que temos: </p> <p> 
     <ul id="ul_B8B627FBF6A04C0CAE6C8543EA3EA56D"> 
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">Segmento 1 criado nestas características e lógica de qualificação: Segmento 1 = Característica A e Característica B e Característica C. </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3 perfis de dispositivo: Dispositivo 1 (dispositivo atual), dispositivo 2 (gráfico de dispositivo), dispositivo 3 (gráfico de dispositivo). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ações</b> </p> </td> 
   <td colname="col2"> <p>Cada característica disponível está associada a um dispositivo: </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">Dispositivo 1: Característica A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">Dispositivo 2: Característica B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">Dispositivo 3: Característica C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p>Considerando os elementos anteriores, a população total do Segmento 1 é uma. </p> <p>In this case, the <span class="wintitle"> Profile Merge Rule</span> uses all the devices and their traits to decide segment qualification. Isso significa que os Dispositivos 1, 2 e 3 se qualificam para o Segmento 1, mas, conforme observado acima, somente o Device 1 está incluído na população de segmentos em tempo real. Isso ocorre porque: </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">Device 1 is the current device interacting with the Audience Manager <span class="wintitle"> Data Collection Servers</span> (<span class="wintitle"> DCS</span>) in real-time. </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">Os dispositivos 2 e 3 estão associados ao Dispositivo 1 por um gráfico de dispositivo, mas não estão interagindo com o DCS ao mesmo tempo que o Dispositivo 1. </li> 
     </ul> </p> <p>Como resultado, os Dispositivos 2 e 3 não são incluídos na métrica de preenchimento de segmentos em tempo real. </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**É possível ver o número total de dispositivos qualificados para um segmento específico com um[!UICONTROL Profile Merge Rule]gráfico de dispositivos?**

Sim. A métrica total de segmentos de segmento inclui os dispositivos adicionais que foram qualificados para um segmento com base nas conexões de um gráfico de dispositivo.

<table id="table_932E61B1D4374DD58F673C3B35C365EB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento do caso de uso </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Condições</b> </p> </td> 
   <td colname="col2"> <p>Suponha que temos: </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">Segmento 1 criado nestas características e lógica de qualificação: Segmento 1 = Característica A e Característica B e Característica C. </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3 perfis de dispositivo: Dispositivo 1 (dispositivo atual), dispositivo 2 (gráfico de dispositivo), dispositivo 3 (gráfico de dispositivo). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Associações</b> </p> </td> 
   <td colname="col2"> <p>Cada característica disponível está associada a um dispositivo: </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">Dispositivo 1: Característica A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">Dispositivo 2: Característica B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">Dispositivo 3: Característica C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p>Considerando os elementos anteriores, a população total do Segmento 1 é de três (3). </p> <p>In this case, the <span class="wintitle"> Profile Merge Rule</span> uses all the devices and their traits to decide segment qualification. Isso significa que os Dispositivos 1, 2 e 3 se qualificam para o Segmento 1 e os três estão incluídos na população total. </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**Os dispositivos qualificados para um segmento com um[!UICONTROL Profile Merge Rule]gráfico de dispositivos que usa um gráfico de dispositivos estão incluídos nos[!UICONTROL Interactive]relatórios,[!UICONTROL Overlap]relatórios e[!UICONTROL Audience Optimization]relatórios?**

Não

>[!MORE_ LIKE_ THIS]
>
>* [Link de perfil](../features/profile-merge-rules/merge-rules-overview.md)

