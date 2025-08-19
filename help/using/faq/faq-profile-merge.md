---
description: Respostas a perguntas comuns sobre a Regra de mesclagem de perfis e Gráfico de dispositivos.
keywords: ID da organização
seo-description: Answers to common Profile Merge Rule and device graph questions.
seo-title: Profile Merge Rules and Device Graph FAQ
solution: Audience Manager
title: Perguntas frequentes sobre Regras de mesclagem de perfis e Gráfico de dispositivos
uuid: ba7986f1-078f-4162-aef3-b5c8740cebf4
feature: Profile Merge
exl-id: 03ad79b7-a111-437e-82c5-c7406bd33c39
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1583'
ht-degree: 81%

---

# Perguntas frequentes sobre Regras de mesclagem de perfis e Gráfico de dispositivos{#profile-merge-rules-and-device-graph-faq}

Respostas a perguntas comuns sobre a Regra de mesclagem de perfis e Gráfico de dispositivos.

<!-- profile-merge-faq.xml -->

## Noções básicas do gráfico de dispositivos {#device-graph-basics}

**O que é um gráfico de dispositivos?**

Um gráfico de dispositivos é um conjunto de mapeamentos de ID que define grupos de dispositivos anônimos. Ele associa esses dispositivos a uma pessoa ou residência com base em elementos comuns nos sinais coletados de cada dispositivo. Esses sinais ajudam a identificar dispositivos de pessoas ou residências.

 

**O que é um gráfico de dispositivos externo?**

Um gráfico de dispositivos externo é qualquer gráfico de dispositivos no [!DNL Audience Manager] que não foi criado exclusivamente a partir de suas próprias fontes de dados entre dispositivos. Por exemplo, ao criar uma [Regra de mesclagem de perfis](../features/profile-merge-rules/merge-rules-start.md) e escolher as opções de gráfico de dispositivos de terceiros, você está trabalhando com um gráfico de dispositivos externo. Consulte [Opções de dispositivos](../features/profile-merge-rules/merge-rule-definitions.md#device-options).

 

**Quais são alguns casos de uso comuns para usar um gráfico de dispositivos externo em uma [!UICONTROL Profile Merge Rule]?**

O principal objetivo de usar um gráfico de dispositivos em uma [!UICONTROL Profile Merge Rule] é avaliar e qualificar vários dispositivos pertencentes a uma única pessoa ou residência para um segmento específico. O próprio segmento pode ter vários usos, como direcionar um público-alvo de prospetos com um anúncio veiculado por uma DSP ou personalizar a experiência de um cliente no site por meio de uma plataforma de personalização no site. Consulte [Casos de uso do gráfico do dispositivos externo](../features/profile-merge-rules/external-graph-use-cases.md).

 

**O Audience Manager oferece suporte global para gráficos de dispositivos externos?**

Não. Os Gráficos de dispositivos externos estão disponíveis apenas nos Estados Unidos e no Canadá.

 

**Com que frequência o [!DNL Audience Manager] atualiza os dados de gráficos de dispositivos externos?**

Uma vez por semana.

 

## Gráficos de dispositivos e Regras de mesclagem de perfis {#device-graph-profile-merge-rules}

**Como o [!DNL Audience Manager] usa um gráfico de dispositivos?**

No [!DNL Audience Manager], os gráficos de dispositivos aparecem como opções de configuração ao [criar uma Regra de mesclagem de perfis](../features/profile-merge-rules/merge-rules-start.md). Por meio das [!UICONTROL Profile Merge Rules], esses gráficos de dispositivos ajudam a [!DNL Audience Manager]:

* Mesclar vários perfis de dispositivo, criando um único superconjunto de características.
* Avaliar o superconjunto de características para a qualificação de segmentos (em vez de avaliar cada perfil de dispositivo individualmente).
* Adicionar dispositivos qualificados aos segmentos disponíveis.

 

**Quantas [!UICONTROL Profile Merge Rules] posso criar?**

Atualmente, é possível criar um máximo de 4 [!UICONTROL Profile Merge Rules]. A quarta Regra de mesclagem de perfis ([!UICONTROL All Cross-Device Profiles]) está disponível somente para clientes que compram o complemento [!UICONTROL People-Based Destinations].

 

**Quantos perfis de dispositivo o [!DNL Audience Manager] mescla e lê ao usar um gráfico de dispositivos em uma [!UICONTROL Profile Merge Rule]?**

Ao qualificar um dispositivo para um segmento usando uma [!UICONTROL Profile Merge Rule], o Audience Manager mescla e lê o perfil do dispositivo atual e um máximo de 99 outros perfis de dispositivo adicionais vinculados pela opção de gráfico do dispositivos selecionado.

 

**Quais dispositivos se qualificam para um segmento ao usar um gráfico de dispositivos em uma [!UICONTROL Profile Merge Rule]?**

Os dispositivos do [!DNL Audience Manager] se mesclam e são os mesmos dispositivos qualificados para um segmento.

 

**Para onde o [!DNL Audience Manager] pode enviar segmentos que foram qualificados por uma [!UICONTROL Profile Merge Rule] que usa um gráfico de dispositivos?**

O [!DNL Audience Manager] pode enviar segmentos para um destino em arquivos em lote ou em tempo real.

 

## Segmentos, gráficos de dispositivos e regras de mesclagem de perfis {#segments-device-graphs-rules}

**Como o [!DNL Audience Manager] cancela os segmentos de um dispositivo quando ele não está mais qualificado para um segmento com uma [!UICONTROL Profile Merge Rule] que usa um gráfico de dispositivos?**

O Audience Manager mescla até 100 dispositivos ao avaliar segmentos com uma [!UICONTROL Profile Merge Rule] que usa um gráfico de dispositivos. Se o sinal de cancelamento de segmento for emitido, o dispositivo atual e até 99 dispositivos adicionais serão removidos do segmento no destino. Para obter mais informações sobre o cancelamento de segmentação, consulte [Regras de mesclagem de perfis e Processos de canelamento de dispositivos](../features/profile-merge-rules/merge-rule-unsegment.md).


 

**Se um destino puder cancelar segmentos de dispositivos, os dispositivos serão removidos dos segmentos pelas [!UICONTROL Profile Merge Rules] que usam um gráfico de dispositivos?**

Sim. Veja a explicação acima.

 

**Se eu criar um segmento com uma [!UICONTROL Profile Merge Rule] que usa um gráfico de dispositivos e o segmento estiver usando dados em tempo real e integrados, meu segmento será atualizado à medida que os dados integrados forem alterados?**

Sim.

 

**As estimativas de tamanho de segmento incluem dispositivos que se qualificam para um segmento com base nas conexões fornecidas por uma [!UICONTROL Profile Merge Rule] que usa uma opção de gráfico de dispositivos?**

Não. Consulte as definições para a [!UICONTROL Estimated Real-Time Population] e [!UICONTROL Estimated Total Population] em [Dados de população de características e segmentos](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html).

 

**Os [!UICONTROL Addressable Audiences] incluem dispositivos qualificados para um segmento com base nas conexões fornecidas por uma [!UICONTROL Profile Merge Rule] que usa uma opção de gráfico de dispositivos?**

Sim.

 

**Se um segmento usar uma [!UICONTROL Profile Merge Rule] com o [!UICONTROL No Cross-Device Profile] e as características que qualificam os dispositivos para o segmento forem armazenadas apenas no perfil entre dispositivos, a população total do segmento será 0?**

Sim. O Audience Manager não contará as características armazenadas no perfil entre dispositivos na avaliação de segmentos quando a Regra de mesclagem de perfis estiver definida como [!UICONTROL No Cross-Device Profile].

 

## Frequência da característica, gráficos de dispositivos e regras de mesclagem de perfis {#trait-freq-device-rules}

**Como o [!DNL Audience Manager] calcula a frequência de características com uma [!UICONTROL Profile Merge Rule] que usa um gráfico de dispositivos?**

A frequência da característica é definida pela soma do número de qualificações para uma característica específica em vários dispositivos. Para ajudar você a entender isso, consulte o seguinte caso de uso.

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
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">O dispositivo A e o dispositivo B são vinculados por um gráfico de dispositivos. </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">Você tem uma <span class="wintitle">Regra de mesclagem de perfis</span> que usa uma opção de gráfico de dispositivos. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">Um único segmento (Segmento 1) composto por uma única característica (Característica 1), onde a Característica 1 tem uma frequência de 8. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ações</b> </p> </td> 
   <td colname="col2"> <p> O <span class="keyword">Audience Manager</span> lê e mescla os perfis do dispositivo para o Dispositivo A e o Dispositivo B. A partir disso, vemos o seguinte: </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">O Dispositivo A se qualificou para a Característica 1 três vezes. Ele tem uma frequência de 3 para a Característica 1. </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">O Dispositivo B se qualificou para a Característica 1 cinco vezes. Ele tem uma frequência de 5 para a Característica 1. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p> O <span class="keyword">Audience Manager</span> soma a frequência da Característica 1 e usa 8 (3 + 5 = 8) para decidir a qualificação de segmentos. O Dispositivo A e o Dispositivo B se qualificam para o segmento 1 porque ele tem uma frequência de 8. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

## Relatórios, gráficos de dispositivos e regras de mesclagem de perfis {#reports-device-graphs-rules}

**Posso ver o número de dispositivos que podem ser acessados por uma [!UICONTROL Profile Merge Rule] que usa um gráfico de dispositivos?**

Sim. Os relatórios retornam dados no nível da [!UICONTROL Profile Merge Rule]. Os dados do relatório são atualizados diariamente. Os dados são baseados nos dispositivos vistos em sua conta, não nos vinculados por um gráfico de dispositivos. Consulte [Métricas de relatório para regras de mesclagem de perfis](../features/profile-merge-rules/profile-link-metrics.md).

 

**Posso ver o número de dispositivos qualificados para um segmento específico em *tempo real* com as [!UICONTROL Profile Merge Rules] que usam um gráfico de dispositivos?**

Sim. A métrica de população em tempo real captura as qualificações de segmento do dispositivo atual (o dispositivo visto em tempo real) usando os perfis de todos os dispositivos vinculados por um gráfico de dispositivos.

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
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">Segmento 1 com base nessas características e lógica de qualificação: Segmento 1 = Característica A e Característica B e Característica C. </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3 perfis de dispositivo: Dispositivo 1 (dispositivo atual), Dispositivo 2 (gráfico de dispositivos), Dispositivo 3 (gráfico de dispositivos). </li> 
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
   <td colname="col2"> <p>Dados os elementos anteriores, a população total do Segmento 1 é um. </p> <p>Nesse caso, a <span class="wintitle">Regra de mesclagem de perfis</span> usa todos os dispositivos e suas características para decidir a qualificação de segmentos. Isso significa que os Dispositivos 1, 2 e 3 estão qualificados para o Segmento 1, mas, como mencionado acima, somente o Dispositivo 1 está incluído na população de segmentos em tempo real. Isso ocorre porque: </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">O Dispositivo 1 é o dispositivo atual que interage com os <span class="wintitle"> Servidores de coleta de dados</span> (<span class="wintitle"> DCS</span>) do Audience Manager em tempo real. </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">Os Dispositivos 2 e 3 são associados ao Dispositivo 1 por um gráfico de dispositivos, mas não interagem com o DCS ao mesmo tempo que o Dispositivo 1. </li> 
     </ul> </p> <p>Como resultado, os Dispositivos 2 e 3 não são incluídos na métrica de população do segmento em tempo real. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**É possível ver o número total de dispositivos qualificados para um segmento específico com uma [!UICONTROL Profile Merge Rule] que usa um gráfico de dispositivos?**

Sim. A métrica de população de segmentos inclui os dispositivos adicionais que se qualificaram para um segmento com base nas conexões de um gráfico de dispositivos.

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
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">Segmento 1 com base nessas características e lógica de qualificação: Segmento 1 = Característica A e Característica B e Característica C. </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3 perfis de dispositivo: Dispositivo 1 (dispositivo atual), Dispositivo 2 (gráfico de dispositivos), Dispositivo 3 (gráfico de dispositivos). </li> 
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
   <td colname="col2"> <p>Dados os elementos anteriores, a população total do Segmento 1 é de três (3). </p> <p>Nesse caso, a <span class="wintitle">Regra de mesclagem de perfis</span> usa todos os dispositivos e suas características para decidir a qualificação de segmentos. Isso significa que os Dispositivos 1, 2 e 3 se qualificam para o Segmento 1 e todos os três estão incluídos na população total. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**Os dispositivos que se qualificam para um segmento com uma [!UICONTROL Profile Merge Rule] que usa um gráfico de dispositivos incluído nos relatórios [!UICONTROL Interactive], [!UICONTROL Overlap] e [!UICONTROL Audience Optimization]?**

Não.

**Por que vejo uma população de segmento zero para exportações de segmento para o Adobe Campaign após 16 de março de 2020?**

No final de 2019, lançamos uma série de melhorias nas Regras de mesclagem de perfis para melhorar a precisão dos arquivos em lote gerados com IDs entre dispositivos. Esses aprimoramentos serão estritamente honrados em sua instância do Audience Manager a partir de segunda-feira, 16 de março de 2020. Consequentemente, os segmentos mapeados para um destino usando IDs de vários dispositivos deixarão de produzir exportações em algumas configurações de Regras de mesclagem de perfis.

Para garantir a integração correta entre sua instância do Audience Manager e destinos usando IDs entre dispositivos, como o Adobe Campaign, verifique se você atende aos seguintes requisitos:

1. Revise a Regra de mesclagem de perfis usada pelos segmentos mapeados para o destino da sua ID declarada do Adobe Campaign. A Regra de Mesclagem de Perfis deve usar a opção [!UICONTROL Last Authenticated Profile] para que todos os perfis autenticados possam ser incluídos nas exportações. Se sua Regra de Mesclagem de Perfis estiver usando uma opção diferente, alterne-a para [!UICONTROL Last Authenticated Profile].
2. Selecione a fonte de dados ID declarada da Adobe Campaign nas configurações da Regra de mesclagem de perfis.

>[!NOTE]
>
> Aumentamos o limite da Regra de mesclagem de perfis em 1 para clientes que enfrentam essa situação, para que você possa criar uma Regra de mesclagem de perfis dedicada para os segmentos mapeados para o destino da ID declarada do Adobe Campaign, sem alterar as Regras de mesclagem de perfis para outros casos de uso.

>[!MORELIKETHIS]
>
>* [Link de perfil](../features/profile-merge-rules/profile-link-use-case.md)
