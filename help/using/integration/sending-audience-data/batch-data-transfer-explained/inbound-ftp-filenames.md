---
description: Descreve os campos, sintaxe, convenções de nomenclatura e tamanhos de arquivo necessários que devem ser seguidos ao enviar dados para o Audience Manager. Defina os nomes e tamanhos de seus arquivos de acordo com essas especificações ao enviar dados para um diretório FTP do Audience Manager.
seo-description: Descreve os campos, sintaxe, convenções de nomenclatura e tamanhos de arquivo necessários que devem ser seguidos ao enviar dados para o Audience Manager. Defina os nomes e tamanhos de seus arquivos de acordo com essas especificações ao enviar dados para um diretório FTP do Audience Manager.
seo-title: Requisitos de nome FTP e tamanho de arquivo para arquivos de dados de entrada
solution: Audience Manager
title: Requisitos de nome FTP e tamanho de arquivo para arquivos de dados de entrada
uuid: 49 eaafac -5 cb 0-482 f -872 a -84 c 056016 bdb
translation-type: tm+mt
source-git-commit: ec2d05290874a95e9cc9b8318fcc5e1e1986f5b9

---


# FTP Name and File Size Requirements for Inbound Data Files{#ftp-name-and-file-size-requirements-for-inbound-data-files}

Descreve os campos, sintaxe, convenções de nomenclatura e tamanhos de arquivo necessários que devem ser seguidos ao enviar dados para o Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager [!DNL FTP] directory.

>[!WARNING]
>
>A transferência FTP para arquivos de dados de entrada não é mais suportada. Use o Amazon S 3 para colocar dados offline no quadro. See [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) for details.

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *itálico*, colchetes `[ ]` `( )` etc.) neste documento indica elementos e opções do código. Consulte [Convenções de estilo para código e elementos de texto](../../../reference/code-style-elements.md) para obter mais informações.

## File Name Syntax {#file-name-syntax}

[!DNL FTP] os nomes de arquivo contêm os seguintes elementos obrigatórios e opcionais:

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

For other accepted file name formats, see [Custom Partner Integrations](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE] {importance = "high"}
>
>[!DNL Audience Manager] somente processos e [!DNL ASCII] arquivos [!DNL UTF-8] codificados.

### Nomear elementos

The table defines the elements in an [!DNL FTP] file name.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento de nome de arquivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ftp_ dpm_</code> </p> </td> 
   <td colname="col2"> <p>The path to and name of your <span class="keyword"> Audience Manager</span> FTP directory. Entre em contato com seu Gerente de contas para obter o diretório FTP e credenciais. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>An lD that tells <span class="keyword"> Audience Manager</span> if a data file contains your own user IDs or Android or iOS IDs. Aceita as seguintes opções: </p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>ID do parceiro de dados:</b> Esta é uma ID exclusiva do Audience Manager atribuída à empresa ou organização. Use essa ID atribuída em um nome de arquivo ao enviar dados que contêm suas próprias IDs de usuário. For example, <code>...ftp_dpm_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that a partner with ID 21 sent the file and it contains user IDs assigned by that partner. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>IDs do Android (GAID):</b> Use a ID 20914 em um nome de arquivo de dados se ele contiver a ID do Android. For example, <code>...ftp_dpm_20914_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains Android IDs only. </li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>IDs do iOS (IDFA):</b> Use a ID 20915 em um nome de arquivo de dados se ele contiver IDs do iOS. For example, <code>...ftp_dpm_20915_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains iOS IDs only. </li> 
    </ul> <p> <p>Observação: Não misture tipos de ID em seus arquivos de dados. Por exemplo, se o nome do arquivo incluir o identificador Android, não coloque IDs do iOS ou suas próprias IDs no arquivo de dados. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>_ DPID_ TARGET_ DATA_ FLOW</i></code> </p> </td> 
   <td colname="col2"> <p>Um espaço reservado para uma ID. For example, you could set it to your <span class="keyword"> Audience Manager</span> ID if you set the DPID to a data source ID or an Android or iOS ID. This lets <span class="keyword"> Audience Manager</span> link the file data back to your organization. </p> <p>Por exemplo: </p> 
    <ul id="ul_55EBBCB11F2B4A858AEFBFA1CD99E286"> 
     <li id="li_3404428F4E3D49A5AB6EDF56310D923F"> <code>… ftp_ dpm_ 33_ 21_ 1234567890. sync</code> mostra um parceiro com a ID 21 enviado em dados de uma fonte de dados que usa a ID 33. </li> 
     <li id="li_CF8D5AF678764E9984A088FD5D7BBFB6"> <code>… ftp_ dpm_ 20914_ 21_ 1234567890. sync</code> mostra um parceiro com a ID 21 enviado em dados que contém IDs do Android. </li> 
     <li id="li_3D73168391D7443BADDF27153090274D"> <code>… ftp_ dpm_ 20915_ 21_ 1234567890. sync</code> mostra um parceiro com a ID 21 enviado em dados que contém IDs do iOS. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (. sync |. overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Opções de sincronização que incluem: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sincronização</code>: Cenário normal quando provedores de dados de terceiros enviam características de uma base por usuário a serem adicionadas ou removidas no sistema do Audience Manager. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> substitui</code>: Permite que os clientes e provedores de dados enviem uma lista de características de cada usuário, que deve substituir todas as características existentes desse usuário por uma determinada fonte de dados no Audience Manager. Você não precisa incluir todos os usuários em um arquivo de substituição. Inclua somente os usuários que você deseja alterar. As características não atribuídas à fonte de dados de destino não serão apagadas. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_ NUMBER</i></code>] </p> </td> 
   <td colname="col2"> <p>Um número inteiro. Usado ao dividir arquivos grandes em várias partes para melhorar o tempo de processamento. O número indica qual parte do arquivo original está sendo enviado. </p> <p>Para processamento eficiente de arquivos, divida seus arquivos de dados conforme indicado: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Descompactado: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Compactado: 200-300 MB </li> 
    </ul> <p>See the first 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> file name examples</a> below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP</i></code> </p> </td> 
   <td colname="col2"> <p>Um carimbo de data e hora de 10 dígitos, UTC UNIX, em segundos. O carimbo de data e hora ajuda a tornar cada nome de arquivo exclusivo. </p> 
    <draft-comment> 
     <p> <p>Observação: O Audience Manager não usa o carimbo de data e hora durante o processamento de arquivos de entrada. O carimbo de data e hora no nome de arquivo foi descontinuado no Audience Manager, mas ainda é necessário para compatibilidade retroativa. </p> </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip é o formato de compactação permitido para um nome de arquivo FTP. Se você usar a compactação de arquivo, certifique-se de que o nome do arquivo tenha a extensão apropriada. </p> <p>Arquivos compactados devem ser de 3 GB ou menor. Se os arquivos de arquivos estiverem maiores, entre em contato com o Atendimento ao cliente. Embora o Audience Manager possa lidar com arquivos grandes, poderemos ajudar você a reduzir o tamanho dos arquivos e tornar as transferências de dados mais eficientes. See <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> File Compression for Inbound Data Transfer Files</a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

## File Name Examples {#file-name-examples}

Os seguintes exemplos mostram nomes de arquivo formatados corretamente. Seus nomes de arquivo podem ser semelhantes.

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_ dpm_ 478_ 1366545717. overwrite</code> </li> 
</ul>

[Baixe](assets/ftp_dpm_1234_1445374061.overwrite) o arquivo de amostra se precisar de mais exemplos. This file is saved with the `.overwrite` file extension. Abra-o com um editor de texto simples.

## Accepted File Sizes {#accepted-file-sizes}

Consider the figures below for fastest/earliest processing of your files as well as for file size limitations when you send data to an [!DNL Audience Manager] / [!DNL FTP] directory.

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
   <td colname="col2"> <p>200-300 MB </p> </td> 
   <td colname="col3"> <p>3 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Descompactado</b> </td> 
   <td colname="col2"> <p>1 GB </p> </td> 
   <td colname="col3"> <p>5 GB </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Requisitos de nome Amazon S3 para arquivos de dados de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

