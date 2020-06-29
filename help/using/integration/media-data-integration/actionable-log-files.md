---
description: Os arquivos de registro acionáveis permitem capturar sinais de mídia de arquivos de log do servidor de publicidade para criar características no Audience Manager. Capture impressões, cliques e conversões de servidores de anúncios como características sem precisar anexar pixels.
keywords: actionable logs, alf, ALF
seo-description: Os arquivos de registro acionáveis permitem capturar sinais de mídia de arquivos de log do servidor de publicidade para criar características no Audience Manager. Capture impressões, cliques e conversões de servidores de anúncios como características sem precisar anexar pixels.
seo-title: Arquivo de registro acionável
solution: Audience Manager
title: Arquivo de registro acionável
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Log Files
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1378'
ht-degree: 3%

---


# Arquivo de registro acionável {#actionable-log-files}

[!UICONTROL Actionable Log Files] permite capturar dados de mídia de arquivos de log do servidor de publicidade e usar os dados para criar características no Audience Manager. Capture impressions, clicks, and conversions from ad servers as traits without having to append [pixels](../../integration/media-data-integration/impression-data-pixels.md).

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *itálico*, colchetes `[ ]` `( )` etc.) neste documento, indique os elementos de código e as opções. Consulte [Convenções de estilo para código e elementos de texto](../../reference/code-style-elements.md) para obter mais informações.

## Propósito {#purpose}

[!UICONTROL Actionable Log Files] simplifique a maneira como você captura impressões, cliques e conversões de servidores de anúncios. Use essas informações para a segmentação do usuário sem precisar pixel de mídia manualmente para enviar atributos de campanha [!DNL Audience Manager].

## Introdução {#getting-started}

Para começar a usar [!UICONTROL Actionable Log Files], é necessário importar dados de log para [!DNL Audience Manager]. Os links a seguir ajudarão você a começar:

* Para obter [!UICONTROL Google DCM] registros, consulte [Importar arquivos de dados do DCM para o Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *e entre* em contato com seu [!DNL Audience Manager] consultor.
* Para obter [!UICONTROL Google DFP] registros, consulte [Importar arquivos de dados DFP para o Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *e entre* em contato com seu [!DNL Audience Manager] consultor.
* Para outros logs de servidor de publicidade, consulte Arquivos [de dados e metadados](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) e *entre em contato com seu* [!DNL Audience Manager] consultor.

Se você já estiver importando dados de log para [!DNL Audience Manager], peça a seu [!DNL Audience Manager] consultor ou ao [Atendimento](https://helpx.adobe.com/br/contact/enterprise-support.ec.html) ao cliente para habilitá-los [!UICONTROL Actionable Log Files] para você.

>[!IMPORTANT]
>
> No final de 2019, [!UICONTROL Actionable Log Files] começou a expandir a disponibilidade para novos servidores de anúncios. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/br/contact/enterprise-support.ec.html) to get started.

## Trabalhar com arquivos de registro acionáveis {#working-with-actionable-log-files}

Com [!UICONTROL Actionable Log Files]o, as informações dos registros do servidor de anúncios são capturadas [!DNL Audience Manager] da mesma forma que você capturaria dados de interações de site em tempo real. [!DNL Audience Manager] conecta-se ao armazenamento de log do servidor de publicidade, analisa as informações dos registros e envia os dados de log como sinais acionáveis para nossos servidores [de coleta de](../../reference/system-components/components-data-collection.md#dcs-pcs)dados.

Você ainda precisa configurar características baseadas em regras para capturar os sinais acionáveis. Veja como configurar características baseadas em regras na interface [do usuário do](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) Audience Manager ou usando nossas Ferramentas [de Gerenciamento em](../../reference/bulk-management-tools/bulk-create.md)massa. Role para baixo até a seção Sinais [](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) acionáveis para obter uma lista de todas as teclas que você pode usar em características baseadas em regras.

>[!IMPORTANT]
>
>Recomendamos implementar [!UICONTROL Actionable Log Files] em vez *de* Pixel Calls [](../../integration/media-data-integration/impression-data-pixels.md). Desencorajamos a utilização de ambas as opções, uma vez que isso leva a um aumento da contagem de frequências para características.

## Sinais acionáveis {#actionable-signals}

Os sinais são as [menores unidades](../../reference/signal-trait-segment.md) de dados do [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] permite capturar valores de anunciante, unidade de negócios, anúncio e campanha em eventos de impressão, eventos de clique e eventos de conversão como sinais de registros de servidor de anúncios.

Lembre-se, para usar essas informações para a criação e segmentação de audiências, é necessário configurar as características baseadas em regras por conta própria.

### Sinais acionáveis de registros do Google DCM {#dcm-logs-signals}

A tabela lista os sinais acionáveis dos arquivos de [!DNL DCM] registro:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome do cabeçalho no arquivo de log </th> 
   <th colname="col2" class="entry"> Sinal </th> 
   <th colname="col3" class="entry"> Descrição </th> 
   <th colname="col4" class="entry"> Exemplo de valor </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Activity ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col3"> <p>Disponível somente para eventos de conversão. </p> <p>Representa a ID numérica da atividade de conversão no DCM. Esse campo mapeia para a ID de Atividade do DCM. </p> <p> <p>Dica: É possível capturar várias atividades de conversão ou específicas do DCM. Crie características usando <code> d_conversion = activity ID</code> para cada atividade de conversão do DCM. </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Disponível somente para eventos de conversão. </p> <p>Esse campo mapeia para a ID de conversão no DCM. Indica a atividade que precede a conversão do usuário do DCM. </p> <p>Os valores aceitos são: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> para conversões pós-clique. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> para conversões pós-impressão. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> para conversões sem correspondência. A conversão não pode ser correspondida a uma atividade anterior. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">Uma data e hora UTC para impressão, clique ou evento de conversão. Representado em microssegundos desde 1970-01-01 00:00:00 UTC.</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>Um código de integração para a fonte de dados do anunciante. Observe que isso não está relacionado a fontes de dados Audience Manager.</p> <p>Esse campo mapeia a ID do grupo de anunciantes do DCM. </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>ID da unidade de negócios. Esse campo mapeia a ID do anunciante do DCM. </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>A ID de Campanha fornecida pelo DCM.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>A ID criativa fornecida pelo DCM. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> O valor das vendas em US$, é de -6. Multiplica por 1.000.000 para ver como uma quantia em dólar.</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Indica o tipo de evento. O Audience Manager lê o tipo de evento do nome do arquivo de log do DCM e o transforma em um sinal acionável. </p> <p>Os valores aceitos são: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> para impressões. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> para cliques. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> para conversões. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>A ID da fonte de dados usada para capturar dados do DCM. Consulte <a href="../../features/manage-datasources.md#create-data-source"> Como criar uma fonte</a>de dados. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Os sinais descritos na tabela são captados em [!DNL Audience Manager] tempo real como uma `HTTP` chamada. A chamada de exemplo abaixo contém informações sobre um evento de conversão de [!DNL DCM]. As chamadas não precisam necessariamente incluir *todos* os sinais na chamada de exemplo.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

Para um arquivo de [!DNL DCM] log de tamanho médio de 2 milhões de linhas, quaisquer características criadas a partir de sinais acionáveis são realizadas aproximadamente uma hora após o processamento dos registros.

>[!NOTE] {important=&quot;high&quot;}
>
>O carimbo de data e hora do evento fornecido nos [!DNL DCM] logs será honrado e passado para o [!UICONTROL Data Collection Servers].
>
>* Se um carimbo de data e hora não estiver disponível para uma linha de dados no arquivo de [!DNL DCM] log, usamos o horário da `HTTP` chamada como carimbo de data e hora do evento.
>* Se a linha de dados no arquivo de [!DNL DCM] log contiver um carimbo de data e hora malformado, ignoraremos a linha inteira.


<br> 

### Sinais acionáveis de registros genéricos do servidor de anúncios {#generic-logs-signals}

Primeiro, você deve depositar seus registros de servidor de anúncios em nossos baldes do Amazon S3. Para fazer isso, leia os Arquivos [de Dados para Relatórios de otimização de Audiência e Arquivos](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) de registro acionáveis *e entre* em contato com seu [!DNL Audience Manager] consultor. A tabela lista os sinais acionáveis dos arquivos de registro genéricos:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome do cabeçalho no arquivo de log </th> 
   <th colname="col2" class="entry"> Sinal </th> 
   <th colname="col3" class="entry"> Descrição </th> 
   <th colname="col4" class="entry"> Exemplo de valor </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Event-Type</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Indica se uma conversão é correspondida ou não. As opções incluem: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 0</code> Impressão </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code> Clique em </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> Não atribuído ou desconhecido </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> Uma data e hora UTC para impressão, clique ou evento de conversão. Use o <code>yyyy-MM-dd HH:mm:ss</code> formato. </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>Um código de integração para a fonte de dados do anunciante. Observe que esse campo não está relacionado a fontes de dados de <a href="../../features/datasources-list-and-settings.md">Audience Manager.</a></p></td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>BU-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>ID da unidade de negócios.  </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>A ID da Campanha do arquivo de log.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>A ID criativa do arquivo de log. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> Compra ou outro valor de conversão. Tipo de dados: Flutuar. </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Indica o tipo de evento. O Audience Manager lê o tipo de evento do nome do arquivo de log e o transforma em um sinal acionável. Consulte convenções <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">de nomenclatura de arquivos</a>de registro. </p> <p>Os valores aceitos são: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> para impressões. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> para cliques. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> para conversões. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>A ID da fonte de dados usada para capturar dados de log. Consulte <a href="../../features/manage-datasources.md#create-data-source"> Como criar uma fonte</a>de dados. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Os sinais descritos na tabela são captados em [!DNL Audience Manager] tempo real como uma `HTTP` chamada. As chamadas não precisam necessariamente incluir *todos* os sinais na chamada de exemplo.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Trabalhar com sinais acionáveis na interface do usuário do Audience Manager {#actionable-signals-in-ui}

Você pode visualização seus sinais acionáveis recebidos na interface de Pesquisa [de](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md) Sinais.

Vá para Dados **de** Audiência (1) > **Sinais** (2) > **Pesquisar** (3) e selecione o filtro Arquivos **** de registro acionáveis (4).

![Sinais acionáveis na interface do usuário](/help/using/integration/assets/alf-in-signals.png)

Para criar características com base em regras usando seus sinais acionáveis, selecione Arquivos **de Log** Acionáveis (1), selecione os sinais acionáveis que deseja usar como regras de características (2) e pressione **Criar característica dos Sinais** Selecionados (3).

![Criar características de sinais](/help/using/integration/assets/alf-create-trait.png)


## Casos de uso {#use-cases}

Um benefício da implementação [!UICONTROL Actionable Log Files] é a opção de aplicar controles de [recenticidade e frequência](../../features/segments/recency-and-frequency.md) a quaisquer características [baseadas em](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) regras que contenham sinais acionáveis. Isso permite, por exemplo, limitar a frequência do número de vezes que um usuário é exibido em um anúncio específico, em uma campanha de mídia. Leia a Supressão [](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) interdispositivo instantânea para saber como fazer isso. Outros casos de uso incluem:

### Redirecionar usuários

Redirecione usuários que viram 123 criativos, mas não clicaram nem converteram e mostraram 456 criativos. Fazer isso:

1. Crie uma característica para capturar usuários que viram o anúncio. Digamos que você dê um nome ao traço [!DNL Creative Trait 123]. Use a regra de características:

   `d_creative == 123 AND d_event == imp`

2. Crie uma característica para capturar usuários que clicam ou convertem. Digamos que você dê um nome a este [!DNL Click and Converter]. Use a regra de características:

   `d_event == click OR d_event=conv`

3. Crie um segmento para preencher com usuários que viram o anúncio 123, mas não clicaram nem converteram. Nomeie-o [!DNL Retarget Users] e use a regra de segmento:

   `Creative Trait 123 AND NOT Click and Converter`

4. Mapeie o segmento [!DNL Retarget Users] para um destino e usuários públicos alvos no destino com o creative 456.

### Usar a Atividade DCM Floodlight nos Relatórios de otimização de Audiência ou no Laboratório de Audiências

[As tags](https://support.google.com/dcm/partner/answer/4293719?hl=en) Floodlight permitem que os anunciantes rastreiem as conversões dos usuários. Com [!UICONTROL Actionable Log Files], você pode rastrear as [!DNL DCM] conversões nos Relatórios [de otimização de](../../reporting/audience-optimization-reports/audience-optimization-reports.md) Audiência ou no Laboratório [de](../../features/audience-lab/audience-lab.md)Audiências:

1. Crie uma característica e use a regra de característica a seguir para capturar uma conversão dos registros do servidor de publicidade:

   `d_event == conv AND d_conversion == 123`

   Ao criar a característica no Audience Manager [!UICONTROL UI], selecione [!UICONTROL Conversion] como a [!UICONTROL Event Type].

2. Depois que você tiver criado a característica, a conversão começará a ser relatada no [!UICONTROL Audience Optimization Reports] e no [!UICONTROL Audience Lab].

>[!MORELIKETHIS]
>
>* [Importar arquivos de dados do DCM para o Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Relatórios de otimização de Audiência](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

