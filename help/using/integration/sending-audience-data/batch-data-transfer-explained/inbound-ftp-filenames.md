---
description: Descreve os campos obrigatórios, a sintaxe, as convenções de nomenclatura e os tamanhos de arquivo que você precisa seguir ao enviar dados para o Audience Manager. Defina os nomes e os tamanhos dos arquivos de acordo com essas especificações ao enviar dados para um diretório Audience Manager FTP.
seo-description: Descreve os campos obrigatórios, a sintaxe, as convenções de nomenclatura e os tamanhos de arquivo que você precisa seguir ao enviar dados para o Audience Manager. Defina os nomes e os tamanhos dos arquivos de acordo com essas especificações ao enviar dados para um diretório Audience Manager FTP.
seo-title: Requisitos de nome e tamanho de arquivo FTP para arquivos de dados de entrada
solution: Audience Manager
title: Requisitos de nome e tamanho de arquivo FTP para arquivos de dados de entrada
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
feature: Transferências de dados de entrada
exl-id: 9c889214-7075-4392-9ed5-f07b91e7b50a
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 8%

---

# [!DNL FTP]Requisitos de nome e tamanho de arquivo para arquivos de dados de entrada{#ftp-name-and-file-size-requirements-for-inbound-data-files}

Descreve os campos, sintaxe, convenções de nomenclatura e tamanhos de arquivo necessários ao enviar dados para [!DNL Audience Manager]. Defina os nomes e os tamanhos dos arquivos de acordo com essas especificações ao enviar dados para um diretório Audience Manager [!DNL FTP].

>[!WARNING]
>
>Estamos removendo gradualmente o suporte para configurações [!DNL FTP]. Embora a assimilação do arquivo de dados de entrada ainda seja compatível em integrações [!DNL FTP] existentes, recomendamos usar [!DNL Amazon S3] para dados offline integrados para novas integrações. Consulte [Requisitos de nome e tamanho de arquivo do Amazon S3 para arquivos de dados de entrada](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) para obter detalhes.

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *itálico*, colchetes `[ ]` `( )` etc.) neste documento, indique elementos e opções de código. Consulte [Convenções de estilo para código e elementos de texto](../../../reference/code-style-elements.md) para obter mais informações.

## Sintaxe do nome do arquivo {#file-name-syntax}

[!DNL FTP] os nomes de arquivo contêm os seguintes elementos obrigatórios e opcionais:

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Para outros formatos de nome de arquivo aceitos, consulte [Integrações personalizadas de parceiros](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>[!DNL Audience Manager] só processa  [!DNL ASCII] e  [!DNL UTF-8] codifica arquivos.

### Nomear elementos

A tabela define os elementos em um nome de arquivo [!DNL FTP].

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento do nome do arquivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ftp_dpm_</code> </p> </td> 
   <td colname="col2"> <p>O caminho e o nome do seu diretório FTP <span class="keyword"> Audience Manager</span>. Entre em contato com seu Gerente de contas para obter o diretório e as credenciais do FTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Um ID que informa <span class="keyword"> Audience Manager</span> se um arquivo de dados contém suas próprias IDs de usuário, IDs do Android, IDs do iOS ou outras IDs pertencentes a <a href="/help/using/features/global-data-sources.md"> fontes de dados globais</a>. Aceita as seguintes opções:</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>ID da fonte de dados (também conhecida como ID do provedor de dados):</b>  essa é uma ID exclusiva que o Audience Manager atribui a uma fonte de dados (consulte o  <a href="/help/using/reference/ids-in-aam.md"> índice Audience Manager de IDs  </a>). Use essa ID atribuída em um nome de arquivo ao enviar dados que contenham suas próprias IDs de usuário. Por exemplo, <code>...ftp_dpm_21_123456789.sync</code> informa <span class="keyword"> Audience Manager</span> para integrar dados a IDs pertencentes à fonte de dados 21. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android IDs (GAID): </b> use a ID 20914 em um nome de arquivo de dados se ela contiver Android IDs. Você precisa usar o campo <code><i>_DPID_TARGET_DATA_OWNER</i></code> quando usar IDs do Android. Por exemplo, <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> informa <span class="keyword"> Audience Manager</span> que o arquivo de dados contém IDs do Android somente e as IDs devem se qualificar para as características pertencentes à fonte de dados <code><i>_DPID_TARGET_DATA_OWNER</i></code>.</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>IDs do iOS (IDFA): </b> use a ID 20915 em um nome de arquivo de dados se ela contiver IDs do iOS. Você precisa usar o campo <code><i>_DPID_TARGET_DATA_OWNER</i></code> quando usar IDs do iOS. Por exemplo, <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> informa <span class="keyword"> Audience Manager</span> que o arquivo de dados contém IDs do iOS somente e as IDs devem se qualificar para as características pertencentes à fonte de dados <code><i>_DPID_TARGET_DATA_OWNER</i></code>.</li>
     <li> <b>IDs pertencentes a outras fontes</b> de dados globais: Você pode integrar IDs Roku para publicidade (RIDA), IDs de publicidade da Microsoft (MAID) e outras IDs. Use a ID correspondente a cada fonte de dados, conforme descrito no <a href="/help/using/features/global-data-sources.md"> artigo de fontes de dados globais</a>.</li> 
    </ul> <p> <p>Observação:  Não misture tipos de ID nos arquivos de dados. Por exemplo, se o nome do arquivo incluir o identificador do Android, não coloque IDs do iOS ou suas próprias IDs no arquivo de dados. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Este campo informa ao Audience Manager para qual fonte de dados integrar dados. Esse campo é obrigatório se você definir a DPID como uma ID do Android ou iOS ou outra ID pertencente a fontes de dados globais. Isso permite que <span class="keyword"> Audience Manager</span> vincule os dados do arquivo de volta à organização. </p> <p>Por exemplo: </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> informa ao Audience Manager que você está qualificando as IDs do cliente pertencentes à fonte de dados 33 para características ou sinais pertencentes à fonte de dados 21. </li> 
     <li> <b>Android IDs (GAID):</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> informa ao  <span class="keyword"> Audience </span> Manager que o arquivo de dados contém Android IDs somente e as IDs devem se qualificar para as características pertencentes à fonte de dados 21.</li> 
     <li> <b>IDs do iOS (IDFA):</b> <code>...ftp_dpm_20915_21_1234567890.sync</code> informa ao  <span class="keyword"> Audience </span> Manager que o arquivo de dados contém IDs do iOS somente e as IDs devem se qualificar para as características pertencentes à fonte de dados 21.</li>
     <li> <b>IDs pertencentes a outras fontes</b> de dados globais:  <code>...ftp_dpm_121963_21_1234567890.sync</code> informa ao  <span class="keyword"> Audience </span> Manager que o arquivo de dados contém somente IDs Roku e que as IDs devem se qualificar para as características pertencentes à fonte de dados 21. Use a ID correspondente a cada fonte de dados, conforme descrito no <a href="/help/using/features/global-data-sources.md"> artigo de fontes de dados globais</a>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync |.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Opções de sincronização que incluem: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Cenário normal quando provedores de dados de terceiros enviam características por usuário para serem adicionadas ou removidas no sistema Audience Manager. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Permite que clientes e provedores de dados enviem uma lista de características por usuário que deve substituir todas as características existentes desse usuário para uma determinada fonte de dados no Audience Manager. Não é necessário incluir todos os usuários em um arquivo de substituição. Inclua apenas os usuários que você deseja alterar. As características que não estão atribuídas à fonte de dados de destino não serão apagadas. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Um inteiro. Usado ao dividir arquivos grandes em várias partes para melhorar o tempo de processamento. O número indica qual parte do arquivo original você está enviando. </p> <p>Para um processamento eficiente de arquivos, divida os arquivos de dados conforme indicado: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Descompactado: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Compactado: 200-300 MB </li> 
    </ul> <p>Consulte os primeiros 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> exemplos de nome de arquivo</a> abaixo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>Um carimbo de data e hora UNIX UTC de 10 dígitos em segundos. O carimbo de data e hora ajuda a tornar cada nome de arquivo exclusivo. </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip é o formato de compactação permitido para um nome de arquivo FTP. Se você usar a compactação de arquivo, verifique se o nome do arquivo tem a extensão adequada. </p> <p>Os arquivos compactados devem ter 3 GB ou menos. Se os arquivos forem maiores, entre em contato com o Atendimento ao cliente. Embora o Audience Manager possa lidar com arquivos grandes, podemos ajudá-lo a reduzir o tamanho dos arquivos e tornar as transferências de dados mais eficientes. Consulte <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">Compactação de arquivos de transferência de dados de entrada</a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemplos de nome de arquivo {#file-name-examples}

Os exemplos a seguir mostram nomes de arquivos formatados corretamente. Os nomes de arquivo podem ser semelhantes.

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

[](assets/ftp_dpm_1234_1445374061.overwrite) Baixe o arquivo de amostra se precisar de mais exemplos. Esse arquivo é salvo com a extensão `.overwrite` do arquivo. Abra-o com um editor de texto simples.

## Tamanhos de arquivo aceitos {#accepted-file-sizes}

Considere as figuras abaixo para o processamento mais rápido/rápido de seus arquivos, bem como para as limitações de tamanho do arquivo ao enviar dados para um diretório [!DNL Audience Manager] / [!DNL FTP].

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
   <td colname="col1"><b>Comprimido</b> </td> 
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

>[!MORELIKETHIS]
>
>* [Requisitos de nome Amazon S3 para arquivos de dados de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

