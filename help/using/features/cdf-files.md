---
description: Informações básicas sobre arquivos de Feed de dados do cliente (CDF) e instruções sobre como começar. Comece aqui se você estiver interessado em receber arquivos CDF ou quiser mais informações.
keywords: dados de terceiros; terceiros; dados de terceiros; segunda parte
seo-description: Informações básicas sobre arquivos de Feed de dados do cliente (CDF) e instruções sobre como começar. Comece aqui se você estiver interessado em receber arquivos CDF ou quiser mais informações.
seo-title: Feeds de dados do cliente
solution: Audience Manager
title: Feeds de dados do cliente
uuid: a 5 de 1630-2 c 7 a -4862-9 ba 0-f 8343 cdd 2782
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Customer Data Feeds {#customer-data-feeds}

Basic information about [!UICONTROL Customer Data Feed] ([!UICONTROL CDF]) files and instructions on how to get started. Start here if you&#39;re interested in receiving [!UICONTROL CDF] files or just want more information.

## File Contents and Purpose {#file-contents-purpose}

<!-- cdf-intro.xml -->

A [!UICONTROL CDF] file contains the same data that an [!DNL Audience Manager] event call ( `/event`) sends to our servers. Isso inclui dados como IDs de usuário, IDs de características, IDs de segmento e todos os outros parâmetros capturados por uma chamada de evento. Internal [!DNL Audience Manager] systems processes event data into a [!UICONTROL CDF] file with content organized into fields that appear in a set order. [!DNL Audience Manager] tenta gerar [!UICONTROL CDF] arquivos por hora e armazená-los em um bucket seguro do cliente em um [!DNL Amazon S3] servidor. We provide these files so you can work with [!DNL Audience Manager] data outside of the limits imposed by our user interface.

>[!NOTE]
>
>You should not use [!UICONTROL CDF] files as a proxy to monitor page traffic, reconcile report discrepancies, or for billing, etc.

## Introdução {#getting-started}

There is no self-service process to start [!UICONTROL CDF] file delivery. Contact your [!DNL Audience Manager] consultant or Customer Care to get started. During implementation, your [!DNL Audience Manager] representative will:

* Set up your [!DNL Amazon S3] storage bucket.
* Provide read-only [!DNL S3] authentication credentials to your file storage bucket. Você não poderá visualizar ou acessar diretórios e arquivos que pertencem a outros clientes.

File notifications and [!UICONTROL CDF] files will appear in your [!DNL S3] bucket when they&#39;re ready for download. You&#39;re responsible for monitoring and downloading files from your assigned [!DNL S3] directory. See [Customer Data Feed File Processing Notifications](#cdf-file-processing-notifications).

## Próximas etapas {#next-steps}

The sections below and the [Customer Data Feed FAQ](../faq/faq-cdf.md) can help you become more familiar with this service.

## Customer Data Feed Contents Defined {#cdf-defined}

Lists and defines the data elements and arrays in a [!UICONTROL CDF] file, by order of appearance. Definitions include data types, but this information is not part of a [!UICONTROL CDF] file.

## Definições {#definitions}

<!-- cdf-contents-defined.xml -->

A [!UICONTROL CDF] file includes some or all of the fields defined below. For information about internal file organization, see [Customer Data Feed File Structure](#cdf-file-structure).

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
   <td colname="col1"> <p><code> Hora do evento</code> </p> </td> 
   <td colname="col2"> <p>Carimbo de data e hora </p> </td> 
   <td colname="col3"> <p>The time a CDF file was processed by the <span class="wintitle"> Data Collection Servers</span> (DCS). The timestamp uses the <i>yyyy-mm-dd hh:mm:ss</i> format and is set in the UTC time zone. </p> <p> <p>Note: The Event Time <i>is not</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">A hora do evento de página ou a chamada do evento em si, embora possa estar perto desses momentos. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">Relacionado à hora DCS no nome do arquivo. See also, <a href="#different-processing-times"> Customer Data Feed File Name Times and File Content Times...</a>. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Dispositivo</code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>This is the <span class="wintitle"> Unique User ID</span> (UUID), which is a 38-digit device ID for your site visitor. Consulte também <a href="../reference/ids-in-aam.md">Índice de IDs no Audience Manager</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> ID do contêiner</code> </p> </td> 
   <td colname="col2"> <p>Numérico </p> </td> 
   <td colname="col3"> <p>A ID do contêiner que aciona sincronizações de ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Características realized</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Uma matriz de IDs características que contém todos os traços que um visitante fez (qualificado para) na chamada do evento. </p> <p>Observe que a matriz pode conter características para as quais o visitante tinha qualificado antes e para o qual ele se qualifica novamente por meio desta chamada de evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Segmentos Realized</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Uma matriz de IDs de segmento que contém todos os segmentos que um visitante verificou (qualificado para) na chamada do evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Parâmetros da solicitação</code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>Uma string que captura todos os parâmetros (variáveis, IDs, pares-valor-valor etc.) passado na chamada do evento. </p> <p>Exemplo abreviado: </p> <p> <code> d_ rtbd: json, c_ contextdata. a. carriername: mobile, c_ contextdata. a. adid: 92 D 56353-49 C 5-431 E-B 474-FC 528 D 585810, c_ contextdata. a, runmode: Application, c_ contextdata. a. dayssincelastupgrade: 61, d_ cid_ ic: xid % 01 EACB 6 E 40-AC 65-4012-9 FE 9-ABD 59965 E 9 C 4% 01, c_ contextdata. a. prevsessionlength: 583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Tipo de dados do referenciador</code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>O URL não codificado da página de referência (se houver). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Tipo de dados IP</code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>O endereço IP do visitante capturado na chamada do evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Mcdevice </code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>The <span class="keyword"> Experience Cloud</span> ID (MID) assigned to the site visitor. See also, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and theExperience Cloud ID service</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Todos os segmentos</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Uma matriz de IDs de segmento que contém segmentos anteriormente estabelecidos e novos segmentos para os quais o visitante está qualificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Todas as características</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Uma matriz de IDs características originais e de terceiros que contém características e novas características anteriormente observadas, que o visitante tem qualificado desde o último feed de dados gerado. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Data Feed File Structure {#cdf-file-structure}

Lists and defines the data structure of a [!UICONTROL CDF] file. Isso inclui sequência de dados, delimitadores de campo e separadores, um mapa de arquivo de dados e um arquivo de amostra.

## Data Field Identifiers and Sequence {#identifiers-and-sequence}

<!-- cdf-file-structure.xml -->

[!UICONTROL CDF] não contêm colunas ou cabeçalhos de campo rotulados. Instead, a [!UICONTROL CDF] file defines fields and arrays with non-printing [!DNL ASCII] characters. Also, the [!UICONTROL CDF] file lists each field and array in a specific order. Entender os identificadores de campo e a ordem ajudará você a analisar o arquivo corretamente.

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
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a (ASCII <code> 001</code> or <code> ^A</code>) separates data in individual fields with a non-printing space indicator. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b (ASCII <code> 002</code> or <code> ^B</code>) separates data an array and request parameters. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c (ASCII <code> 003</code> or <code> ^C</code>) defines key-value pairs. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sequência de campos </p> </td> 
   <td colname="col2"> <p> <p>Important: <span class="keyword"> Audience Manager</span> reserves the right to add new fields to the end of the CDF file in future releases. Isso significa que o design técnico do seu sistema de análise de arquivo não deve assumir um número fixo de colunas (embora possa assumir uma ordem fixa para colunas existentes). </p> </p> <p>Os dados no arquivo CDF aparecem na ordem mostrada abaixo. </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">Hora do evento </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">Dispositivo </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">ID do container </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">Características realized </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">Segmentos Realized </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">Parâmetros da solicitação </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">Endereço IP </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">ID do dispositivo da Experience Cloud (ou MID). See also, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID Service</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">Todos os segmentos </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">Todas as características </li> 
     </ol> </p> <p>For field descriptions, see <a href="#cdf-defined"> Customer Data Feed Contents Defined</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## CDF File Map {#cdf-file-map}

[!UICONTROL CDF] os dados do arquivo aparecem na ordem mostrada abaixo.

![](assets/sequence-map.png)

## Identificação de matrizes

Arrays in a [!UICONTROL CDF] file start and end with the `Ctrl + a` field separator. Isso faz com que o primeiro elemento em uma matriz apareça como um campo de dados independente. For example, the realized traits array starts with `^A1234`. The array delimiter and ID `^B5678` follows this entry. As a result, you might be tempted to think that the first element in the realized traits array is ID 5678 (because it starts with `^B`). Esse não é o caso, por isso é necessário familiarizar-se com a sequência e a estrutura de um arquivo de dados. Even though the first element in the realized trait array (or any of the other arrays in a [!UICONTROL CDF] file) starts with `^A`, the order of appearance or position in the file defines the start of an array. And, the first element in an array is always separated from the preceding entry by `^A`.

## Sample CDF File {#sample-file}

A sample [!UICONTROL CDF] file could look similar to the following. Nós inserimos quebras de linha neste exemplo para ajudar a ajustar a página.

![](assets/CDF-sample.png)

## Customer Data Feed File Naming Conventions {#cdf-naming-conventions}

The sections below list and define the elements in your [!UICONTROL CDF] file name.

## CDF File Name: Syntax and Example {#cdf-file-name}

<!-- cdf-file-name.xml -->

A typical [!UICONTROL CDF] file name contains the elements listed below. Note, *italics* indicates a variable placeholder:

* **Sintaxe**

<pre><code>s 3: //aam-cdf/your<i>nome do bucket</i>/dia =<i>aaaa-mm-dd</i>-dd/hora =<i>hh</i>/<i>AAM_ CDF_ partner ID_ PROCESS ID</i>_0.gz</code>
</pre>

* **Exemplo**

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz
```

In your [!DNL S3] storage bucket, files are sorted in ascending order by Partner ID ([!UICONTROL PID]), day, and hour.

## CDF File Name Elements Defined {#cdf-file-name-elements}

The following table lists and defines the elements in a [!UICONTROL CDF] file name.

<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento de nome de arquivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> s 3: //aam-cdf/</code> </p> </td> 
   <td colname="col2"> <p>Esse é o bucket padrão de armazenamento raiz do arquivo CDF em um servidor Amazon S 3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>seu nome de bucket S 3</i></code> </p> </td> 
   <td colname="col2"> <p>O nome do bucket S 3 somente leitura que armazena seus arquivos CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dia =<i>aaaa-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>A data em que o arquivo foi processado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour =<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>Um valor de tempo expresso em uma notação de 24 horas e definido no fuso horário UTC. See also, <a href="#different-processing-times"> Customer Data Feed File Name Times and File Content Times...</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>ID do parceiro</i></code> </p> </td> 
   <td colname="col2"> <p>Sua ID do parceiro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>ID de processo do AAM</i>_ 0</code> </p> </td> 
   <td colname="col2"> <p>An internal, <span class="keyword"> Audience Manager</span> process ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>Uma extensão de arquivo gzip. Os arquivos CDF são compactados. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Data Feed File Processing Notifications {#cdf-file-processing-notifications}

[!DNL Audience Manager] grava um `.info` arquivo no [!DNL S3] diretório para avisá-lo quando ( [!UICONTROL Customer Data File][!UICONTROL CDF]) está pronto para download. The `.info` file also includes [!DNL JSON] formatted metadata about the contents of your [!UICONTROL CDF] files. Revise esta seção para obter informações sobre a sintaxe e os campos usados por esse arquivo de notificação.

## Sample Info File {#sample-info-file}

<!-- cdf-notifications.xml -->

Each `.info` file contains a `Files` and `Totals` section. `Files` A seção contém uma matriz que contém métricas específicas para cada arquivo por hora. `Totals` A seção contém métricas agregadas a todos [!UICONTROL CDF] os arquivos de um dia específico. The contents of your `.info` file could look similar to the following example.

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

## Info File Fields Defined {#info-file-fields-defined}

The following tables list and define the elements in a [!UICONTROL CDF] `.info` file.

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
   <td colname="col1"> <p> <code> Arquivos</code> </p> </td> 
   <td colname="col2"> <p>Inicia a matriz que contém metadados sobre seus arquivos CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filebytesize</code> </p> </td> 
   <td colname="col2"> <p>Tamanho do arquivo em bytes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>O Amazon S 3 etag. O número a seguir ao hífen mostra o número de partes usadas para criar o arquivo durante o upload de várias partes. <code> O etag não</code> é idêntico à soma de verificação MD 5 do arquivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filename</code> </p> </td> 
   <td colname="col2"> <p>O nome do arquivo. See <a href="#cdf-naming-conventions"> Customer Data Feed File Naming Conventions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filesequencenumber</code> </p> </td> 
   <td colname="col2"> <p>Um número de índice para cada arquivo. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Objeto de totais

<table id="table_44F0B2D229E84A5DB3041760B1A50858"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Totais</code> </p> </td> 
   <td colname="col2"> <p>Inicia o objeto que contém dados agregados sobre todos os arquivos CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Dia</code> </p> </td> 
   <td colname="col2"> <p>O dia para o qual os dados estão disponíveis. Uses <i>yyyy-mm-dd</i> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hora</code> </p> </td> 
   <td colname="col2"> <p>A hora para a qual os dados estão disponíveis. Usa o formato de 24 horas definido em fuso horário UTC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Totalbytesize</code> </p> </td> 
   <td colname="col2"> <p>Tamanho total de todos os arquivos CDF para essa data em bytes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Totalnumberfiles</code> </p> </td> 
   <td colname="col2"> <p>O número total de arquivos carregados no diretório S 3. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Data Feed File Name Times and File Content Times are Different {#different-processing-times}

Your [!UICONTROL CDF] file contains timestamps in the file name and file contents. These timestamps record different event processes for the same [!UICONTROL CDF] file. Não é mais comum ver carimbos de data e hora diferentes no nome e no conteúdo do mesmo arquivo. Entender cada carimbo de data e hora pode ajudá-lo a evitar erros comuns ao trabalhar com esses dados ou tentar classificá-los por tempo.

## Locating CDF File Timestamps {#locating-timestamps}

<!-- cdf-time-differences.xml -->

[!UICONTROL CDF] arquivos registram o tempo de maneira diferente em 2 locais separados.

![](assets/cdf-timestamp.png)

## Understanding the Difference Between Timestamps {#understanding-timestamps}

The following table provides additional details about your [!UICONTROL CDF] file timestamps along with information about how to use them properly.

| Local do carimbo de data e hora | Descrição |
|--- |--- |
| Nome do arquivo | The timestamp in your CDF file name marks the time when [!DNL Audience Manager] started preparing your file for delivery. Esse carimbo de data e hora é definido no fuso horário UTC. It uses the `hour=` parameter, with time formatted as a 2-digit hour in 24-hour notation. Esse tempo pode ser diferente do tempo registrado no conteúdo do arquivo. Breakao trabalhar com arquivos CDF, você observará que o bucket S 3 está vazio para uma hora específica. Um compartimento vazio significa que um dos seguintes meios pode significar:<ul><li>Não há dados para essa hora em particular. </li><li> Nossos servidores estão sob cargas pesadas e não podem processar arquivos de uma hora específica. Quando o servidor é capturado, coloca os arquivos que deveriam ter passado em um compartimento de tempo anterior para um bucket com um valor de tempo posterior. For example, you&#39;ll see this when a file that should have been in the hour 17 bucket appear in the hour 18 bucket (with `hour=18` in the file name). Nesse caso, o servidor provavelmente começou a processar seu arquivo na hora 17, mas não pôde preenchê-lo dentro desse intervalo de tempo. Em vez disso, o arquivo é enviado para o próximo intervalo de tempo por hora.</li></ul><br>**Importante**: Não use o carimbo de data e hora do nome de arquivo para agrupar eventos por tempo. If you need to group by time, use the `EventTime` timestamp in the file contents. |
| Conteúdo do arquivo | O carimbo de data e hora no conteúdo do arquivo CDF marca o momento em que os servidores de coleta de dados começaram a processar o arquivo. Esse carimbo de data e hora é definido no fuso horário UTC. It uses the `EventTime` field, with time formatted as *`yyyy-mm-dd hh:mm:ss`*. This time is close to the actual time of the event on the page, but it can be different than the hour indicator in the file name. <br> **Dica**: Diferentemente do `hour=` carimbo de data e hora no nome do arquivo, você pode usar `EventTime` para agrupar dados por tempo. |

>[!MORE_ LIKE_ THIS]
>
>* [Perguntas frequentes sobre o feed de dados do cliente](../faq/faq-cdf.md)

