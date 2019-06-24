---
description: Perguntas frequentes sobre como colocar dados offline no Audience Manager.
keywords: ftp ou s 3; s 3 ou ftp
seo-description: Perguntas frequentes sobre como colocar dados offline no Audience Manager.
seo-title: Perguntas frequentes sobre ingestão de dados do cliente
solution: Audience Manager
title: Perguntas frequentes sobre ingestão de dados do cliente
uuid: 491 e 9 ec 1-4731-46 a 8-86 e 7-d 8 c 613 e 6 cedc
translation-type: tm+mt
source-git-commit: dd5c3d28097251c58e1fb095aaf4076883d1c1a1

---


# Inbound Customer Data Ingestion FAQ{#inbound-customer-data-ingestion-faq}

Perguntas frequentes sobre como colocar dados offline no Audience Manager.

<br> 

<!-- 

c_inbound_crm_data_ingestion.xml

 -->

**É possível resumir o processo de onboarding?**

The onboarding process consists of 2 core components described in [Batch Data Transfer Process Described](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process). Isso envolve:

* Sincronização de ID
* Inbound Data File ( [!DNL .sync] file or [!DNL .overwrite] file)

<!-- 

Removed the Data Translation File bullet from the list above.

 -->

Abaixo está uma lista de perguntas e respostas que pode ser útil após revisar a documentação.

>[!NOTE]
>
>Os exemplos nesta seção são simplificados ou reduzidos para fins de afinidade e demonstração. Consulte a documentação Ingestão de dados de entrada para obter especificações detalhadas sobre formatos de arquivo e sintaxe.

<br> 

**É possível resumir o processo de implantação?**

Recomendamos o seguinte:

* Work with your data provider to format the daily inbound data file according to [!DNL Adobe] specifications.
* Transfer a test data file to [!DNL Adobe] for format verification.
* Work with your [!DNL Adobe] consultant to produce a taxonomy suitable for interpreting the contents of the data file.
* In the staging/development environment, confirm that the ID sync is configured to properly pick up the data provider&#39;s visitor ID and transfer it to the [!DNL Audience Manager] servers in realtime.
* Implantar sincronização DIL/ID com produção. A sincronização de ID já será configurada como um módulo no código DIL pelo seu consultor da Adobe.
* Transfer production data files to [!DNL Audience Manager]. Considerando as dependências em mapeamentos de sincronização de ID, pode fazer sentido começar a transferir dados até uma semana após a implantação do código de produção, embora você possa começar a transferir os arquivos de dados assim que o código entra na produção.

<br> 

**Qual modo FTP devo usar para transferir arquivos compactados ou criptografados?**

See [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br> 

**É possível carregar um arquivo de dados de entrada ([!DNL .sync]ou arquivo[!DNL .overwrite]) antes de implantar o código[!DNL Audience Manager]na produção?**

* If the data provider is configured to use [Profile Link](../features/profile-merge-rules/merge-rules-overview.md) for cross-device targeting, the data available for targeting shortly after an ID sync identifies to the matching [!DNL Audience Manager] visitor ID.

* If the data provider is not configured to use the [!UICONTROL Profile Link] feature, [!DNL Audience Manager] processes only the data for visitor IDs in the inbound data file that have been previously synced/matched back to an [!DNL Audience Manager] visitor ID.

Consider the following use cases in which the data provider is not configured to use [!UICONTROL Profile Merge]:

<table id="table_1A367ED6D016428FB21B3F3BC261BA98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso de uso </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Caso 1</b> </p> </td> 
   <td colname="col2"> <p>Na segunda-feira, um visitante identificado no banco de dados CRM como logs ABC do visitante, que inicia uma sincronização de ID do cliente. <span class="keyword"> O Audience Manager</span> armazena o mapeamento do visitante ABC para <span class="keyword"> o visitante 123 do Audience Manager</span> . </p> <p>On Tuesday, the CRM database transfers a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager </span>server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC "gender" = "homem", "luxo_ shopper" = "yes"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">Reconhece o visitante ABC do mapeamento de sincronização de ID armazenado. </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Associates the traits <code> male</code> and <code> luxury_shopper</code> with the visitor 123 profile. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Caso 2</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the CRM database pushes a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender" = "women", "wine_ entusiastast" = "yes"</code> </li> 
     </ul> </p> <p> <span class="keyword"> O Audience Manager</span> não tem um registro desse visitante (ou uma ID de visitante associada) para que esse registro não seja processado. </p> <p>Na terça-feira, os logs DEF do visitante. Esta ação inicia a primeira sincronização de ID do cliente para esse visitante. This action maps visitor DEF to <span class="keyword"> Audience Manager</span> ID 456. No entanto, esse visitante não tem dados de CRM associados ao perfil. As a result, <span class="keyword"> Audience Manager</span> does not go back and reprocess old files. </p> <p>On Wednesday, the CRM database pushes another data file to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender" = "women", "wine_ entusiastast" = "yes", "dma" = "paris"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">Reconhece o DEF do visitante do mapeamento de sincronização de ID armazenado. </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Associates the traits <code> female</code>, <code> paris</code>, and <code> wine_enthusiast</code> with the visitor 456 profile. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Caso 3</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the <span class="keyword"> Audience Manager</span> server receives two files with the following records: </p> <p> <code> arquivo. sync</code> contendo: </p> <p> 
     <ul class="simplelist"> 
      <li><code> GHI 123456789</code> </li> 
     </ul> </p> <p> <code> . overwrite</code> arquivo contendo: </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GHI "gender" = "men" "wine_ entusiastast" = "não"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL "gender" = "female" "wine_ entusiastast" = "yes"</code> </li> 
    </ul> <p><span class="keyword"> O Audience Manager</span> armazena um registro mapeado do visitante JKL para a ID 789, de uma sincronização de ID anterior. </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">Reconhece o JKL do visitante do mapeamento de sincronização de ID armazenado. </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Associates the traits <code> female</code> and <code> wine_enthusiast</code> with visitor ID 789's profile. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">Ignora a associação de características para o visitante GHI, já que sua ID foi sincronizada apenas no lote atual. To associate traits with visitor GHI, you need to include them in future <code> .overwrite</code> files. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**Qual hora do dia devo transferir meu arquivo?**

[!DNL Audience Manager] verifica e processa arquivos várias vezes durante todo o dia. Faça upload dos dados sempre que estiver pronto.

<br> 

**Quanto tempo leva antes dos dados de um arquivo carregado estarem disponíveis para definição de metas?**

Os dados estão disponíveis para definição de metas após 48 horas. Além disso, não interprete o email &quot;carregado bem-sucedido&quot; como uma declaração que os dados estão disponíveis. This only means that [!DNL Audience Manager] has picked up the file and completed the first step of processing.

<br> 

**Com que frequência eu devo enviar arquivos e se eles devem ser arquivos completos ou incrementais?**

Como prática recomendada, envie um arquivo incremental uma vez por dia para novos visitantes e para visitantes cujos dados foram alterados. Many [!DNL Audience Manager] customers send a full file once per month. No entanto, esses intervalos de arquivo e incrementos são flexíveis. Você deve enviar dados em incrementos e, às vezes, que façam sentido para você.

<br> 

**Por quanto tempo o Audience Manager mantém meus arquivos no servidor?**

Os arquivos FTP são removidos após serem processados. [!DNL S3] são removidos após 30 dias. Os arquivos que não podem ser processados devido a formato, sintaxe ou outros erros são removidos. See also, [Privacy and Data Retention FAQ](../faq/faq-privacy.md).

<br> 

**Qual é a diferença entre arquivos completos e incrementais?**

* **Total:** Um arquivo completo substitui todos os perfis de visitantes existentes e os substitui pelos dados do arquivo. Full files are identified by the `.overwrite` tag appended to the file name. You can use a `.overwrite` file to reset visitor traits or remove stale, obsolete traits.

   >[!NOTE]
   >
   >The [!DNL .overwrite] files only overwrite [!DNL Audience Manager] profile data associated to this data provider. In other words, all [!DNL Adobe Analytics] data associated to the visitor remains intact after a [!DNL .overwrite] file has been processed.

* **Incremental:** Um arquivo incremental anexa novos dados aos perfis de visitantes existentes. Incremental files are identified by the `.sync` tag appended to the file name. Enviar um arquivo incremental não apaga nem substitui perfis existentes.

Os casos de uso a seguir demonstram como esses tipos de arquivos afetam os perfis de visitante armazenados.

<table id="table_CE43B49508384ABF8B25FA8A8FFE5362"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso de uso </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Incremental e Completo</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_E89301D815174D45B9B238F2CDE6CCC6"> 
      <li id="li_FA841FEEC0534AD59D1AB61DD5B9DEC4">Day 1 <code> .sync</code> file contents: <code> visitor123 = a,b,c</code> </li> 
      <li id="li_0E1A57B04D26481C8C41EBA63ACBEFE0">Day 2 <code> .overwrite</code> file contents: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_497A5604AD9A49A2ADE548C7CE158F0E"> Day 3 visitor profile ID 123 contains <code> c,d,e </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Somente incremental</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8271C9796BD040E4B8DC64DCE4FE2AD3"> 
      <li id="li_347959BDE83549F794E6661C95097891">Day 1 <code> .sync</code> file contents: <code> visitor123 = a,b,c </code> </li> 
      <li id="li_B25D96526DE94171A3A5DC8DB7A19415">Day 2 <code> .sync</code> file contents: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_6E17809D49C74F4991B0B445469055E6">Day 3 visitor profile ID 123 contains <code> a,b,c,d,e</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Para obter mais informações sobre tipos de arquivos completos e incrementais, consulte:

* [Requisitos de nome e tamanho de arquivo do Amazon S 3 para dados de entrada…](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

<br> 

**O que acontece se eu enviar um arquivo com IDs para visitantes que nunca executaram a sincronização da ID na página?**

During processing, [!DNL Audience Manager] simply skips that record and moves on to the next. Se uma DPID (ID do provedor de dados) estiver configurada como uma DPID de dispositivo cruzado, os dados assimilados antes de uma sincronização de ID ser salva e estará disponível para uso pouco após a sincronização da ID.

<br> 

**Qual é o carimbo de data e hora, para que serve e é possível fornecer um exemplo?**

Os carimbos de data e hora são usados para registro e manutenção de registros. Eles são exigidos pela sintaxe usada para um nome de arquivo de entrada devidamente formatado. Consulte:

* [Requisitos de nome Amazon S3 para arquivos de dados de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)


<br> 

**O que é uma ID de provedor de dados (DPID) e como posso obtê-la?**

Seu consultor da Adobe atribuirá uma DPID de três dígitos ou de quatro dígitos à sua fonte de dados específica. Essa ID é exclusiva e não muda.

<br> 

**Qual é o tamanho dos arquivos de dados diários?**

See [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br> 

**O Audience Manager suporta compactação de arquivo?**

Sim, consulte o:

* [Compactação de arquivo para arquivos de transferência de dados de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [Requisitos de nome Amazon S3 para arquivos de dados de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)


<br> 

**A chave primária do banco de dados da fonte de dados é um endereço de email. Is that considered personally identifiable information?**

Sim. [!DNL Audience Manager] não armazena endereços de email em nosso banco de dados. Os visitantes devem receber uma ID aleatória ou uma versão com hash de mão única do endereço de email antes de iniciar sincronizações de ID.

<br> 

**A diferenciação entre letras maiúsculas e minúsculas dos conteúdos do arquivo de dados? How about the ID sync?**

Há dois componentes básicos de um arquivo de dados: Uma ID de usuário exclusiva (UUID) e dados de perfil, normalmente na forma de pares de valor chave ou códigos. O UUID diferencia maiúsculas e minúsculas. Geralmente, os dados de perfil ou chave não distinguem maiúsculas de minúsculas.

<br> 

**Devo usar FTP ou[!DNL Amazon S3]transferir arquivos?**

As best practice, we recommend [!DNL Amazon S3] because the process is simpler. [!DNL Audience Manager] transfere arquivos FTP [!DNL S3] para independentemente, portanto, o processo é mais simplificado se você soltar os arquivos sozinho [!DNL Amazon S3] . Além disso, os clientes carregando simultaneamente em FTP compartilham a largura de banda do FTP, então devem esperar velocidades de upload mais lentas. [!DNL Amazon S3] também é replicado e distribuído, de modo que geralmente é mais seguro e confiável do que um servidor FTP. For more information, see [About Amazon S3](../reference/amazon-s3.md).

<br> 

**Como o Audience Manager processa arquivos de entrada?**

[!DNL Audience Manager] usado [!DNL Amazon Simple Queue Service (SQS)] para processamento de dados de entrada. Veja como isso funciona:

1. [!DNL Audience Manager] os clientes carregam seus dados de entrada em um [!DNL Amazon S3] compartimento.

2. The data enters the [!DNL Amazon SQS] queue, waiting to be processed by [!DNL Audience Manager].

3. [!DNL Audience Manager] lê até 119000 entradas da [!DNL Amazon SQS] fila e divide-as em até 3 lotes. Os arquivos em cada lote são processados simultaneamente.

<br> 

**Eu preciso fazer upload de vários arquivos ao mesmo tempo. Will the files be processed simultaneously?**

Depende de. [!DNL Audience Manager] lê até 119000 entradas da [!DNL Amazon SQS] fila e divide-as em até 3 lotes. Seus arquivos serão processados simultaneamente apenas se terminarem no mesmo lote. However, due to the high amount of data ingested by [!DNL Audience Manager] on a daily basis, we cannot guarantee any file processing order.

>[!MORE_ LIKE_ THIS]
>
>* [Descrição do processo de transferência de dados em lote](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process)

