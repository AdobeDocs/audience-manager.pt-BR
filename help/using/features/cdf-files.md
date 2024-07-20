---
description: Informações básicas sobre os arquivos do Feed de dados do cliente (CDF) e instruções sobre como começar. Comece aqui se estiver interessado em receber arquivos CDF ou quiser mais informações.
keywords: dados de terceiros;dados de terceiros;dados de terceiros;dados de terceiros
seo-description: Basic information about Customer Data Feed (CDF) files and instructions on how to get started. Start here if you're interested in receiving CDF files or just want more information.
seo-title: Customer Data Feeds
solution: Audience Manager
title: Feeds de dados de clientes
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
feature: Customer Data Feeds
exl-id: 118c4225-3b57-4a02-ae05-2fcbf3e5d743
source-git-commit: 89137248aa47573f5b65e387a152f651419da827
workflow-type: tm+mt
source-wordcount: '1988'
ht-degree: 2%

---

# [!UICONTROL Customer Data Feeds] {#customer-data-feeds}

Informações básicas sobre [!UICONTROL Customer Data Feed] ([!UICONTROL CDF]) arquivos e instruções sobre como começar. Comece aqui se estiver interessado em receber [!UICONTROL CDF] arquivos ou quiser mais informações.

## Conteúdo e finalidade do arquivo {#file-contents-purpose}

Um arquivo [!UICONTROL CDF] contém os mesmos dados que uma chamada de evento [!DNL Audience Manager] (`/event`) envia para nossos servidores. Isso inclui dados como IDs de usuário, [!UICONTROL trait IDs], [!UICONTROL segment IDs] e todos os outros parâmetros capturados por uma chamada de evento. Sistemas [!DNL Audience Manager] internos processam dados de evento em um arquivo [!UICONTROL CDF] com conteúdo organizado em campos que aparecem em uma ordem definida. O [!DNL Audience Manager] tenta gerar [!UICONTROL CDF] arquivos por hora e os armazena em um compartimento seguro e específico do cliente em um servidor [!DNL Amazon S3]. Fornecemos esses arquivos para que você possa trabalhar com dados do [!DNL Audience Manager] fora dos limites impostos pela interface do usuário.

>[!IMPORTANT]
>
>Observe as seguintes restrições ao trabalhar com arquivos CDF:
>
>* Antes de configurar a entrega de arquivos CDF, verifique se você tem as permissões apropriadas de provedores de dados de terceiros para a exportação de características de terceiros. No momento, o Audience Manager não oferece suporte à funcionalidade na interface do usuário para solicitar permissão de exportação de entrega de arquivo CDF de Provedores de dados de terceiros. Portanto, entre em contato com eles independentemente.
>* Você não deve usar [!UICONTROL CDF] arquivos como proxy para monitorar o tráfego da página, reconciliar discrepâncias de relatório, para cobrança etc.

## Introdução {#getting-started}

Não há um processo de autoatendimento para iniciar a entrega do arquivo [!UICONTROL CDF]. Entre em contato com o consultor do [!DNL Audience Manager] ou com o Atendimento ao cliente para começar. Durante a implementação, o representante do [!DNL Audience Manager] irá:

* Configure seu bucket de armazenamento do [!DNL Amazon S3].
* Forneça credenciais de autenticação [!DNL S3] somente leitura ao seu bucket de armazenamento de arquivos. Você não poderá ver ou acessar diretórios e arquivos que pertencem a outros clientes.

Notificações de arquivo e [!UICONTROL CDF] arquivos aparecerão no bucket [!DNL S3] quando estiverem prontos para download. Você é responsável por monitorar e baixar arquivos do diretório [!DNL S3] atribuído. Consulte [Notificações de processamento de arquivos de feed de dados do cliente](#cdf-file-processing-notifications).

## Próximas etapas {#next-steps}

As seções abaixo e as [Perguntas frequentes sobre o Feed de Dados do Cliente](../faq/faq-cdf.md) podem ajudar você a se familiarizar com esse serviço.

## [!UICONTROL Customer Data Feed] Conteúdo definido {#cdf-defined}

Lista e define os elementos de dados e as matrizes em um arquivo [!UICONTROL CDF], por ordem de aparência. As definições incluem tipos de dados, mas essas informações não fazem parte de um arquivo [!UICONTROL CDF].

>[!IMPORTANT]
>
>Por padrão, os pixels do evento são excluídos nas configurações CDF. Certifique-se de especificar em sua solicitação para o atendimento ao cliente se deseja que os pixels do evento sejam incluídos em seus arquivos CDF. Cada pixel de evento será preenchido como uma linha exclusiva em seus arquivos CDF.

## Definições {#definitions}

Um arquivo [!UICONTROL CDF] inclui alguns ou todos os campos definidos abaixo. Para obter informações sobre a organização interna do arquivo, consulte [Estrutura do arquivo de feed de dados do cliente](#cdf-file-structure).

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
   <td colname="col3"> <p>A hora em que um arquivo CDF foi processado pelos <span class="wintitle"> Servidores de Coleta de Dados</span> (DCS). O carimbo de data/hora usa o formato <i>aaaa-mm-dd hh:mm:ss</i> e está definido no fuso horário UTC. </p> <p> <p>Observação: o Tempo de Evento <i>não</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">A hora do evento da página ou a chamada do evento propriamente dito, embora possa ser próxima a esses horários. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">Relacionado à hora DCS no nome do arquivo. Consulte também <a href="#different-processing-times"> Horários do nome do arquivo do feed de dados do cliente e Horários do conteúdo do arquivo...</a>. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>Esta é a Identificação de Usuário Exclusiva <span class="wintitle"> </span> (UUID), que é uma Identificação de dispositivo de 38 dígitos para o visitante do site. Consulte também, <a href="../reference/ids-in-aam.md"> Índice de IDs em Audience Manager</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Container ID</code> </p> </td> 
   <td colname="col2"> <p>Numérico </p> </td> 
   <td colname="col3"> <p>A ID do contêiner que dispara sincronizações de ID. Este campo só será preenchido se você definir a ID do contêiner no campo <i>d_nsid</i> na implementação do site. Caso contrário, o valor padrão de 0 não será incluído nos arquivos CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Uma matriz de IDs de característica que contém todas as características que um visitante realizou (se qualificou para) na chamada de evento. </p> <p>Observe que a matriz pode conter características para as quais o visitante se qualificou antes e para as quais se requalificou por meio desta chamada de evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Uma matriz de IDs de segmento que contém todos os segmentos que um visitante realizou (se qualificou para) na chamada de evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>Uma string que captura todos os parâmetros (variáveis, IDs, pares de valores chave, IDs de publicidade do dispositivo etc.) transmitido na chamada de evento. </p> <p>Exemplo abreviado: </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
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
   <td colname="col3"> <p>A Experience Cloud <span class="keyword"> ID (MID) atribuída ao visitante do site. </span> Consulte também Cookies do <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> e o Serviço de Identidade do Adobe Experience Platform</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Uma matriz de IDs de segmento que contém segmentos realizados anteriormente e novos segmentos para os quais o visitante está qualificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Uma matriz de IDs de características originais e de terceiros que contém características anteriormente realizadas e novas características para as quais o visitante se qualificou desde o último feed de dados gerado. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Estrutura de arquivos [!UICONTROL Customer Data Feed] {#cdf-file-structure}

Lista e define a estrutura de dados de um arquivo [!UICONTROL CDF]. Isso inclui sequência de dados, delimitadores e separadores de campo, um mapa de arquivo de dados e um arquivo de amostra.

## Identificadores e sequência do campo de dados {#identifiers-and-sequence}

[!UICONTROL CDF] arquivos não contêm colunas rotuladas ou cabeçalhos de campos. Em vez disso, um arquivo [!UICONTROL CDF] define campos e matrizes com [!DNL ASCII] caracteres não imprimíveis. Além disso, o arquivo [!UICONTROL CDF] lista cada campo e matriz em uma ordem específica. Entender os identificadores de campo e a ordem ajudará você a analisar o arquivo corretamente.

<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento do arquivo CDF </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Separadores de campo e delimitadores </p> </td> 
   <td colname="col2"> <p>Esses caracteres não imprimíveis definem os elementos e a estrutura do arquivo CDF: </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a (ASCII <code> 001</code> ou <code> ^A</code>) separa dados em campos individuais com um indicador de espaço não imprimível. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b (ASCII <code> 002</code> ou <code> ^B</code>) separa dados em uma matriz e solicita parâmetros. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c (ASCII <code> 003</code> ou <code> ^C</code>) define pares de valores chave. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sequência do campo </p> </td> 
   <td colname="col2"> <p> <p>Importante: <span class="keyword"> Audience Manager</span> reserva o direito de adicionar novos campos ao final do arquivo CDF em versões futuras. Isso significa que o design técnico do sistema de análise de arquivos não deve pressupor um número fixo de colunas (embora possa pressupor uma ordem fixa para colunas existentes).</p> </p> <p>Os dados no arquivo CDF aparecem na ordem mostrada abaixo. /N pode aparecer no lugar de qualquer um desses campos, indicando um valor nulo.</p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">Hora do Evento </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">Dispositivo </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">ID do container </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">Características Realizadas </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">Segmentos realizados </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">Parâmetros da solicitação </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referenciador </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">Endereço IP </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">ID de dispositivo Experience Cloud (ou MID). Consulte também Cookies do <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> e o Serviço de identidade da Adobe Experience Platform</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">Todos os segmentos </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">Todas as características </li> 
     </ol> </p> <p>Para obter descrições dos campos, consulte <a href="#cdf-defined"> Conteúdo do feed de dados do cliente definido</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Mapa de arquivos de [!UICONTROL CDF] {#cdf-file-map}

Os dados do arquivo [!UICONTROL CDF] aparecem na ordem mostrada abaixo.

![](assets/sequence-map.png)

## Identificação de storages

Matrizes em um arquivo [!UICONTROL CDF] começam e terminam com o separador de campo `Ctrl + a`. Isso faz com que o primeiro elemento em uma matriz apareça como um campo de dados independente. Por exemplo, a matriz [!UICONTROL traits] realizada começa com `^A1234`. O delimitador de matriz e a ID `^B5678` seguem esta entrada. Como resultado, você pode ser tentado a pensar que o primeiro elemento na matriz [!UICONTROL traits] realizada é a ID 5678 (porque começa com `^B`). Esse não é o caso, por isso é necessário estar familiarizado com a sequência e a estrutura de um arquivo de dados. Mesmo que o primeiro elemento na matriz [!UICONTROL trait] realizada (ou em qualquer outra matriz em um arquivo [!UICONTROL CDF]) comece com `^A`, a ordem de aparência ou posição no arquivo define o início de uma matriz. E, o primeiro elemento em uma matriz é sempre separado da entrada anterior por `^A`.

## Arquivo de amostra [!UICONTROL CDF] {#sample-file}

Um arquivo de amostra [!UICONTROL CDF] pode ser semelhante ao seguinte. Inserimos quebras de linha neste exemplo para ajudá-lo a se ajustar à página.

![](assets/CDF-sample.png)

## [!UICONTROL Customer Data Feed] Convenções de nomenclatura de arquivos {#cdf-naming-conventions}

As seções abaixo listam e definem os elementos no nome do arquivo [!UICONTROL CDF].

## [!UICONTROL CDF] Nome do Arquivo: Sintaxe e Exemplo {#cdf-file-name}

Um nome de arquivo [!UICONTROL CDF] típico contém os elementos listados abaixo. Observe que *itálico* indica um espaço reservado para variável:

### Sintaxe

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF_PARTNER-ID_FILE-SEQUENCE_0.gz
```

### Exemplo

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_0_0_0.gz
```

No bucket de armazenamento do [!DNL S3], os arquivos são classificados em ordem crescente pela ID do Parceiro ([!UICONTROL PID]), dia e hora.

## [!UICONTROL CDF] Elementos de nome de arquivo definidos {#cdf-file-name-elements}

A tabela a seguir lista e define os elementos em um nome de arquivo [!UICONTROL CDF].

<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento do nome do arquivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> s3://aam-cdf/</code> </p> </td> 
   <td colname="col2"> <p>Esse é o bucket de armazenamento raiz padrão para o arquivo CDF em um servidor Amazon S3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>your S3 bucket name</i> </code> </p> </td> 
   <td colname="col2"> <p>O nome do bucket do S3 somente leitura que armazena seus arquivos CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>A data em que o arquivo foi processado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>Um valor de hora expresso em notação de 24 horas e definido no fuso horário UTC. Consulte também <a href="#different-processing-times"> Horários do nome do arquivo do feed de dados do cliente e Horários do conteúdo do arquivo...</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>ID do parceiro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>File Sequence</i>_0</code> </p> </td> 
   <td colname="col2"> <p>Valores que identificam a sequência de arquivos. A sequência é incrementada da seguinte maneira: 0_0_0 , 0_1_0, 0_2_0...1_0_0</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>Uma extensão de arquivo gzip. Os arquivos CDF são compactados por gzip. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Notificações de Processamento de Arquivos {#cdf-file-processing-notifications}

[!DNL Audience Manager] grava um arquivo `.info` no diretório [!DNL S3] para informar quando o [!UICONTROL Customer Data File] ([!UICONTROL CDF]) está pronto para download. O arquivo `.info` também inclui [!DNL JSON] metadados formatados sobre o conteúdo dos arquivos [!UICONTROL CDF]. Consulte esta seção para obter informações sobre a sintaxe e os campos usados por esse arquivo de notificação.

## Arquivo de Informações de Exemplo {#sample-info-file}

Cada arquivo `.info` contém uma seção `Files` e `Totals`. A seção `Files` contém uma matriz que contém métricas específicas para cada arquivo por hora. A seção `Totals` contém métricas agregadas em todos os arquivos [!UICONTROL CDF] para um dia específico. O conteúdo do arquivo `.info` pode ser semelhante ao exemplo a seguir.

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

## Campos do arquivo de informações definidos {#info-file-fields-defined}

As tabelas a seguir listam e definem os elementos em um arquivo [!UICONTROL CDF] `.info`.

### Objeto Files

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
   <td colname="col2"> <p>Inicia a matriz que contém metadados sobre os arquivos CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>Tamanho do arquivo em bytes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>O Amazon S3 ETag. O número após o hífen mostra o número de partes usadas para criar o arquivo durante o upload de várias partes. O <code> ETag</code> não é idêntico à soma de verificação MD5 do arquivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>O nome do arquivo. Consulte <a href="#cdf-naming-conventions"> Convenções de nomenclatura de arquivos de feed de dados do cliente</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileSequenceNumber</code> </p> </td> 
   <td colname="col2"> <p>Um número de índice para cada arquivo. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Objeto Totals

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
   <td colname="col2"> <p>O dia para o qual os dados estão disponíveis. Usa o formato <i>aaaa-mm-dd</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hour</code> </p> </td> 
   <td colname="col2"> <p>A hora para a qual os dados estão disponíveis. Usa o formato de 24 horas definido no fuso horário UTC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>Tamanho total de todos os arquivos CDF naquela data, em bytes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>Número total de arquivos carregados no diretório S3. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Os horários do nome e do conteúdo do arquivo são diferentes {#different-processing-times}

Seu arquivo [!UICONTROL CDF] contém carimbos de data/hora no nome do arquivo e conteúdo do arquivo. Esses carimbos de data/hora registram processos de evento diferentes para o mesmo arquivo [!UICONTROL CDF]. Não é incomum ver carimbos de data e hora diferentes no nome e conteúdo do mesmo arquivo. Entender cada carimbo de data e hora pode ajudar você a evitar erros comuns ao trabalhar com esses dados ou tentar classificá-los por tempo.

## Localizando Carimbos de Data/Hora do Arquivo [!UICONTROL CDF] {#locating-timestamps}

[!UICONTROL CDF] arquivos registram o tempo de forma diferente em 2 locais separados.

![](assets/cdf-timestamp.png)

## Entender a diferença entre carimbos de data e hora {#understanding-timestamps}

A tabela a seguir fornece detalhes adicionais sobre os carimbos de data e hora do arquivo [!UICONTROL CDF], juntamente com informações sobre como usá-los corretamente.

| Localização do carimbo de data e hora | Descrição |
|--- |--- |
| Nome do arquivo | O carimbo de data/hora no nome do arquivo [!DNL CDF] marca a hora em que o [!DNL Audience Manager] começou a preparar seu arquivo para entrega. Este carimbo de data/hora está definido no fuso horário [!DNL UTC]. Ele usa o parâmetro `hour=`, com a hora formatada como uma hora de 2 dígitos na notação de 24 horas. Esse horário pode ser diferente do horário do evento registrado no conteúdo do arquivo. Ao trabalhar com [!DNL CDF] arquivos, às vezes você perceberá que o seu bucket de [!DNL S3] fica vazio por uma hora específica. Um bucket vazio significa uma das seguintes opções:<ul><li>Não há dados para aquela hora em particular. </li><li> Nossos servidores estão sob uma carga pesada e não podem processar arquivos por uma hora específica. Quando o servidor alcança, ele coloca os arquivos que deveriam ter sido enviados em arquivos de um intervalo de tempo anterior em um intervalo com um valor de tempo posterior. Por exemplo, você verá isso quando um arquivo que deveria estar no intervalo de 17 horas aparecer no intervalo de 18 horas (com `hour=18` no nome do arquivo). Nesse caso, o servidor provavelmente iniciou o processamento do arquivo na hora 17, mas não pôde concluí-lo nesse intervalo de tempo. Em vez disso, o arquivo é enviado para o próximo intervalo de tempo por hora.</li></ul><br>**Importante**: não use o carimbo de data/hora do nome do arquivo para agrupar eventos por hora. Se você precisar agrupar por tempo, use o carimbo de data/hora `EventTime` no conteúdo do arquivo. |
| Conteúdo do arquivo | O carimbo de data/hora no conteúdo do arquivo [!DNL CDF] marca a hora em que o [!DNL Data Collection Servers] iniciou o processamento do arquivo. Este carimbo de data/hora está definido no fuso horário [!DNL UTC]. Ele usa o campo `EventTime`, com a hora formatada como *`yyyy-mm-dd hh:mm:ss`*. Essa hora é próxima à hora real do evento na página, mas pode ser diferente do indicador de hora no nome do arquivo. <br> **Dica**: ao contrário do carimbo de data/hora `hour=` no nome do arquivo, você pode usar `EventTime` para agrupar dados por hora. |

>[!MORELIKETHIS]
>
>* [Perguntas frequentes sobre o feed de dados do cliente](../faq/faq-cdf.md)
