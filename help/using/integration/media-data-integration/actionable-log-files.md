---
description: Arquivos de registro acionáveis permitem capturar dados de mídia de arquivos de log do Google DCM e usar os dados para criar características no Audience Manager. Capture impressões, cliques e conversões de servidores de anúncios como características sem ter que usar chamadas de pixel.
keywords: logs acionáveis
seo-description: Arquivos de registro acionáveis permitem capturar dados de mídia de arquivos de log do Google DCM e usar os dados para criar características no Audience Manager. Capture impressões, cliques e conversões de servidores de anúncios como características sem ter que usar chamadas de pixel.
seo-title: Arquivo de registro acionável
solution: Audience Manager
title: Arquivo de registro acionável
uuid: 4 c 47615 f-ed 47-41 ba -8694-1 d 7 de 4 f 55 d 62
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Arquivo de registro acionável {#actionable-log-files}

[!UICONTROL Actionable Log Files] permite capturar dados de mídia de arquivos [!DNL Google DCM] de registro e usar os dados para criar características no Audience Manager. Capture impressões, cliques e conversões de servidores de anúncios como características sem ter que usar chamadas de pixel.

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *itálico*, colchetes `[ ]` `( )` etc.) neste documento indica elementos e opções do código. Consulte [Convenções de estilo para código e elementos de texto](../../reference/code-style-elements.md) para obter mais informações.

## Propósito {#purpose}

[!UICONTROL Actionable Log Files] simplificar a forma como capturar impressões, cliques e conversões de servidores de anúncios. Use this information for user segmentation without having to manually pixel media to send campaign attributes to [!DNL Audience Manager].

## Introdução {#getting-started}

To get started with [!UICONTROL Actionable Log Files], and to use our [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md), you need to import DCM log data into [!DNL Audience Manager]. See [Import DCM Data Files Into Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *and* contact your [!DNL Audience Manager] consultant.

If you are already importing [!UICONTROL DCM] log data into [!DNL Audience Manager], ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to enable [!UICONTROL Actionable Log Files] for you.

>[!NOTE] {importance = &quot;high&quot;}
>
>[!UICONTROL Actionable Log Files] funcionam somente com [!DNL Google DCM] arquivos de log.

## Working with Actionable Log Files {#working-with-actionable-log-files}

With [!UICONTROL Actionable Log Files], the information from [!DNL DCM] logs is captured in [!DNL Audience Manager] the same way that you would capture data from real-time website interactions. [!DNL Audience Manager] se conecta com seu [!DNL Google Cloud] armazenamento, analisa as informações de [!DNL DCM] logs e envia os dados de log como sinais acionáveis para nossos [servidores de coleta de dados](../../reference/system-components/components-data-collection.md#dcs-pcs).

Ainda é necessário configurar características baseadas em regras para capturar os sinais acionáveis. See how to set up rule-based traits either in the [Audience Manager UI](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) or using our [Bulk Management Tools](../../reference/bulk-management-tools/bulk-create.md). Scroll down to the [Actionable Signals](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) section for a list of all the keys you can use in rule-based traits.

For an average-sized [!DNL DCM] log file of 2 million lines, any traits created from actionable signals are realized within approximately one hour after we process the logs.

>[!IMPORTANT] {importance = &quot;high&quot;}
>
>We recommend implementing [!UICONTROL Actionable Log Files] *instead of*  [Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md). Desincentivamos o uso de ambas as opções, pois isso resulta em um aumento nas contagens de frequência para características.

## Actionable Signals {#actionable-signals}

Signals are the [smallest data units](../../reference/signal-trait-segment.md) in [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] permite capturar anunciantes, unidades de negócios, criação e valores de campanha em eventos de impressão, eventos de clique e eventos de conversão como sinais de [!DNL DCM] logs.

Lembre-se, para usar essas informações para criação e segmentação de público-alvo, de configurar as características baseadas em regras. The table lists the actionable signals from [!DNL DCM] log files:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Sinal </th> 
   <th colname="col2" class="entry"> Descrição </th> 
   <th colname="col3" class="entry"> Exemplo de valor </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ event</code> </p> </td> 
   <td colname="col2"> <p>Indica o tipo de evento do DCM. </p> <p>Os valores aceitos são: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_ event = imp</code> para impressões. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_ event = clique</code> para cliques. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_ event = conv</code> para conversões. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ conversion</code> </p> </td> 
   <td colname="col2"> <p>Disponível apenas para eventos de conversão. </p> <p>Representa a ID numérica da atividade de conversão no DCM. Este campo mapeia para a ID de atividade do DCM. </p> <p> <p>Dica: Você pode capturar atividades de conversão múltiplas ou específicas do DCM. Create traits using <code> d_conversion = activity ID</code> for each conversion activity from DCM. </p> </p> </td> 
   <td colname="col3"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ conversiontype</code> </p> </td> 
   <td colname="col2"> <p>Disponível apenas para eventos de conversão. </p> <p>Este campo mapeia para a ID de conversão no DCM. Indica a atividade anterior à conversão do usuário do DCM. </p> <p>Os valores aceitos são: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> para conversões após clique. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> para conversões pós-impressão. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> para conversões não correspondentes. A conversão não pode corresponder a uma atividade anterior. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> 0,1,2</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ adsrc</code> </p> </td> 
   <td colname="col2"> <p>ID do anunciante. Este campo mapeia para a ID do grupo de anunciante a partir do DCM. </p> </td> 
   <td colname="col3"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ bu</code> </p> </td> 
   <td colname="col2"> <p>ID da unidade de negócios. Este campo mapeia para a ID de anunciante do DCM. </p> </td> 
   <td colname="col3"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ campaign</code> </p> </td> 
   <td colname="col2"> <p>A ID da campanha fornecida pelo DCM. </p> </td> 
   <td colname="col3"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ creative</code> </p> </td> 
   <td colname="col2"> <p>A ID de criação fornecida pelo DCM. </p> </td> 
   <td colname="col3"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ src</code> </p> </td> 
   <td colname="col2"> <p>A ID da fonte de dados usada para capturar dados do DCM. See <a href="../../features/manage-datasources.md#create-data-source"> How to Create a Data Source</a>. </p> </td> 
   <td colname="col3"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

The signals described in the table are captured in [!DNL Audience Manager] like a real-time `HTTP` call. The example call below contains information on a conversion event from [!DNL DCM]. Calls do not necessarily have to include *all* the signals in the example call.

```
https://sample.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

>[!NOTE] {importance = &quot;high&quot;}
>
>The event timestamp provided in the [!DNL DCM] logs will be honored and passed to the [!UICONTROL Data Collection Servers].
>
>* If a timestamp isn&#39;t available for a data row in the [!DNL DCM] log file, we use the time of the `HTTP` call as the event timestamp.
>* If the data row in the [!DNL DCM] log file contains a malformed timestamp, we ignore the entire row.


## Casos de uso {#use-cases}

One benefit of implementing [!UICONTROL Actionable Log Files] is the option to apply [recency and frequency](../../features/segments/recency-and-frequency.md) controls to any [rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) that contain actionable signals. Isso permite, por exemplo, que você capitfique o número de vezes que um usuário recebe um anúncio específico em uma campanha de mídia. Outros casos de uso incluem:

### Usuários do redirecionamento

Redirecione os usuários que viram o anúncio 123, mas não clicaram ou convertem e mostraram a creative 456. Fazer isso:

1. Crie uma característica para capturar usuários que viram a criação. Let&#39;s say you name the trait [!DNL Creative Trait 123]. Use a regra de características:

   `d_creative == 123 AND d_event == imp`

1. Crie uma característica para capturar usuários que clicam ou convertem. Let&#39;s say you name this one [!DNL Click and Converter]. Use a regra de características:

   `d_event == click OR d_event=conv`

1. Crie um segmento para preencher com usuários que viram o anúncio 123, mas não clicaram ou convertem. Name it [!DNL Retarget Users] and use the segment rule:

   `Creative Trait 123 AND NOT Click and Converter`

1. Map the segment [!DNL Retarget Users] to a destination and target users in the destination with creative 456.

### Usar atividade do DCM Floodlight nos Relatórios de otimização de público-alvo ou no Audience Lab

[As tags Floodlight](https://support.google.com/dcm/partner/answer/4293719?hl=en) permitem que os anunciantes rastreiem conversões de usuários. With [!UICONTROL Actionable Log Files], you can track the [!DNL DCM] conversions in the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md) or in [Audience Lab](../../features/audience-lab/audience-lab.md):

1. Crie uma característica e use a seguinte regra de característica para capturar uma conversão nos logs do servidor de anúncios:

   `d_event == conv AND d_conversion == 123`

   When creating the trait in the Audience Manager [!UICONTROL UI], select [!UICONTROL Conversion] as the [!UICONTROL Event Type].

2. Once you have created the trait, the conversion will begin to be reported against in the [!UICONTROL Audience Optimization Reports] and in [!UICONTROL Audience Lab].

>[!MORE_ LIKE_ THIS]
>
>* [Importar arquivos de dados DCM para o Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Relatórios de otimização de público-alvo](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

