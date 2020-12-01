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
source-git-commit: a4d86fb0324a03002123f8713eb9786b5b74c38e
workflow-type: tm+mt
source-wordcount: '1605'
ht-degree: 3%

---


# Arquivo de registro acionável {#actionable-log-files}

[!UICONTROL Actionable Log Files] permite capturar dados de mídia de arquivos de log do servidor de publicidade e usar os dados para criar características no Audience Manager. Capture impressões, cliques e conversões de servidores de anúncios como características sem precisar anexar [pixels](../../integration/media-data-integration/impression-data-pixels.md).

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *itálico*, colchetes `[ ]` `( )` etc.) neste documento, indique os elementos de código e as opções. Consulte [Convenções de estilo para código e elementos de texto](../../reference/code-style-elements.md) para obter mais informações.

## Propósito {#purpose}

[!UICONTROL Actionable Log Files] simplifique a maneira como você captura impressões, cliques e conversões de servidores de anúncios. Use essas informações para a segmentação do usuário sem precisar pixel de mídia manualmente para enviar atributos de campanha para [!DNL Audience Manager].

## Introdução {#getting-started}

Para começar com [!UICONTROL Actionable Log Files], é necessário importar dados de log para [!DNL Audience Manager]. Os links a seguir ajudarão você a começar:

* Para registros [!UICONTROL Google Campaign Manager], consulte [Importar arquivos de dados do Google Campaign Manager para o Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *e* entre em contato com seu consultor [!DNL Audience Manager].
* Para acessar os registros [!UICONTROL Google Ad Manager] (antigo Google DFP), consulte [Importar arquivos de dados do Google Ad Manager para o Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *e* entre em contato com seu consultor [!DNL Audience Manager].
* Para outros logs de servidor de publicidade, consulte [Arquivos de Dados e Metadados](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *e* entre em contato com seu consultor [!DNL Audience Manager].

Se você já estiver importando dados de log para [!DNL Audience Manager], entre em contato com seu [!DNL Audience Manager] consultor ou [Atendimento ao cliente](https://helpx.adobe.com/br/contact/enterprise-support.ec.html) para habilitar [!UICONTROL Actionable Log Files] para você.

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

-->

## Trabalhar com arquivos de registro acionáveis {#working-with-actionable-log-files}

Com [!UICONTROL Actionable Log Files], as informações dos registros do servidor de anúncios são capturadas [!DNL Audience Manager] da mesma forma que você capturaria dados de interações de sites em tempo real. [!DNL Audience Manager] conecta-se ao armazenamento de log do servidor de publicidade, analisa as informações dos registros e envia os dados de log como sinais acionáveis para nossos servidores [ de coleta de ](../../reference/system-components/components-data-collection.md#dcs-pcs)dados.

Você ainda precisa configurar características baseadas em regras para capturar os sinais acionáveis. Consulte como configurar características baseadas em regras na interface do usuário [Audience Manager](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) ou usando nossas [Ferramentas de Gerenciamento em Massa](../../reference/bulk-management-tools/bulk-create.md). Role para baixo até a seção [Sinais acionáveis](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) para obter uma lista de todas as teclas que você pode usar em características baseadas em regras.

>[!IMPORTANT]
>
>Recomendamos implementar [!UICONTROL Actionable Log Files] *em vez de* [Chamadas de pixel](../../integration/media-data-integration/impression-data-pixels.md). Desencorajamos a utilização de ambas as opções, uma vez que isso leva a um aumento da contagem de frequências para características.

## Sinais acionáveis {#actionable-signals}

Os sinais são as [menores unidades de dados](../../reference/signal-trait-segment.md) em [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] permite capturar valores de anunciante, unidade de negócios, anúncio e campanha em eventos de impressão, eventos de clique e eventos de conversão como sinais de registros de servidor de anúncios.

Lembre-se, para usar essas informações para a criação e segmentação de audiências, é necessário configurar as características baseadas em regras por conta própria.

### Sinais acionáveis de registros do Google Campaign Manager {#dcm-logs-signals}

A tabela lista os sinais acionáveis dos arquivos de log [!DNL Google Campaign Manager]:

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
   <td colname="col3"> <p>Disponível somente para eventos de conversão. </p> <p>Representa a ID numérica da atividade de conversão no Google Campaign Manager. Esse campo mapeia para a ID de Atividade do Google Campaign Manager. </p> <p> <p>Dica: É possível capturar várias atividades de conversão ou específicas do Google Campaign Manager. Crie características usando <code> d_conversion = activity ID</code> para cada atividade de conversão do Google Campaign Manager. </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Disponível somente para eventos de conversão. </p> <p>Esse campo mapeia para a ID de conversão no Google Campaign Manager. Indica a atividade que precede a conversão do usuário no Google Campaign Manager. </p> <p>Os valores aceitos são: </p> <p> 
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
   <td colname="col3"><p>Um código de integração para a fonte de dados do anunciante. Observe que isso não está relacionado a fontes de dados Audience Manager.</p> <p>Esse campo mapeia para a ID do grupo de anunciantes do Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>ID da unidade de negócios. Esse campo mapeia a ID do anunciante do Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>A ID de Campanha fornecida pelo Google Campaign Manager.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>A ID criativa fornecida pelo Google Campaign Manager. </p> </td> 
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
   <td colname="col3"> <p>Indica o tipo de evento. O Audience Manager lê o tipo de evento do nome do arquivo de log do Google Campaign Manager e o transforma em um sinal acionável. </p> <p>Os valores aceitos são: </p> <p> 
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
   <td colname="col3"> <p>A ID da fonte de dados usada para capturar dados do Google Campaign Manager. Consulte <a href="../../features/manage-datasources.md#create-data-source"> Como criar uma fonte de dados</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Os sinais descritos na tabela são capturados em [!DNL Audience Manager] como uma chamada `HTTP` em tempo real. A chamada de exemplo abaixo contém informações sobre um evento de conversão de [!DNL Google Campaign Manager]. As chamadas não precisam necessariamente incluir *all* os sinais na chamada de exemplo.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

Para um arquivo de log de [!DNL Google Campaign Manager] tamanho médio de 2 milhões de linhas, quaisquer características criadas a partir de sinais acionáveis são realizadas em aproximadamente uma hora após o processamento dos logs.

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>O carimbo de data e hora do evento fornecido nos registros [!DNL Google Campaign Manager] será honrado e passado para [!UICONTROL Data Collection Servers].
>
>* Se um carimbo de data e hora não estiver disponível para uma linha de dados no arquivo de log [!DNL Google Campaign Manager], usamos a hora da chamada `HTTP` como o carimbo de data e hora do evento.
>* Se a linha de dados no arquivo de log [!DNL Google Campaign Manager] contiver um carimbo de data e hora malformado, ignoraremos a linha inteira.


<br> 

### Sinais acionáveis de [!DNL Google Ad Manager] registros {#ad-manager-logs-signals}

A tabela lista os sinais acionáveis dos arquivos de log [!DNL Google Ad Manager]:


| Nome do cabeçalho no arquivo de log | Sinal | Descrição |
---------|----------|---------
| `LineItemId` | `d_lineitem` | A ID numérica do item de linha do Gerenciador de publicidade entregue |
| `OrderId` | `d_orderid` | A ID numérica do pedido do Gerenciador de publicidade que continha o item de linha e o anúncio fornecidos. |
| `CreativeId` | `d_creative` | A ID numérica do anúncio do Ad Manager. |
| `-` | `d_event` | Indica o tipo de evento. O Audience Manager lê o tipo de evento do nome do arquivo de log do Gerenciador de publicidade e o transforma em um sinal acionável. Os valores aceitos são: <br> <ul><li>d_evento = imp para impressões.</li><li>d_evento = clique para clicar.</li><li>d_evento = conversão para conversões e atividades.</li></ul> |
| `-` | `d_src` | A ID da fonte de dados usada para capturar os dados do Gerenciador de publicidade. Consulte [Como criar uma fonte de dados](/help/using/features/manage-datasources.md). |

Os sinais descritos na tabela são capturados em Audience Manager como uma chamada HTTP em tempo real. A chamada de exemplo abaixo contém informações sobre um evento de conversão do Google Ad Manager. As chamadas não precisam necessariamente incluir todos os sinais na chamada de exemplo.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>O carimbo de data e hora do evento fornecido nos registros [!DNL Google Ad Manager] será honrado e passado para [!UICONTROL Data Collection Servers].
>
>* Se um carimbo de data e hora não estiver disponível para uma linha de dados no arquivo de log [!DNL Google Ad Manager], usamos a hora da chamada `HTTP` como o carimbo de data e hora do evento.
>* Se a linha de dados no arquivo de log [!DNL Google Ad Manager] contiver um carimbo de data e hora malformado, ignoraremos a linha inteira.


<br> 

### Sinais acionáveis de registros genéricos do servidor de anúncios {#generic-logs-signals}

Primeiro, você deve depositar seus logs de servidor de anúncios em nossos buckets Amazon S3. Para fazer isso, leia [Arquivos de Dados para Relatórios de Audience Optimization e Arquivos de Log Acionáveis](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *e* entre em contato com seu consultor [!DNL Audience Manager]. A tabela lista os sinais acionáveis dos arquivos de registro genéricos:

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
   <td colname="col3"> <p> Uma data e hora UTC para impressão, clique ou evento de conversão. Use o formato <code>yyyy-MM-dd HH:mm:ss</code>. </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>Um código de integração para a fonte de dados do anunciante. Observe que esse campo não está relacionado a <a href="../../features/datasources-list-and-settings.md">fontes de dados de Audience Manager.</a></p></td> 
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
   <td colname="col3"> <p>Indica o tipo de evento. O Audience Manager lê o tipo de evento do nome do arquivo de log e o transforma em um sinal acionável. Consulte <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">convenções de nomenclatura de arquivos de registro</a>. </p> <p>Os valores aceitos são: </p> <p> 
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
   <td colname="col3"> <p>A ID da fonte de dados usada para capturar dados de log. Consulte <a href="../../features/manage-datasources.md#create-data-source"> Como criar uma fonte de dados</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Os sinais descritos na tabela são capturados em [!DNL Audience Manager] como uma chamada `HTTP` em tempo real. As chamadas não precisam necessariamente incluir *all* os sinais na chamada de exemplo.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Trabalhar com sinais acionáveis na interface do usuário do Audience Manager {#actionable-signals-in-ui}

Você pode visualização seus sinais acionáveis recebidos na interface [Sigals Search](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md).

Vá para **Dados de Audiência** (1) > **Sinais** (2) > **Pesquisar** (3) e selecione o filtro **Ficheiros de Registro Acionáveis** (4).

![Sinais acionáveis na interface do usuário](/help/using/integration/assets/alf-in-signals.png)

Para criar características baseadas em regras usando seus sinais acionáveis, selecione **Arquivos de Log Acionáveis** (1), selecione os sinais acionáveis que deseja usar como regras de características (2) e pressione **Criar característica dos Sinais Selecionados** (3).

![Criar características de sinais](/help/using/integration/assets/alf-create-trait.png)


## Casos de uso {#use-cases}

Um benefício da implementação de [!UICONTROL Actionable Log Files] é a opção de aplicar [controles de recenticidade e frequência](../../features/segments/recency-and-frequency.md) a quaisquer [características baseadas em regras](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) que contenham sinais acionáveis. Isso permite, por exemplo, limitar a frequência do número de vezes que um usuário é exibido em um anúncio específico, em uma campanha de mídia. Leia [Supressão interdispositivo instantânea](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) para saber como fazer isso. Outros casos de uso incluem:

### Redirecionar usuários

Redirecione usuários que viram 123 criativos, mas não clicaram nem converteram e mostraram 456 criativos. Fazer isso:

1. Crie uma característica para capturar usuários que viram o anúncio. Digamos que você nomeie o traço [!DNL Creative Trait 123]. Use a regra de características:

   `d_creative == 123 AND d_event == imp`

2. Crie uma característica para capturar usuários que clicam ou convertem. Digamos que você nomeie este [!DNL Click and Converter]. Use a regra de características:

   `d_event == click OR d_event=conv`

3. Crie um segmento para preencher com usuários que viram o anúncio 123, mas não clicaram nem converteram. Nomeie-o [!DNL Retarget Users] e use a regra de segmento:

   `Creative Trait 123 AND NOT Click and Converter`

4. Mapeie o segmento [!DNL Retarget Users] para um destino e usuários públicos alvos no destino com o creative 456.

### Usar a Atividade Floodlight do Google Campaign Manager nos Relatórios do Audience Optimization ou no Laboratório de Audiências

[Anunciantes ](https://support.google.com/dcm/partner/answer/4293719?hl=en) marcáveis do Floodlight para rastrear conversões de usuários. Com [!UICONTROL Actionable Log Files], você pode rastrear as conversões [!DNL Google Campaign Manager] nos [Relatórios Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md) ou em [Laboratório de Audiências](../../features/audience-lab/audience-lab.md):

1. Crie uma característica e use a regra de característica a seguir para capturar uma conversão dos registros do servidor de publicidade:

   `d_event == conv AND d_conversion == 123`

   Ao criar a característica no Audience Manager [!UICONTROL UI], selecione [!UICONTROL Conversion] como [!UICONTROL Event Type].

2. Depois que você criar a característica, a conversão começará a ser relatada em [!UICONTROL Audience Optimization Reports] e em [!UICONTROL Audience Lab].

>[!MORELIKETHIS]
>
>* [Importar arquivos de dados do Google Campaign Manager para o Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Relatórios de otimização de público-alvo](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

