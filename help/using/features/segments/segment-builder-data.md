---
description: Adicione e remova características no Construtor de segmentos para ver as populações de características reais junto com os dados de população de segmentos atuais e estimados. Os dados estimados do tamanho da população ajudam a criar o segmento certo para sua campanha.
seo-description: Adicione e remova características no Construtor de segmentos para ver as populações de características reais junto com os dados de população de segmentos atuais e estimados. Os dados estimados do tamanho da população ajudam a criar o segmento certo para sua campanha.
seo-title: Dados de características e preenchimento de segmentos no Construtor de segmentos
solution: Audience Manager
title: Dados de características e preenchimento de segmentos no Construtor de segmentos
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
translation-type: tm+mt
source-git-commit: 63d89cac2f18538f56e2f6d0f64257ea9b5788bd
workflow-type: tm+mt
source-wordcount: '1294'
ht-degree: 0%

---


# Trait and Segment Population Data in Segment Builder {#trait-and-segment-population-data-in-segment-builder}

Adicione e remova características para ver as populações de características reais, juntamente com dados de população de segmentos reais e estimados. [!UICONTROL Segment Builder] Os dados estimados do tamanho da população ajudam a criar o segmento certo para sua campanha.

## Dados de preenchimento de traços {#trait-population-data}

[!UICONTROL Segment Builder] mostra [!UICONTROL Total Trait Population] o último dia quando você adiciona uma característica a um segmento. Esses dados aparecem no campo azul ao redor da característica selecionada na [!UICONTROL Basic View] seção.

![](assets/trait-size.png)

A tabela a seguir define as métricas de preenchimento de características

<table id="table_9D837CF9ACA04D04BEE5925EC0B4A5D2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descrição </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> População total do traço</span> </p> </td>
   <td colname="col2"> <p>O número de IDs exclusivas que têm a característica selecionada em seus perfis. </p> </td>
  </tr> 
 </tbody> 
</table>

## Calculando populações de segmentos reais e estimados {#calculating-real-estimated-populations}

Quando você cria um novo segmento ou altera um segmento existente, o Audience Manager demora até 24 horas para exibir resultados para as populações de segmentos reais e totais.

No entanto, o Audience Manager pode estimar imediatamente o tamanho da população total e em tempo real do seu segmento. Estas estimativas baseiam-se em dados históricos de amostra e resultados de retorno no intervalo de confiança de 95%.

![](assets/confidence-interval.png)

Em [!UICONTROL Segment Builder], uma barra azul nos gráficos de população estimados indica os possíveis intervalos superior e inferior para o tamanho do segmento. Embora o desempenho anterior não garanta resultados futuros, os dados estimados podem ajudá-lo a entender o tamanho potencial de um segmento novo ou editado.

## Visão geral dos dados da população de segmentos {#segment-populations}

[!UICONTROL Segment Builder] mostra os dados de preenchimento do segmento à medida que você cria e edita segmentos.

* Para dados estimados de população de segmentos (tempo real e total), [!UICONTROL Segment Builder] não atualiza os gráficos automaticamente à medida que você adiciona ou remove características em um segmento. Clique **[!UICONTROL Calculate Estimates]** para ver (ou atualizar) os números de população estimados.

* Para dados reais (reais) de preenchimento de segmentos (em tempo real e total), [!UICONTROL Segment Builder] atualiza o gráfico de segmentos automaticamente quando você carrega um segmento existente. Para novos segmentos, ou quando você adiciona novas características a um segmento existente, os dados de população real não são atualizados até 24 horas após a criação do segmento.

![](assets/segment-data.png)

Consulte as definições abaixo para obter mais informações sobre dados estimados e reais sobre a população de segmentos.

## Dados de preenchimento de segmento estimado definidos {#estimated-segment-population}

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
   <td colname="col1"> <p> <span class="wintitle"> População em tempo real estimada (potencial) </span> </p> </td> 
   <td colname="col2"> <p>O número estimado de visitantes únicos vistos em tempo real para o intervalo de tempo especificado e que eram qualificados para o segmento no momento em que eram vistos pelo Audience Manager. </p> <p>No <span class="wintitle"> Construtor</span>de segmentos, as últimas populações de 30 dias para características (<span class="wintitle"> Total de populações</span>de características) podem ser diferentes para características e segmentos avaliados em tempo real. </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">Para características, a última métrica de 30 dias conta o número de usuários únicos que se qualificaram para essa característica nos últimos 30 dias. </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">Para segmentos avaliados em tempo real, a última métrica de 30 dias conta o número de usuários que se qualificaram para uma característica (nesse segmento) em algum momento do passado e que foram vistos novamente pela Audience Manager nos últimos 30 dias. Por exemplo, digamos que você tenha um usuário que se qualificou para uma característica 60 dias atrás e foi visto novamente há 10 dias. Nos dados, esse usuário não será adicionado à contagem de características porque ele primeiro se qualificou para a característica há mais de 30 dias. No entanto, eles serão incluídos na última contagem de 30 dias para os segmentos avaliados em tempo real. Isso ocorre porque eles se qualificaram para o segmento dentro do intervalo de 30 dias. </li>
     </ul> </p> <p> <p>Observação: A métrica Preenchimento <span class="wintitle"> em tempo real</span> estimado não inclui dispositivos que se qualificaram para um segmento com base nas conexões fornecidas por uma Regra <span class="wintitle"> de mesclagem de</span> Perfil que usa uma opção <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> de gráfico de</a>dispositivo. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> População Total Estimada (Potencial)</span> </p> </td> 
   <td colname="col2"> <p>O número estimado de visitantes únicos que podem estar em seu segmento novo ou modificado. Como em quase qualquer estimativa, o desempenho passado não garante resultados futuros, mas você pode usar o total estimado para: </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">Veja quantas pessoas um segmento novo ou revisado pode atingir enquanto você cria um segmento. </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">Ajuste o segmento dependendo de suas metas. Por exemplo, segmentos grandes são úteis para campanhas de reconhecimento de marca e segmentos menores são úteis para direcionamento ou redirecionamento de campanhas. </li> 
     </ul> </p> <p> <p>Observação: A métrica Preenchimento <span class="wintitle"> total</span> estimado não inclui dispositivos que se qualificaram para um segmento com base nas conexões fornecidas por uma Regra <span class="wintitle"> de mesclagem de</span> Perfil que usa uma opção <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> de gráfico de</a>dispositivo. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Dados de preenchimento de segmento existentes (reais) Definidos {#existing-segment-population}

[!UICONTROL Profile Merge Rules] afetam os números efetivos em tempo real e totais da população. Esses totais variam dependendo se o segmento pertencer a [!UICONTROL Profile Merge Rule] usa ou não uma opção de gráfico de dispositivo. Consulte também, Opções de Regra de Mesclagem de [Perfis Definidas](../../features/profile-merge-rules/merge-rule-definitions.md).

### Dados de preenchimento de segmento para regras de mesclagem sem uma opção de gráfico de dispositivo

A tabela a seguir define as métricas reais em tempo real e total de população quando seus segmentos são usados por um [!UICONTROL Profile Merge Rule] criado sem uma opção de gráfico de dispositivo. Estas são as configurações de opções do dispositivo **[!UICONTROL No Device Options]** e **[!UICONTROL Current Device Proflie]**.

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
   <td colname="col2"> <p>O número real de visitantes únicos vistos em tempo real para o intervalo de tempo especificado e que eram qualificados para o segmento no momento em que eram vistos pelo Audience Manager. </p> <p>No <span class="wintitle"> Construtor</span>de segmentos, as últimas populações de 30 dias para características (<span class="wintitle"> Total de populações</span>de características) podem ser diferentes para características e segmentos avaliados em tempo real. </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">Para características, a última métrica de 30 dias conta o número de usuários únicos que se qualificaram para essa característica nos últimos 30 dias. </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">Para segmentos avaliados em tempo real, a última métrica de 30 dias conta o número de usuários que se qualificaram para uma característica (nesse segmento) em algum momento do passado e que foram vistos novamente pela Audience Manager nos últimos 30 dias. Por exemplo, digamos que você tenha um usuário que se qualificou para uma característica 60 dias atrás e foi visto novamente há 10 dias. Nos dados, esse usuário não será adicionado à contagem de características porque ele primeiro se qualificou para a característica há mais de 30 dias. No entanto, eles serão incluídos na última contagem de 30 dias para os segmentos avaliados em tempo real. Isso ocorre porque eles se qualificaram para o segmento dentro do intervalo de 30 dias. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> População total (existente)</span> </p> </td> 
   <td colname="col2"> <p>O número real de visitantes únicos qualificados para o segmento a partir de ontem. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Dados de preenchimento de segmento para regras de mesclagem com uma opção de gráfico de dispositivo

A tabela a seguir define as métricas reais em tempo real e total de população quando seus segmentos são usados por um [!UICONTROL Profile Merge Rule] criado com uma opção de gráfico de dispositivo. Estas são as configurações de opções do dispositivo para [!UICONTROL Profile Link Device Graph]o, o gráfico do [!DNL Adobe] dispositivo e outras opções de gráficos de dispositivos de terceiros que estão disponíveis para você.

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
   <td colname="col2"> <p>O número real de dispositivos vistos em tempo real com perfis atuais que, quando mesclados com até 100 outros perfis de dispositivos conectados pelo gráfico de dispositivos, contém as características para qualificar-se para o segmento no momento em que foi visto pelo <span class="keyword"> Audience Manager</span>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> População total (existente)</span> </p> </td> 
   <td colname="col2"> <p>O número total de dispositivos com perfis que, quando mesclados com até 100 outros perfis de dispositivo conectados pelo gráfico de dispositivo, eram todos qualificados para o segmento. </p> </td>
  </tr>
 </tbody>
</table>

### Limitações devido a Expressões de recenticidade e frequência ao estimar as populações de segmentos

[!UICONTROL Segment Builder] suporta estimativas de tamanho de segmento para regras de segmento que contêm até 4 expressões recentes e de frequência. Escolher mais de 4 expressões de recenticidade e frequência ao criar uma regra de segmento faz com que o avaliador de segmentos mostre um erro ao estimar a população.

### Limitações devido às Regras de mesclagem ao estimar as populações de segmentos

Atualmente, há uma limitação conhecida porque nosso avaliador de tamanho de segmento não considera as regras de mesclagem de perfil. Por exemplo, observe os segmentos com a regra **** Sem Perfil autenticado + Perfil[de dispositivo atual para](../../features/profile-merge-rules/merge-rule-definitions.md)mesclar. Devido à forma como atualmente calculamos os números de estimativa de segmento, as populações estimadas incluirão perfis autenticados. No entanto, as populações de segmentos existentes ignorarão corretamente os perfis autenticados.

>[!MORELIKETHIS]
>
>* [Perguntas frequentes sobre Regras de mesclagem de Perfis e Gráfico de dispositivos](../../faq/faq-profile-merge.md)
>* [Link de perfil](../profile-merge-rules/merge-rules-overview.md)

