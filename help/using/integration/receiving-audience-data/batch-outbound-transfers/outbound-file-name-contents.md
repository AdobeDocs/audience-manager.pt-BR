---
description: Descreve os campos, sintaxe e convenções necessários usados para nomear um arquivo de dados de saída.
seo-description: Descreve os campos, sintaxe e convenções necessários usados para nomear um arquivo de dados de saída.
seo-title: Sintaxe e exemplos de nome de arquivo de dados de saída
solution: Audience Manager
title: Sintaxe e exemplos de nome de arquivo de dados de saída
uuid: effdcaf 6-c 37 c -45 f 3-9 d 2 f-a 938 a 9 da 47 a 6
translation-type: tm+mt
source-git-commit: e6f1a3b86658a882ebe927cefe55be6ddd40b906

---


# Nome do arquivo de dados de saída: Sintaxe e exemplos{#outbound-data-file-name-syntax-and-examples}

Descreve os campos, sintaxe e convenções necessários usados para nomear um arquivo de dados de saída.

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>Os elementos de estilo (`monospaced text`, *itálico*, colchetes `[ ]``( )`etc.) neste documento indica elementos e opções do código. Consulte [Convenções de estilo para código e elementos de texto](../../../reference/code-style-elements.md) para obter mais informações.

## Sintaxe e elementos de nome de arquivo {#syntax-file-name}

Os nomes de arquivo de saída contêm os seguintes elementos. Todos os elementos abaixo são opcionais.

```
[SYNC_TYPE][_DID][_MASTER_DPID][_PID_ALIAS][_SYNC-MODE][_TIMESTAMP]SPLITNUM.sync[.gz]
```

### Parâmetros

A tabela define os elementos em um nome de arquivo de dados de saída.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento de nome de arquivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_ TYPE </i></code> </p> </td> 
   <td colname="col2"> <p>Refere-se aos métodos de transferência de dados. Os métodos de transferência incluem: </p> 
    <ul id="ul_4E0CFC7A34E04E2FA216A07E3654D6EE"> 
     <li id="li_0066B99222A64BE9975AE2E91511FB77">FTP - Transferir usando SFTP </li> 
     <li id="li_646767FE8AD247B88D0DD5461349F019"> <span class="keyword"> Amazon S 3 </span> - Transferir para <span class="keyword"> Amazon AWS </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DID </i></code> </p> </td> 
   <td colname="col2"> <p>ID de destino. </p> <p>No <span class="keyword"> Audience Manager </span>, um destino é a instância da integração na qual você pode mapear seus segmentos direcionáveis. Os clientes podem ter vários destinos, dependendo do requisito comercial. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>MASTER_ DPID </i></code> </p> </td> 
   <td colname="col2"> <p>Provedor de dados ou ID de fonte de dados. Essa ID identifica o tipo de ID de usuário presente no conteúdo do arquivo. As chaves de ID de usuário mais comuns são: </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">20914 - <span class="keyword"> ID de anunciante do Google </span> (bruto, não hash) </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">20915 - <span class="keyword"> ID da Apple para anunciantes </span> (bruta, não hash) </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">ID do fornecedor - IDs de usuário de terceiros (web/cookie) </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID_ ALIAS </i></code> </p> </td> 
   <td colname="col2"> O identificador do cliente na plataforma de terceiros. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_ MODE </i></code> </p> </td> 
   <td colname="col2"> <p>O modo de sincronização é um espaço reservado de macro que adiciona um rótulo ao nome do arquivo com base no tipo de sincronização. Os tipos de sincronização incluem total e incremental. Eles aparecerão no nome do arquivo como <code> iter </code> ou <code> completo </code>. </p> 
    <ul id="ul_3B3585CEF1434951B6FDCDD29E5013CD"> 
     <li id="li_947D94E9CFAC4041AC1AAEB191805529"> <code> iter </code>: Indica uma sincronização "iterativa" ou incremental. Um arquivo incremental contém apenas novos dados coletados desde a última sincronização. </li> 
     <li id="li_13ADB3B3346943DAA767A1F416482D3C"> <code> completo </code>: Indica uma sincronização "completa". Um arquivo sincronizado totalmente sincronizado contém dados antigos e novos dados coletados desde a última sincronização. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP </i></code> </p> </td> 
   <td colname="col2"> <p>Um carimbo de data e hora UNIX de 13 dígitos em milissegundos, no fuso horário UTC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>SPLITNUM</i></code></p> </td> 
   <td colname="col2"> <p>Um número inteiro. Identifica parte de um arquivo que foi dividido em várias partes para melhorar o tempo de processamento. O número indica a qual parte do arquivo original os dados pertencem.</p>  <p>O número inteiro deve ter pelo menos 3 dígitos, precedido por zeros, se o tamanho da divisão for inferior a 100 partes.</p>  <p>O arquivo original não terá nenhum número dividido. O primeiro arquivo dividido será encerrado com 001. Veja exemplos abaixo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz (opcional) </i></code> </p> </td> 
   <td colname="col2"> <p>Compactação GZIP. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemplos de nome de arquivo {#file-name-examples}

### Cenário 1

Arquivos enviados para um [!DNL Amazon S3] local, com *`PID_ALIAS="XYZCustomer"`* e com [!DNL Google Advertiser IDs] o conteúdo do arquivo.

Por exemplo, arquivos incrementais:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000001.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000002.sync.gz </code> </li> 
</ul>

Por exemplo, arquivos completos:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000001.sync.gz </code> </li> 
</ul>

### Cenário 2

Arquivos enviados para [!DNL FTP] o local, sem *`PID_ALIAS`* e com [!DNL Apple Advertiser IDs] o conteúdo do arquivo:

Por exemplo, arquivos incrementais:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_iter_1486140843000001.sync.gz </code> </li> 
</ul>

Por exemplo, arquivos completos:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_full_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_full_1486140843000001.sync.gz </code> </li> 
</ul>

**Cenário 3**: Arquivos enviados para [!DNL FTP] o local, com *`PID_ALIAS="XYZCustomer"`* e com ID de usuário de terceiros no conteúdo do arquivo ( *`Vendor ID=45454`*):

Por exemplo, arquivos incrementais:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
</ul>

Por exemplo, arquivos completos:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200001.sync.gz </code> </li> 
</ul>

## Conteúdo do arquivo de dados de saída: Sintaxe e parâmetros {#outbound-contents-syntax}

Descreve os campos, sintaxe e convenções necessários usados para organizar as informações em um arquivo de dados de saída. Formate seus dados de acordo com essas especificações.

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>Os elementos de estilo (`monospaced text`, *itálico*, colchetes `[ ]``( )`etc.) neste documento indica elementos e opções do código. Consulte [Convenções de estilo para código e elementos de texto](../../../reference/code-style-elements.md) para obter mais informações.

### Sintaxe

Os campos no arquivo de dados aparecem nesta ordem:

`UUID<SPACE>SEGMENT_1,SEGMENT_2<SPACE>REMOVED_SEGMENT_,...`

### Parâmetros

A tabela lista variáveis que definem o conteúdo de um arquivo de dados.

<table id="table_109BA747CFDA40108370EFEB208C7E11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>UUID </i></code> </p> </td> 
   <td colname="col2"> <p>Uma ID de usuário exclusiva atribuída pelo <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>&lt; SPACE &gt; </i></code> </p> </td> 
   <td colname="col2"> <p>Separe o UUID e segmenta os dados com um espaço </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SEGMENT_ N </i></code> </p> </td> 
   <td colname="col2"> <p>A ID do segmento à qual um visitante pertence. Separe vários segmentos com vírgula. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>REMOVED_ SEGMENT_ N </i></code> </p> </td> 
   <td colname="col2"> <p>A ID do segmento a partir da qual o usuário foi desqualificado. Separe vários segmentos com vírgula. Com uma sincronização completa, você pode ignorar os segmentos removidos, pois o arquivo de dados conterá a lista completa de segmentos atuais para o usuário. Em geral, você quer saber sobre segmentos aos quais um usuário pertence, e não os que foram removidos. Consulte também <a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples"> Nome do arquivo de dados de saída: Sintaxe e exemplos </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exemplo: Formato de arquivo básico

Um arquivo de dados formatado adequadamente pode ser semelhante à seguinte amostra. Essa entrada de arquivo indica que um usuário é qualificado para os segmentos 24, 26 e 27. Conforme necessário, um espaço separa as IDs `UUID` de segmento. Outro espaço separa os conjuntos de IDs de segmento. Neste exemplo, um usuário pertence aos segmentos 24, 26 e 27. Eles foram removidos dos segmentos 25 e 28.

```
59767559181262060060278870901087098252  24,26,27  25,28
```
