---
description: Adicione e remova características no Construtor de segmentos para ver as populações de características reais junto com os dados de população de segmentos reais e estimados. Os dados de tamanho estimado da população ajudam a criar o segmento certo para a campanha.
seo-description: Add and remove traits in Segment Builder to see actual trait populations along with actual and estimated segment population data. The estimated population size data helps you build the right segment for your campaign.
seo-title: Trait and Segment Population Data in Segment Builder
solution: Audience Manager
title: Dados de população de características e segmentos no Construtor de segmentos
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
feature: Segments
exl-id: f8953d10-8a31-4c07-8d96-169c30a21de0
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1213'
ht-degree: 1%

---

# Dados de População de [!UICONTROL Trait] e [!UICONTROL Segment] em [!UICONTROL Segment Builder] {#trait-and-segment-population-data-in-segment-builder}

Adicione e remova [!UICONTROL traits] em [!UICONTROL Segment Builder] para ver as populações reais de [!UICONTROL trait] junto com os dados de população de segmentos reais e estimados. Os dados de tamanho estimado da população ajudam a criar o segmento certo para a campanha.

## Dados de população [!UICONTROL Trait] {#trait-population-data}

[!UICONTROL Segment Builder] mostra [!UICONTROL Total Trait Population] do último dia quando você adiciona um [!UICONTROL trait] a um segmento. Esses dados aparecem no campo azul ao redor do [!UICONTROL trait] selecionado na seção [!UICONTROL Basic View].

![](assets/trait-size.png)

A tabela a seguir define as métricas de população de características:


| Métrica | Descrição |
|---------|----------|
| [!UICONTROL Total Trait Population] | O número de IDs exclusivas que têm a característica selecionada em seus perfis. |


## Cálculo de populações de segmentos reais e estimados {#calculating-real-estimated-populations}

Ao criar um novo segmento ou alterar um segmento existente, o Audience Manager leva até 24 horas para exibir resultados para as populações reais e totais de segmentos.

No entanto, o Audience Manager pode estimar imediatamente o tamanho da população total e em tempo real do seu segmento. Essas estimativas são baseadas em dados históricos amostrados e retornam resultados no intervalo de confiança de 95%.

![](assets/confidence-interval.png)

Em [!UICONTROL Segment Builder], uma barra azul nos gráficos de população estimados indica os intervalos superiores e inferiores possíveis para o tamanho do segmento. Embora o desempenho passado não garanta resultados futuros, os dados estimados podem ajudar a entender o tamanho potencial de um segmento novo ou editado.

## Visão geral dos dados de população do segmento {#segment-populations}

O [!UICONTROL Segment Builder] mostra os dados de preenchimento do segmento à medida que você cria e edita segmentos.

* Para dados estimados da população de segmentos (tempo real e total), o [!UICONTROL Segment Builder] não atualiza os gráficos automaticamente à medida que você adiciona ou remove características em um segmento. Clique em **[!UICONTROL Calculate Estimates]** para ver (ou atualizar) os números de população estimados.

* Para dados de população de segmentos reais (em tempo real e total), o [!UICONTROL Segment Builder] atualiza o gráfico de segmentos automaticamente quando você carrega um segmento existente. Para novos segmentos, ou quando você adiciona novas características a um segmento existente, os dados da população real não são atualizados até 24 horas após a criação do segmento.

![](assets/segment-data.png)

Consulte as definições abaixo para obter mais informações sobre dados estimados e reais da população do segmento.

## Definição dos Dados de População do Segmento Estimado {#estimated-segment-population}

A tabela a seguir define as métricas de população estimadas.

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> População Estimada Em Tempo Real (Potencial) </span> </p> </td> 
   <td colname="col2"> <p>O número estimado de visitantes únicos vistos em tempo real pelo intervalo de tempo especificado e que foram qualificados para o segmento no momento em que foram vistos pelo Audience Manager. </p> <p>No <span class="wintitle"> Construtor de segmentos</span>, as últimas populações de 30 dias para características (<span class="wintitle"> Populações de características totais</span>) podem ser diferentes para características e segmentos avaliados em tempo real. </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">Para características, a última métrica de 30 dias conta o número de usuários únicos que se qualificaram para essa característica nos últimos 30 dias. </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">Para segmentos avaliados em tempo real, a última métrica de 30 dias conta o número de usuários que se qualificaram para uma característica (nesse segmento) em algum momento no passado e foram vistos novamente pelo Audience Manager nos últimos 30 dias. Por exemplo, digamos que você tenha um usuário que se qualificou para uma característica de 60 dias atrás e foi visto novamente há 10 dias. Nos dados, esse usuário não será adicionado à contagem de características porque se qualificou pela primeira vez para a característica há mais de 30 dias. No entanto, elas serão incluídas na última contagem de 30 dias para os segmentos avaliados em tempo real. Isso ocorre porque elas se qualificaram para o segmento dentro do intervalo de 30 dias. </li>
     </ul> </p> <p> <p>Observação: a métrica <span class="wintitle"> População em Tempo Real Estimada</span> não inclui dispositivos que se qualificaram para um segmento com base nas conexões fornecidas por uma <span class="wintitle"> Regra de Mesclagem de Perfis</span> que usa uma <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> opção de gráfico de dispositivos</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> População Total Estimada (Potencial)</span> </p> </td> 
   <td colname="col2"> <p>O número estimado de visitantes únicos que podem estar em seu segmento novo ou modificado. Como em quase qualquer estimativa, o desempenho passado não garante resultados futuros, mas você pode usar o total estimado para: </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">Veja quantas pessoas um segmento novo ou revisado pode alcançar ao criar um segmento. </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">Ajuste o segmento dependendo de suas metas. Por exemplo, segmentos grandes são úteis para campanhas de reconhecimento de marca e segmentos menores são úteis para campanhas de direcionamento ou redirecionamento focadas. </li> 
     </ul> </p> <p> <p>Observação: a métrica <span class="wintitle"> População Total estimada</span> não inclui dispositivos que se qualificaram para um segmento com base nas conexões fornecidas por uma <span class="wintitle"> Regra de mesclagem de perfis</span> que usa uma <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> opção de gráfico de dispositivos</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Definição de Dados de População de Segmento Existentes (Reais) {#existing-segment-population}

[!UICONTROL Profile Merge Rules] afetam os números de população total e em tempo real. Esses totais variam dependendo se o [!UICONTROL Profile Merge Rule] ao qual um segmento pertence usa ou não uma opção de gráfico de dispositivos. Consulte também [Definição das opções de regra de mesclagem de perfis](../../features/profile-merge-rules/merge-rule-definitions.md).

### Segmentar Dados de População para [!UICONTROL Merge Rules] sem um [!UICONTROL Device Graph Option]

A tabela a seguir define as métricas de população total e em tempo real quando seus segmentos são usados por um [!UICONTROL Profile Merge Rule] criado sem uma opção [!UICONTROL device graph]. Estas são as configurações de opções de dispositivo **[!UICONTROL No Device Options]** e **[!UICONTROL Current Device Proflie]**.

<table id="table_A18C973855DB46A0B39B81F32E0E7540"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> População em Tempo Real <span class="wintitle"> (Existente) </span> </p> </td> 
   <td colname="col2"> <p>O número real de visitantes únicos vistos em tempo real pelo intervalo de tempo especificado e que foram qualificados para o segmento no momento em que foram vistos pelo Audience Manager. </p> <p>No <span class="wintitle"> Construtor de segmentos</span>, as últimas populações de 30 dias para características (<span class="wintitle"> Populações de características totais</span>) podem ser diferentes para características e segmentos avaliados em tempo real. </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">Para características, a última métrica de 30 dias conta o número de usuários únicos que se qualificaram para essa característica nos últimos 30 dias. </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">Para segmentos avaliados em tempo real, a última métrica de 30 dias conta o número de usuários que se qualificaram para uma característica (nesse segmento) em algum momento no passado e foram vistos novamente pelo Audience Manager nos últimos 30 dias. Por exemplo, digamos que você tenha um usuário que se qualificou para uma característica de 60 dias atrás e foi visto novamente há 10 dias. Nos dados, esse usuário não será adicionado à contagem de características porque se qualificou pela primeira vez para a característica há mais de 30 dias. No entanto, elas serão incluídas na última contagem de 30 dias para os segmentos avaliados em tempo real. Isso ocorre porque elas se qualificaram para o segmento dentro do intervalo de 30 dias. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> População Total (Existente)</span> </p> </td> 
   <td colname="col2"> <p>O número real de visitantes únicos qualificados para o segmento desde ontem. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Segmentar Dados de População para [!UICONTROL Merge Rules] com uma Opção [!UICONTROL Device Graph]

A tabela a seguir define as métricas de população total e em tempo real quando seus segmentos são usados por um [!UICONTROL Profile Merge Rule] criado com uma opção [!DNL device graph]. Estas são as configurações de opções de dispositivo para o [!UICONTROL Profile Link Device Graph], o [!DNL Adobe] [!DNL device graph] e outras opções de [!DNL device graph] de terceiros que estão disponíveis para você.


| Coluna A | Coluna B |
|---------|----------|
| [!UICONTROL Real-Time Population (Existing)] | O número real de dispositivos vistos em tempo real com perfis atuais que, quando mesclados com até 100 outros perfis de dispositivos conectados pelo gráfico do dispositivo, contêm as características para se qualificar para o segmento no momento em que foi visto pelo Audience Manager. |
| [!UICONTROL Total Population (Existing)] | O número total de dispositivos com perfis que, quando mesclados com até 100 outros perfis de dispositivos conectados pelo gráfico de dispositivos, eram todos qualificados para o segmento. |

### Limitações devido a expressões de recenticidade e frequência ao estimar populações de segmentos

O [!UICONTROL Segment Builder] oferece suporte a estimativas de tamanho de segmento para regras de segmento que contêm até quatro expressões de recenticidade e frequência. Escolher mais de quatro expressões de recenticidade e frequência ao criar uma regra de segmento faz com que o avaliador de segmento mostre um erro ao estimar a população.

### Limitações devido a [!UICONTROL Merge Rules] ao estimar populações de segmentos

Atualmente, há uma limitação conhecida porque nosso avaliador de tamanho de segmento não contabiliza [!UICONTROL profile merge rules]. Por exemplo, examine os segmentos com a **[!UICONTROL No Authenticated Profile + Current Device Profile]** [regra de mesclagem](../../features/profile-merge-rules/merge-rule-definitions.md). Devido à maneira como calculamos os números de estimativa do segmento atualmente, as populações estimadas incluirão perfis autenticados. No entanto, as populações de segmentos existentes ignorarão corretamente os perfis autenticados.

>[!MORELIKETHIS]
>
>* [Perguntas frequentes sobre regras de mesclagem de perfis e gráfico de dispositivos](../../faq/faq-profile-merge.md)
>* [Link de perfil](../profile-merge-rules/merge-rules-overview.md)
