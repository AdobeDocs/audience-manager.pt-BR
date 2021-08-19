---
description: Descreve os campos, sintaxe e convenções necessários usados para nomear um arquivo de dados de saída.
seo-description: Descreve os campos, sintaxe e convenções necessários usados para nomear um arquivo de dados de saída.
seo-title: Sintaxe e exemplos do nome do arquivo de dados de saída
solution: Audience Manager
title: Sintaxe e exemplos do nome do arquivo de dados de saída
uuid: effdcaf6-c37c-45f3-9d2f-a938a9da47a6
feature: Transferências de dados de saída
exl-id: 0944da72-5a8d-45a2-951e-b2988eb3d490
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 6%

---

# Nome do arquivo de dados de saída: sintaxe e exemplos{#outbound-data-file-name-syntax-and-examples}

Descreve os campos, sintaxe e convenções necessários usados para nomear um arquivo de dados de saída.

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>Os elementos de estilo (`monospaced text`, *itálico*, colchetes `[ ]` `( )`, etc.) neste documento, indique elementos e opções de código. Consulte [Convenções de estilo para código e elementos de texto](../../../reference/code-style-elements.md) para obter mais informações.

## Elementos de sintaxe e nome de arquivo {#syntax-file-name}

Os nomes de arquivo de saída contêm os seguintes elementos. Todos os elementos abaixo são opcionais.

```
[SYNC_TYPE][_DID][_MASTER_DPID][_PID_ALIAS][_SYNC-MODE][_TIMESTAMP]SPLITNUM.sync[.gz]
```

### Parâmetros

A tabela define os elementos em um nome de arquivo de dados de saída.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento do nome do arquivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_TYPE </i></code> </p> </td> 
   <td colname="col2"> <p>Refere-se aos métodos de transferência de dados. Os métodos de transferência incluem: </p> 
    <ul id="ul_4E0CFC7A34E04E2FA216A07E3654D6EE"> 
     <li id="li_0066B99222A64BE9975AE2E91511FB77">FTP - Transferência usando SFTP </li> 
     <li id="li_646767FE8AD247B88D0DD5461349F019"> <span class="keyword"> Amazon S3  </span> - Transferência para o  <span class="keyword"> Amazon AWS  </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DID </i></code> </p> </td> 
   <td colname="col2"> <p>ID de destino. </p> <p>No <span class="keyword"> Audience Manager </span>, um destino é a instância da integração, onde você pode mapear seus segmentos direcionáveis. Os clientes podem ter vários destinos, dependendo do requisito de negócios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>MASTER_DPID </i></code> </p> </td> 
   <td colname="col2"> <p>Provedor de dados ou ID da fonte de dados. Essa ID identifica o tipo de ID de usuário presente no conteúdo do arquivo. As chaves de ID de usuário mais comuns são: </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">2014 - <span class="keyword"> ID do anunciante do Google </span> (bruto, sem hash) </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">20915 - <span class="keyword"> Apple ID para anunciantes </span> (bruto, sem hash) </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">ID do fornecedor - IDs de usuário de terceiros (web/cookie) </li> 
     </ul> </p> <p>Consulte <a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/global-data-sources.html">Fontes de dados globais</a> para obter mais detalhes.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID_ALIAS </i></code> </p> </td> 
   <td colname="col2"> O identificador do cliente da plataforma de terceiros. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_MODE </i></code> </p> </td> 
   <td colname="col2"> <p>O modo de sincronização é um espaço reservado para macro que adiciona um rótulo ao nome do arquivo com base no tipo de sincronização. Os tipos de sincronização incluem completo e incremental. Eles aparecerão no nome do arquivo como <code> iter </code> ou <code> full </code>. </p> 
    <ul id="ul_3B3585CEF1434951B6FDCDD29E5013CD"> 
     <li id="li_947D94E9CFAC4041AC1AAEB191805529"> <code> iter </code>: Indica uma sincronização "iterativa" ou incremental. Um arquivo incremental contém apenas novos dados coletados desde a última sincronização. </li> 
     <li id="li_13ADB3B3346943DAA767A1F416482D3C"> <code> full </code>: Indica uma sincronização "completa". Um arquivo totalmente sincronizado contém dados antigos e quaisquer novos dados coletados desde a última sincronização. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP </i></code> </p> </td> 
   <td colname="col2"> <p>Um carimbo de data e hora UNIX de 13 dígitos, em milissegundos, no fuso horário UTC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>SPLITNUM</i></code></p> </td> 
   <td colname="col2"> <p>Um inteiro. Identifica parte de um arquivo que foi dividido em várias partes para melhorar o tempo de processamento. O número indica a qual parte do arquivo original os dados pertencem.</p>  <p>O número inteiro deve ter pelo menos 3 dígitos, precedido de zeros, se o tamanho da divisão for menor que 100 partes.</p>  <p>O arquivo original não terá nenhum número de divisão. O primeiro arquivo dividido terminará com 001. Consulte os exemplos abaixo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz (optional) </i></code> </p> </td> 
   <td colname="col2"> <p>Compactação GZIP. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemplos de nome de arquivo {#file-name-examples}

### Cenário 1

Arquivos enviados para um local [!DNL Amazon S3], com *`PID_ALIAS="XYZCustomer"`* e com [!DNL Google Advertiser IDs] no conteúdo do arquivo.

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

Arquivos enviados para o local [!DNL FTP], sem *`PID_ALIAS`* e com [!DNL Apple Advertiser IDs] no conteúdo do arquivo:

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

**Cenário 3**: Arquivos enviados para o  [!DNL FTP] local, com  *`PID_ALIAS="XYZCustomer"`* e com ID de usuário de terceiros no conteúdo do arquivo (  *`Vendor ID=45454`*):

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

Descreve os campos, sintaxe e convenções necessários usados para organizar informações em um arquivo de dados de saída. Formate os dados de acordo com essas especificações.

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>Os elementos de estilo (`monospaced text`, *itálico*, colchetes `[ ]` `( )`, etc.) neste documento, indique elementos e opções de código. Consulte [Convenções de estilo para código e elementos de texto](../../../reference/code-style-elements.md) para obter mais informações.

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
   <td colname="col2"> <p>Uma ID de usuário exclusiva atribuída por <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>&lt;SPACE&gt; </i></code> </p> </td> 
   <td colname="col2"> <p>Separe a UUID e os dados do segmento com um espaço </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>A ID de segmento à qual um visitante pertence. Separe vários segmentos com uma vírgula. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>REMOVED_SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>A ID de segmento da qual o usuário foi desqualificado. Separe vários segmentos com uma vírgula. Com uma sincronização completa, você pode ignorar os segmentos removidos porque o arquivo de dados conterá a lista completa de segmentos atuais para o usuário. Normalmente, você quer saber sobre segmentos aos quais um usuário pertence, em vez daqueles dos quais ele foi removido. Consulte também <a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples"> Nome do arquivo de dados de saída: Sintaxe e exemplos </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exemplo: Formato básico de arquivo

Um arquivo de dados corretamente formatado pode ser semelhante à seguinte amostra. Essa entrada de arquivo indica que um usuário se qualifica para os segmentos 24, 26 e 27. Conforme necessário, um espaço separa as `UUID` e as IDs do segmento. Outro espaço separa os conjuntos de IDs de segmento. Neste exemplo, um usuário pertence aos segmentos 24, 26 e 27. Eles foram removidos dos segmentos 25 e 28.

```
59767559181262060060278870901087098252  24,26,27  25,28
```
