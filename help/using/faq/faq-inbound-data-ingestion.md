---
description: Perguntas frequentes sobre como trazer dados offline para o Gerenciador de Audiências.
keywords: ftp or s3;s3 or ftp
seo-description: Perguntas frequentes sobre como trazer dados offline para o Gerenciador de Audiências.
seo-title: Perguntas frequentes sobre ingestão de dados do cliente de entrada
solution: Audience Manager
title: Perguntas frequentes sobre ingestão de dados do cliente de entrada
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
translation-type: tm+mt
source-git-commit: 187874fb5d0c4363f771297766f3c4bc9d967c9b

---


# Perguntas frequentes sobre ingestão de dados do cliente de entrada{#inbound-customer-data-ingestion-faq}

Perguntas frequentes sobre como trazer dados offline para o Gerenciador de Audiências.

 

**Você pode resumir o processo de integração?**

O processo de integração consiste em duas etapas descritas em [Enviar dados em lote para a visão geral](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)do Audiência Manager:

* Etapa 1: sincronizar IDs de usuário;
* Etapa 2: crie e transfira seu arquivo de dados de entrada, seguindo os requisitos de formato de arquivo.

 

**Você pode resumir o processo de implantação?**

Recomendamos o seguinte:

* Trabalhe com seu provedor de dados para formatar o arquivo de dados de entrada diário de acordo com as especificações da Adobe. Consulte a documentação a seguir para conhecer os requisitos de sintaxe e nome de arquivo:
   * [Requisitos de nome e conteúdo para arquivos de sincronização de ID](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)
   * [Conteúdo do arquivo de dados de entrada: Sintaxe, caracteres inválidos, variáveis e exemplos](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)
   * [Requisitos de nome e tamanho de arquivo do Amazon S3 para arquivos de dados de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* Trabalhe com seu [!DNL Adobe] consultor para transferir um arquivo de dados de teste para [!DNL Adobe] a verificação de formato.
* Trabalhe com seu [!DNL Adobe] consultor para produzir uma taxonomia adequada para interpretar o conteúdo do arquivo de dados.
* No ambiente de armazenamento temporário/desenvolvimento, confirme se a sincronização da ID está configurada para coletar corretamente a ID do visitante do provedor de dados e transferi-la para os [!DNL Audience Manager] servidores em tempo real.
* Implantar sincronização DIL/ID para produção. A sincronização de ID já será configurada como um módulo dentro do código DIL pelo seu consultor da Adobe.
* Transfira os arquivos de dados de produção para [!DNL Audience Manager]. Considerando as dependências nos mapeamentos de sincronização de ID, pode fazer sentido começar a transferir dados até uma semana após a implantação do código de produção, embora seja possível transferir os arquivos de dados em start assim que o código entrar em produção.

 

**Que modo FTP devo usar para transferir arquivos compactados ou criptografados?**

Consulte Compactação de [arquivos para arquivos](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)de transferência de dados de entrada.

>[!WARNING]
>
>Estamos gradualmente removendo o suporte para configurações FTP. Embora a ingestão de arquivos de dados de entrada ainda seja suportada em integrações FTP existentes, recomendamos usar o Amazon S3 para dados offline integrados para novas integrações. Consulte Requisitos de nome e tamanho de arquivo do [Amazon S3 para arquivos](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) de dados de entrada para obter detalhes.

 

**É possível carregar um arquivo de dados de entrada ([!DNL .sync] ou arquivo [!DNL .overwrite]) antes de implantar o código [!DNL Audience Manager] na produção?**

Sim. Desde que você use uma fonte de dados entre dispositivos para armazenar os dados do CRM que você carrega, o Audiência Manager sempre armazena os dados. Na verdade, após os aprimoramentos das Regras de mesclagem de Perfis que o Audiência Manager lançou em outubro de 2019 e que permitem casos de uso somente offline, você pode fazer upload e executar ações em dados sem implantar o código do Audiência Manager na produção. Consulte:

* [Visão geral das melhorias nas regras de mesclagem de Perfis](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/overview-of-profile-merge-rule-enhancements.html)
* Destinos baseados em pessoas - [Personalização baseada em dados somente offline](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/destinations/people-based/implementation-guide/people-based-destinations-workflow-offline.html)

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

**A que horas do dia devo transferir meu arquivo?**

[!DNL Audience Manager] verifica e processa arquivos várias vezes ao longo do dia. Carregue seus dados sempre que estiver pronto.

 

**Quanto tempo leva até que os dados de um arquivo carregado estejam disponíveis para definição de metas?**

Os dados estão disponíveis para definição de metas após 48 horas. Além disso, não interprete o email de &quot;carregamento bem-sucedido&quot; como uma declaração de que os dados estão disponíveis. Isso significa apenas que [!DNL Audience Manager] o selecionou o arquivo e concluiu a primeira etapa do processamento.

 

**Com que frequência devo enviar arquivos e esses arquivos devem ser completos ou incrementais?**

Como prática recomendada, envie um arquivo incremental uma vez por dia para novos visitantes e para visitantes cujos dados foram alterados. Muitos [!DNL Audience Manager] clientes enviam um arquivo completo uma vez por mês. No entanto, esses intervalos de arquivos e incrementos são flexíveis. Você deve enviar dados em incrementos e às vezes que fizerem sentido para você.

 

**Por quanto tempo o Audiência Manager mantém meus arquivos no servidor?**

Os arquivos FTP são removidos após serem processados. [!DNL S3] os arquivos são removidos após 30 dias. Os arquivos que não podem ser processados devido a erros de formato, sintaxe ou outros erros são removidos. Consulte também Perguntas frequentes sobre [privacidade e retenção de dados](../faq/faq-privacy.md).

 

**Qual é a diferença entre arquivos completos e incrementais?**

* **Total:** Um arquivo completo substitui todos os perfis de visitante existentes e os substitui pelos dados do arquivo. Os arquivos completos são identificados pela `.overwrite` tag anexada ao nome do arquivo. Você pode usar um `.overwrite` arquivo para redefinir características do visitante ou remover características obsoletas e obsoletas.

   >[!NOTE]
   >
   >Os [!DNL .overwrite] arquivos substituem apenas os dados do [!DNL Audience Manager] perfil associados a esse provedor de dados. Em outras palavras, todos os [!DNL Adobe Analytics] dados associados ao visitante permanecem intactos depois que um [!DNL .overwrite] arquivo é processado.

* **Incremental:** Um arquivo incremental anexa novos dados aos perfis de visitantes existentes. Os arquivos incrementais são identificados pela `.sync` tag anexada ao nome do arquivo. Enviar um arquivo incremental não apaga nem substitui perfis existentes.

Os casos de uso a seguir demonstram como esses tipos de arquivos afetam os perfis de visitante armazenados.

| Caso de uso | Descrição |
|---|---|
| Incremental e Completo | <ul><li>Conteúdo `.sync` do arquivo do dia 1: `visitor123 = a,b,c`</li><li>Conteúdo `.overwrite` do arquivo no dia 2: `visitor123 = c,d,e`</li><li>Conteúdo da ID de perfil do dia 3: `c,d,e`</li></ul> |
| Apenas Incremental | <ul><li>Conteúdo `.sync` do arquivo do dia 1: `visitor123 = a,b,c`</li><li>Conteúdo `.sync` do arquivo no dia 2: `visitor123 = c,d,e`</li><li>Conteúdo da ID de perfil do dia 3: `a,b,c,d,e`</li></ul> |

Para obter mais informações sobre tipos de arquivos completos e incrementais, consulte:

* [Requisitos de nome e tamanho de arquivo do Amazon S3 para dados de entrada...](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**O que acontece se eu enviar um arquivo com IDs para visitantes que nunca executaram a sincronização de ID na página?**

Durante o processamento, [!DNL Audience Manager] ignora esse registro e avança para o seguinte. Se um [DPID (ID do provedor de dados)](../reference/ids-in-aam.md) estiver configurado como um DPID entre dispositivos, os dados ingeridos antes de uma sincronização de ID serão salvos e estarão disponíveis para uso logo após a sincronização de ID ocorrer.

 

**Para que serve o carimbo de data e hora e pode dar um exemplo?**

Os carimbos de data e hora são usados para registro e manutenção de registros. Elas são exigidas pela sintaxe usada para um nome de arquivo de entrada corretamente formatado. Consulte:

* [Requisitos de nome Amazon S3 para arquivos de dados de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**O que é uma ID de provedor de dados (DPID) e como faço para obtê-la?**

Seu consultor da Adobe atribuirá um [DPID de três ou quatro dígitos (ID do provedor de dados)](../reference/ids-in-aam.md) à sua fonte de dados específica. Essa ID é exclusiva e não é alterada.

 

**Qual pode ser o tamanho dos arquivos de dados diários?**

Consulte Compactação de [arquivos para arquivos](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)de transferência de dados de entrada.

 

**O Gerenciador de Audiências oferece suporte à compactação de arquivos?**

Sim, consulte o:

* [Compactação de arquivos para arquivos de transferência de dados de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [Requisitos de nome Amazon S3 para arquivos de dados de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**A chave primária no meu banco de dados de fonte de dados é um endereço de email. Isso é considerado informação pessoal?**

Sim. [!DNL Audience Manager] não armazena endereços de email em seu banco de dados. Os Visitantes devem receber uma ID gerada aleatoriamente ou uma versão com hash unidirecional do endereço de email antes de iniciar sincronizações de ID.

 

**O conteúdo do arquivo de dados faz distinção entre maiúsculas e minúsculas? Que tal a sincronização de ID?**

Há dois componentes básicos de um arquivo de dados: Um [!UICONTROL User ID] (consulte [!UICONTROL User ID] Variáveis de [arquivo definidas](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined)) e dados de perfil, geralmente na forma de pares de valores chave ou códigos. O [!UICONTROL User ID] é sensível a maiúsculas e minúsculas. Geralmente, os dados de perfil ou valor chave não fazem distinção entre maiúsculas e minúsculas.

 

**Devo usar o FTP ou[!DNL Amazon S3]transferir arquivos?**

Como prática recomendada, recomendamos [!DNL Amazon S3] porque o processo é mais simples. [!DNL Audience Manager] transfere arquivos FTP para [!DNL S3] qualquer instância, de modo que o processo é mais simplificado se você soltar os arquivos em [!DNL Amazon S3] si mesmo. Além disso, os clientes que fazem upload simultaneamente para FTP compartilham a largura de banda do FTP, para que esperem velocidades de upload mais lentas. [!DNL Amazon S3] também é replicado e distribuído, portanto, geralmente é mais seguro e confiável do que um servidor FTP. Para obter mais informações, consulte [Sobre o Amazon S3](../reference/amazon-s3.md).

>[!WARNING]
>
>Estamos gradualmente removendo o suporte para configurações FTP. Embora a ingestão de arquivos de dados de entrada ainda seja suportada em integrações FTP existentes, recomendamos usar o Amazon S3 para dados offline integrados para novas integrações. Consulte Requisitos de nome e tamanho de arquivo do [Amazon S3 para arquivos](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) de dados de entrada para obter detalhes.

 

**Como o Audiência Manager processa arquivos de entrada?**

[!DNL Audience Manager] usa [!DNL Amazon Simple Queue Service (SQS)] o processamento de dados de entrada. Veja como isso funciona:

1. [!DNL Audience Manager] os clientes carregam seus dados de entrada em um [!DNL Amazon S3] bucket.
1. Os dados entram na [!DNL Amazon SQS] fila, aguardando para serem processados por [!DNL Audience Manager].
1. [!DNL Audience Manager] lê até 119.000 entradas da [!DNL Amazon SQS] fila e as divide em até 3 lotes. Os arquivos em cada lote são processados simultaneamente.

 

**Preciso carregar vários arquivos ao mesmo tempo. Os arquivos serão processados simultaneamente?**

Depende. [!DNL Audience Manager] lê até 119.000 entradas da [!DNL Amazon SQS] fila e as divide em até 3 lotes. Seus arquivos serão processados simultaneamente somente se eles terminarem no mesmo lote. No entanto, devido à grande quantidade de dados ingeridos [!DNL Audience Manager] diariamente, não podemos garantir nenhuma ordem de processamento de arquivos.

>[!MORELIKETHIS]
>
>* [Processo de transferência de dados em lote descrito](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)

