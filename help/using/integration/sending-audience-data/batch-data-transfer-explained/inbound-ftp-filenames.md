---
description: Descreve os campos obrigatórios, a sintaxe, as convenções de nomenclatura e os tamanhos de arquivo que você precisa seguir ao enviar dados para o Audience Manager. Defina os nomes e os tamanhos dos arquivos de acordo com essas especificações ao enviar dados para um diretório FTP Audience Manager.
seo-description: Descreve os campos obrigatórios, a sintaxe, as convenções de nomenclatura e os tamanhos de arquivo que você precisa seguir ao enviar dados para o Audience Manager. Defina os nomes e os tamanhos dos arquivos de acordo com essas especificações ao enviar dados para um diretório FTP Audience Manager.
seo-title: Requisitos de nome e tamanho de arquivo FTP para arquivos de dados de entrada
solution: Audience Manager
title: Requisitos de nome e tamanho de arquivo FTP para arquivos de dados de entrada
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: b3ff5ca68022cc30632d6b647ffde507533b5ddf
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 9%

---


# [!DNL FTP]Requisitos de nome e tamanho de arquivo para arquivos de dados de entrada{#ftp-name-and-file-size-requirements-for-inbound-data-files}

Descreve os campos obrigatórios, a sintaxe, as convenções de nomenclatura e os tamanhos de arquivo que você precisa seguir ao enviar dados para [!DNL Audience Manager]. Defina os nomes e tamanhos dos arquivos de acordo com essas especificações ao enviar dados para um diretório Audience Manager [!DNL FTP] .

>[!WARNING]
>
>We are gradually phasing out support for [!DNL FTP] configurations. While inbound data file ingestion is still supported in existing [!DNL FTP] integrations, we strongly recommend using [!DNL Amazon S3] to onboard offline data for new integrations. Consulte [Requisitos de nome e tamanho de arquivo do Amazon S3 para arquivos de dados de entrada](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) para obter detalhes.

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *itálico*, colchetes `[ ]` `( )` etc.) neste documento, indique os elementos de código e as opções. Consulte [Convenções de estilo para código e elementos de texto](../../../reference/code-style-elements.md) para obter mais informações.

## Sintaxe do nome do arquivo {#file-name-syntax}

[!DNL FTP] os nomes de arquivo contêm os seguintes elementos obrigatórios e opcionais:

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Para outros formatos de nome de arquivo aceitos, consulte Integrações [](/help/using/integration/sending-audience-data/custom-partner-integrations.md)personalizadas de parceiros.

>[!NOTE]
>
>[!DNL Audience Manager] só processa [!DNL ASCII] e [!DNL UTF-8] codifica arquivos.

### Elementos de nome

A tabela define os elementos em um nome de [!DNL FTP] arquivo.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento de nome de arquivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ftp_dpm_</code> </p> </td> 
   <td colname="col2"> <p>O caminho e o nome do diretório FTP do <span class="keyword"> Audience Manager</span> . Entre em contato com seu Gerente de contas para obter o diretório FTP e as credenciais. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Um lD que informa <span class="keyword"> Audience Manager</span> se um arquivo de dados contém suas próprias IDs de usuário ou IDs do Android ou iOS. Aceita as seguintes opções: </p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>ID do parceiro de dados:</b> Esta é uma Audience Manager de ID exclusiva atribuída à sua empresa ou organização. Use essa ID atribuída em um nome de arquivo ao enviar dados que contenham suas próprias IDs de usuário. Por exemplo, <code>...ftp_dpm_21_123456789.sync</code> informa à <span class="keyword"> Audience Manager</span> que um parceiro com ID 21 enviou o arquivo e ele contém IDs de usuário atribuídas por esse parceiro. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>IDs do Android (GAID):</b> Use a ID 20914 em um nome de arquivo de dados se ela contiver a ID do Android. Por exemplo, <code>...ftp_dpm_20914_123456789.sync</code> informa ao <span class="keyword"> Audience Manager</span> que o arquivo de dados contém somente IDs do Android. </li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>IDs do iOS (IDFA):</b> Use a ID 20915 em um nome de arquivo de dados se ela contiver IDs do iOS. Por exemplo, <code>...ftp_dpm_20915_123456789.sync</code> informa ao <span class="keyword"> Audience Manager</span> que o arquivo de dados contém somente IDs do iOS. </li> 
    </ul> <p> <p>Observação:  Não misture tipos de ID em seus arquivos de dados. Por exemplo, se o nome do arquivo incluir o identificador do Android, não coloque IDs do iOS ou suas próprias IDs no arquivo de dados. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Um espaço reservado para uma ID. Por exemplo, você pode defini-lo como sua ID de <span class="keyword"> Audience Manager</span> se definir o DPID como uma ID de fonte de dados ou uma ID do Android ou iOS. Isso permite que o Audience Manager <span class="keyword"></span> vincule os dados do arquivo de volta à sua organização. </p> <p>Por exemplo: </p> 
    <ul id="ul_55EBBCB11F2B4A858AEFBFA1CD99E286"> 
     <li id="li_3404428F4E3D49A5AB6EDF56310D923F"> <code>...ftp_dpm_33_21_1234567890.sync</code> mostra que um parceiro com a ID 21 enviou dados de uma fonte de dados que usa a ID 33. </li> 
     <li id="li_CF8D5AF678764E9984A088FD5D7BBFB6"> <code>...ftp_dpm_20914_21_1234567890.sync</code> mostra que um parceiro com a ID 21 enviou dados que contêm IDs do Android. </li> 
     <li id="li_3D73168391D7443BADDF27153090274D"> <code>...ftp_dpm_20915_21_1234567890.sync</code> mostra que um parceiro com a ID 21 enviou dados que contêm IDs do iOS. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync |.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Opções de sincronização que incluem: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Cenário normal quando provedores de dados de terceiros enviam características por usuário para serem adicionadas ou removidas no sistema Audience Manager. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Permite que os clientes e provedores de dados enviem uma lista de características por usuário que devem substituir todas as características existentes desse usuário para uma determinada fonte de dados no Audience Manager. Não é necessário incluir todos os usuários em um arquivo de substituição. Inclua somente os usuários que você deseja alterar. As características que não estão atribuídas à fonte de dados do público alvo não serão apagadas. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i></code>] </p> </td> 
   <td colname="col2"> <p>Um número inteiro. Usado ao dividir arquivos grandes em várias partes para melhorar o tempo de processamento. O número indica qual parte do arquivo original você está enviando. </p> <p>Para um processamento de arquivos eficiente, divida os arquivos de dados conforme indicado: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Descompactado: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Compactado: 200 a 300 MB </li> 
    </ul> <p>Consulte os primeiros 2 exemplos <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"></a> de nome de arquivo abaixo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>Um carimbo de data e hora UNIX UTC de 10 dígitos em segundos. O carimbo de data e hora ajuda a tornar cada nome de arquivo único. </p> 
    <draft-comment> 
     <p> <p>Observação:  Audience Manager não usa o carimbo de data e hora durante o processamento de arquivos de entrada. O carimbo de data e hora no nome do arquivo foi substituído no Audience Manager, mas ainda é necessário para compatibilidade com versões anteriores. </p> </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip é o formato de compactação permitido para um nome de arquivo FTP. Se você usar a compactação de arquivo, verifique se o nome do arquivo tem a extensão correta. </p> <p>Os arquivos compactados devem ter 3 GB ou menos. Se os arquivos forem maiores, entre em contato com o Atendimento ao cliente. Embora o Audience Manager possa lidar com arquivos grandes, talvez possamos ajudá-lo a reduzir o tamanho de seus arquivos e tornar as transferências de dados mais eficientes. Consulte <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">Compactação de arquivos de transferência de dados de entrada</a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemplos de nome de arquivo {#file-name-examples}

Os exemplos a seguir mostram nomes de arquivos formatados corretamente. Seus nomes de arquivo podem ser semelhantes.

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

[Baixe](assets/ftp_dpm_1234_1445374061.overwrite) o arquivo de amostra se precisar de outros exemplos. Esse arquivo é salvo com a extensão do `.overwrite` arquivo. Abra-o com um editor de texto simples.

## Tamanhos de arquivo aceitos {#accepted-file-sizes}

Considere as figuras abaixo para o processamento mais rápido/rápido de seus arquivos, bem como para as limitações de tamanho de arquivo ao enviar dados para um [!DNL Audience Manager] / [!DNL FTP] diretório.

<table id="table_59FCC63806684DF8BE54A1EAF224A234"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de arquivo </th> 
   <th colname="col2" class="entry"> Tamanho ideal </th> 
   <th colname="col3" class="entry"> Tamanho máximo </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Compactado</b> </td> 
   <td colname="col2"> <p>200 a 300 MB </p> </td> 
   <td colname="col3"> <p>3 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Descompactado</b> </td> 
   <td colname="col2"> <p>1 GB </p> </td> 
   <td colname="col3"> <p>5 GB </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Requisitos de nome Amazon S3 para arquivos de dados de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

