---
description: Adicione e remova características no Construtor de segmentos para ver as populações de característica reais juntamente com os dados reais de preenchimento do segmento. Os dados de tamanho de população previstos ajudam a construir o segmento certo para sua campanha.
seo-description: Adicione e remova características no Construtor de segmentos para ver as populações de característica reais juntamente com os dados reais de preenchimento do segmento. Os dados de tamanho de população previstos ajudam a construir o segmento certo para sua campanha.
seo-title: Dados de características e preenchimento de segmentos no Construtor de segmentos
solution: Audience Manager
title: Dados de características e preenchimento de segmentos no Construtor de segmentos
uuid: e 1 e 59 c 0 a-b 4 c 7-4 cad -8485-3667 e 0 a 95 e 83
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Trait and Segment Population Data in Segment Builder {#trait-and-segment-population-data-in-segment-builder}

Add and remove traits in [!UICONTROL Segment Builder] to see actual trait populations along with actual and estimated segment population data. Os dados de tamanho de população previstos ajudam a construir o segmento certo para sua campanha.

## Trait Population Data {#trait-population-data}

[!UICONTROL Segment Builder] mostra o [!UICONTROL Total Trait Population] último dia quando você adiciona uma característica a um segmento. This data appears in the blue field around your selected trait in the [!UICONTROL Basic View] section.

![](assets/trait-size.png)

A tabela a seguir define as métricas de preenchimento da população

<table id="table_9D837CF9ACA04D04BEE5925EC0B4A5D2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descrição </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> População de característica total</span> </p> </td>
   <td colname="col2"> <p>O número de IDs exclusivas que têm a característica selecionada em seu perfil. </p> </td>
  </tr> 
 </tbody> 
</table>

## Calculating Real and Estimated Segment Populations {#calculating-real-estimated-populations}

Ao criar um novo segmento ou alterar um segmento existente, o Audience Manager demora até 24 horas para exibir resultados para as populações reais de segmentos e de segmentos em tempo real.

No entanto, o Audience Manager pode estimar imediatamente o tamanho em tempo real e o tamanho total de preenchimento do seu segmento. Essas estimativas têm por base dados históricos amostrados e resultados de retorno no intervalo de confiança de 95%.

![](assets/confidence-interval.png)

In [!UICONTROL Segment Builder], a blue bar on the estimated population graphs indicates the possible upper and lower ranges for segment size. Embora o desempenho passado não garanta resultados futuros, os dados estimados podem ajudar você a entender o tamanho potencial de um segmento novo ou editado.

## Segment Population Data Overview {#segment-populations}

[!UICONTROL Segment Builder] mostra os dados de preenchimento à medida que você cria e edita segmentos.

* For estimated segment population data (real-time and total), [!UICONTROL Segment Builder] does not update the graphs automatically as you add or remove traits in a segment. Click **[!UICONTROL Calculate Estimates]** to see (or refresh) the estimated population numbers.

* For actual (real) segment population data (real-time and total), [!UICONTROL Segment Builder] updates the segment graph automatically when you load an existing segment. Para novos segmentos, ou quando você adiciona novas características a um segmento existente, os dados reais da população não são atualizados até 24 horas após a criação do segmento.

![](assets/segment-data.png)

Consulte as definições abaixo para obter mais informações sobre os dados de população de segmentos previstos e reais.

## Estimated Segment Population Data Defined {#estimated-segment-population}

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
   <td colname="col1"> <p> <span class="wintitle"> População estimada em tempo real (potencial) </span> </p> </td> 
   <td colname="col2"> <p>O número estimado de visitantes únicos vistos em tempo real para o intervalo de tempo especificado e que foram qualificados para o segmento no momento em que foram vistos pelo Audience Manager. </p> <p>In <span class="wintitle"> Segment Builder</span>, the last 30-day populations for traits (<span class="wintitle"> Total Trait Populations</span>), can be different for traits and segments evaluated in real-times. </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">Para características, a última métrica de 30 dias conta o número de usuários únicos que qualificados para essa característica nos últimos 30 dias. </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">Para segmentos avaliados em tempo real, a última métrica de 30 dias conta o número de usuários que se qualificaram para uma característica (nesse segmento) em algum momento no passado e foram vistos novamente pelo Audience Manager nos últimos 30 dias. Por exemplo, digamos que você tenha um usuário que qualificado para uma característica 60 dias atrás e foi visto novamente há 10 dias. Nos dados, esse usuário não será adicionado à contagem de características porque eles primeiro qualificados para a característica há mais de 30 dias. No entanto, serão incluídos nos últimos 30 dias para os segmentos avaliados em tempo real. Isso ocorre porque eles se qualificaram para o segmento dentro do intervalo de tempo de 30 dias. </li>
     </ul> </p> <p> <p>Note: The <span class="wintitle"> Estimated Real-Time Population</span> metric does not include devices that have qualified for a segment based on connections provided by a <span class="wintitle"> Profile Merge Rule</span> that uses a <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> device graph option</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> População total estimada (Potencial)</span> </p> </td> 
   <td colname="col2"> <p>O número estimado de visitantes únicos que podem estar no seu segmento novo ou modificado. Como em praticamente qualquer estimativa, o desempenho passado não garante resultados futuros, mas você pode usar o total estimado para: </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">Veja quantas pessoas um segmento novo ou revisado pode atingir à medida que você cria um segmento. </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">Ajuste o segmento dependendo de suas metas. Por exemplo, segmentos grandes são úteis para campanhas de identificação de marca e segmentos menores são úteis para direcionamento focado ou campanhas de redirecionamento. </li> 
     </ul> </p> <p> <p>Note: The <span class="wintitle"> Estimated Total Population</span> metric does not include devices that have qualified for a segment based on connections provided by a <span class="wintitle"> Profile Merge Rule</span> that uses a <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> device graph option</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Existing (Actual) Segment Population Data Defined {#existing-segment-population}

[!UICONTROL Profile Merge Rules] afeta os números reais de população real e total. These totals vary depending on if the [!UICONTROL Profile Merge Rule] a segment belongs to uses a device graph option or not. See also, [Profile Merge Rule Options Defined](../../features/profile-merge-rules/merge-rule-definitions.md).

### Dados de preenchimento de segmentos para regras de mesclagem sem uma opção de gráfico de dispositivo

The following table defines the actual real-time and total population metrics when your segments are used by a [!UICONTROL Profile Merge Rule] created without a device graph option. These are the device options settings **[!UICONTROL No Device Options]** and **[!UICONTROL Current Device Proflie]**.

<table id="table_A18C973855DB46A0B39B81F32E0E7540"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> População em tempo real (existente)</span> </p> </td> 
   <td colname="col2"> <p>O número real de visitantes únicos vistos em tempo real para o intervalo de tempo especificado e que estavam qualificados para o segmento no momento em que foram vistos pelo Audience Manager. </p> <p>In <span class="wintitle"> Segment Builder</span>, the last 30-day populations for traits (<span class="wintitle"> Total Trait Populations</span>), can be different for traits and segments evaluated in real-time. </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">Para características, a última métrica de 30 dias conta o número de usuários únicos que qualificados para essa característica nos últimos 30 dias. </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">Para segmentos avaliados em tempo real, a última métrica de 30 dias conta o número de usuários que se qualificaram para uma característica (nesse segmento) em algum momento no passado e foram vistos novamente pelo Audience Manager nos últimos 30 dias. Por exemplo, digamos que você tenha um usuário que qualificado para uma característica 60 dias atrás e foi visto novamente há 10 dias. Nos dados, esse usuário não será adicionado à contagem de características porque eles primeiro qualificados para a característica há mais de 30 dias. No entanto, serão incluídos nos últimos 30 dias para os segmentos avaliados em tempo real. Isso ocorre porque eles se qualificaram para o segmento dentro do intervalo de tempo de 30 dias. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> População total (existente)</span> </p> </td> 
   <td colname="col2"> <p>O número real de visitantes únicos que foram qualificados para o segmento a partir de ontem. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Dados de preenchimento de segmento para mesclar regras com uma opção de gráfico de dispositivo

The following table defines the actual real-time and total population metrics when your segments are used by a [!UICONTROL Profile Merge Rule] created with a device graph option. These are the device options settings for the [!UICONTROL Profile Link Device Graph], the [!DNL Adobe] device graph, and other third-party device graph choices that are available to you.

<table id="table_157EC6E5B5C44EB899854CA10B090F60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> População em tempo real (existente)</span> </p> </td> 
   <td colname="col2"> <p>The actual number of devices seen in real-time with current profiles that, when merged with up to 3-other device profiles connected by the device graph, contains the traits to qualify for the segment the moment it was seen by <span class="keyword"> Audience Manager</span>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> População total (existente)</span> </p> </td> 
   <td colname="col2"> <p>O número total de dispositivos com perfis que, quando unidos com até 3 outros perfis de dispositivo conectados pelo gráfico do dispositivo, eram todos qualificados para o segmento. </p> </td>
  </tr>
 </tbody>
</table>

### Limitações devido a expressões Recenticidade e Frequência ao Estimar Populações de Segmentos

[!UICONTROL Segment Builder] suporta as estimações de tamanho do segmento para regras de segmento que contêm até 4 expressões de tempo decorrido e frequência. Escolher mais de 4 expressões recenticidade e frequência ao construir uma regra de segmento faz com que o avaliador de segmento mostre um erro ao estimar a população.

### Limitações devido à mesclagem de regras ao estimar populações de segmentos

Atualmente, há uma limitação conhecida porque o avaliador de tamanho de segmento não conta regras de mesclagem de perfil. For example, look at segments with the **No Authenticated Profile + Current Device Profile** [merge rule](../../features/profile-merge-rules/merge-rule-definitions.md). Devido à forma como atualmente computamos os números de estimativa de segmentos, as populações estimadas incluirão perfis autenticados. No entanto, as populações de segmento existentes ignorarão corretamente os perfis autenticados.

>[!MORE_ LIKE_ THIS]
>
>* [Regras de mesclagem de perfil e perguntas frequentes sobre o gráfico de dispositivos](../../faq/faq-profile-merge.md)
>* [Link de perfil](../../features/profile-merge-rules/merge-rules-overview.md)

