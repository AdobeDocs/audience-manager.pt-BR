---
description: Um arquivo de dados contém dados de impressão, clique ou conversão. Quando formatados corretamente, você pode importar esses dados para o Audience Manager e usá-los nos relatórios de Audience Optimization e nos arquivos de registro acionáveis. Formate os arquivos de dados de acordo com as especificações desta seção.
seo-description: Um arquivo de dados contém dados de impressão, clique ou conversão. Quando formatados corretamente, você pode importar esses dados para o Audience Manager e usá-los nos relatórios de Audience Optimization e nos arquivos de registro acionáveis. Formate os arquivos de dados de acordo com as especificações desta seção.
seo-title: Arquivos de dados para Relatórios de otimização de público-alvo e arquivos de registro acionáveis
solution: Audience Manager
title: Arquivos de dados para Relatórios de otimização de público-alvo e arquivos de registro acionáveis
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
feature: log files
translation-type: tm+mt
source-git-commit: ff592184ba1785e3448aa449745d0e66ecba955b
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 5%

---


# Arquivos de dados para Relatórios de otimização de público-alvo e arquivos de registro acionáveis {#data-files-for-audience-optimization-reports}

Um arquivo de dados contém dados de impressão, clique ou conversão. Quando formatados corretamente, você pode importar esses dados para o Audience Manager para visualização nos Relatórios [do](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) Audience Optimization e criar características usando os dados por meio dos Arquivos [de registro](/help/using/integration/media-data-integration/actionable-log-files.md)acionáveis. Formate seus arquivos de dados de acordo com essas especificações nesta seção.

## Visão geral {#overview}

Um arquivo de dados com nome e formato adequados permite importar dados de impressão, clique ou conversão para os Relatórios [do](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)Audience Optimization. Isso é útil ao trabalhar com um parceiro que não está integrado [!DNL Audience Manager] e você deseja trabalhar com seus dados nesse conjunto de relatórios. Esse processo requer arquivos separados para impressão, clique e dados de conversão. Não misture esses eventos em um único arquivo.

Um ficheiro de dados deve ser acompanhado de um ficheiro de metadados. O conteúdo do arquivo de metadados corresponde às informações do arquivo de dados a rótulos relacionados e legíveis por humanos nos menus do relatório. Para obter mais informações, consulte [Visão geral e mapeamentos para arquivos](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)de metadados.

## Naming Conventions for Data Files {#naming-conventions}

A sintaxe a seguir define a estrutura de um nome de arquivo de dados bem formado. Observação: *itálico* indica um espaço reservado variável que muda dependendo do conteúdo do arquivo.

**Sintaxe:** `event type_yyyymmdd`

Em um nome de arquivo:

* O tipo de evento indica que o arquivo contém impressões, cliques ou conversões. Crie um arquivo separado para cada tipo de evento.
* Um sublinhado separa o tipo de evento e um carimbo de data e hora de ano e mês.
* Antes de carregar, compacte seus arquivos usando gzip e salve-os com a extensão do `.gz` arquivo.

Dadas estas exigências, nomeie seus arquivos de dados com base em seus conteúdos como este:

* Dados de impressão: `impressions_yyyymmdd.gz`
* Dados de clique: `clicks_yyyymmdd.gz`
* Dados de conversão: `conversions_yyyymmdd.gz`

## Content Format for Data Files {#content-format}

A sintaxe a seguir define a estrutura do conteúdo em um arquivo de dados bem formado. Observação: *itálico* indica um espaço reservado variável e é substituído por um rótulo em um arquivo de dados real.

**Sintaxe:** `header label 1 | header label 2 ... header label n | version`

No conteúdo do arquivo:

* Os rótulos do cabeçalho devem aparecer na ordem, conforme mostrado na tabela abaixo. As impressões e os cliques usam os mesmos rótulos. Os arquivos de conversão contêm cabeçalhos adicionais.
* Se você não tiver dados para uma coluna específica, preencha esse campo com uma `-1`.

* Os arquivos *devem* terminar com um número de versão. A versão atual é 1.1.
* Separe os cabeçalhos e conteúdos dos arquivos com o caractere ASCII 001 não imprimível. Se você não puder usar ASCII 001, separe os cabeçalhos e dados com um delimitador de tabulação. Como esses são caracteres não imprimíveis, o exemplo de sintaxe acima mostra um pipe somente `"|"` para fins de exibição.

**Rótulos de campo**

A tabela abaixo lista e descreve os cabeçalhos de coluna para seu arquivo de dados. Os cabeçalhos fazem distinção entre maiúsculas e minúsculas e devem aparecer conforme ordenado na tabela. Todos os tipos de dados são inteiros (INT), a menos que seja indicado o contrário.

<table id="table_D8C5068741C3460380505F95F3016757"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rótulo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Carimbo de data e hora </p> </td> 
   <td colname="col2"> <p>Uma data e hora UTC para impressão, clique ou evento de conversão. Use o <code> yyyy-MM-dd HH:mm:ss</code> formato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID do usuário </p> </td> 
   <td colname="col2"> <p>Sua ID de um visitante do site, também conhecida como ID <span class="term"> de usuário exclusiva ou DPUUID do provedor de</span> dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID do anunciante </p> </td> 
   <td colname="col2"> <p>A ID da fonte de dados ou o código de integração do anunciante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>ID da unidade de negócios. </p> </td> 
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
   <td colname="col2"> <p> ID de disposição numérica do servidor de publicidade. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Insertion-Order-ID </p> </td> 
   <td colname="col2"> <p>ID do pedido de inserção. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactic-ID </p> </td> 
   <td colname="col2"> <p>ID Tática. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID vertical </p> </td> 
   <td colname="col2"> <p>ID para uma categoria vertical ou vertical do setor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quantidade </p> </td> 
   <td colname="col2"> <p> O número de itens vendidos em um evento de conversão. </p> <p> <i>Somente para arquivos de dados de conversão.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Receita </p> </td> 
   <td colname="col2"> <p>Compra ou outro valor de conversão. Tipo de dados: Flutuar. </p> <p> <i>Somente para arquivos de dados de conversão.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Outros dados </p> </td> 
   <td colname="col2"> <p>URL da landing page de conversão. Tipo de dados: string. </p> <p> <i>Somente para arquivos de dados de conversão.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tipo de evento </p> </td> 
   <td colname="col2"> <p>Tipo de conversão. Indica se uma conversão é correspondida ou não. As opções incluem: </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: Impressão </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: Clique em </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>: Não atribuído ou desconhecido </li> 
    </ul> <p> <i>Somente para arquivos de dados de conversão.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Versão </p> </td> 
   <td colname="col2"> <p>Um número de versão necessário que aparece no final de cada linha em uma impressão, clique ou arquivo de dados de conversão. A versão atual é 1.1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Delivery Methods for Data Files {#delivery-methods}

Faça upload de sua impressão, clique ou converta arquivos de dados em um diretório Amazon S3 da sua [!DNL Audience Manager] conta. Consulte esta seção para obter informações sobre caminhos de delivery/diretório, tempos de processamento de arquivos e atualizações.

>[!IMPORTANT]
>
> Entre em contato com seu consultor de Audience Manager ou com o Atendimento ao cliente para começar e configurar um [!DNL Amazon S3] diretório para seus arquivos de dados.

**Sintaxe e exemplos de caminho de delivery**

Os dados são armazenados em uma namespace separada para cada cliente em um [!DNL Amazon S3] diretório. O caminho do arquivo segue a sintaxe mostrada abaixo. Note, *italics* indicates a variable placeholder. Outros elementos são constantes ou teclas e não são alterados.

**Sintaxe:** `.../log_ingestion/pid=AAM ID/dpid=d_src/logs/file type_yyyymmdd`

A tabela a seguir define cada um desses elementos em um caminho de delivery de arquivo.

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
   <td colname="col2"> <p>Este é o start do caminho do armazenamento do diretório. Você receberá o caminho completo quando tudo estiver configurado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>Esse par de valor-chave contém a ID do cliente do <span class="keyword"> Audience Manager</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>Esse par de valor-chave contém a ID da fonte de dados transmitida em uma chamada de evento. Ela identifica a agência de onde vêm os dados e vincula esses dados a um arquivo de metadados de suporte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> Um diretório de nível superior para arquivos de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>Um nome de tipo de arquivo que indica que tipo de dados ele contém e um carimbo de data e hora do delivery. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemplo de caminho de upload e nome de arquivo**

Ao carregar um arquivo, o caminho será semelhante a este:

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**Tempos e atualizações de processamento de arquivo**

Os arquivos de dados são processados quatro vezes por dia, em intervalos regulares.

Para atualizar seus dados, envie um arquivo que contenha todas as impressões, cliques ou conversões de um dia específico. Neste caso, um dia é o período de 24 horas de uma meia-noite para o próximo. Como prática recomendada, você pode usar o horário UTC para definir o intervalo de dias.

## Próximas etapas {#next-steps}

Revise os requisitos para nomear e criar arquivos de metadados. Para começar, consulte [Visão geral e mapeamentos para arquivos](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)de metadados.
