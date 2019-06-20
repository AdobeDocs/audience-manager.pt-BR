---
description: Envie ou atualize arquivos de metadados enviando-os a um diretório especial Amazon S 3 para sua conta do Audience Manager. Consulte esta seção para obter informações sobre caminhos de entrega/diretório, tempo de processamento de arquivos e atualizações.
seo-description: Envie ou atualize arquivos de metadados enviando-os a um diretório especial Amazon S 3 para sua conta do Audience Manager. Consulte esta seção para obter informações sobre caminhos de entrega/diretório, tempo de processamento de arquivos e atualizações.
seo-title: Métodos de entrega para arquivos de metadados
solution: Audience Manager
title: Métodos de entrega para arquivos de metadados
uuid: 5199 ee 9 b -920 d -423 d -8070-05 a 017 asu 562
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Delivery Methods for Metadata Files{#delivery-methods-for-metadata-files}

Envie ou atualize arquivos de metadados enviando-os a um diretório especial Amazon S 3 para sua conta do Audience Manager. Consulte esta seção para obter informações sobre caminhos de entrega/diretório, tempo de processamento de arquivos e atualizações.

## Delivery Path Syntax and Examples {#syntax}

Os dados são armazenados em namespaces separados para cada cliente em um diretório Amazon S 3. O caminho do arquivo segue a sintaxe mostrada abaixo. Note, *italics* indicates a variable placeholder. Brackets `[ ]` indicate optional parameters. Os outros elementos são constantes e não são alterados.

**Sintaxe:**
<pre><code>…/log_ ingestion/pid =<i>AAM ID</i>/dpid = <i>d_ src</i>/[meta | status]/ <i>aaaammdd</i>_ <i>parent ID</i>_ <i>filho ID</i></code></pre>

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
   <td colname="col1"> <p> <code> …/log_ ingestion/</code> </p> </td> 
   <td colname="col2"> <p>Este é o início do caminho de armazenamento de diretório. Você receberá o caminho completo quando tudo estiver configurado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid =<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>This key-value pair that contains your <span class="keyword"> Audience Manager</span> customer ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid =<i>d_ src</i></code> </p> </td> 
   <td colname="col2"> <p>Esse par de valor chave contém a ID de fonte de dados transmitida em uma chamada de evento. A ID da fonte de dados é o valor que vincula todo o conteúdo do arquivo aos dados reais aos quais pertence. </p> <p>Por exemplo, digamos que você tenha um anúncio com a ID 123 e o nome "Anunciante A A." Como uma chamada de evento somente passa na ID que você precisa incluir no arquivo de metadados. A campanha e criação pertencem a uma fonte de dados. A ID da fonte de dados é o que os une em conjunto e permite associar com precisão conteúdos de arquivo a uma ID enviada em uma chamada de evento. See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names"> How Event Call IDs Determine File Names, Contents, and Delivery Paths</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_8AFA4E7FCE984789AF05EA31718F39CD"> 
     <li id="li_A493880F6ECB467DBB590226CC7A5847"> <code> meta</code> </li> 
     <li id="li_2D6DAC956D084A1DB43C9C5B2C821F87"> <code> status</code> </li> 
    </ul> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_5907ADF5B20C4FEC94EF5A09BE02F2CD"> 
      <li id="li_AE70B44FEDCF4A05ADAFF4E49296F67D"> <code> meta</code> é um upload de arquivo/diretório de armazenamento. </li> 
      <li id="li_2ADEA90E01364E888CAAAB8A65A6383F"> <code> é</code> um caminho para um diretório que contém informações de sucesso ou falha sobre os arquivos processados. After your file is processed, you'll see a <code> .info</code> file with <code> yyyymmdd</code> timestamp title. Os arquivos de status contêm dados em um objeto JSON. See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md"> Status Updates for Metadata Files</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>aaaammdd</i>_<i>parent ID</i>_<i>child ID</i></code> </p> </td> 
   <td colname="col2"> <p>Esse é o nome do arquivo. See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Naming Conventions for Metadata Files</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Amostra de upload e caminhos de status**

To upload a metadata file or to [check its status](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md), the file paths will look similar to these:

* Upload path: `/log_ingestion/pid=1234/dpid=567/meta/20150827_1_2`
* Processing status path: `/log_ingestion/pid=1234/dpid=567/status/20150827.info`.

## File Processing Times and Updates {#processing-times}

Os arquivos de metadados são processados quatro vezes por dia, em intervalos regulares.

Para atualizar os registros de metadados, basta enviar um arquivo que contenha novas informações. Você não precisa enviar atualizações completas todas as vezes.
