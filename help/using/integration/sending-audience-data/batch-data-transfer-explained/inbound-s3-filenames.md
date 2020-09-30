---
description: Descreve os campos obrigatórios, a sintaxe, as convenções de nomenclatura e os tamanhos de arquivo que você precisa seguir ao enviar dados para o Audience Manager. Defina os nomes e tamanhos dos arquivos de acordo com essas especificações ao enviar dados para um diretório Audience Manager / Amazon S3.
seo-description: Descreve os campos obrigatórios, a sintaxe, as convenções de nomenclatura e os tamanhos de arquivo que você precisa seguir ao enviar dados para o Audience Manager. Defina os nomes e tamanhos dos arquivos de acordo com essas especificações ao enviar dados para um diretório Audience Manager / Amazon S3.
seo-title: Requisitos de nome e tamanho de arquivo do Amazon S3 para arquivos de dados de entrada
solution: Audience Manager
title: Requisitos de nome e tamanho de arquivo do Amazon S3 para arquivos de dados de entrada
uuid: 3692a122-6ad5-468c-934e-53067bd8cf71
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: f037a12af641da44ed67e62a249c41487da7ac07
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 6%

---


# [!DNL Amazon S3]Requisitos de nome e tamanho de arquivo para arquivos de dados de entrada{#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

Descreve os campos obrigatórios, a sintaxe, as convenções de nomenclatura e os tamanhos de arquivo que você precisa seguir ao enviar dados para [!DNL Audience Manager]. Defina os nomes e tamanhos dos arquivos de acordo com essas especificações ao enviar dados para um diretório [!DNL Audience Manager] / [!DNL Amazon S3] .

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *itálico*, colchetes `[ ]` `( )` etc.) neste documento, indique os elementos de código e as opções. Consulte [Convenções de estilo para código e elementos de texto](../../../reference/code-style-elements.md) para obter mais informações.

## Sintaxe do nome do arquivo {#file-name-syntax}

[!DNL S3] os nomes de arquivo contêm os seguintes elementos obrigatórios e opcionais:

* **[!DNL S3]prefixo:**   `s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **Elementos de nome de arquivo:**   `ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Para outros formatos de nome de arquivo aceitos, consulte Integrações [](/help/using/integration/sending-audience-data/custom-partner-integrations.md)personalizadas de parceiros.

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>[!DNL Audience Manager] só processa [!DNL ASCII] e [!DNL UTF-8] codifica arquivos.

### Elementos de nome

A tabela define os elementos em um nome de [!DNL S3] arquivo.

<table id="table_455D174BAB9B494D973DA1023F22B962"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento de nome </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AWS_directory</i> </code> </p> </td> 
   <td colname="col2"> <p>O caminho e o nome do seu bucket do Amazon S3. Entre em contato com seu Gerente de contas para obter o nome, o caminho e as credenciais do diretório S3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Um carimbo de data e hora (com base no horário UTC) de quando você envia os arquivos para o bucket S3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Um lD que informa <span class="keyword"> Audience Manager</span> se um arquivo de dados contém suas próprias IDs de usuário, IDs do Android, IDs do iOS ou outras IDs pertencentes a fontes <a href="/help/using/features/global-data-sources.md"> de dados</a>globais. Aceita as seguintes opções:</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>ID da fonte de dados (também conhecida como ID do provedor de dados):</b> Essa é uma ID exclusiva que o Audience Manager atribui a uma fonte de dados (consulte o índice de Audience Manager <a href="/help/using/reference/ids-in-aam.md"> das IDs </a>). Use essa ID atribuída em um nome de arquivo ao enviar dados que contenham suas próprias IDs de usuário. Por exemplo, <code>...ftp_dpm_21_123456789.sync</code> informa ao <span class="keyword"> Audience Manager</span> para os dados integrados às IDs pertencentes à fonte de dados 21. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>IDs do Android (GAID):</b> Use a ID 20914 em um nome de arquivo de dados se ela contiver IDs do Android. É necessário usar o campo <code><i>_DPID_TARGET_DATA_OWNER</i></code> ao usar IDs do Android. Por exemplo, <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> informa à Audience Manager <span class="keyword"> que o arquivo de dados contém somente IDs do Android e que as IDs devem se qualificar para as características pertencentes à fonte de</span> <code><i>_DPID_TARGET_DATA_OWNER</i></code> dados.</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>IDs do iOS (IDFA):</b> Use a ID 20915 em um nome de arquivo de dados se ela contiver IDs do iOS. É necessário usar o campo <code><i>_DPID_TARGET_DATA_OWNER</i></code> ao usar IDs do iOS. Por exemplo, <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> informa à <span class="keyword"> Audience Manager</span> que o arquivo de dados contém somente IDs do iOS e que as IDs devem se qualificar para as características pertencentes à fonte de <code><i>_DPID_TARGET_DATA_OWNER</i></code> dados.</li>
     <li> <b>IDs pertencentes a outras fontes</b>de dados globais: Você pode inserir IDs Roku para publicidade (RIDA), IDs de publicidade da Microsoft (MAID) e outras IDs. Use a ID correspondente a cada fonte de dados, conforme descrito no artigo <a href="/help/using/features/global-data-sources.md"></a>de fontes de dados globais.</li> 
    </ul> <p> <p>Observação:  Não misture tipos de ID em seus arquivos de dados. Por exemplo, se o nome do arquivo incluir o identificador do Android, não coloque IDs do iOS ou suas próprias IDs no arquivo de dados. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Esse campo informa ao Audience Manager a qual fonte de dados os dados integrados. Esse campo é obrigatório se você definir o DPID como uma ID do Android ou iOS ou outra ID pertencente a fontes de dados globais. Isso permite que o Audience Manager <span class="keyword"></span> vincule os dados do arquivo de volta à sua organização. </p> <p>Por exemplo: </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> informa à Audience Manager que você está qualificando as IDs do cliente pertencentes à fonte de dados 33 para características ou sinais pertencentes à fonte de dados 21. </li> 
     <li> <b>IDs do Android (GAID):</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> informa à Audience Manager <span class="keyword"></span> que o arquivo de dados contém somente IDs do Android e que as IDs devem se qualificar para as características pertencentes à fonte de dados 21.</li> 
     <li> <b>IDs do iOS (IDFA):</b> <code>...ftp_dpm_20915_21_1234567890.sync</code> informa ao Audience Manager <span class="keyword"></span> que o arquivo de dados contém somente IDs do iOS e que as IDs devem se qualificar para as características pertencentes à fonte de dados 21.</li>
     <li> <b>IDs pertencentes a outras fontes</b>de dados globais: <code>...ftp_dpm_121963_21_1234567890.sync</code> informa ao Audience Manager <span class="keyword"></span> que o arquivo de dados contém somente IDs Roku e que as IDs devem se qualificar para as características pertencentes à fonte de dados 21. Use a ID correspondente a cada fonte de dados, conforme descrito no artigo <a href="/help/using/features/global-data-sources.md"></a>de fontes de dados globais.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner_name</i> </code> </p> </td> 
   <td colname="col2"> <p>O nome da empresa ou organização que você usa no <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>Um carimbo de data e hora UNIX UTC de 10 dígitos em segundos. O carimbo de data e hora ajuda a tornar cada nome de arquivo único. </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync|.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Opções de sincronização que incluem: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Cenário normal quando provedores de dados de terceiros enviam características por usuário para serem adicionadas ou removidas no sistema Audience Manager. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Permite que os provedores de dados enviem uma lista de características por usuário que devem substituir todas as características de terceiros existentes para esse provedor de dados no Audience Manager. Não é necessário incluir todos os usuários em um arquivo de substituição. Inclua somente os usuários que você deseja alterar. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Um número inteiro. Usado ao dividir arquivos grandes em várias partes para melhorar o tempo de processamento. O número indica qual parte do arquivo original você está enviando. </p> <p>Para um processamento de arquivos eficiente, divida os arquivos de dados conforme indicado: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Descompactado: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Compactado: 200 a 300 MB </li> 
    </ul> <p>Consulte os primeiros 2 exemplos <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples"></a> de nome de arquivo abaixo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Ao enviar arquivos para o Amazon S3, use apenas a compactação gzip. Quando compactados, esses arquivos recebem a <code> .gz</code> extensão. Não use compactação .zip. </p> <p>Os arquivos compactados devem ter 3 GB ou menos. Se seus arquivos forem maiores, entre em contato com o Atendimento ao cliente. Embora o Audience Manager possa lidar com arquivos grandes, talvez possamos ajudá-lo a reduzir o tamanho de seus arquivos e tornar as transferências de dados mais eficientes. Consulte <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">Compactação de arquivos de transferência de dados de entrada</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemplos de nome de arquivo {#file-name-examples}

Os exemplos a seguir mostram nomes de arquivos formatados corretamente. Seus nomes de arquivo podem ser semelhantes.

<ul class="simplelist"> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_567_1366545717.sync.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

Você pode [baixar](assets/ftp_dpm_1234_1445374061.overwrite) o arquivo de amostra se quiser exemplos adicionais. Este arquivo foi salvo com a extensão do `.overwrite` arquivo. Abra-o com um editor de texto simples.

## Tamanhos de arquivo aceitos {#accepted-file-sizes}

Considere as figuras abaixo para o processamento mais rápido/rápido de seus arquivos, bem como para as limitações de tamanho de arquivo ao enviar dados para um [!DNL Audience Manager] / [!DNL Amazon S3] diretório.

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

>[!NOTE]
>
>O processo de validação de dados de entrada marcará os arquivos vazios como inválidos e não os processará.

>[!MORELIKETHIS]
>
>* [Requisitos de nome de FTP para arquivos de dados de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

