---
description: Um arquivo de metadados vincula IDs numéricas com nomes que você pode ler e entender. Os relatórios de Otimização de público-alvo exibem nomes legíveis nos vários menus de opções de relatório.
seo-description: Um arquivo de metadados vincula IDs numéricas com nomes que você pode ler e entender. Os relatórios de Otimização de público-alvo exibem nomes legíveis nos vários menus de opções de relatório.
seo-title: Visão geral e mapeamentos para arquivos de metadados
solution: Audience Manager
title: Visão geral e mapeamentos para arquivos de metadados
uuid: 70 df 7 f 11-69 c 5-4873-a 69 d -8 f 93 f 94 e 9837
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Overview and Mappings for Metadata Files{#overview-and-mappings-for-metadata-files}

Um arquivo de metadados vincula IDs numéricas com nomes que você pode ler e entender. Os relatórios de Otimização de público-alvo exibem nomes legíveis nos vários menus de opções de relatório.

## Visão geral {#overview}

Uma revisão de metadados e como ela é usada. Um arquivo de metadados deve ser acompanhado de um arquivo de dados. O conteúdo do arquivo de metadados corresponde a informações do arquivo de dados para rótulos relacionados e legíveis, nos menus do relatório. For more information, see [Data Files for Audience Optimization Reports](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md).

### Arquivos de metadados contém dados sobre outros dados

Um arquivo de metadados contém informações sobre outros tipos de dados. To help you understand how this works, let’s review how [!DNL Audience Manager] receives data.

During an impression or click event, [!DNL Audience Manager] receives data in an URL string known as an *event call*.

A chamada de evento organiza informações em conjuntos de pares de valores chave definidos. Os valores em um par de valor chave contêm dados numéricos. O arquivo de metadados contém nomes e outras informações legíveis que correspondem à ID em cada par de valor chave.

### IDs de links de metadados para nomes legíveis

O arquivo de metadados é necessário para vincular uma ID numérica a um nome legível. As an example, say an event call contains a creative ID in a key-value pair like this: `d_creative:1234`. Sem um arquivo de metadados, essa criação apareceria como 1234 em um menu de opções.

No entanto, um arquivo de metadados formatado adequadamente pode vincular essa criação a um nome real, como «Anunciante a Creative A», que é um nome que você pode ler e reconhecer em um relatório.

### Quando necessário um arquivo de metadados

First, a metadata file, and all of the parameters listed below, are required in an event call when you want to use the [Audience Optimization Reports](../../../reporting/audience-optimization-reports/audience-optimization-reports.md).

Second, you need a metadata file if you’re sending your own data to [!DNL Audience Manager] or if you want to see data in the reports from other providers we’re not integrated with. For example, [!DNL Audience Manager] has an integration with Google’s [Double-click Campaign Manager](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) (DCM). Because of this relationship, [!DNL Audience Manager] can associate IDs with names and descriptions used by the report options. Sem uma integração, ainda podemos assimilar dados, mas as opções de relatório mostrarão IDs numéricas em vez de nome descritivo.

![](assets/metadata_menu.png)

## File Mappings {#file-mappings}

The following table lists the key-value pairs that hold data used by the [!UICONTROL Audience Optimization] reports. Se você precisar usar um arquivo de metadados, ele conterá informações legível por humanos que correspondam aos valores desses pares chave-valor. Os valores dessas teclas aceitam apenas inteiros (tipo de dados INT). Note, *italics* indicates a variable placeholder. Outros elementos são constantes ou teclas e não são alteradas.

>[!IMPORTANT]
>
>If you&#39;re using the [!UICONTROL Audience Optimization] reports, *all* of these values are required in the event call.

<table id="table_B2C8C493080E449CA71C4EF07D9476BD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opção de relatório </th> 
   <th colname="col2" class="entry"> Pares de valores chave de metadados </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Anunciante </p> </td> 
   <td colname="col2"> <p> <code>d_ adsrc = <i>ID de fonte de dados ou código de integração</i></code> </p> <p>Este é o ID de fonte de dados ou código de integração do anunciante fornecidos durante a criação de uma fonte de dados. See <a href="../../../features/manage-datasources.md#create-data-source"> Create a Data Source</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Unidade de negócios (BU) </p> </td> 
   <td colname="col2"> <p> <code>d_ bu = <i>ID de unidade de negócio</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campanha </p> </td> 
   <td colname="col2"> <p> <code>d_ campaign = <i>ID da campanha</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative </p> </td> 
   <td colname="col2"> <p> <code>d_ creative = <i>id criativa</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exchange </p> </td> 
   <td colname="col2"> <p>Aceita 2 pares de valor chave diferentes: </p> 
    <ul id="ul_3B3B751A8A134096B0912E81A0983B9D"> 
     <li id="li_57BAC45A7B274AB695945E174A4D8A35"> <code>d_ exchange = <i>ID para a troca que hospeda o anúncio</i></code> </li> 
     <li id="li_CCDF00DE59D3451C8EF590DD3E1A806D"> <code>d_ site = <i>ID para o site em que um anúncio foi veiculado</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ordem de inserção (IO) </p> </td> 
   <td colname="col2"> <p> <code>d_ io = <i>ID do pedido de inserção</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plataforma </p> </td> 
   <td colname="col2"> <p> <code>d_ src = <i>ID da fonte de dados</i></code> </p> <p>This is the <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> data source</a> ID for the platform providing metadata information (e.g., DFA, Atlas, GBM, MediaMath, etc.). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Táticas </p> </td> 
   <td colname="col2"> <p> <code>d_ toma = <i>tática ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertical </p> </td> 
   <td colname="col2"> <p> <code>d_ vert = <i>ID vertical</i></code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## How Event Call IDs Shape File Names, Contents, and Delivery Paths {#how-ids-shape-file-names}

As IDs enviadas por esses pares chave-valor ajudam a criar o nome do arquivo de metadados e seu conteúdo. As seções e ilustrações a seguir demonstram como isso funciona. Esses exemplos criam um arquivo que contém o nome de uma criação em uma campanha, mas outras combinações são possíveis.

### Chamada de evento

In this example we&#39;ll create a metadata file that brings creative names in to an [!UICONTROL Audience Optimization] report. Para fazer isso, precisamos extrair IDs de fonte de criação, campanha e dados de uma chamada de evento.

![](assets/metadata_file_event.png)

### Nome do arquivo

O nome do arquivo é baseado nas IDs de fonte, campanha e fonte de dados. Nesse caso, compare as diferenças entre os dados de chave-valor em uma chamada de evento e como ela é usada em um nome de arquivo.

Em um nome de arquivo:

* The data source key changes to `dpid` from `d_src`.

* As IDs de criação e campanha representam uma categoria em vez de um identificador real.

![](assets/metadata_file_name.png)

See [Naming Conventions for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md).

### Conteúdo do arquivo

Neste exemplo, o conteúdo do arquivo reflete as IDs de criação e campanha passadas na chamada do evento. O novo elemento é um nome legível. Once processed, the name in this file will appear as an option in the Creative menu of an [!UICONTROL Audience Optimization] report.

![](assets/metadata_file_contents.png)

See [Content Format for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md).

### Entrega de arquivos

After you name and add data to a file, you send it to an Amazon S3 storage directory provided by [!DNL Audience Manager]. See [Delivery Methods for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md) and [Status Updates for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md).

>[!MORE_ LIKE_ THIS]
>
>* [Arquivos de dados para relatórios de otimização de público-alvo](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [Captura de dados de cliques da campanha por meio de chamadas de pixel](../../../integration/media-data-integration/click-data-pixels.md)
>* [Captura de dados de impressão da campanha via Pixel Calls](../../../integration/media-data-integration/impression-data-pixels.md)

