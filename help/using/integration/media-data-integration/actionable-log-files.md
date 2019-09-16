---
description: Os arquivos de registro acionáveis permitem capturar dados de mídia dos arquivos de registro do Google DCM e usar os dados para criar características no Audience Manager. Capture impressões, cliques e conversões de servidores de anúncios como características sem ter que usar chamadas de pixel.
keywords: logs acionáveis
seo-description: Os arquivos de registro acionáveis permitem capturar dados de mídia dos arquivos de registro do Google DCM e usar os dados para criar características no Audience Manager. Capture impressões, cliques e conversões de servidores de anúncios como características sem ter que usar chamadas de pixel.
seo-title: Arquivo de registro acionável
solution: Audience Manager
title: Arquivo de registro acionável
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
translation-type: tm+mt
source-git-commit: dbc96973ed2214d171fe32b7e1314d40c22c2d79

---


# Arquivo de registro acionável {#actionable-log-files}

[!UICONTROL Actionable Log Files] permite capturar dados de mídia de arquivos de [!DNL Google DCM] log e usar os dados para criar características no Audience Manager. Capture impressões, cliques e conversões de servidores de anúncios como características sem ter que usar chamadas de pixel.

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *itálico*, colchetes `[ ]` `( )` etc.) neste documento, indique os elementos de código e as opções. Consulte [Convenções de estilo para código e elementos de texto](../../reference/code-style-elements.md) para obter mais informações.

## Propósito {#purpose}

[!UICONTROL Actionable Log Files] simplifique a maneira como você captura impressões, cliques e conversões de servidores de anúncios. Use essas informações para a segmentação do usuário sem precisar pixel de mídia manualmente para enviar atributos de campanha [!DNL Audience Manager].

## Introdução {#getting-started}

Para começar a usar [!UICONTROL Actionable Log Files]e usar nossos Relatórios [de otimização de](../../reporting/audience-optimization-reports/audience-optimization-reports.md)público-alvo, é necessário importar os dados de log do DCM para [!DNL Audience Manager]. Consulte [Importar arquivos de dados do DCM para o Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *e entre* em contato com seu [!DNL Audience Manager] consultor.

Se você já estiver importando [!UICONTROL DCM] dados de log para [!DNL Audience Manager], peça a seu [!DNL Audience Manager] consultor ou ao [Atendimento](https://helpx.adobe.com/contact/enterprise-support.ec.html) ao cliente para habilitá-los [!UICONTROL Actionable Log Files] para você.

>[!NOTE] {important="high"}
>
>[!UICONTROL Actionable Log Files] trabalhar somente com arquivos [!DNL Google DCM] de registro.

## Trabalhar com arquivos de registro acionáveis {#working-with-actionable-log-files}

Com [!UICONTROL Actionable Log Files]o, as informações dos [!DNL DCM] registros são capturadas da mesma forma que [!DNL Audience Manager] os dados de interações de sites em tempo real. [!DNL Audience Manager] conecta-se ao seu [!DNL Google Cloud] armazenamento, analisa as informações dos [!DNL DCM] registros e envia os dados de log como sinais acionáveis para nossos servidores [de coleta de](../../reference/system-components/components-data-collection.md#dcs-pcs)dados.

Você ainda precisa configurar características baseadas em regras para capturar os sinais acionáveis. Consulte como configurar características com base em regras na interface do usuário do [Audience Manager](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) ou usando nossas Ferramentas [de gerenciamento em](../../reference/bulk-management-tools/bulk-create.md)massa. Role para baixo até a seção Sinais [](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) acionáveis para obter uma lista de todas as teclas que você pode usar em características baseadas em regras.

Para um arquivo de [!DNL DCM] log de tamanho médio de 2 milhões de linhas, quaisquer características criadas a partir de sinais acionáveis são realizadas aproximadamente uma hora após o processamento dos registros.

>[!IMPORTANT] {important="high"}
>
>Recomendamos implementar [!UICONTROL Actionable Log Files] em vez *de* Pixel Calls [](../../integration/media-data-integration/impression-data-pixels.md). Desencorajamos a utilização de ambas as opções, uma vez que isso leva a um aumento da contagem de frequências para características.

## Sinais acionáveis {#actionable-signals}

Os sinais são as [menores unidades](../../reference/signal-trait-segment.md) de dados do [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] permite capturar valores de anunciante, unidade de negócios, anúncio e campanha em eventos de impressão, eventos de clique e eventos de conversão como sinais de [!DNL DCM] registros.

Lembre-se, para usar essas informações para a criação e segmentação do público-alvo, é necessário configurar as características baseadas em regras por si mesmo. A tabela lista os sinais acionáveis dos arquivos de [!DNL DCM] registro:

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
   <td colname="col1"> <p> <code> d_event</code> </p> </td> 
   <td colname="col2"> <p>Indica o tipo de evento do DCM. </p> <p>Os valores aceitos são: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> para impressões. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> para cliques. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conversão</code> para conversões. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> imp, clique, console</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col2"> <p>Disponível somente para eventos de conversão. </p> <p>Representa a ID numérica da atividade de conversão no DCM. Este campo mapeia para a ID de atividade do DCM. </p> <p> <p>Dica: É possível capturar várias atividades de conversão ou específicas do DCM. Crie características usando <code> d_conversion = ID</code> de atividade para cada atividade de conversão do DCM. </p> </p> </td> 
   <td colname="col3"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_conversionType</code> </p> </td> 
   <td colname="col2"> <p>Disponível somente para eventos de conversão. </p> <p>Esse campo mapeia para a ID de conversão no DCM. Indica a atividade anterior à conversão do usuário do DCM. </p> <p>Os valores aceitos são: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> para conversões pós-clique. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> para conversões pós-impressão. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> para conversões sem correspondência. A conversão não pode ser correspondida a uma atividade anterior. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> 0,1,2</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col2"> <p>ID do anunciante.</p> <p>Um código de integração para a fonte de dados do anunciante. Observe que isso não está relacionado às fontes de dados do Audience Manager.</p> <p>Esse campo mapeia a ID do grupo de anunciantes do DCM. </p> </td> 
   <td colname="col3"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col2"> <p>ID da unidade de negócios. Esse campo mapeia a ID do anunciante do DCM. </p> </td> 
   <td colname="col3"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col2"> <p>A ID da campanha fornecida pelo DCM. </p> </td> 
   <td colname="col3"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col2"> <p>A ID criativa fornecida pelo DCM. </p> </td> 
   <td colname="col3"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col2"> <p>A ID da fonte de dados usada para capturar dados do DCM. Consulte <a href="../../features/manage-datasources.md#create-data-source"> Como criar uma fonte</a>de dados. </p> </td> 
   <td colname="col3"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Os sinais descritos na tabela são captados em [!DNL Audience Manager] tempo real como uma `HTTP` chamada. A chamada de exemplo abaixo contém informações sobre um evento de conversão de [!DNL DCM]. As chamadas não precisam necessariamente incluir *todos* os sinais na chamada de exemplo.

```
https://sample.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

>[!NOTE] {important="high"}
>
>O carimbo de data e hora do evento fornecido nos [!DNL DCM] logs será respeitado e passado para o [!UICONTROL Data Collection Servers].
>
>* Se um carimbo de data e hora não estiver disponível para uma linha de dados no arquivo de [!DNL DCM] log, usaremos o horário da `HTTP` chamada como carimbo de data e hora do evento.
>* Se a linha de dados no arquivo de [!DNL DCM] log contiver um carimbo de data e hora malformado, ignoraremos a linha inteira.


## Casos de uso {#use-cases}

Um benefício da implementação [!UICONTROL Actionable Log Files] é a opção de aplicar controles de [recenticidade e frequência](../../features/segments/recency-and-frequency.md) a quaisquer características [baseadas em](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) regras que contenham sinais acionáveis. Isso permite, por exemplo, limitar a frequência do número de vezes que um usuário é exibido em uma campanha de mídia. Outros casos de uso incluem:

### Redirecionar usuários

Redirecione usuários que viram 123 criativos, mas não clicaram nem converteram e mostraram 456 criativos. Fazer isso:

1. Crie uma característica para capturar usuários que viram o anúncio. Digamos que você dê um nome ao traço [!DNL Creative Trait 123]. Use a regra de características:

   `d_creative == 123 AND d_event == imp`

1. Crie uma característica para capturar usuários que clicam ou convertem. Digamos que você dê um nome a este [!DNL Click and Converter]. Use a regra de características:

   `d_event == click OR d_event=conv`

1. Crie um segmento para preencher com usuários que viram o anúncio 123, mas não clicaram nem converteram. Nomeie-o [!DNL Retarget Users] e use a regra de segmento:

   `Creative Trait 123 AND NOT Click and Converter`

1. Mapeie o segmento [!DNL Retarget Users] para um destino e direcione usuários para o destino com o creative 456.

### Usar a atividade do DCM Floodlight nos Relatórios de otimização de público-alvo ou no Audience Lab

[As tags](https://support.google.com/dcm/partner/answer/4293719?hl=en) Floodlight permitem que os anunciantes rastreiem as conversões dos usuários. Com [!UICONTROL Actionable Log Files], você pode rastrear as [!DNL DCM] conversões nos Relatórios [de otimização de](../../reporting/audience-optimization-reports/audience-optimization-reports.md) público-alvo ou no Laboratório [de](../../features/audience-lab/audience-lab.md)público-alvo:

1. Crie uma característica e use a regra de característica a seguir para capturar uma conversão dos registros do servidor de publicidade:

   `d_event == conv AND d_conversion == 123`

   Ao criar a característica no Audience Manager [!UICONTROL UI], selecione [!UICONTROL Conversion] como a [!UICONTROL Event Type].

2. Depois que você tiver criado a característica, a conversão começará a ser relatada no [!UICONTROL Audience Optimization Reports] e no [!UICONTROL Audience Lab].

>[!MORE_LIKE_THIS]
>
>* [Importar arquivos de dados do DCM para o Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Relatórios de otimização de público-alvo](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

