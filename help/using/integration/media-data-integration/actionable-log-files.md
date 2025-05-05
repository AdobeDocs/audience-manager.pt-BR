---
description: Arquivos de registro acionáveis permitem capturar sinais de mídia de arquivos de registro de servidor de anúncios para criar características no Audience Manager. Capture impressões, cliques e conversões de servidores de anúncios como características sem precisar anexar pixels.
keywords: logs acionáveis, alf, ALF
seo-description: Actionable Log Files allow you to capture media signals from ad server log files to create traits in Audience Manager. Capture impressions, clicks, and conversions from ad servers as traits without having to append pixels.
seo-title: Actionable Log Files
solution: Audience Manager
title: Arquivo de registro acionável
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Log Files
exl-id: bd499931-4e02-4f64-82ba-46ef7c4ffd3c
source-git-commit: b3f97cfbbd5167f03a6951fcc571368e4a0d15a4
workflow-type: tm+mt
source-wordcount: '1601'
ht-degree: 2%

---

# Arquivo de registro acionável {#actionable-log-files}

O [!UICONTROL Actionable Log Files] permite capturar dados de mídia de arquivos de log do servidor de anúncios e usar os dados para criar características no Audience Manager. Capture impressões, cliques e conversões de servidores de anúncios como características sem precisar acrescentar [pixels](../../integration/media-data-integration/impression-data-pixels.md).

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *itálico*, colchetes `[ ]` `( )` etc.) neste documento indique elementos e opções de código. Consulte [Convenções de estilo para código e elementos de texto](../../reference/code-style-elements.md) para obter mais informações.

## Propósito {#purpose}

O [!UICONTROL Actionable Log Files] simplifica a maneira de capturar impressões, cliques e conversões de servidores de anúncios. Use essas informações para segmentação de usuário sem precisar aplicar pixels manualmente na mídia para enviar atributos de campanha para [!DNL Audience Manager].

## Introdução {#getting-started}

Para começar a usar o [!UICONTROL Actionable Log Files], você precisa importar os dados de log para o [!DNL Audience Manager]. Os links a seguir ajudarão você a começar:

* Para logs do [!UICONTROL Google Campaign Manager], consulte [Importar arquivos de dados do Google Campaign Manager para o Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *and*, entre em contato com seu consultor do [!DNL Audience Manager].
* Para logs do [!UICONTROL Google Ad Manager] (antigo Google DFP), consulte [Importar arquivos de dados do Google Ad Manager para o Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *and*, entre em contato com o consultor do [!DNL Audience Manager].
* Para outros logs do servidor de anúncios, consulte [Arquivos de Dados e Metadados](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *e*. Entre em contato com o consultor do [!DNL Audience Manager].

Se você já estiver importando dados de log para o [!DNL Audience Manager], peça ao seu consultor do [!DNL Audience Manager] ou ao [Atendimento ao cliente](https://helpx.adobe.com/br/contact/enterprise-support.ec.html) para habilitar o [!UICONTROL Actionable Log Files] para você.

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/br/contact/enterprise-support.ec.html) to get started.

-->

## Trabalhar com arquivos de registro acionáveis {#working-with-actionable-log-files}

Com o [!UICONTROL Actionable Log Files], as informações dos logs do servidor de publicidade são capturadas no [!DNL Audience Manager] da mesma forma que você capturaria os dados das interações do site em tempo real. O [!DNL Audience Manager] se conecta ao seu armazenamento de log do servidor de publicidade, analisa as informações dos logs e envia os dados do log como sinais acionáveis para nossos [Servidores de Coleta de Dados](../../reference/system-components/components-data-collection.md#dcs-pcs).

Você ainda precisa configurar características baseadas em regras para capturar os sinais acionáveis. Veja como configurar características baseadas em regras na [interface do usuário do Audience Manager](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) ou usando as [Ferramentas de Gerenciamento em Massa](../../reference/bulk-management-tools/bulk-create.md). Role para baixo até a seção [Sinais acionáveis](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) para obter uma lista de todas as chaves que você pode usar em características baseadas em regras.

>[!IMPORTANT]
>
>Recomendamos implementar [!UICONTROL Actionable Log Files] *em vez de* [Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md). Desincentivamos o uso de ambas as opções, pois isso resulta em um aumento nas contagens de frequência para características.

## Sinais acionáveis {#actionable-signals}

Os sinais são as [menores unidades de dados](../../reference/signal-trait-segment.md) em [!DNL Audience Manager]. O [!UICONTROL Actionable Log Files] permite capturar valores de anunciante, unidade de negócios, criativo e campanha em eventos de impressão, eventos de clique e eventos de conversão como sinais dos logs do servidor de anúncios.

>[!IMPORTANT]
>
>[!UICONTROL Actionable Log Files] têm suporte para os seguintes servidores de anúncios:
> <br>
>
> * [Gerente de campanha do Google](#dcm-logs-signals)
> * [Gerenciador de Anúncios do Google](#ad-manager-logs-signals)
> * [Adobe Advertising Cloud, Flashtalk e Sizmek](#generic-logs-signals)

Lembre-se de que, para usar essas informações para a criação e segmentação de público-alvo, é necessário configurar as características com base em regras.

### Sinais acionáveis de logs do Google Campaign Manager {#dcm-logs-signals}

A tabela lista os sinais acionáveis de [!DNL Google Campaign Manager] arquivos de log:

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
   <td colname="col3"> <p>Disponível somente para eventos de conversão. </p> <p>Representa a ID numérica da atividade de conversão no Google Campaign Manager. Este campo mapeia para a ID da atividade do gerente de campanha da Google. </p> <p> <p>Dica: você pode capturar várias atividades de conversão ou atividades específicas do Google Campaign Manager. Crie características usando <code> d_conversion = activity ID</code> para cada atividade de conversão do Google Campaign Manager. </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Disponível somente para eventos de conversão. </p> <p>Este campo mapeia para a ID de conversão no Google Campaign Manager. Indica a atividade que precede a conversão do usuário do Google Campaign Manager. </p> <p>Os valores aceitos são: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> para conversões pós-clique. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> para conversões pós-impressão. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> para conversões sem correspondência. A conversão não pode corresponder a uma atividade anterior. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">Uma data e hora UTC para o evento de impressão, clique ou conversão. Representado em microssegundos desde 1970-01-01 00:00:00 UTC.</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>Um código de integração para a fonte de dados do anunciante. Observe que isso não está relacionado às fontes de dados Audience Manager.</p> <p>Este campo mapeia para a ID de grupo do anunciante do gerente de campanha do Google. </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>ID da unidade de negócios. Este campo mapeia para a ID do anunciante do Gerenciador de campanhas do Google. </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>A ID da campanha fornecida pelo Gerente de campanha do Google.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>A Creative ID fornecida pelo Gerente de campanha do Google. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> O valor das vendas em USD, à potência de -6. Multiplique por 1.000.000 para ver como uma quantia em dólar.</td> 
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
   <td colname="col3"> <p>A ID da fonte de dados usada para capturar dados do Google Campaign Manager. Consulte <a href="../../features/manage-datasources.md#create-data-source"> Como Criar uma Source de Dados</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Os sinais descritos na tabela são capturados em [!DNL Audience Manager] como uma chamada `HTTP` em tempo real. A chamada de exemplo abaixo contém informações sobre um evento de conversão de [!DNL Google Campaign Manager]. As chamadas não precisam necessariamente incluir *todos* os sinais na chamada de exemplo.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

Para um arquivo de log de tamanho médio [!DNL Google Campaign Manager] de 2 milhões de linhas, todas as características criadas a partir de sinais acionáveis são percebidas dentro de aproximadamente uma hora após processarmos os logs.

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>O carimbo de data/hora do evento fornecido nos logs [!DNL Google Campaign Manager] será respeitado e passado para [!UICONTROL Data Collection Servers].
>
>* Se um carimbo de data/hora não estiver disponível para uma linha de dados no arquivo de log [!DNL Google Campaign Manager], usamos a hora da chamada `HTTP` como carimbo de data/hora do evento.
>* Se a linha de dados no arquivo de log [!DNL Google Campaign Manager] contiver um carimbo de data/hora malformado, ignoraremos a linha inteira.

<br> 

### Sinais Acionáveis de [!DNL Google Ad Manager] logs {#ad-manager-logs-signals}

A tabela lista os sinais acionáveis de [!DNL Google Ad Manager] arquivos de log:


| Nome do cabeçalho no arquivo de log | Sinal | Descrição |
|---------|----------|---------|
| `LineItemId` | `d_lineitem` | A ID numérica do item de linha entregue do Gerenciador de publicidade |
| `OrderId` | `d_orderid` | A ID numérica da ordem do Gerenciador de anúncios que continha o item de linha entregue e o criativo. |
| `CreativeId` | `d_creative` | A ID numérica do criativo entregue do Ad Manager. |
| `-` | `d_event` | Indica o tipo de evento. O Audience Manager lê o tipo de evento do nome do arquivo de registro do Ad Manager e o transforma em um sinal acionável. Os valores aceitos são: <br> <ul><li>d_event = imp para impressões.</li><li>d_event = clique para cliques.</li><li>d_event = conv para conversões e atividades.</li></ul> |
| `-` | `d_src` | A ID da fonte de dados usada para capturar os dados do Ad Manager. Consulte [Como Criar uma Source de Dados](/help/using/features/manage-datasources.md). |

Os sinais descritos na tabela são capturados no Audience Manager como uma chamada HTTP em tempo real. O exemplo de chamada abaixo contém informações sobre um evento de conversão do Google Ad Manager. As chamadas não precisam necessariamente incluir todos os sinais na chamada de exemplo.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>O carimbo de data/hora do evento fornecido nos logs [!DNL Google Ad Manager] será respeitado e passado para [!UICONTROL Data Collection Servers].
>
>
>* Se um carimbo de data/hora não estiver disponível para uma linha de dados no arquivo de log [!DNL Google Ad Manager], usamos a hora da chamada `HTTP` como carimbo de data/hora do evento.
>* Se a linha de dados no arquivo de log [!DNL Google Ad Manager] contiver um carimbo de data/hora malformado, ignoraremos a linha inteira.

<br> 

### Sinais acionáveis de logs de servidor de anúncios do Adobe Advertising Cloud, Flashtalk e Sizmek {#generic-logs-signals}

Primeiro, você deve depositar os logs do servidor de anúncios em nossos buckets do Amazon S3. Para fazer isso, leia os [Arquivos de Dados para os Relatórios de Audience Optimization e os Arquivos de Log Acionáveis](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *e* e entre em contato com seu consultor do [!DNL Audience Manager]. A tabela lista os sinais acionáveis dos arquivos de log do servidor de anúncios:

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
   <td colname="col3"> <p>Indica se uma conversão corresponde ou não. As opções incluem: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 0</code> Impressão </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code> Clique </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> Não atribuído ou desconhecido </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> Uma data e hora UTC para o evento de impressão, clique ou conversão. Use o formato <code>yyyy-MM-dd HH:mm:ss</code>. </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>Um código de integração para a fonte de dados do anunciante. Observe que este campo não está relacionado a <a href="../../features/datasources-list-and-settings.md">fontes de dados Audience Manager.</a></p></td> 
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
   <td colname="col3"> <p>A ID da campanha do arquivo de log.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>A Creative ID do arquivo de log. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> Compra ou outro valor de conversão. Tipo de dados: Flutuante. </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Indica o tipo de evento. O Audience Manager lê o tipo de evento do nome do arquivo de log e o transforma em um sinal acionável. Consulte <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">convenções de nomenclatura de arquivos de log</a>. </p> <p>Os valores aceitos são: </p> <p> 
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
   <td colname="col3"> <p>A ID da fonte de dados usada para capturar dados de log. Consulte <a href="../../features/manage-datasources.md#create-data-source"> Como Criar uma Source de Dados</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Os sinais descritos na tabela são capturados em [!DNL Audience Manager] como uma chamada `HTTP` em tempo real. As chamadas não precisam necessariamente incluir *todos* os sinais na chamada de exemplo.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Trabalhar com sinais acionáveis na interface do usuário do Audience Manager {#actionable-signals-in-ui}

Você pode visualizar os sinais acionáveis recebidos na interface da [Pesquisa de sinais](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md).

Vá para **Dados de Público** (1) > **Sinais** (2) > **Pesquisar** (3) e selecione o filtro **Arquivos de Log Acionáveis** (4).

![Sinais acionáveis na interface do usuário](/help/using/integration/assets/alf-in-signals.png)

Para criar características baseadas em regras usando seus sinais acionáveis, selecione **Arquivos de Log Acionáveis** (1), selecione os sinais acionáveis que você deseja usar como regras de características (2) e pressione **Criar Característica dos Sinais Selecionados** (3).

![Criar características a partir de sinais](/help/using/integration/assets/alf-create-trait.png)


## Casos de uso {#use-cases}

Um benefício de implementar o [!UICONTROL Actionable Log Files] é a opção de aplicar controles de [recenticidade e frequência](../../features/segments/recency-and-frequency.md) a qualquer [característica com base em regras](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) que contenha sinais acionáveis. Isso permite, por exemplo, limitar a frequência do número de vezes que um usuário recebe um anúncio específico em uma campanha de mídia. Leia [Supressão instantânea entre dispositivos](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) para saber como fazer isso. Outros casos de uso incluem:

### Redirecionar usuários

Redirecione usuários que viram o creative 123, mas não clicaram ou converteram e mostrem o creative 456. Faça o seguinte:

1. Crie uma característica para capturar os usuários que viram o criativo. Digamos que você nomeie a característica [!DNL Creative Trait 123]. Usar a regra de característica:

   `d_creative == 123 AND d_event == imp`

2. Crie uma característica para capturar usuários que clicam ou convertem. Digamos que você nomeie este [!DNL Click and Converter]. Usar a regra de característica:

   `d_event == click OR d_event=conv`

3. Crie um segmento para popular com usuários que viram o creative 123, mas não clicaram nem converteram. Nomeie-o [!DNL Retarget Users] e use a regra de segmento:

   `Creative Trait 123 AND NOT Click and Converter`

4. Mapeie o segmento [!DNL Retarget Users] para um destino e direcione usuários no destino com o creative 456.

### Use a atividade de Floodlight do Google Campaign Manager nos Relatórios de Audience Optimization ou no Audience Lab

[As marcas Floodlight](https://support.google.com/dcm/partner/answer/4293719?hl=en) permitem que anunciantes rastreiem conversões de usuário. Com o [!UICONTROL Actionable Log Files], você pode acompanhar as [!DNL Google Campaign Manager] conversões nos [Relatórios de Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md) ou no [Audience Lab](../../features/audience-lab/audience-lab.md):

1. Crie uma característica e use a seguinte regra de característica para capturar uma conversão dos logs do servidor de publicidade:

   `d_event == conv AND d_conversion == 123`

   Ao criar a característica no Audience Manager [!UICONTROL UI], selecione [!UICONTROL Conversion] como [!UICONTROL Event Type].

2. Depois de criar a característica, a conversão começará a ser relatada no [!UICONTROL Audience Optimization Reports] e em [!UICONTROL Audience Lab].

>[!MORELIKETHIS]
>
>* [Importar arquivos de dados do Google Campaign Manager para o Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Relatórios de otimização de público-alvo](../../reporting/audience-optimization-reports/audience-optimization-reports.md)
