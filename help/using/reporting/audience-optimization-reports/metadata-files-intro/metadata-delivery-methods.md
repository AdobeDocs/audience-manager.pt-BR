---
description: Envie ou atualize arquivos de metadados enviando-os para um diretório especial do Amazon S3 para sua conta do Audience Manager. Consulte esta seção para obter informações sobre caminhos de entrega/diretório, tempos de processamento de arquivos e atualizações.
seo-description: Envie ou atualize arquivos de metadados enviando-os para um diretório especial do Amazon S3 para sua conta do Audience Manager. Consulte esta seção para obter informações sobre caminhos de entrega/diretório, tempos de processamento de arquivos e atualizações.
seo-title: Métodos de entrega para arquivos de metadados
solution: Audience Manager
title: Métodos de entrega para arquivos de metadados
uuid: 5199e9b-920d-423d-8070-05a017ecd562
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Métodos de entrega para arquivos de metadados{#delivery-methods-for-metadata-files}

Envie ou atualize arquivos de metadados enviando-os para um diretório especial do Amazon S3 para sua conta do Audience Manager. Consulte esta seção para obter informações sobre caminhos de entrega/diretório, tempos de processamento de arquivos e atualizações.

## Sintaxe do caminho de entrega e exemplos {#syntax}

Os dados são armazenados em namespace separado para cada cliente em um diretório Amazon S3. O caminho do arquivo segue a sintaxe mostrada abaixo. Note, *italics* indicates a variable placeholder. Colchetes `[ ]` indicam parâmetros opcionais. Os outros elementos são constantes e não são alterados.

**Sintaxe:**
<pre><code>.../log_ingestion/pid=ID<i>do</i>AAM/dpid= <i>d_src</i>/[meta|status]/ <i>aayymmdd</i>_ ID <i></i>pai_ ID <i>filho</i></code></pre>

A tabela a seguir define cada um desses elementos em um caminho de entrega de arquivo.

<table id="table_E3DB873D4CB3479AA7173838EB9898CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro de arquivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> .../log_ingestão/</code> </p> </td> 
   <td colname="col2"> <p>Este é o início do caminho de armazenamento do diretório. Você receberá o caminho completo quando tudo estiver configurado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=ID<i>AAM</i></code> </p> </td> 
   <td colname="col2"> <p>Esse par de valores chave que contém a ID do cliente do <span class="keyword"> Audience Manager</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>Esse par de valor-chave contém a ID da fonte de dados transmitida em uma chamada de evento. A ID da fonte de dados é o valor que vincula todo o conteúdo do arquivo aos dados reais aos quais ele pertence. </p> <p>Por exemplo, digamos que você tenha um anúncio com a ID 123 e o nome "Advertiser Creative A". Como uma chamada de evento só passa na ID, é necessário incluir "Advertiser Creative A" no arquivo de metadados. A campanha e o anúncio pertencem a uma fonte de dados. A ID da fonte de dados é o que os vincula e permite associar com precisão o conteúdo do arquivo a uma ID enviada em uma chamada de evento. Consulte <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names"> Como as IDs de chamada de evento determinam nomes de arquivo, conteúdo e caminhos</a>de entrega. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_8AFA4E7FCE984789AF05EA31718F39CD"> 
     <li id="li_A493880F6ECB467DBB590226CC7A5847"> <code> meta</code> </li> 
     <li id="li_2D6DAC956D084A1DB43C9C5B2C821F87"> <code> status</code> </li> 
    </ul> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_5907ADF5B20C4FEC94EF5A09BE02F2CD"> 
      <li id="li_AE70B44FEDCF4A05ADAFF4E49296F67D"> <code> meta</code> é um diretório de upload/armazenamento de arquivos. </li> 
      <li id="li_2ADEA90E01364E888CAAAB8A65A6383F"> <code> status</code> é um caminho para um diretório que contém informações de sucesso ou falha sobre seus arquivos processados. Depois que o arquivo for processado, você verá um arquivo <code> .info</code> com o título do carimbo de data e hora <code> aaaammdd</code> . Os arquivos de status contêm dados em um objeto JSON. Consulte <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md"> Atualizações de status para arquivos</a>de metadados. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ID <i>_</i>filho_<i>aaaammdd</i>_<i>parent</i></code> </p> </td> 
   <td colname="col2"> <p>Este é o nome do arquivo. Consulte <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Nomear convenções para arquivos</a>de metadados. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemplo de caminhos de upload e status**

Para carregar um arquivo de metadados ou [verificar seu status](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md), os caminhos de arquivo serão semelhantes aos seguintes:

* Caminho de upload: `/log_ingestion/pid=1234/dpid=567/meta/20150827_1_2`
* Caminho do status de processamento: `/log_ingestion/pid=1234/dpid=567/status/20150827.info`.

## Tempos e atualizações de processamento de arquivo {#processing-times}

Os arquivos de metadados são processados quatro vezes por dia, em intervalos regulares.

Para atualizar seus registros de metadados, basta enviar um arquivo que contenha novas informações. Não é necessário enviar atualizações completas sempre.
