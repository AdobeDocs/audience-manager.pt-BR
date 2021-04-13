---
description: Um arquivo de dados contém dados de impressão, clique ou conversão. Quando formatados corretamente, é possível importar esses dados para o Audience Manager e usá-los nos relatórios do Audience Optimization e nos Arquivos de registro acionáveis. Formate os arquivos de dados de acordo com as especificações desta seção.
seo-description: Um arquivo de dados contém dados de impressão, clique ou conversão. Quando formatados corretamente, é possível importar esses dados para o Audience Manager e usá-los nos relatórios do Audience Optimization e nos Arquivos de registro acionáveis. Formate os arquivos de dados de acordo com as especificações desta seção.
seo-title: Arquivos de dados para Relatórios de otimização de público-alvo e arquivos de registro acionáveis
solution: Audience Manager
title: Arquivos de dados para Relatórios de otimização de público-alvo e arquivos de registro acionáveis
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
feature: Arquivos de registro
exl-id: 0da2c1d3-5ff8-40dd-b831-21d8941688ce
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1044'
ht-degree: 5%

---

# Arquivos de dados para Relatórios de otimização de público-alvo e arquivos de registro acionáveis {#data-files-for-audience-optimization-reports}

Um arquivo de dados contém dados de impressão, clique ou conversão. Quando formatados corretamente, você pode importar esses dados para o Audience Manager para exibi-los nos [Relatórios do Audience Optimization](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) e criar características usando os dados via [Arquivos de registro acionáveis](/help/using/integration/media-data-integration/actionable-log-files.md). Formate os arquivos de dados de acordo com essas especificações nesta seção.

## Visão geral {#overview}

Um arquivo de dados corretamente nomeado e formatado permite importar dados de impressão, clique ou conversão para os [Relatórios do Audience Optimization](../../../reporting/audience-optimization-reports/audience-optimization-reports.md). Isso é útil ao trabalhar com um parceiro que não está integrado com [!DNL Audience Manager] e você deseja trabalhar com seus dados nesse conjunto de relatórios. Esse processo requer arquivos separados para dados de impressão, clique e conversão. Não misture esses eventos em um único arquivo.

Um arquivo de dados deve ser acompanhado por um arquivo de metadados. O conteúdo do arquivo de metadados corresponde às informações do arquivo de dados aos rótulos relacionados e legível nos menus de relatório. Para obter mais informações, consulte [Visão geral e mapeamentos para arquivos de metadados](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## Convenções de nomenclatura para arquivos de dados {#naming-conventions}

A sintaxe a seguir define a estrutura de um nome de arquivo de dados bem formado. Observação: *itálico* indica um espaço reservado de variável que muda de acordo com o conteúdo do arquivo.

**Sintaxe:** <pre><i>tipo de evento</i>_<i>aaaammdd</i></code></pre>

Em um nome de arquivo:

* O tipo de evento indica que o arquivo contém impressões, cliques ou conversões. Crie um arquivo separado para cada tipo de evento.
* Um sublinhado separa o tipo de evento e um carimbo de data e hora de mês de ano.
* Antes de fazer upload, compacte seus arquivos usando gzip e salve-os com a extensão `.gz` do arquivo.

Considerando esses requisitos, nomeie os arquivos de dados com base em seus conteúdos da seguinte forma:

* Dados de impressão: <pre>impressões_<i>aaaammdd</i>.gz</code></pre>
* Dados de clique: <pre>clicks_<i>aaaammdd</i>.gz</code></pre>
* Dados de conversão: <pre>conversões_<i>aaaammdd</i>.gz</code></pre>

## Formato de conteúdo para arquivos de dados {#content-format}

A sintaxe a seguir define a estrutura do conteúdo no arquivo de dados bem formado. Observação: *itálico* indica um espaço reservado para variável e é substituído por um rótulo em um arquivo de dados real.

**Sintaxe:** <pre><i>rótulo do cabeçalho 1</i>  | rótulo do  <i>cabeçalho 2</i> ... rótulo do  <i>cabeçalho n</i>  |  <i>versão</i></code></pre>

No conteúdo do arquivo:

* Os rótulos do cabeçalho devem aparecer na ordem mostrada na tabela abaixo. Impressões e cliques usam os mesmos rótulos. Os arquivos de conversão contêm cabeçalhos extras.
* Se não tiver dados para uma coluna específica, preencha esse campo com um `-1`.

* Os arquivos *devem* terminar com um número de versão. A versão atual é a 1.1.
* Separe os cabeçalhos e conteúdos do arquivo com o caractere ASCII 001 não imprimível. Se não for possível usar ASCII 001, separe os cabeçalhos e dados com um delimitador de tabulação. Como esses são caracteres não imprimíveis, o exemplo de sintaxe acima mostra uma barra vertical `"|"` somente para fins de exibição.

**Rótulos de campo**

A tabela abaixo lista e descreve os cabeçalhos da coluna para seu arquivo de dados. Os cabeçalhos fazem distinção entre maiúsculas e minúsculas e devem aparecer conforme a ordem na tabela. Todos os tipos de dados são inteiros (INT), a menos que seja indicado o contrário.

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
   <td colname="col2"> <p>Uma data e hora UTC para o evento de impressão, clique ou conversão. Use o formato <code> yyyy-MM-dd HH:mm:ss</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>User-ID </p> </td> 
   <td colname="col2"> <p>Sua ID para um visitante do site, também conhecido como <span class="term"> ID de usuário exclusiva do provedor de dados</span> ou DPUUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anunciante-ID </p> </td> 
   <td colname="col2"> <p>A ID da fonte de dados ou o código de integração do seu anunciante. </p> </td> 
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
   <td colname="col2"> <p> ID de posicionamento numérico do servidor de anúncios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Insertion-Order-ID </p> </td> 
   <td colname="col2"> <p>Inserção da ID do pedido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactic-ID </p> </td> 
   <td colname="col2"> <p>ID Tática. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID Vertical </p> </td> 
   <td colname="col2"> <p>ID para um negócio vertical ou categoria. </p> </td> 
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
   <td colname="col2"> <p>URL da página de aterrissagem de conversão. Tipo de dados: string. </p> <p> <i>Somente para arquivos de dados de conversão.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tipo de evento </p> </td> 
   <td colname="col2"> <p>Tipo de conversão. Indica se uma conversão corresponde ou não. As opções incluem: </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: Impressão </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: Clique em </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>: Não atribuído ou desconhecido </li> 
    </ul> <p> <i>Somente para arquivos de dados de conversão.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Versão </p> </td> 
   <td colname="col2"> <p>Um número de versão necessário que aparece no final de cada linha em um arquivo de dados de impressão, clique ou conversão. A versão atual é a 1.1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Métodos de delivery para arquivos de dados {#delivery-methods}

Carregue seus arquivos de dados de impressão, clique ou conversão em um diretório Amazon S3 para sua conta [!DNL Audience Manager]. Consulte esta seção para obter informações sobre caminhos de entrega/diretório, tempos de processamento de arquivos e atualizações.

>[!IMPORTANT]
>
> Entre em contato com seu consultor do Audience Manager ou com o Atendimento ao cliente para começar e configurar um diretório [!DNL Amazon S3] para seus arquivos de dados.

**Sintaxe e exemplos do caminho de entrega**

Os dados são armazenados em um namespace separado para cada cliente em um diretório [!DNL Amazon S3]. O caminho do arquivo segue a sintaxe mostrada abaixo. Observação: *itálico* indica um espaço reservado para variável. Outros elementos são constantes ou chaves e não são alterados.

**Sintaxe:** <pre>.../log_ingestion/pid= <i>AAM ID<i>/dpid= <i>d_src</i>/logs/ <i>tipo de arquivo</i>_<i>aaaammdd</i></code></pre>

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
   <td colname="col2"> <p>Esse par de valores chave contém sua ID do cliente <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>Esse par de valores chave contém a ID da fonte de dados transmitida em uma chamada de evento. Ela identifica a agência de origem dos dados e vincula esses dados a um arquivo de metadados de suporte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> Um diretório de nível superior para arquivos de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>Um nome de tipo de arquivo que indica o tipo de dados que ele contém e um carimbo de data e hora do delivery. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemplo de caminho de upload e nome de arquivo**

Ao carregar um arquivo, o caminho será semelhante a este:

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**Tempos e atualizações do processamento de arquivos**

Os arquivos de dados são processados quatro vezes por dia, em intervalos regulares.

Para atualizar seus dados, envie um arquivo que contenha todas as impressões, cliques ou conversões de um dia específico. Nesse caso, um dia é o período de 24 horas de uma meia-noite para a próxima. Como prática recomendada, você pode usar o horário UTC para definir o intervalo de dias.

## Próximas etapas {#next-steps}

Revise os requisitos para nomear e criar arquivos de metadados. Para começar, consulte [Visão geral e mapeamentos para arquivos de metadados](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).
