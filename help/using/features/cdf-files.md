---
description: Informações básicas sobre os arquivos do Feed de dados do cliente (CDF) e instruções sobre como começar. Comece aqui se estiver interessado em receber arquivos CDF ou só quiser mais informações.
keywords: second party data;2nd party;2nd party data;second party
seo-description: Informações básicas sobre os arquivos do Feed de dados do cliente (CDF) e instruções sobre como começar. Comece aqui se estiver interessado em receber arquivos CDF ou só quiser mais informações.
seo-title: Feeds de dados do cliente
solution: Audience Manager
title: Feeds de dados do cliente
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# Feeds de dados do cliente {#customer-data-feeds}

Informações básicas sobre [!UICONTROL Customer Data Feed] ([!UICONTROL CDF]) arquivos e instruções sobre como começar. Comece aqui se estiver interessado em receber [!UICONTROL CDF] arquivos ou só quiser mais informações.

## Conteúdo e finalidade do arquivo {#file-contents-purpose}

<!-- cdf-intro.xml -->

Um [!UICONTROL CDF] arquivo contém os mesmos dados que uma chamada de [!DNL Audience Manager] evento ( `/event`) envia para nossos servidores. Isso inclui dados como IDs de usuário, IDs de característica, IDs de segmento e todos os outros parâmetros capturados por uma chamada de evento. Os [!DNL Audience Manager] sistemas internos processam dados de eventos em um [!UICONTROL CDF] arquivo com conteúdo organizado em campos que aparecem em uma ordem definida. [!DNL Audience Manager] tenta gerar [!UICONTROL CDF] arquivos por hora e armazena-os em um bucket seguro e específico do cliente em um [!DNL Amazon S3] servidor. Fornecemos esses arquivos para que você possa trabalhar com [!DNL Audience Manager] dados fora dos limites impostos pela interface do usuário.

>[!NOTE]
>
>Você não deve usar [!UICONTROL CDF] arquivos como proxy para monitorar o tráfego da página, reconciliar discrepâncias de relatório, faturamento etc.

## Introdução {#getting-started}

Não há processo de autoatendimento para iniciar a entrega [!UICONTROL CDF] de arquivos. Contact your [!DNL Audience Manager] consultant or Customer Care to get started. Durante a implementação, seu [!DNL Audience Manager] representante:

* Configure seu [!DNL Amazon S3] armazenamento.
* Forneça credenciais de autenticação somente leitura para o seu bucket de armazenamento de arquivos. [!DNL S3] Você não poderá ver nem acessar diretórios e arquivos que pertencem a outros clientes.

As notificações e [!UICONTROL CDF] os arquivos serão exibidos no seu [!DNL S3] bucket quando estiverem prontos para download. Você é responsável por monitorar e baixar arquivos do diretório atribuído. [!DNL S3] Consulte Notificações [de processamento de arquivos de feed de dados do](#cdf-file-processing-notifications)cliente.

## Próximas etapas {#next-steps}

As seções abaixo e as Perguntas frequentes [sobre o Feed de dados do](../faq/faq-cdf.md) cliente podem ajudá-lo a se familiarizar com esse serviço.

## Conteúdo do feed de dados do cliente definido {#cdf-defined}

Lista e define os elementos de dados e as matrizes em um [!UICONTROL CDF] arquivo, por ordem de aparência. As definições incluem tipos de dados, mas essas informações não fazem parte de um [!UICONTROL CDF] arquivo.

## Definições {#definitions}

<!-- cdf-contents-defined.xml -->

Um [!UICONTROL CDF] arquivo inclui alguns ou todos os campos definidos abaixo. Para obter informações sobre a organização interna do arquivo, consulte Estrutura [do arquivo do feed de dados do](#cdf-file-structure)cliente.

<table id="table_46BC897A30C2469AB5911F5B85A3FAA7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Tipo de dados </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> Event Time</code> </p> </td> 
   <td colname="col2"> <p>Carimbo de data e hora </p> </td> 
   <td colname="col3"> <p>A hora em que um arquivo CDF foi processado pelos Servidores <span class="wintitle"> de Coleta de</span> Dados (DCS). O carimbo de data e hora usa o formato <i>aaaa-mm-dd hh:mm:ss</i> e é definido no fuso horário UTC. </p> <p> <p>Observação: A hora do evento não <i></i>é: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">A hora do evento da página ou da chamada do evento, embora possa estar próxima desses momentos. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">Relacionado à hora do DCS no nome do arquivo. Consulte também, <a href="#different-processing-times"> Horários do Nome do Arquivo do Feed de Dados do Cliente e Horários do Conteúdo do Arquivo...</a>. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>Esta é a ID <span class="wintitle"> de usuário</span> exclusiva (UUID), que é uma ID de dispositivo de 38 dígitos para o visitante do site. Consulte também <a href="../reference/ids-in-aam.md">Índice de IDs no Audience Manager</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Container ID</code> </p> </td> 
   <td colname="col2"> <p>Numérico </p> </td> 
   <td colname="col3"> <p>A ID do contêiner que aciona sincronizações de ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Uma matriz de IDs de características que contém todas as características que um visitante realizou (qualificado para) na chamada de evento. </p> <p>Observe que a matriz pode conter características para as quais o visitante se qualificou antes e para as quais se qualificam novamente por meio dessa chamada de evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Uma matriz de IDs de segmento que contém todos os segmentos que um visitante realizou (qualificado para) na chamada de evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>Uma string que captura todos os parâmetros (variáveis, IDs, pares chave-valor, IDs de publicidade do dispositivo etc.) passado na chamada de evento. </p> <p>Exemplo abreviado: </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referer Data Type</code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>O URL não codificado da página de referência (se houver). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP Data Type</code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>O endereço IP do visitante capturado na chamada de evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> MCDevice </code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>A <span class="keyword"> Experience Cloud</span> ID (MID) atribuída ao visitante do site. Consulte também Cookies e o Serviço <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"></a>de identificação da plataforma Adobe Experience. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Uma matriz de IDs de segmento que contém segmentos realizados anteriormente e novos segmentos para os quais o visitante está qualificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Uma matriz de IDs de características originais e de terceiros que contém características e novas características realizadas anteriormente para as quais o visitante se qualificou desde o último feed de dados gerado. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Estrutura do arquivo de feed de dados do cliente {#cdf-file-structure}

Lista e define a estrutura de dados de um [!UICONTROL CDF] arquivo. Isso inclui sequências de dados, delimitadores de campos e separadores, um mapa de arquivos de dados e um arquivo de amostra.

## Identificadores e sequência do campo de dados {#identifiers-and-sequence}

<!-- cdf-file-structure.xml -->

[!UICONTROL CDF] os arquivos não contêm colunas rotuladas nem cabeçalhos de campo. Em vez disso, um [!UICONTROL CDF] arquivo define campos e matrizes com [!DNL ASCII] caracteres não imprimíveis. Além disso, o [!UICONTROL CDF] arquivo lista cada campo e matriz em uma ordem específica. Compreender os identificadores de campo e a ordem o ajudará a analisar o arquivo corretamente.

<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento de arquivo CDF </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Separadores de campo e delimitadores </p> </td> 
   <td colname="col2"> <p>Esses caracteres não imprimíveis definem os elementos e a estrutura do arquivo CDF: </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a (ASCII <code> 001</code> ou <code> ^A</code>) separa dados em campos individuais com um indicador de espaço não imprimível. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b (ASCII <code> 002</code> ou <code> ^B</code>) separa os dados de uma matriz e os parâmetros de solicitação. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c (ASCII <code> 003</code> ou <code> ^C</code>) define pares de valores chave. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sequência de campo </p> </td> 
   <td colname="col2"> <p> <p>Importante: O <span class="keyword"> Audience Manager</span> reserva o direito de adicionar novos campos ao final do arquivo CDF em versões futuras. Isso significa que o design técnico do seu sistema de análise de arquivos não deve assumir um número fixo de colunas (embora possa assumir uma ordem fixa para colunas existentes). </p> </p> <p>Os dados no arquivo CDF são exibidos na ordem mostrada abaixo. </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">Hora do evento </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">Dispositivo </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">ID do container </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">Características Realizadas </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">Segmentos Realizados </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">Parâmetros da solicitação </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">Endereço IP </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Experience Cloud Device ID (ou MID). Consulte também, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies e o Adobe Experience Platform Identity Service</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">Todos os segmentos </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">Todas as características </li> 
     </ol> </p> <p>Para obter descrições de campos, consulte Conteúdo definido <a href="#cdf-defined"></a>do feed de dados do cliente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Mapa de arquivos CDF {#cdf-file-map}

[!UICONTROL CDF] os dados do arquivo são exibidos na ordem mostrada abaixo.

![](assets/sequence-map.png)

## Identificação de matrizes

As matrizes em um [!UICONTROL CDF] arquivo iniciam e terminam com o separador de `Ctrl + a` campo. Isso faz com que o primeiro elemento em uma matriz apareça como um campo de dados independente. Por exemplo, a matriz de características realizadas começa com `^A1234`. O delimitador e a ID da matriz `^B5678` seguem essa entrada. Como resultado, você pode ficar tentado a pensar que o primeiro elemento na matriz de características realizadas é ID 5678 (porque começa com `^B`). Esse não é o caso, e é por isso que você precisa estar familiarizado com a sequência e estrutura de um arquivo de dados. Embora o primeiro elemento na matriz de características realizadas (ou qualquer outra matriz em um [!UICONTROL CDF] arquivo) comece com `^A`, a ordem de aparência ou posição no arquivo define o início de uma matriz. E o primeiro elemento em um storage é sempre separado da entrada anterior por `^A`.

## Arquivo CDF de amostra {#sample-file}

Um arquivo de amostra [!UICONTROL CDF] pode ser semelhante ao seguinte. Inserimos quebras de linha neste exemplo para ajudar a ajustar a página.

![](assets/CDF-sample.png)

## Convenções de nomenclatura de arquivos do feed de dados do cliente {#cdf-naming-conventions}

As seções abaixo listam e definem os elementos no nome do seu [!UICONTROL CDF] arquivo.

## Nome do arquivo CDF: Sintaxe e exemplo {#cdf-file-name}

<!-- cdf-file-name.xml -->

Um nome de [!UICONTROL CDF] arquivo típico contém os elementos listados abaixo. Note, *italics* indicates a variable placeholder:

### Sintaxe

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF-PARTNER-ID-AAM PROCESS-ID_0.gz
```

### Exemplo

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz
```

Em seu período de [!DNL S3] armazenamento, os arquivos são classificados em ordem crescente pela ID do parceiro ([!UICONTROL PID]), dia e hora.

## Elementos de nome de arquivo CDF definidos {#cdf-file-name-elements}

A tabela a seguir lista e define os elementos em um nome de [!UICONTROL CDF] arquivo.

<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento de nome de arquivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> s3://aam-cdf/</code> </p> </td> 
   <td colname="col2"> <p>Esse é o bucket de armazenamento raiz padrão para seu arquivo CDF em um servidor Amazon S3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>your S3 bucket name</i> </code> </p> </td> 
   <td colname="col2"> <p>O nome do bucket S3 somente leitura que armazena seus arquivos CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>A data em que seu arquivo foi processado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>Um valor de hora expresso em notação de 24 horas e definido no fuso horário UTC. Consulte também, <a href="#different-processing-times"> Horários do Nome do Arquivo do Feed de Dados do Cliente e Horários do Conteúdo do Arquivo...</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Sua ID do parceiro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AAM process ID</i>_0</code> </p> </td> 
   <td colname="col2"> <p>Uma ID de processo interna do Audience Manager <span class="keyword"></span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>Uma extensão de arquivo gzip. Os arquivos CDF são compactados por gzip. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Notificações de processamento de arquivo de feed de dados do cliente {#cdf-file-processing-notifications}

[!DNL Audience Manager] grava um `.info` arquivo no seu [!DNL S3] diretório para informá-lo quando seu [!UICONTROL Customer Data File] ([!UICONTROL CDF]) está pronto para download. O `.info` arquivo também inclui metadados [!DNL JSON] formatados sobre o conteúdo de seus [!UICONTROL CDF] arquivos. Consulte esta seção para obter informações sobre a sintaxe e os campos usados por este arquivo de notificação.

## Arquivo de informações de amostra {#sample-info-file}

<!-- cdf-notifications.xml -->

Cada `.info` arquivo contém uma seção `Files` e `Totals` . A `Files` seção contém uma matriz que contém métricas específicas para cada arquivo por hora. A `Totals` seção contém métricas agregadas em todos os [!UICONTROL CDF] arquivos de um dia específico. O conteúdo do seu `.info` arquivo pode ser semelhante ao seguinte exemplo.

```js
{
    "Files": [
        {
            "FileByteSize": 2709730,
            "FileChecksumMD5": "a9ea418e79511642cff11c2a898037dc-1",
            "FileName": "AAM_CDF_1109_000000_0.gz",
            "FileSequenceNumber": 1
        },
        {
            "FileByteSize": 2783351,
            "FileChecksumMD5": "7b469485d60274b6991acd0817855840-3",
            "FileName": "AAM_CDF_1109_000001_0.gz",
            "FileSequenceNumber": 2
        }
    ],
    "Totals": {
        "Day": "2017-09-26",
        "Hour": "18",
        "TotalByteSize": 150092997,
        "TotalNumberFiles": 2
    }
}
```

## Campos de arquivo de informações definidos {#info-file-fields-defined}

As tabelas a seguir listam e definem os elementos em um [!UICONTROL CDF]`.info` arquivo.

### Objeto de arquivos

<table id="table_582101B414864DA991CE813A7937ECC6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Files</code> </p> </td> 
   <td colname="col2"> <p>Inicia o storage que contém metadados sobre seus arquivos CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>Tamanho do arquivo em bytes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Amazon S3 ETag. O número após o hífen mostra o número de partes usadas para criar o arquivo durante o upload de várias partes. O arquivo não <code> ETag</code> é idêntico à soma de verificação MD5 do arquivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>O nome do arquivo. Consulte <a href="#cdf-naming-conventions"> Convenções</a>de nomenclatura do arquivo de feed de dados do cliente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileSequenceNumber</code> </p> </td> 
   <td colname="col2"> <p>Um número de índice para cada arquivo. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Objeto Totais

<table id="table_44F0B2D229E84A5DB3041760B1A50858"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Totals</code> </p> </td> 
   <td colname="col2"> <p>Inicia o objeto que contém dados agregados sobre todos os arquivos CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>O dia em que os dados estão disponíveis. Usa o formato <i>aaaa-mm-dd</i> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hour</code> </p> </td> 
   <td colname="col2"> <p>A hora para a qual os dados estão disponíveis. Usa o formato de 24 horas definido no fuso horário UTC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>Tamanho total de todos os arquivos CDF daquela data, em bytes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>O número total de arquivos carregados no diretório S3. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Os tempos de nome do arquivo do feed de dados do cliente e os tempos de conteúdo do arquivo são diferentes {#different-processing-times}

Seu [!UICONTROL CDF] arquivo contém carimbos de data e hora no nome do arquivo e no conteúdo do arquivo. Esses carimbos de data e hora registram processos de evento diferentes para o mesmo [!UICONTROL CDF] arquivo. Não é incomum ver carimbos de data e hora diferentes no nome e conteúdo do mesmo arquivo. Compreender cada carimbo de data e hora pode ajudar a evitar erros comuns ao trabalhar com esses dados ou tentar classificá-los por tempo.

## Localização de carimbos de data e hora do arquivo CDF {#locating-timestamps}

<!-- cdf-time-differences.xml -->

[!UICONTROL CDF] os arquivos registram o tempo de forma diferente em 2 locais separados.

![](assets/cdf-timestamp.png)

## Como entender a diferença entre os carimbos de data e hora {#understanding-timestamps}

A tabela a seguir fornece detalhes adicionais sobre os carimbos de data e hora do [!UICONTROL CDF] arquivo, juntamente com informações sobre como usá-los corretamente.

| Localização do carimbo de data e hora | Descrição |
|--- |--- |
| Nome do arquivo | O carimbo de data e hora em seu nome de arquivo CDF marca a hora em que [!DNL Audience Manager] começou a preparar o arquivo para entrega. Esse carimbo de data e hora é definido no fuso horário UTC. Ele usa o `hour=` parâmetro, com o tempo formatado como uma hora de 2 dígitos em uma notação de 24 horas. Essa hora pode ser diferente da hora do evento registrada no conteúdo do arquivo. DETALHAMENTOAo trabalhar com arquivos CDF, às vezes você perceberá que seu bucket S3 está vazio por uma hora específica. Um compartimento vazio significa um dos seguintes:<ul><li>Não há dados para aquela hora em particular. </li><li> Nossos servidores estão sob cargas pesadas e não podem processar arquivos por uma hora específica. Quando o servidor pega, coloca os arquivos que deveriam ter entrado em um período anterior em um bucket com um valor de tempo posterior. Por exemplo, você verá isso quando um arquivo que deveria estar na hora 17 do bucket for exibido na hora 18 do bucket (com `hour=18` o nome do arquivo). Nesse caso, o servidor provavelmente começou a processar seu arquivo na hora 17, mas não pôde concluí-lo dentro desse intervalo de tempo. Em vez disso, o arquivo é encaminhado para o próximo intervalo de tempo por hora.</li></ul><br>**Importante **: Não use o carimbo de data e hora do nome do arquivo para agrupar eventos por hora. Se precisar agrupar por hora, use o`EventTime`carimbo de data e hora no conteúdo do arquivo. |
| Conteúdo do arquivo | O carimbo de data e hora no conteúdo do arquivo CDF marca o momento em que os servidores de coleta de dados iniciaram o processamento do arquivo. Esse carimbo de data e hora é definido no fuso horário UTC. Ele usa o `EventTime` campo, com o tempo formatado como *`yyyy-mm-dd hh:mm:ss`*. Essa hora está próxima à hora real do evento na página, mas pode ser diferente do indicador de hora no nome do arquivo. <br> **Dica**: Diferentemente do `hour=` carimbo de data e hora no nome do arquivo, é possível usar `EventTime` para agrupar dados por hora. |

>[!MORELIKETHIS]
>
>* [Perguntas frequentes sobre o Feed de dados do cliente](../faq/faq-cdf.md)

