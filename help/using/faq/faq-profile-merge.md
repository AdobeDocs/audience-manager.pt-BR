---
description: Respostas a perguntas comuns sobre a regra de mesclagem de Perfis e gráficos de dispositivos.
keywords: Organization ID
seo-description: Respostas a perguntas comuns sobre a regra de mesclagem de Perfis e gráficos de dispositivos.
seo-title: Perguntas frequentes sobre Regras de mesclagem de Perfis e Gráfico de dispositivos
solution: Audience Manager
title: Perguntas frequentes sobre Regras de mesclagem de Perfis e Gráfico de dispositivos
uuid: ba7986f1-078f-4162-aef3-b5c8740cebf4
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1548'
ht-degree: 2%

---


# Perguntas frequentes sobre Regras de mesclagem de Perfis e Gráfico de dispositivos{#profile-merge-rules-and-device-graph-faq}

Respostas a perguntas comuns sobre a regra de mesclagem de Perfis e gráficos de dispositivos.

<!-- profile-merge-faq.xml -->

## Noções básicas sobre o gráfico de dispositivos {#device-graph-basics}

**O que é um gráfico de dispositivos?**

Um gráfico de dispositivo é um conjunto de mapeamentos de ID que define grupos de dispositivos anônimos. Ela associa esses dispositivos a uma pessoa ou família com base em elementos comuns nos sinais coletados de cada dispositivo. Esses sinais ajudam a identificar dispositivos a nível individual ou doméstico.

 

**O que é um gráfico de dispositivos externos?**

Um gráfico de dispositivo externo é qualquer gráfico de dispositivo em [!DNL Audience Manager] que não foi criado exclusivamente a partir de suas próprias fontes de dados entre dispositivos. Por exemplo, ao criar uma Regra [de mesclagem de](../features/profile-merge-rules/merge-rules-start.md) Perfis e escolher as opções de gráfico de dispositivo [!UICONTROL Co-op Device Graph] ou de terceiros, você está trabalhando com um gráfico de dispositivo externo. Consulte Opções [](../features/profile-merge-rules/merge-rule-definitions.md#device-options)do dispositivo.

 

**Quais são alguns casos de uso comuns para usar um gráfico de dispositivo externo em um[!UICONTROL Profile Merge Rule]?**

O principal objetivo de usar um gráfico de dispositivos em um segmento [!UICONTROL Profile Merge Rule] é avaliar e qualificar vários dispositivos pertencentes a uma única pessoa ou residência para um segmento específico. O próprio segmento pode ter vários usos, por exemplo, como direcionar uma audiência de prospectos com um anúncio veiculado por um DSP ou personalizar a experiência de um cliente no local por meio de uma plataforma de personalização no site. See [External Device Graph Use Cases](../features/profile-merge-rules/external-graph-use-cases.md).

 

**O Audience Manager oferece suporte global para gráficos de dispositivos externos?**

Não. Gráficos de dispositivos externos estão disponíveis apenas nos Estados Unidos e Canadá.

 

**Com que frequência os dados de gráficos de dispositivos externos são[!DNL Audience Manager]atualizados?**

Uma vez por semana.

 

## Gráficos de dispositivos e regras de mesclagem de Perfis {#device-graph-profile-merge-rules}

**Como[!DNL Audience Manager]usar um gráfico de dispositivo?**

Em [!DNL Audience Manager], os gráficos de dispositivo aparecem como opções de configuração quando você [cria uma Regra](../features/profile-merge-rules/merge-rules-start.md)de mesclagem de Perfis. Por meio de seu [!UICONTROL Profile Merge Rules], esses gráficos de dispositivos ajudam [!DNL Audience Manager]:

* Mesclar vários perfis de dispositivo. Isto cria um único super conjunto de características.
* Avalie o superconjunto de características para a qualificação de segmentos (em vez de avaliar cada perfil de dispositivo individualmente).
* Adicione dispositivos qualificados aos segmentos disponíveis.

 

**Quantos[!UICONTROL Profile Merge Rules]posso criar?**

Atualmente, você pode criar um máximo de 4 [!UICONTROL Profile Merge Rules]. A quarta Regra de mesclagem de Perfis ([!UICONTROL All Cross-Device Profiles]) está disponível somente para clientes que compram o complemento [!UICONTROL People-Based Destinations] .

 

**Quantos perfis de dispositivo são[!DNL Audience Manager]unidos e lidos ao usar um gráfico de dispositivo em um[!UICONTROL Profile Merge Rule]?**

Ao qualificar um dispositivo para um segmento usando um [!UICONTROL Profile Merge Rule], o Audience Manager mescla e lê o perfil do dispositivo atual e um máximo de 99 outros perfis de dispositivo adicionais vinculados pela opção de gráfico do dispositivo selecionado.

 

**Quais dispositivos se qualificam para um segmento ao usar um gráfico de dispositivo em um[!UICONTROL Profile Merge Rule]?**

Os dispositivos [!DNL Audience Manager] se mesclam e são os mesmos dispositivos qualificados para um segmento.

 

**Onde pode[!DNL Audience Manager]enviar segmentos que foram qualificados por um gráfico de dispositivo[!UICONTROL Profile Merge Rule]que usa um gráfico de dispositivo?**

[!DNL Audience Manager] pode enviar segmentos para um destino em arquivos em lote ou em tempo real.

 

## Segmentos, gráficos de dispositivos e regras de mesclagem de Perfis {#segments-device-graphs-rules}

**Como[!DNL Audience Manager]cancelar a segmentação de um dispositivo quando ele não é mais qualificado para um segmento com um[!UICONTROL Profile Merge Rule]gráfico de dispositivo?**

Audience Manager mescla até 100 dispositivos ao avaliar segmentos com um gráfico de dispositivos [!UICONTROL Profile Merge Rule] . Se o sinal de cancelamento de segmento for emitido, o dispositivo atual e até 99 dispositivos adicionais serão removidos do segmento no destino. Para obter mais informações sobre a dessegmentação, consulte Regras de mesclagem de [Perfis e Processos](../features/profile-merge-rules/merge-rule-unsegment.md)de dessegmentação de dispositivos.

 

**Se um destino puder cancelar a segmentação de dispositivos, os dispositivos serão removidos dos segmentos usando[!UICONTROL Profile Merge Rules]um gráfico de dispositivos?**

Sim. Veja a explicação acima.

 

**Se eu criar um segmento com um gráfico de dispositivos[!UICONTROL Profile Merge Rule]que usa um segmento e ele estiver usando dados em tempo real e integrados, meu segmento será atualizado à medida que os dados integrados forem alterados?**

Sim.

 

**As estimativas de tamanho de segmento incluem dispositivos que se qualificam para um segmento com base nas conexões fornecidas por um[!UICONTROL Profile Merge Rule]que usa uma opção de gráfico de dispositivo?**

Não. Consulte as definições para o [!UICONTROL Estimated Real-Time Population] e [!UICONTROL Estimated Total Population] em Dados de [características e preenchimento de segmentos no Construtor](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/segments/segment-builder-data.html)de segmentos.

 

**Inclui dispositivos que se qualificam para um segmento com base nas conexões fornecidas por um[!UICONTROL Addressable Audiences][!UICONTROL Profile Merge Rule]que usa uma opção de gráfico de dispositivo?**

Sim.

 

**Se um segmento usar um com[!UICONTROL Profile Merge Rule]e as características[!UICONTROL No Cross-Device Profile]que qualificam dispositivos para o segmento forem armazenadas apenas no perfil entre dispositivos, a população total do segmento será 0?**

Sim. Audience Manager não contará as características armazenadas no perfil entre dispositivos na avaliação de segmentos quando a Regra de mesclagem de Perfis estiver definida como [!UICONTROL No Cross-Device Profile].

 

## Frequência da característica, gráficos do dispositivo e regras de mesclagem de Perfis {#trait-freq-device-rules}

**Como[!DNL Audience Manager]calcular a frequência de características com um gráfico de dispositivos[!UICONTROL Profile Merge Rule]que usa um gráfico de dispositivos?**

A frequência da característica é definida pela soma do número de qualificações para uma característica específica em vários dispositivos. Para ajudá-lo a entender isso, consulte o seguinte caso de uso.

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
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">O dispositivo A e o dispositivo B são vinculados por um gráfico de dispositivo. </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">Você tem uma Regra <span class="wintitle"> de mesclagem de</span> Perfis que usa uma opção de gráfico de dispositivo. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">Um único segmento (Segmento 1) composto por um único traço (Caractere 1), onde a característica 1 tem uma frequência de 8. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ações</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> O Audience Manager</span> lê e mescla os perfis do dispositivo para o Dispositivo A e o Dispositivo B. A partir disso, vemos o seguinte: </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">O dispositivo A qualificou-se para a característica 1 três vezes. Tem uma frequência de 3 para a característica 1. </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">O dispositivo B qualificou-se para a característica 1 cinco vezes. Tem uma frequência de 5 para a característica 1. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> soma a frequência da característica 1 e utiliza 8 (3 + 5 = 8) para decidir a qualificação de segmentos. O dispositivo A e o dispositivo B se qualificam para o segmento 1 porque ele tem uma frequência de 8. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

## Relatórios, gráficos de dispositivo e regras de mesclagem de Perfis {#reports-device-graphs-rules}

**Posso ver o número de dispositivos que podem ser acessados por um dispositivo[!UICONTROL Profile Merge Rule]que usa um gráfico?**

Sim. Os relatórios retornam dados no [!UICONTROL Profile Merge Rule] nível. Os dados do relatório são atualizados diariamente. Os dados são baseados nos dispositivos vistos em sua conta, não nos vinculados por um gráfico de dispositivos. Consulte Métricas [de relatório para Regras](../features/profile-merge-rules/profile-link-metrics.md)de mesclagem de Perfis.

 

**Posso ver o número de dispositivos qualificados para um segmento específico em tempo *real*com[!UICONTROL Profile Merge Rules]o uso de um gráfico de dispositivo?**

Sim. A métrica de população em tempo real captura as qualificações de segmento do dispositivo atual (o dispositivo visto em tempo real) usando os perfis de todos os dispositivos vinculados por um gráfico de dispositivo.

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
   <td colname="col2"> <p>Suponha que tenhamos: </p> <p> 
     <ul id="ul_B8B627FBF6A04C0CAE6C8543EA3EA56D"> 
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">Segmento 1 baseado nessas características e lógica de qualificação: Segmento 1 = Traço A e Traço B e Traço C. </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3 perfis de dispositivo: Dispositivo 1 (dispositivo atual), Dispositivo 2 (gráfico do dispositivo), Dispositivo 3 (gráfico do dispositivo). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ações</b> </p> </td> 
   <td colname="col2"> <p>Cada característica disponível está associada a um dispositivo: </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">Dispositivo 1: Traço A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">Dispositivo 2: Traço B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">Dispositivo 3: Traço C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p>Dados os elementos anteriores, a população total do Segmento 1 é uma. </p> <p>Nesse caso, a Regra <span class="wintitle"> de mesclagem de</span> Perfis usa todos os dispositivos e suas características para decidir a qualificação de segmentos. Isso significa que os dispositivos 1, 2 e 3 estão qualificados para o Segmento 1, mas, como mencionado acima, somente o Dispositivo 1 está incluído na população de segmentos em tempo real. Isso ocorre porque: </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">O dispositivo 1 é o dispositivo atual que interage com os Audience Manager <span class="wintitle"> Data Collection Servers</span> (<span class="wintitle"> DCS</span>) em tempo real. </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">Os dispositivos 2 e 3 são associados ao Dispositivo 1 por um gráfico de dispositivo, mas não interagem com o DCS ao mesmo tempo que o Dispositivo 1. </li> 
     </ul> </p> <p>Como resultado, os Dispositivos 2 e 3 não são incluídos na métrica de população do segmento em tempo real. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**É possível ver o número total de dispositivos qualificados para um segmento específico com um gráfico de dispositivo[!UICONTROL Profile Merge Rule]que usa um gráfico de dispositivo?**

Sim. A métrica de preenchimento total do segmento inclui os dispositivos adicionais que se qualificaram para um segmento com base nas conexões de um gráfico de dispositivo.

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
   <td colname="col2"> <p>Suponha que tenhamos: </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">Segmento 1 baseado nessas características e lógica de qualificação: Segmento 1 = Traço A e Traço B e Traço C. </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3 perfis de dispositivo: Dispositivo 1 (dispositivo atual), Dispositivo 2 (gráfico do dispositivo), Dispositivo 3 (gráfico do dispositivo). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Associações</b> </p> </td> 
   <td colname="col2"> <p>Cada característica disponível está associada a um dispositivo: </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">Dispositivo 1: Traço A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">Dispositivo 2: Traço B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">Dispositivo 3: Traço C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p>Dados os elementos anteriores, a população total do segmento 1 é de três (3). </p> <p>Nesse caso, a Regra <span class="wintitle"> de mesclagem de</span> Perfis usa todos os dispositivos e suas características para decidir a qualificação de segmentos. Isso significa que os dispositivos 1, 2 e 3 se qualificam para o Segmento 1 e todos os três estão incluídos na população total. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**Os dispositivos que se qualificam para um segmento com um gráfico de dispositivo[!UICONTROL Profile Merge Rule]incluído nos[!UICONTROL Interactive]relatórios,[!UICONTROL Overlap]relatórios e[!UICONTROL Audience Optimization]relatórios?**

Não.

**Por que vejo uma população de segmentos zero para exportações de segmentos para a Adobe Campaign após 16 de março de 2020?**

No final de 2019, lançamos uma série de melhorias nas Regras de mesclagem de Perfis para melhorar a precisão dos arquivos em lote gerados com IDs de vários dispositivos. Esses aprimoramentos serão rigorosamente respeitados em sua instância do Audience Manager a partir de segunda-feira, 16 de março de 2020. Consequentemente, os segmentos mapeados para um destino usando IDs entre dispositivos pararão de produzir exportações em algumas configurações de Regras de mesclagem de Perfis.

Para garantir a integração correta entre a instância do Audience Manager e os destinos usando IDs de dispositivos cruzados, como o Adobe Campaign, verifique se você atende aos seguintes requisitos:

1. Revise a Regra de mesclagem de Perfil usada pelos segmentos mapeados para o destino da ID declarada do Adobe Campaign. A regra de mesclagem de Perfis deve usar a [!UICONTROL Last Authenticated Profile] opção, para que todos os perfis autenticados possam ser incluídos nas exportações. Se a Regra de mesclagem de Perfis estiver usando uma opção diferente, alterne para [!UICONTROL Last Authenticated Profile].
2. Selecione a fonte de dados de ID declarada do Adobe Campaign nas configurações da Regra de mesclagem do Perfil.

>[!NOTE]
>
> Aumentamos o limite da Regra de mesclagem de Perfil em 1 para clientes que enfrentam essa situação, para que você possa criar uma Regra de mesclagem de Perfis dedicada para os segmentos mapeados para o destino da ID declarada de Adobe Campaign, sem alterar as Regras de mesclagem de Perfis para outros casos de uso.

>[!MORELIKETHIS]
>
>* [Link de perfil](../features/profile-merge-rules/profile-link-use-case.md)

