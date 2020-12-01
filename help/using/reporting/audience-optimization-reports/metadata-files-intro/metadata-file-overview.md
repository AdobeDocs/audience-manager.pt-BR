---
description: Um arquivo de metadados vincula IDs numéricas com nomes que você pode ler e entender. Os relatórios de Audience Optimization exibem nomes legíveis nos vários menus de opções de relatório.
seo-description: Um arquivo de metadados vincula IDs numéricas com nomes que você pode ler e entender. Os relatórios de Audience Optimization exibem nomes legíveis nos vários menus de opções de relatório.
seo-title: Visão geral e mapeamentos para arquivos de metadados
solution: Audience Manager
title: Visão geral e mapeamentos para arquivos de metadados
uuid: 70df7f11-69c5-4873-a69d-8f93f94e9837
feature: log files
translation-type: tm+mt
source-git-commit: 5d6983f5308f1dfd4560ee1b38bcaee3ca6e422f
workflow-type: tm+mt
source-wordcount: '841'
ht-degree: 4%

---


# Visão geral e mapeamentos para arquivos de metadados{#overview-and-mappings-for-metadata-files}

Um arquivo de metadados vincula IDs numéricas com nomes que você pode ler e entender. Os relatórios de Audience Optimization exibem nomes legíveis nos vários menus de opções de relatório.

## Visão geral {#overview}

Uma análise dos metadados e como eles são usados. Um arquivo de metadados deve ser acompanhado por um arquivo de dados. O conteúdo do arquivo de metadados corresponde às informações do arquivo de dados a rótulos relacionados e legíveis por humanos nos menus do relatório. Para obter mais informações, consulte [Arquivos de dados para relatórios de Audience Optimization e arquivos de registro acionáveis](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md).

### Os Arquivos De Metadados Contêm Dados Sobre Outros Dados

Um arquivo de metadados contém informações sobre outros tipos de dados. Para ajudá-lo a entender como isso funciona, vamos rever como [!DNL Audience Manager] recebe os dados.

Durante uma impressão ou evento de clique, [!DNL Audience Manager] recebe dados em uma sequência de caracteres de URL conhecida como *chamada de evento*.

A chamada do evento organiza informações em conjuntos de pares de valores chave definidos. Os valores em um par de valores chave contêm dados numéricos. O arquivo de metadados contém nomes e outras informações legíveis correspondentes à ID em cada par de valor chave.

### IDs de links de metadados para nomes legíveis

O arquivo de metadados é necessário para vincular uma ID numérica a um nome legível. Por exemplo, digamos que uma chamada de evento contenha uma ID criativa em um par de valor chave como este: `d_creative:1234`. Sem um arquivo de metadados, esse anúncio seria exibido como 1234 em um menu de opções.

No entanto, um arquivo de metadados devidamente formatado pode vincular esse anúncio a um nome real como &quot;Advertiser Creative A&quot;, que é um nome que você pode ler e reconhecer em um relatório.

### Quando você precisa de um arquivo de metadados

Primeiro, um arquivo de metadados e todos os parâmetros listados abaixo são necessários em uma chamada de evento quando você deseja usar os [Relatórios de Audience Optimization](../../../reporting/audience-optimization-reports/audience-optimization-reports.md).

Em segundo lugar, você precisa de um arquivo de metadados se estiver enviando seus próprios dados para [!DNL Audience Manager] ou se quiser ver os dados nos relatórios de outros provedores com os quais não estamos integrados. Por exemplo, [!DNL Audience Manager] tem uma integração com o [Duplo-clique no Gerenciador de Campanhas](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) (DCM) do Google. Devido a essa relação, [!DNL Audience Manager] pode associar IDs a nomes e descrições usados pelas opções de relatório. Sem uma integração, ainda podemos assimilar dados, mas as opções de relatório mostrarão IDs numéricas em vez de nome descritivo.

![imagem do menu de metadados](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_menu.png)

## Mapeamentos de arquivo {#file-mappings}

A tabela a seguir lista os pares de valores chave que contêm dados usados pelos relatórios [!UICONTROL Audience Optimization]. Se você precisar usar um arquivo de metadados, ele conterá informações legíveis para humanos que correspondem aos valores nesses pares de valores chave. Os valores dessas chaves aceitam apenas números inteiros (tipo de dados INT). Observação: *italics* indica um espaço reservado variável. Outros elementos são constantes ou teclas e não são alterados.

>[!IMPORTANT]
>
>Se você estiver usando os relatórios [!UICONTROL Audience Optimization], *todos* desses valores serão necessários na chamada do evento.

<table id="table_B2C8C493080E449CA71C4EF07D9476BD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opção de relatório </th> 
   <th colname="col2" class="entry"> Pares de valores principais de metadados </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Anunciante </p> </td> 
   <td colname="col2"> <p> <code>d_adsrc = <i>data source ID or integration code</i></code> </p> <p>Essa é a ID da fonte de dados ou o código de integração do anunciante fornecido ao criar uma fonte de dados. Consulte <a href="../../../features/manage-datasources.md#create-data-source"> Criar uma fonte de dados</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Unidade de negócio (BU) </p> </td> 
   <td colname="col2"> <p> <code>d_bu = <i>business unit ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campanha </p> </td> 
   <td colname="col2"> <p> <code>d_campaign = <i>campaign ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative </p> </td> 
   <td colname="col2"> <p> <code>d_creative = <i>creative ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exchange </p> </td> 
   <td colname="col2"> <p>Aceita dois pares de valores chave diferentes: </p> 
    <ul id="ul_3B3B751A8A134096B0912E81A0983B9D"> 
     <li id="li_57BAC45A7B274AB695945E174A4D8A35"> <code>d_exchange = <i>ID for the exchange that served the ad</i></code> </li> 
     <li id="li_CCDF00DE59D3451C8EF590DD3E1A806D"> <code>d_site = <i>ID for the site an ad served on</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ordem de inserção (E/S) </p> </td> 
   <td colname="col2"> <p> <code>d_io = <i>insertion order ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plataforma </p> </td> 
   <td colname="col2"> <p> <code>d_src = <i>data source ID</i></code> </p> <p>Essa é a ID <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> da fonte de dados</a> da plataforma que fornece informações de metadados (por exemplo, DFA, Atlas, GBM, MediaMath etc.). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tático </p> </td> 
   <td colname="col2"> <p> <code>d_tactic = <i>tactic ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertical </p> </td> 
   <td colname="col2"> <p> <code>d_vert = <i>vertical ID</i></code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Como as IDs de chamada de Evento formam nomes de arquivos, conteúdo e caminhos de Delivery {#how-ids-shape-file-names}

As IDs enviadas por esses pares de valores chave ajudam a criar o nome do arquivo de metadados e seu conteúdo. As seções e ilustrações a seguir demonstram como isso funciona. Esses exemplos criam um arquivo que contém o nome de um anúncio em uma campanha, mas outras combinações são possíveis.

### Chamada de evento

Neste exemplo, criaremos um arquivo de metadados que traz nomes criativos para um relatório [!UICONTROL Audience Optimization]. Para fazer isso, precisamos extrair IDs criativas, de campanha e de fonte de dados de uma chamada de evento.

![Imagem de chamada de evento](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_event.png)

### Nome do arquivo

O nome do arquivo é baseado nas IDs criativas, de campanha e de fonte de dados. Nesse caso, compare as diferenças aqui entre os dados de valor chave em uma chamada de evento e como eles são usados em um nome de arquivo.

Em um nome de arquivo:

* A chave da fonte de dados muda para `dpid` de `d_src`.

* As IDs criativas e de campanha representam uma categoria em vez de um identificador real.

![como é criado um nome de arquivo](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_name.png)

Consulte [Convenções de nomenclatura para arquivos de metadados](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md).

### Conteúdo do arquivo

Neste exemplo, o conteúdo do arquivo reflete as IDs criativas e de campanha passadas na chamada do evento. O novo elemento aqui é um nome legível. Depois de processado, o nome neste arquivo aparecerá como uma opção no menu Criativo de um relatório [!UICONTROL Audience Optimization].

![conteúdo de um arquivo de metadados](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_contents.png)

Consulte [Formato de conteúdo para arquivos de metadados](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md).

### Delivery de arquivo

Depois de nomear e adicionar dados a um arquivo, envie-os para um diretório de armazenamentos Amazon S3 fornecido por [!DNL Audience Manager]. Consulte [Métodos de Delivery para Arquivos de Metadados](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md).

>[!MORELIKETHIS]
>
>* [Arquivos de dados para relatórios Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [Captura de dados de cliques da campanha via Pixel Calls](../../../integration/media-data-integration/click-data-pixels.md)
>* [Captura de dados de impressão da campanha via Pixel Calls](../../../integration/media-data-integration/impression-data-pixels.md)

