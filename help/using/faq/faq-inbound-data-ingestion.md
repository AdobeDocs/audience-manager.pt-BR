---
description: Perguntas frequentes sobre como trazer dados offline para o Audience Manager.
keywords: ftp ou s3;s3 ou ftp
seo-description: Frequently asked questions about bringing offline data into Audience Manager.
seo-title: Inbound Customer Data Ingestion FAQ
solution: Audience Manager
title: Perguntas frequentes sobre assimilação de dados de entrada do cliente
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
feature: Onboarding Offline Data
exl-id: 48eef5f1-0655-4dac-9ab4-74b11c705c13
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1343'
ht-degree: 86%

---

# Perguntas frequentes sobre assimilação de dados de entrada do cliente{#inbound-customer-data-ingestion-faq}

Perguntas frequentes sobre como trazer dados offline para o Audience Manager.

 

**Você pode resumir o processo de integração?**

O processo de integração consiste em duas etapas descritas em [Enviar dados em lote para a visão geral do Audience Manager](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md):

* Etapa 1: sincronizar IDs de usuário;
* Etapa 2: criar e transferir o arquivo de dados de entrada seguindo os requisitos de formato de arquivo.

 

**Você pode resumir o processo de implantação?**

Recomendamos o seguinte:

* Trabalhe com seu provedor de dados para formatar o arquivo de dados de entrada diário de acordo com as especificações da Adobe. Consulte a documentação a seguir para conhecer os requisitos de sintaxe e nome de arquivo:
   * [Requisitos de nome e conteúdo para arquivos de sincronização de ID](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)
   * [Conteúdo do arquivo de dados de entrada: sintaxe, caracteres inválidos, variáveis e exemplos](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)
   * [Requisitos de nome e tamanho de arquivo do Amazon S3 para arquivos de dados de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* Trabalhe com o consultor da [!DNL Adobe] para transferir um arquivo de dados de teste para a [!DNL Adobe] para verificação de formato.
* Trabalhe com o consultor da [!DNL Adobe] para produzir uma taxonomia adequada para interpretar o conteúdo do arquivo de dados.
* No ambiente de armazenamento temporário/desenvolvimento, confirme se a sincronização da ID está configurada para coletar corretamente a ID do visitante do provedor de dados e transferi-la para os servidores do [!DNL Audience Manager] em tempo real.
* Implantar sincronização de DIL/ID para produção. A sincronização de ID já será configurada como um módulo dentro do código de DIL pelo consultor da Adobe.
* Transfira os arquivos de dados de produção para o [!DNL Audience Manager]. Considerando as dependências nos mapeamentos de sincronização de ID, pode fazer sentido começar a transferir dados até uma semana após a implantação do código de produção, embora seja possível começar a transferir os arquivos de dados assim que o código entrar em produção.

 

**Que modo FTP devo usar para transferir arquivos compactados ou criptografados?**

Consulte [Compactação de arquivos de transferência de dados de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

>[!WARNING]
>
>Estamos removendo gradualmente o suporte para configurações FTP. Embora a assimilação de arquivos de dados de entrada ainda seja aceita em integrações FTP existentes, recomendamos o uso do Amazon S3 para dados offline integrados para novas integrações. Consulte [Requisitos de nome e tamanho de arquivo do Amazon S3 para arquivos de dados de entrada](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) para obter detalhes.

 

**É possível carregar um arquivo de dados de entrada ([!DNL .sync] ou arquivo [!DNL .overwrite]) antes de implantar o código [!DNL Audience Manager] na produção?**

Sim. Desde que você use um [!UICONTROL cross-device data source] para armazenar os dados do CRM que você carrega, o Audience Manager sempre armazena os dados. Na verdade, após os [!UICONTROL Profile Merge Rules] aprimoramentos do Audience Manager iniciados em outubro de 2019 que permitem casos de uso somente offline, você pode fazer upload e executar ações em dados sem implantar o código do Audience Manager na produção. Consulte:

* [Visão geral das melhorias nas Regras de mesclagem de perfis](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/overview-of-profile-merge-rule-enhancements.html?lang=pt-BR)
* [!UICONTROL People-based Destinations] - [Personalization com base em dados somente offline](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/destinations/people-based/implementation-guide/people-based-destinations-workflow-offline.html?lang=pt-BR)

<br> 

<!---
* If the data provider is configured to use [Profile Link](../features/profile-merge-rules/merge-rules-overview.md) for cross-device targeting, the data available for targeting shortly after an ID sync identifies to the matching [!DNL Audience Manager] visitor ID.

* If the data provider is not configured to use the [!UICONTROL Profile Link] feature, [!DNL Audience Manager] processes only the data for visitor IDs in the inbound data file that have been previously synced/matched back to an [!DNL Audience Manager] visitor ID.

Consider the following use cases in which the data provider is not configured to use [!UICONTROL Profile Merge]:

<table id="table_1A367ED6D016428FB21B3F3BC261BA98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Case 1</b> </p> </td> 
   <td colname="col2"> <p>On Monday, a visitor identified in the CRM database as visitor ABC logs in, which initiates a client-side ID sync. <span class="keyword"> Audience Manager</span> stores the mapping of visitor ABC to <span class="keyword"> Audience Manager</span> visitor 123. </p> <p>On Tuesday, the CRM database transfers a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager </span>server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC "gender"="male","luxury_shopper"="yes"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">Recognizes visitor ABC from the stored ID sync mapping. </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Associates the traits <code> male</code> and <code> luxury_shopper</code> with the visitor 123 profile. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Case 2</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the CRM database pushes a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes"</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience Manager</span> does not have a record of this visitor (or an associated visitor ID) so this record is not processed. </p> <p>On Tuesday, visitor DEF logs in. This action initiates the first client-side ID sync for that visitor. This action maps visitor DEF to <span class="keyword"> Audience Manager</span> ID 456. However, this visitor does not have CRM data associated with their profile. As a result, <span class="keyword"> Audience Manager</span> does not go back and reprocess old files. </p> <p>On Wednesday, the CRM database pushes another data file to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes","dma"="paris"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">Recognizes visitor DEF from the stored ID sync mapping. </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Associates the traits <code> female</code>, <code> paris</code>, and <code> wine_enthusiast</code> with the visitor 456 profile. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Case 3</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the <span class="keyword"> Audience Manager</span> server receives two files with the following records: </p> <p> <code> .sync</code> file containing: </p> <p> 
     <ul class="simplelist"> 
      <li><code> GHI 123456789</code> </li> 
     </ul> </p> <p> <code> .overwrite</code> file containing: </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GHI "gender"="male" "wine_enthusiast"="no"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL "gender"="female" "wine_enthusiast"="yes"</code> </li> 
    </ul> <p><span class="keyword"> Audience Manager</span> holds a mapped record of visitor JKL to ID 789, from a previous ID sync. </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">Recognizes visitor JKL from the stored ID sync mapping. </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Associates the traits <code> female</code> and <code> wine_enthusiast</code> with visitor ID 789's profile. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">Ignores the trait association for visitor GHI, since its ID was only synced in the current batch. To associate traits with visitor GHI, you need to include them in future <code> .overwrite</code> files. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

-->

**A que horas do dia devo transferir o arquivo?**

O [!DNL Audience Manager] verifica e processa arquivos várias vezes ao longo do dia. Faça upload dos dados sempre que estiver pronto.

 

**Quanto tempo leva até que os dados de um arquivo carregado estejam disponíveis para direcionamento?**

Os dados estão disponíveis para direcionamento após 48 horas. Além disso, não interprete o email de &quot;carregamento bem-sucedido&quot; como uma declaração de que os dados estão disponíveis. Isso significa apenas que o [!DNL Audience Manager] selecionou o arquivo e concluiu a primeira etapa do processamento.

 

**Com que frequência devo enviar arquivos? Esses arquivos devem ser completos ou incrementais?**

Como prática recomendada, envie um arquivo incremental uma vez por dia para novos visitantes e para visitantes cujos dados foram alterados. Muitos clientes do [!DNL Audience Manager] enviam um arquivo completo uma vez por mês. No entanto, esses intervalos de arquivos e incrementos são flexíveis. Você deve enviar dados em incrementos e quando fizer sentido para você.

 

**Por quanto tempo o Audience Manager mantém os arquivos no servidor?**

Os arquivos FTP são removidos após serem processados. Os arquivos [!DNL S3] são removidos após 30 dias. Os arquivos que não podem ser processados devido a erros de formato, sintaxe ou outros erros são removidos. Consulte também [Perguntas frequentes sobre privacidade e retenção de dados](../faq/faq-privacy.md).

 

**Qual é a diferença entre arquivos completos e incrementais?**

* **Total:** um arquivo completo substitui todos os perfis de visitante existentes e os substitui pelos dados do arquivo. Os arquivos completos são identificados pela tag `.overwrite` anexada ao nome do arquivo. Você pode usar um arquivo `.overwrite` para redefinir características do visitante ou remover características obsoletas.

  >[!NOTE]
  >
  >Os arquivos [!DNL .overwrite] substituem apenas os dados do perfil do [!DNL Audience Manager] associados a esse provedor de dados. Em outras palavras, todos os dados do [!DNL Audience Manager] associados ao visitante permanecem intactos depois que um arquivo [!DNL .overwrite] é processado.

* **Incremental:** um arquivo incremental anexa novos dados aos perfis de visitantes existentes. Os arquivos incrementais são identificados pela tag `.sync` anexada ao nome do arquivo. Enviar um arquivo incremental não apaga nem substitui perfis existentes.

Os casos de uso a seguir demonstram como esses tipos de arquivos afetam os perfis de visitante armazenados.

| Caso de uso | Descrição |
|---|---|
| Incremental e completo | <ul><li>Conteúdo do arquivo `.sync` do dia 1: `visitor123 = a,b,c`</li><li>Conteúdo do arquivo `.overwrite` do dia 2: `visitor123 = c,d,e`</li><li>Conteúdo da ID de perfil do visitante 123 do dia 3: `c,d,e`</li></ul> |
| Apenas incremental | <ul><li>Conteúdo do arquivo `.sync` do dia 1: `visitor123 = a,b,c`</li><li>Conteúdo do arquivo `.sync` do dia 2: `visitor123 = c,d,e`</li><li>Conteúdo da ID de perfil do visitante 123 do dia 3: `a,b,c,d,e`</li></ul> |

Para obter mais informações sobre tipos de arquivos completos e incrementais, consulte:

* [Requisitos de nome e tamanho de arquivo do Amazon S3 para dados de entrada...](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**O que acontece se eu enviar um arquivo com IDs para visitantes que nunca executaram a sincronização de ID na página?**

Durante o processamento, o [!DNL Audience Manager] ignora esse registro e avança para o seguinte. Se uma [DPID (ID do provedor de dados)](../reference/ids-in-aam.md) estiver configurada como uma DPID entre dispositivos, os dados assimilados antes de uma sincronização de ID serão salvos e estarão disponíveis para uso logo após a sincronização de ID.

 

**Para que serve o carimbo de data e hora? Você pode dar um exemplo?**

Os carimbos de data e hora são usados para fazer registros e mantê-los. Eles são exigidos pela sintaxe usada para um nome de arquivo de entrada corretamente formatado. Consulte:

* [Requisitos de nome Amazon S3 para arquivos de dados de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**O que é um [!DNL Data Provider ID (DPID)] e como obtê-lo?**

O consultor da Adobe atribuirá uma [DPID (ID do provedor de dados)](../reference/ids-in-aam.md) de três ou quatro dígitos à sua fonte de dados específica. Essa ID é exclusiva e não é alterada.

 

**Que tamanho podem ter os arquivos de dados diários?**

Consulte [Compactação de arquivos de transferência de dados de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

 

**O Audience Manager oferece suporte à compactação de arquivos?**

Sim, consulte:

* [Compactação de arquivos de transferência de dados de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [Requisitos de nome Amazon S3 para arquivos de dados de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**A chave primária no meu banco de dados de fonte de dados é um endereço de email. Ele é considerado informação pessoal?**

Sim. O [!DNL Audience Manager] não armazena endereços de email no banco de dados. Os visitantes devem receber uma ID gerada aleatoriamente ou uma versão com hash unidirecional do endereço de email antes de iniciar sincronizações de ID.

 

**O conteúdo do arquivo de dados faz distinção entre maiúsculas e minúsculas? E a sincronização de ID?**

Há dois componentes básicos de um arquivo de dados: Uma [!UICONTROL User ID] (consulte [!UICONTROL User ID] em [Variáveis de arquivo definidas](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined)) e dados de perfil, geralmente na forma de pares de valores-chave ou códigos. O [!UICONTROL User ID] diferencia maiúsculas e minúsculas. Geralmente, os dados de perfil ou valor-chave não fazem distinção entre maiúsculas e minúsculas.

 

**Devo usar o FTP ou o [!DNL Amazon S3] para transferir arquivos?**

Como prática recomendada, recomendamos o [!DNL Amazon S3] porque o processo é mais simples. O [!DNL Audience Manager] transfere arquivos FTP para o [!DNL S3] independentemente, de modo que o processo é mais simples se você soltar os arquivos no próprio [!DNL Amazon S3]. Além disso, os clientes que fazem upload simultaneamente para FTP compartilham a largura de banda do FTP, portanto as velocidades de upload são mais lentas. O [!DNL Amazon S3] também é replicado e distribuído, portanto, geralmente é mais seguro e confiável do que um servidor FTP. Para obter mais informações, consulte [Sobre o Amazon S3](../reference/amazon-s3.md).

>[!WARNING]
>
>Estamos removendo gradualmente o suporte para configurações FTP. Embora a assimilação de arquivos de dados de entrada ainda seja suportada em integrações FTP existentes, recomendamos o uso do [!DNL Amazon S3] para dados offline integrados para novas integrações. Consulte [Requisitos de nome e tamanho de arquivo do Amazon S3 para arquivos de dados de entrada](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) para obter detalhes.

 

**Como o Audience Manager processa arquivos de entrada?**

O [!DNL Audience Manager] usa o [!DNL Amazon Simple Queue Service (SQS)] para processar dados de entrada. Veja como isso funciona:

1. Os clientes do [!DNL Audience Manager] fazem o upload de dados de entrada em um bucket do [!DNL Amazon S3].
1. Os dados entram na fila do [!DNL Amazon SQS], aguardando para serem processados pelo [!DNL Audience Manager].
1. O [!DNL Audience Manager] lê até 119.000 entradas da fila do [!DNL Amazon SQS] e as divide em até 3 lotes. Os arquivos em cada lote são processados simultaneamente.

 

**Preciso carregar vários arquivos ao mesmo tempo.. Os arquivos serão processados simultaneamente?**

Depende. O [!DNL Audience Manager] lê até 119.000 entradas da fila do [!DNL Amazon SQS] e as divide em até 3 lotes. Os arquivos serão processados simultaneamente somente se eles terminarem no mesmo lote. No entanto, devido à grande quantidade de dados assimilados pelo [!DNL Audience Manager] diariamente, não podemos garantir nenhuma ordem de processamento de arquivos.

>[!MORELIKETHIS]
>
>* [Descrição do processo de transferência de dados em lote](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)
