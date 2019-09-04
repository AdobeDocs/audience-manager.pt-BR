---
description: Arquivos de registro acionáveis permitem capturar dados de mídia de arquivos de log do Google DCM e usar os dados para criar características no Audience Manager. Capture impressões, cliques e conversões de servidores de anúncios como características sem ter que usar chamadas de pixel.
keywords: logs acionáveis
seo-description: Arquivos de registro acionáveis permitem capturar dados de mídia de arquivos de log do Google DCM e usar os dados para criar características no Audience Manager. Capture impressões, cliques e conversões de servidores de anúncios como características sem ter que usar chamadas de pixel.
seo-title: Arquivo de registro acionável
solution: Audience Manager
title: Arquivo de registro acionável
uuid: 4 c 47615 f-ed 47-41 ba -8694-1 d 7 de 4 f 55 d 62
translation-type: tm+mt
source-git-commit: dbc96973ed2214d171fe32b7e1314d40c22c2d79

---


# Arquivo de registro acionável {#actionable-log-files}

[!UICONTROL Actionable Log Files] permite capturar dados de mídia de arquivos [!DNL Google DCM] de registro e usar os dados para criar características no Audience Manager. Capture impressões, cliques e conversões de servidores de anúncios como características sem ter que usar chamadas de pixel.

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *itálico*, colchetes `[ ]` `( )` etc.) neste documento indica elementos e opções do código. Consulte [Convenções de estilo para código e elementos de texto](../../reference/code-style-elements.md) para obter mais informações.

## Propósito {#purpose}

[!UICONTROL Actionable Log Files] simplificar a forma como capturar impressões, cliques e conversões de servidores de anúncios. Use essas informações para segmentação do usuário sem precisar de mídia pixels manualmente para enviar atributos de campanha.[!DNL Audience Manager]

## Introdução {#getting-started}

Para começar [!UICONTROL Actionable Log Files]e usar nossos Relatórios [de otimização de público-alvo](../../reporting/audience-optimization-reports/audience-optimization-reports.md), você precisa importar dados de log do DCM [!DNL Audience Manager]para. Consulte [Importar arquivos de dados DCM para o Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *e* entre em contato com seu [!DNL Audience Manager] consultor.

Se você já estiver importando [!UICONTROL DCM] dados de log para, [!DNL Audience Manager]peça ao [!DNL Audience Manager] seu consultor ou [ao Atendimento ao cliente](https://helpx.adobe.com/contact/enterprise-support.ec.html) para ativá- [!UICONTROL Actionable Log Files] lo.

>[!NOTE] {importance = "high"}
>
>[!UICONTROL Actionable Log Files] funcionam somente com [!DNL Google DCM] arquivos de log.

## Trabalhar com arquivos de registro acionáveis {#working-with-actionable-log-files}

Com [!UICONTROL Actionable Log Files], as informações de [!DNL DCM] registros são capturadas da [!DNL Audience Manager] mesma forma que capturaria dados de interações de site em tempo real. [!DNL Audience Manager] se conecta com seu [!DNL Google Cloud] armazenamento, analisa as informações de [!DNL DCM] logs e envia os dados de log como sinais acionáveis para nossos [servidores de coleta de dados](../../reference/system-components/components-data-collection.md#dcs-pcs).

Ainda é necessário configurar características baseadas em regras para capturar os sinais acionáveis. Consulte como configurar características baseadas em regras na interface do [usuário do Audience Manager](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) ou usando nossas [Ferramentas de gerenciamento em massa](../../reference/bulk-management-tools/bulk-create.md). Role para baixo até [a](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) seção Sinais acionáveis para obter uma lista de todas as teclas que você pode usar em traços baseados em regras.

Para um arquivo [!DNL DCM] de log de tamanho médio de 2 milhões de linhas, quaisquer características criadas de sinais acionáveis são observadas aproximadamente uma hora depois de processar os logs.

>[!IMPORTANT] {importance = "high"}
>
>Recomendamos implementar [!UICONTROL Actionable Log Files]*em vez de Chamadas* [de pixel](../../integration/media-data-integration/impression-data-pixels.md). Desincentivamos o uso de ambas as opções, pois isso resulta em um aumento nas contagens de frequência para características.

## Sinais acionáveis {#actionable-signals}

Os sinais são as [menores unidades de dados](../../reference/signal-trait-segment.md) em [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] permite capturar anunciantes, unidades de negócios, criação e valores de campanha em eventos de impressão, eventos de clique e eventos de conversão como sinais de [!DNL DCM] logs.

Lembre-se, para usar essas informações para criação e segmentação de público-alvo, de configurar as características baseadas em regras. A tabela lista os sinais acionáveis dos arquivos [!DNL DCM] de registro:

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
   <td colname="col2"> <p>Disponível apenas para eventos de conversão. </p> <p>Representa a ID numérica da atividade de conversão no DCM. Este campo mapeia para a ID de atividade do DCM. </p> <p> <p>Dica: Você pode capturar atividades de conversão múltiplas ou específicas do DCM. Crie características usando <code> d_ conversion = activity ID</code> para cada atividade de conversão do DCM. </p> </p> </td> 
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
   <td colname="col2"> <p>ID do anunciante.</p> <p>Um código de integração para a fonte de dados do anunciante. Observe que isso não está relacionado às fontes de dados do Audience Manager.</p> <p>Este campo mapeia para a ID do grupo de anunciante a partir do DCM. </p> </td> 
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
   <td colname="col2"> <p>A ID da fonte de dados usada para capturar dados do DCM. Consulte <a href="../../features/manage-datasources.md#create-data-source"> Como criar uma fonte de dados</a>. </p> </td> 
   <td colname="col3"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Os sinais descritos na tabela são capturados [!DNL Audience Manager] em uma `HTTP` chamada de tempo real. A chamada de exemplo abaixo contém informações sobre um evento de conversão. [!DNL DCM] As chamadas não precisam necessariamente incluir *todos* os sinais na chamada de exemplo.

```
https://sample.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

>[!NOTE] {importance = "high"}
>
>O carimbo de data e hora do evento fornecido nos [!DNL DCM] registros será respeitado e enviado para o [!UICONTROL Data Collection Servers].
>
>* Se um carimbo de data e hora não estiver disponível para uma linha de dados no arquivo [!DNL DCM] de log, usaremos a hora da `HTTP` chamada como o carimbo de data e hora do evento.
>* Se a linha de dados no arquivo [!DNL DCM] de log contiver um carimbo de data e hora malformado, ignoramos a linha inteira.


## Casos de uso {#use-cases}

Uma vantagem da implementação [!UICONTROL Actionable Log Files] é a opção de aplicar controles [de recenticidade e frequência](../../features/segments/recency-and-frequency.md) a qualquer [característica](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) baseada em regras que contenha sinais acionáveis. Isso permite, por exemplo, que você capitfique o número de vezes que um usuário recebe um anúncio específico em uma campanha de mídia. Outros casos de uso incluem:

### Usuários do redirecionamento

Redirecione os usuários que viram o anúncio 123, mas não clicaram ou convertem e mostraram a creative 456. Fazer isso:

1. Crie uma característica para capturar usuários que viram a criação. Considere que você nomeia a característica [!DNL Creative Trait 123]. Use a regra de características:

   `d_creative == 123 AND d_event == imp`

1. Crie uma característica para capturar usuários que clicam ou convertem. Digamos que você nomeie este [!DNL Click and Converter]. Use a regra de características:

   `d_event == click OR d_event=conv`

1. Crie um segmento para preencher com usuários que viram o anúncio 123, mas não clicaram ou convertem. Nomeie-o [!DNL Retarget Users] e use a regra de segmento:

   `Creative Trait 123 AND NOT Click and Converter`

1. Mapeie o segmento [!DNL Retarget Users] para um destino e para os usuários direcionados no destino com o anúncio 456.

### Usar atividade do DCM Floodlight nos Relatórios de otimização de público-alvo ou no Audience Lab

[As tags Floodlight](https://support.google.com/dcm/partner/answer/4293719?hl=en) permitem que os anunciantes rastreiem conversões de usuários. Com [!UICONTROL Actionable Log Files], você pode rastrear [!DNL DCM] as conversões nos Relatórios [de otimização de público-alvo](../../reporting/audience-optimization-reports/audience-optimization-reports.md) ou no [Audience Lab](../../features/audience-lab/audience-lab.md):

1. Crie uma característica e use a seguinte regra de característica para capturar uma conversão nos logs do servidor de anúncios:

   `d_event == conv AND d_conversion == 123`

   Ao criar a característica no Audience Manager [!UICONTROL UI], selecione [!UICONTROL Conversion] como o [!UICONTROL Event Type].

2. Depois de criar a característica, a conversão começará a ser relatada no [!UICONTROL Audience Optimization Reports] e [!UICONTROL Audience Lab]no.

>[!MORE_ LIKE_ THIS]
>
>* [Importar arquivos de dados DCM para o Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Relatórios de otimização de público-alvo](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

