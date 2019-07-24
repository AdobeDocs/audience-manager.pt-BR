---
description: Um arquivo de dados contém impressão, cliques ou dados de conversão. Quando formatado corretamente, você pode importar esses dados para o Audience Manager e exibi-los nos relatórios de Otimização de público-alvo. Formate seus arquivos de dados de acordo com essas especificações nesta seção.
seo-description: Um arquivo de dados contém impressão, cliques ou dados de conversão. Quando formatado corretamente, você pode importar esses dados para o Audience Manager e exibi-los nos relatórios de Otimização de público-alvo. Formate seus arquivos de dados de acordo com essas especificações nesta seção.
seo-title: Arquivos de dados para relatórios de otimização de público-alvo
solution: Audience Manager
title: Arquivos de dados para relatórios de otimização de público-alvo
uuid: c 19 eb 0 c 7-47 c 1-4 cdf -8 a 6 c-cd 15 fe 04 c 379
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Files for Audience Optimization Reports{#data-files-for-audience-optimization-reports}

Um arquivo de dados contém impressão, cliques ou dados de conversão. Quando formatado corretamente, você pode importar esses dados para o Audience Manager e exibi-los nos relatórios de Otimização de público-alvo. Formate seus arquivos de dados de acordo com essas especificações nesta seção.

## Visão geral {#overview}

A properly named and formatted data file lets you import impression, click, or conversion data into the [Audience Optimization Reports](../../../reporting/audience-optimization-reports/audience-optimization-reports.md). This is useful when working with a partner who is not integrated with [!DNL Audience Manager] and you want to work with their data in that report suite. Esse processo requer arquivos separados para impressão, clique e conversão de dados. Não misture esses eventos em um único arquivo.

Um arquivo de dados deve ser acompanhado de um arquivo de metadados. O conteúdo do arquivo de metadados corresponde a informações do arquivo de dados para rótulos relacionados e legíveis, nos menus do relatório. For more information, see [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## Naming Conventions for Data Files {#naming-conventions}

A sintaxe a seguir define a estrutura de um nome de arquivo de dados bem formado. Note, *italics* indicates a variable placeholder that changes depending on the file contents.

**Sintaxe:** <pre><code><i>event type</i>_<i>aaaammdd</i></code></pre>

Em um nome de arquivo:

* O tipo de evento indica que o arquivo contém impressões, cliques ou conversões. Crie um arquivo separado para cada tipo de evento.
* Um sublinhado separa o tipo de evento e um carimbo de data e hora de ano com ano.
* Before uploading, compress your files using gzip and save them with the `.gz` file extension.

Considerando estes requisitos, nomeie seus arquivos de dados com base em seu conteúdo:

* Dados de impressão: <pre><code>impressões_<i>aaaammdd<i>.gz</code></pre>
* Clique em dados: <pre><code>cliques_<i>aaaammdd</i>.gz</code></pre>
* Dados de conversão: <pre><code>conversões_<i>aaaammdd</i>.gz</code></pre>

## Content Format for Data Files {#content-format}

A sintaxe a seguir define a estrutura do conteúdo em um arquivo de dados bem formado. Note, *italics* indicates a variable placeholder and is replaced with an label in an actual data file.

**Sintaxe:** <pre><code><i>rótulo do cabeçalho 1</i> | <i>rótulo do cabeçalho 2</i> … <i>rótulo do cabeçalho n</i> | <i>version</i></code></pre>

No conteúdo do arquivo:

* Os rótulos de cabeçalho devem aparecer na ordem mostrada na tabela abaixo. As impressões e cliques usam os mesmos rótulos. Os arquivos de conversão contêm cabeçalhos adicionais.
* If you don't have data for a particular column, populate that field with a `NULL` object or `-1`.

* Files *must* end with a version number. A versão atual é 1.1.
* Separe cabeçalhos de arquivo e conteúdo com o caractere ASCII de não impressão 001. Se não puder usar ASCII 001, separe os cabeçalhos e os dados com um delimitador de tabulação. As these are non-printing characters, the syntax example above shows a pipe `"|"` for display purposes only.

**Rótulos de campo**

A tabela abaixo lista e descreve os cabeçalhos das colunas para seu arquivo de dados. Os cabeçalhos fazem distinção entre maiúsculas e minúsculas e devem aparecer conforme ordenados na tabela. Todos os tipos de dados são inteiros (INT), a menos que seja indicado contrário.

<table id="table_D8C5068741C3460380505F95F3016757"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rótulo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Carimbo de data/hora </p> </td> 
   <td colname="col2"> <p>Uma data e hora UTC para impressão, clique ou evento de conversão. Use the <code> yyyy-dd-mm hh:mm:ss</code> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID do usuário </p> </td> 
   <td colname="col2"> <p>Your ID for a site visitor, also known as the <span class="term"> data provider unique user ID</span> or DPUUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de anunciante </p> </td> 
   <td colname="col2"> <p>O ID da fonte de dados ou o código de integração do seu anunciante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>ID da unidade comercial. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID da campanha </p> </td> 
   <td colname="col2"> <p>ID da campanha. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative-ID </p> </td> 
   <td colname="col2"> <p>ID de criação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID do site </p> </td> 
   <td colname="col2"> <p>ID do site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de posicionamento </p> </td> 
   <td colname="col2"> <p> ID de posicionamento numérico do servidor de publicidade. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Inserção-Pedido-ID </p> </td> 
   <td colname="col2"> <p>ID do pedido de inserção. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID tática </p> </td> 
   <td colname="col2"> <p>ID tática. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID vertical </p> </td> 
   <td colname="col2"> <p>ID de uma vertical ou categoria do setor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quantidade </p> </td> 
   <td colname="col2"> <p> O número de itens vendidos em um evento de conversão. </p> <p> <i>Apenas para arquivos de dados de conversão.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Receita </p> </td> 
   <td colname="col2"> <p>Compra ou outra quantia de conversão. Tipo de dados: Flutuante. </p> <p> <i>Apenas para arquivos de dados de conversão.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Outros dados </p> </td> 
   <td colname="col2"> <p>URL da página de aterrissagem de conversão. Tipo de dados: string. </p> <p> <i>Apenas para arquivos de dados de conversão.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tipo de evento </p> </td> 
   <td colname="col2"> <p>Tipo de conversão. Indica se uma conversão está correspondente ou não. As opções incluem: </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: Impressão </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: Clique em </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>: Não atribuído ou desconhecido </li> 
    </ul> <p> <i>Apenas para arquivos de dados de conversão.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Versão </p> </td> 
   <td colname="col2"> <p>Um número de versão necessário que aparece no final de cada linha em uma impressão, clique ou arquivo de dados de conversão. A versão atual é 1.1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Delivery Methods for Data Files {#delivery-methods}

Upload your impression, click, or conversion data files to an Amazon S3 directory for your [!DNL Audience Manager] account. Consulte esta seção para obter informações sobre caminhos de entrega/diretório, tempo de processamento de arquivos e atualizações.

**Sintaxe de caminho de entrega e exemplos**

Os dados são armazenados em um namespace separado para cada cliente em um diretório Amazon S 3. O caminho do arquivo segue a sintaxe mostrada abaixo. Note, *italics* indicates a variable placeholder. Outros elementos são constantes ou teclas e não são alteradas.

**Sintaxe:** <pre><code>…/log_ ingestion/pid = <i>AAM ID<i>/dpid = <i>d_ src</i>/logs/ <i>file type</i>_<i>aaaammdd</i></code></pre>

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
   <td colname="col2"> <p>Esse par de valor chave contém a ID de fonte de dados transmitida em uma chamada de evento. Identifica a agência de onde os dados são originados e associa esses dados a um arquivo de metadados compatível. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> Um diretório de nível superior para arquivos de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>arquivo type</i>_<i>aaaammdd</i></code> </p> </td> 
   <td colname="col2"> <p>Um nome de tipo de arquivo que indica que tipo de dados ela contém e um carimbo de data e hora de entrega. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemplo de caminho de carregamento e nome do arquivo**

Ao carregar um arquivo, o caminho será semelhante a isto:

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**Tempo de processamento de arquivos e atualizações**

Os arquivos de dados são processados quatro vezes por dia, em intervalos regulares.

Para atualizar seus dados, envie um arquivo que contenha todas as impressões, cliques ou conversões de um dia específico. Nesse caso, um dia é o período de 24 horas de uma meia-noite para a seguinte. Como prática recomendada, você pode usar o tempo UTC para definir o intervalo de dias.

## Próximas etapas {#next-steps}

Revise os requisitos para nomear e criar arquivos de metadados. To get started, see [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).
