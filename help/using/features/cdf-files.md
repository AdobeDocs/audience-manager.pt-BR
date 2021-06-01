---
description: Informações básicas sobre os arquivos do Feed de dados do cliente (CDF) e instruções sobre como começar. Comece aqui se estiver interessado em receber arquivos CDF ou só quiser obter mais informações.
keywords: dados de terceiros; dados de terceiros; dados de terceiros; dados de terceiros; dados de terceiros
seo-description: Informações básicas sobre os arquivos do Feed de dados do cliente (CDF) e instruções sobre como começar. Comece aqui se estiver interessado em receber arquivos CDF ou só quiser obter mais informações.
seo-title: Feeds de dados do cliente
solution: Audience Manager
title: Feeds de dados do cliente
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
feature: Feeds de dados do cliente
exl-id: 118c4225-3b57-4a02-ae05-2fcbf3e5d743
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1935'
ht-degree: 4%

---

# [!UICONTROL Customer Data Feeds] {#customer-data-feeds}

Informações básicas sobre os arquivos [!UICONTROL Customer Data Feed] ([!UICONTROL CDF]) e instruções sobre como começar. Comece aqui se estiver interessado em receber arquivos [!UICONTROL CDF] ou só quiser mais informações.

## Conteúdo e finalidade do arquivo {#file-contents-purpose}

Um arquivo [!UICONTROL CDF] contém os mesmos dados que uma chamada de evento [!DNL Audience Manager] (`/event`) envia para nossos servidores. Isso inclui dados como IDs de usuário, [!UICONTROL trait IDs], [!UICONTROL segment IDs] e todos os outros parâmetros capturados por uma chamada de evento. Os sistemas [!DNL Audience Manager] internos processam os dados do evento em um arquivo [!UICONTROL CDF] com o conteúdo organizado em campos que aparecem em uma ordem definida. [!DNL Audience Manager] O tenta gerar  [!UICONTROL CDF] arquivos por hora e os armazena em um bucket seguro e específico do cliente em um  [!DNL Amazon S3] servidor. Fornecemos esses arquivos para que você possa trabalhar com dados [!DNL Audience Manager] fora dos limites impostos pela interface do usuário.

>[!IMPORTANT]
>
>Observe as seguintes restrições ao trabalhar com arquivos CDF:
>
>* Antes de configurar a entrega de arquivos CDF, verifique se você tem as permissões apropriadas de provedores de dados de terceiros para a exportação de características de terceiros. No momento, o Audience Manager não oferece suporte à funcionalidade na interface do usuário para solicitar permissão de exportação de entrega de arquivos CDF de provedores de dados de terceiros, portanto, entre em contato com eles de maneira independente.
>* Você não deve usar os arquivos [!UICONTROL CDF] como proxy para monitorar o tráfego da página, reconciliar discrepâncias de relatório ou para faturamento etc.


## Introdução {#getting-started}

Não há processo de autoatendimento para iniciar a entrega de arquivos [!UICONTROL CDF]. Entre em contato com seu consultor [!DNL Audience Manager] ou com o Atendimento ao cliente para começar. Durante a implementação, o representante [!DNL Audience Manager] fará o seguinte:

* Configure seu bucket de armazenamento [!DNL Amazon S3].
* Forneça credenciais de autenticação [!DNL S3] somente leitura para o seu bucket de armazenamento de arquivos. Você não poderá ver ou acessar diretórios e arquivos que pertencem a outros clientes.

As notificações de arquivo e os arquivos [!UICONTROL CDF] aparecerão em seu bucket [!DNL S3] quando estiverem prontos para download. Você é responsável por monitorar e baixar arquivos do diretório atribuído [!DNL S3]. Consulte [Notificações de processamento de arquivos de feed de dados do cliente](#cdf-file-processing-notifications).

## Próximas etapas {#next-steps}

As seções abaixo e as [Perguntas frequentes sobre o Feed de dados do cliente](../faq/faq-cdf.md) podem ajudá-lo a se familiarizar mais com esse serviço.

## [!UICONTROL Customer Data Feed] Conteúdo definido  {#cdf-defined}

Lista e define os elementos de dados e as matrizes em um arquivo [!UICONTROL CDF], por ordem de aparência. As definições incluem tipos de dados, mas essas informações não fazem parte de um arquivo [!UICONTROL CDF].

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
   <td colname="col3"> <p>A hora em que um arquivo CDF foi processado pelos <span class="wintitle"> Servidores de coleta de dados</span> (DCS). O carimbo de data e hora usa o formato <i>aaaa-mm-dd hh:mm:ss</i> e é definido no fuso horário UTC. </p> <p> <p>Observação: O Tempo do Evento <i>não é</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">O horário do evento da página ou da própria chamada do evento, embora possa estar próximo desses horários. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">Relacionado à hora do DCS no nome do arquivo. Consulte também, <a href="#different-processing-times"> Tempo do nome do arquivo do feed de dados do cliente e Tempo do conteúdo do arquivo...</a>. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>Esta é a <span class="wintitle"> ID de usuário exclusiva</span> (UUID), que é uma ID de dispositivo de 38 dígitos para o visitante do site. Consulte também <a href="../reference/ids-in-aam.md">Índice de IDs no Audience Manager</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Container ID</code> </p> </td> 
   <td colname="col2"> <p>Numérico </p> </td> 
   <td colname="col3"> <p>A ID do contêiner que aciona sincronizações de ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Uma matriz de IDs de característica que contém todas as características que um visitante realizou (qualificado para) na chamada de evento. </p> <p>Observe que a matriz pode conter características para as quais o visitante se qualificou antes e para as quais se requaliu por meio dessa chamada de evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Uma matriz de IDs de segmento que contém todos os segmentos que um visitante realizou (qualificado para) na chamada de evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>Uma string que captura todos os parâmetros (variáveis, IDs, pares de valores chave, IDs de publicidade de dispositivos etc.) passado na chamada de evento. </p> <p>Exemplo reduzido: </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
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
   <td colname="col3"> <p>A ID <span class="keyword"> Experience Cloud</span> (MID) atribuída ao visitante do site. Consulte também, <a href="https://docs.adobe.com/content/help/pt-BR/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies e o serviço de identidade do Adobe Experience Platform</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Uma matriz de IDs de segmento que contém segmentos realizados anteriormente e novos segmentos para os quais o visitante está qualificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Uma matriz de IDs de características originais e de terceiros que contém características e novas características realizadas anteriormente pelas quais o visitante se qualificou desde o último feed de dados gerado. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Estrutura do arquivo  {#cdf-file-structure}

Lista e define a estrutura de dados de um arquivo [!UICONTROL CDF]. Isso inclui sequência de dados, delimitadores e separadores de campo, um mapa de arquivo de dados e arquivo de amostra.

## Identificadores de campo de dados e sequência {#identifiers-and-sequence}

[!UICONTROL CDF] os arquivos não contêm colunas rotuladas ou cabeçalhos de campo. Em vez disso, um arquivo [!UICONTROL CDF] define campos e matrizes com caracteres [!DNL ASCII] não imprimíveis. Além disso, o arquivo [!UICONTROL CDF] lista cada campo e matriz em uma ordem específica. Entender os identificadores de campo e a ordem ajudará a analisar o arquivo corretamente.

<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento de arquivo CDF </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Separadores e delimitadores de campo </p> </td> 
   <td colname="col2"> <p>Esses caracteres não imprimíveis definem os elementos e a estrutura do arquivo CDF: </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a (ASCII <code> 001</code> ou <code> ^A</code>) separa dados em campos individuais com um indicador de espaço não imprimível. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b (ASCII <code> 002</code> ou <code> ^B</code>) separa dados em uma matriz e solicita parâmetros. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c (ASCII <code> 003</code> ou <code> ^C</code>) define pares de valores chave. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sequência do campo </p> </td> 
   <td colname="col2"> <p> <p>Importante: <span class="keyword"> Audience Manager</span> reserva o direito de adicionar novos campos ao final do arquivo CDF em versões futuras. Isso significa que o design técnico do seu sistema de análise de arquivos não deve assumir um número fixo de colunas (embora possa assumir uma ordem fixa para as colunas existentes). </p> </p> <p>Os dados no arquivo CDF são exibidos na ordem mostrada abaixo. </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">Hora do evento </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">Dispositivo </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">ID do container </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">Características Realizadas </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">Segmentos realizados </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">Parâmetros da solicitação </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">Endereço IP </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Experience Cloud Device ID (ou MID). Consulte também, <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies e o serviço de identidade da Adobe Experience Platform</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">Todos os segmentos </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">Todas as características </li> 
     </ol> </p> <p>Para obter descrições de campos, consulte <a href="#cdf-defined"> Conteúdo do feed de dados do cliente definido</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL CDF] Mapa de arquivos  {#cdf-file-map}

[!UICONTROL CDF] os dados do arquivo são exibidos na ordem mostrada abaixo.

![](assets/sequence-map.png)

## Identificação de matrizes

Matrizes em um arquivo [!UICONTROL CDF] iniciam e terminam com o separador de campo `Ctrl + a`. Isso faz com que o primeiro elemento em uma matriz pareça um campo de dados independente. Por exemplo, a matriz [!UICONTROL traits] realizada começa com `^A1234`. O delimitador de matriz e a ID `^B5678` seguem essa entrada. Como resultado, você pode ficar tentado a pensar que o primeiro elemento na matriz [!UICONTROL traits] realizada é ID 5678 (porque começa com `^B`). Esse não é o caso, por isso você precisa estar familiarizado com a sequência e a estrutura de um arquivo de dados. Mesmo que o primeiro elemento na matriz [!UICONTROL trait] realizada (ou qualquer uma das outras matrizes em um arquivo [!UICONTROL CDF]) comece com `^A`, a ordem de aparência ou posição no arquivo define o início de uma matriz. E o primeiro elemento em uma matriz é sempre separado da entrada anterior por `^A`.

## Arquivo [!UICONTROL CDF] de amostra {#sample-file}

Um arquivo de amostra [!UICONTROL CDF] pode ser semelhante ao seguinte. Inserimos quebras de linha neste exemplo para ajudar a ajustar a página.

![](assets/CDF-sample.png)

## [!UICONTROL Customer Data Feed] Convenções de nomenclatura de arquivos  {#cdf-naming-conventions}

As seções abaixo listam e definem os elementos no nome do arquivo [!UICONTROL CDF].

## [!UICONTROL CDF] Nome do arquivo: Sintaxe e exemplo  {#cdf-file-name}

Um nome de arquivo típico [!UICONTROL CDF] contém os elementos listados abaixo. Observação: *itálico* indica um espaço reservado de variável:

### Sintaxe

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF-PARTNER-ID-AAM PROCESS-ID_0.gz
```

### Exemplo

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz
```

No seu bucket de armazenamento [!DNL S3], os arquivos são classificados em ordem crescente pela ID do parceiro ([!UICONTROL PID]), dia e hora.

## [!UICONTROL CDF] Elementos de nome de arquivo definidos  {#cdf-file-name-elements}

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
   <td colname="col2"> <p>Esse é o bucket de armazenamento raiz padrão para seu arquivo CDF em um servidor Amazon S3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>your S3 bucket name</i> </code> </p> </td> 
   <td colname="col2"> <p>O nome do bucket S3 somente leitura que armazena seus arquivos CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>A data em que o arquivo foi processado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>Um valor de hora expresso em notação de 24 horas e definido no fuso horário UTC. Consulte também, <a href="#different-processing-times"> Tempo do nome do arquivo do feed de dados do cliente e Tempo do conteúdo do arquivo...</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Sua ID de parceiro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AAM process ID</i>_0</code> </p> </td> 
   <td colname="col2"> <p>Uma ID de processo <span class="keyword"> Audience Manager</span> interna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>Uma extensão de arquivo gzip. Os arquivos CDF são compactados por gzip. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Notificações de processamento de arquivos  {#cdf-file-processing-notifications}

[!DNL Audience Manager] grava um  `.info` arquivo no seu  [!DNL S3] diretório para informá-lo quando o  [!UICONTROL Customer Data File] ([!UICONTROL CDF]) estiver pronto para download. O arquivo `.info` também inclui [!DNL JSON] metadados formatados sobre o conteúdo dos arquivos [!UICONTROL CDF]. Consulte esta seção para obter informações sobre a sintaxe e os campos usados por este arquivo de notificação.

## Arquivo de Informações de Exemplo {#sample-info-file}

Cada arquivo `.info` contém uma seção `Files` e `Totals`. A seção `Files` contém uma matriz que contém métricas específicas para cada arquivo por hora. A seção `Totals` contém métricas agregadas em todos os arquivos [!UICONTROL CDF] de um dia específico. O conteúdo do arquivo `.info` pode ser semelhante ao seguinte exemplo.

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

### Objeto de Arquivos

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
   <td colname="col2"> <p>Inicia a matriz que contém metadados sobre seus arquivos CDF. </p> </td> 
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
   <td colname="col2"> <p>O dia para o qual os dados estão disponíveis. Usa o formato <i>aaaa-mm-dd</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hour</code> </p> </td> 
   <td colname="col2"> <p>A hora para a qual os dados estão disponíveis. Usa o formato de 24 horas definido no fuso horário UTC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>Tamanho total de todos os arquivos CDF dessa data em bytes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>Número total de arquivos carregados no diretório S3. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] O tempo de nome do arquivo e o tempo de conteúdo do arquivo são diferentes  {#different-processing-times}

Seu arquivo [!UICONTROL CDF] contém carimbos de data e hora no nome do arquivo e no conteúdo do arquivo. Esses carimbos de data e hora registram processos de evento diferentes para o mesmo arquivo [!UICONTROL CDF] . Não é incomum ver carimbos de data e hora diferentes no nome e no conteúdo do mesmo arquivo. Entender cada carimbo de data e hora pode ajudar a evitar erros comuns ao trabalhar com esses dados ou tentar classificá-los por tempo.

## Localizando [!UICONTROL CDF] Carimbos de data e hora do arquivo {#locating-timestamps}

[!UICONTROL CDF] os arquivos registram o tempo de forma diferente em 2 locais separados.

![](assets/cdf-timestamp.png)

## Como entender a diferença entre carimbos de data e hora {#understanding-timestamps}

A tabela a seguir fornece detalhes adicionais sobre os carimbos de data e hora do arquivo [!UICONTROL CDF], juntamente com informações sobre como usá-los corretamente.

| Localização do carimbo de data e hora | Descrição |
|--- |--- |
| Nome do arquivo | O carimbo de data e hora no nome do arquivo [!DNL CDF] marca o horário em que [!DNL Audience Manager] começou a preparar o arquivo para entrega. Esse carimbo de data e hora é definido no fuso horário [!DNL UTC]. Ele usa o parâmetro `hour=` , com o tempo formatado como uma hora de 2 dígitos em uma notação de 24 horas. Essa hora pode ser diferente da hora do evento registrada no conteúdo do arquivo. Ao trabalhar com arquivos [!DNL CDF], às vezes você perceberá que o bucket [!DNL S3] está vazio por uma hora específica. Um bucket vazio significa que:<ul><li>Não há dados para aquela hora em particular. </li><li> Nossos servidores estão sob cargas pesadas e não podem processar arquivos por uma hora específica. Quando o servidor captura, ele coloca os arquivos que devem ter entrado em um arquivo de bucket de tempo anterior em um bucket com um valor de tempo posterior. Por exemplo, você verá isso quando um arquivo que deveria estar no período de 17 horas aparecer no período de 18 horas (com `hour=18` no nome do arquivo). Nesse caso, o servidor provavelmente começou a processar seu arquivo na hora 17, mas não pôde concluí-lo dentro desse intervalo de tempo. Em vez disso, o arquivo é enviado para o próximo período de hora.</li></ul><br>**Importante**: Não use o carimbo de data e hora do nome do arquivo para agrupar eventos por tempo. Se precisar agrupar por tempo, use o carimbo de data e hora `EventTime` no conteúdo do arquivo. |
| Conteúdo do arquivo | O carimbo de data e hora no conteúdo do arquivo [!DNL CDF] marca o horário em que o [!DNL Data Collection Servers] começou a processar o arquivo. Esse carimbo de data e hora é definido no fuso horário [!DNL UTC]. Ele usa o campo `EventTime`, com o tempo formatado como *`yyyy-mm-dd hh:mm:ss`*. Essa hora está próxima da hora real do evento na página, mas pode ser diferente do indicador de hora no nome do arquivo. <br> **Dica**: Diferente do  `hour=` carimbo de data e hora no nome do arquivo, é possível usar  `EventTime` para agrupar dados por tempo. |

>[!MORELIKETHIS]
>
>* [Perguntas frequentes sobre o Feed de dados do cliente](../faq/faq-cdf.md)

