---
description: Envie ou atualize arquivos de metadados enviando-os para um diretório especial do Amazon S3 para sua conta do Audience Manager. Consulte esta seção para obter informações sobre caminhos de entrega/diretório, tempos de processamento de arquivos e atualizações.
seo-description: Envie ou atualize arquivos de metadados enviando-os para um diretório especial do Amazon S3 para sua conta do Audience Manager. Consulte esta seção para obter informações sobre caminhos de entrega/diretório, tempos de processamento de arquivos e atualizações.
seo-title: Métodos de entrega para arquivos de metadados
solution: Audience Manager
title: Métodos de entrega para arquivos de metadados
uuid: 5199e9b-920d-423d-8070-05a017ecd562
translation-type: tm+mt
source-git-commit: 1ff46970470eae4bc30760468013d994c976e549

---


# Métodos de entrega para arquivos de metadados{#delivery-methods-for-metadata-files}

Envie ou atualize arquivos de metadados enviando-os para um diretório especial do Amazon S3 para sua conta do Audience Manager. Consulte esta seção para obter informações sobre caminhos de entrega/diretório, tempos de processamento de arquivos e atualizações.

## Sintaxe do caminho de entrega e exemplos {#syntax}

Os dados são armazenados em namespace separado para cada cliente em um diretório Amazon S3. O caminho do arquivo segue a sintaxe mostrada abaixo. Note, *italics* indicates a variable placeholder. Colchetes `[ ]` indicam parâmetros opcionais. Os outros elementos são constantes e não são alterados.

**Sintaxe:**
<pre><code>.../log_ingestion/pid=<i>AAM ID</i>/dpid= <i>d_src</i>/[meta|status]/ <i>yyyymmdd</i>_ <i>parent ID</i>_ <i>child ID</i></code></pre>

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
   <td colname="col1"> <p> <code> .../log_ingestion/</code> </p> </td> 
   <td colname="col2"> <p>Este é o início do caminho de armazenamento do diretório. Você receberá o caminho completo quando tudo estiver configurado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>Esse par de valores chave que contém a ID do cliente do <span class="keyword"> Audience Manager</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>Esse par de valor-chave contém a ID da fonte de dados transmitida em uma chamada de evento. A ID da fonte de dados é o valor que vincula todo o conteúdo do arquivo aos dados reais aos quais ele pertence. </p> <p>Por exemplo, digamos que você tenha um anúncio com a ID 123 e o nome "Advertiser Creative A". Como uma chamada de evento só passa na ID, é necessário incluir "Advertiser Creative A" no arquivo de metadados. A campanha e o anúncio pertencem a uma fonte de dados. A ID da fonte de dados é o que os vincula e permite associar com precisão o conteúdo do arquivo a uma ID enviada em uma chamada de evento. Consulte <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names"> Como as IDs de chamada de evento determinam nomes de arquivo, conteúdo e caminhos</a>de entrega. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>yyyymmdd</i>_<i>parent ID</i>_<i>child ID</i></code> </p> </td> 
   <td colname="col2"> <p>Este é o nome do arquivo. Consulte <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Nomear convenções para arquivos</a>de metadados. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Tempos e atualizações de processamento de arquivo {#processing-times}

Os arquivos de metadados são processados quatro vezes por dia, em intervalos regulares.

Para atualizar seus registros de metadados, basta enviar um arquivo que contenha novas informações. Não é necessário enviar atualizações completas sempre.
