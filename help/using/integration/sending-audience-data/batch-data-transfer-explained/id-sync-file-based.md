---
description: Describes the required fields, syntax, and naming conventions used for file-based ID synchronization. Nomeie e organize o conteúdo do arquivo de acordo com essas especificações.
seo-description: Describes the required fields, syntax, and naming conventions used for file-based ID synchronization. Name and organize your file contents according to these specifications.
seo-title: Requisitos de nome e conteúdo para arquivos de sincronização de ID
solution: Audience Manager
title: Requisitos de nome e conteúdo para arquivos de sincronização de ID
uuid: bfe42af9-9149-4da3-830e-f227c4e610c2
translation-type: tm+mt
source-git-commit: 4bc3d7c0a34619e556f58b39b7812a5612050f7f

---


# Requisitos de nome e conteúdo para arquivos de sincronização de ID {#name-and-content-requirements-for-id-synchronization-files}

Describes the required fields, syntax, and naming conventions used for file-based ID synchronization. Name and organize your file contents according to these specifications.

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *itálico*, colchetes `[ ]` `( )` etc.) in this document indicate code elements and options. Consulte [Convenções de estilo para código e elementos de texto](../../../reference/code-style-elements.md) para obter mais informações.

## File Name Syntax and Examples {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

ID file names contain the following required and optional elements:

*`[adobe_id_]`* _DPID_DPID.gz *`[c2c_id_]`*`MASTERDPID_DPID`*[]*`_TIMESTAMP.sync`*`[.SPLIT_NUMBER]`*[]

<table id="table_727A465D7C38419CA0750EF32DEDA2FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> adobe_id</code> </p> </td> 
   <td colname="col2"> <p>A static prefix that identifies the file as an ID synchronization file. Use this prefix when matching device IDs to other device IDs or customer IDs (DPUUIDs).  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> c2c_id</code> </p> </td> 
   <td colname="col2"> <p>A static prefix that identifies the file as an ID synchronization file for People-Based Destinations. Use this prefix when matching customer IDs (DPUUIDs) to hashed email addresses for People-Based Destinations.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> A ID do provedor de dados mestre é a ID pai dos DPIDs no nome do arquivo. Além disso, a primeira ID de usuário no arquivo de dados corresponde à ID mestre. Os DPIDs subsequentes são outros identificadores que pertencem ao mestre. A sincronização mapeia DPIDs no nome do arquivo para UUIDs no arquivo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>IDs do provedor de dados. Essas IDs representam entidades ou fontes de dados associadas ao DPID mestre. A sincronização mapeia DPIDs no nome do arquivo para UUIDs no arquivo. </p> <p>O número de DPIDs no nome do arquivo deve corresponder ao número de UUIDs no arquivo de dados. Por exemplo, digamos que seu nome de arquivo contenha um DPID mestre e 3 DPIDs. Seu arquivo de dados deve incluir 4 colunas correspondentes de UUIDs, formatadas conforme descrito na seção de conteúdo do arquivo abaixo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>Um carimbo de data e hora UNIX de 10 dígitos em segundos. O carimbo de data e hora ajuda a tornar cada nome de arquivo único. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .sync</code> </p> </td> 
   <td colname="col2"> <p>Indica uma sincronização normal e completa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>.SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Um número inteiro. Usado ao dividir arquivos grandes em vários arquivos menores. Isso ajuda a melhorar os tempos de processamento. O número indica qual parte do arquivo original você está enviando. Consulte os exemplos de nome de arquivo abaixo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Especifica que seu arquivo é compactado com compactação gzip opcional. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exemplos de nome de arquivo

Os exemplos a seguir mostram nomes de arquivos formatados corretamente. Seus nomes de arquivo podem ser semelhantes.

<ul class="simplelist"> 
 <li> <code> adobe_id_111_222_333_444_1454442149.sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
 <li> <code>c2c_id_123_898_1454442149.sync.gz</code> </li> 
</ul>

>[!NOTE]
> For ID synchronization file naming (c2c prefix) for People-Based Destinations, see Workflow A - Personalization Based on All Online Activity Combined with Offline Data or Workflow B - Personalization Based on Offline-Only Data.[](../../../features/destinations/people-based-destinations-workflow-combined.md)[](../../../features/destinations/people-based-destinations-workflow-offline.md)

## Sintaxe de conteúdo de arquivo e exemplos {#file-content-syntax}

The contents of an ID file include the following elements:

*`UUID`* `<tab>`*`UUID`* `<tab>`*`UUID`*`<tab>` *`UUID`*

The file contains user IDs (). [!DNL UUID] In each row, separate the IDs with a tab. The following example shows a properly formatted ID file. Your contents could look similar.

```
abc123 def456 ghi789 xyz987
```

## Synchronization Matches DPUUIDs to UUIDs {#sync-matches-dpuuids-uuids}

The purpose of an ID sync file is to sync the DPUUIDs from your own Data Sources with  UUIDs. [](../../../reference/ids-in-aam.md)[!DNL Audience Manager] Synchronization maps the s from the master  and its related s to the  s. Where you put the IDs in the file name and body determines how these identifiers are mapped to each other. [!DNL DPUUID][!DNL DPID][!DNL DPID][!DNL Audience Manager][!DNL UUID] Por exemplo, pegue os dois arquivos de amostra mostrados aqui:

* **** Arquivo 1: `adobe_id_0_12345_1476312152.sync`

* **** Arquivo 2:  `adobe_id_12345_67890_1476312876.sync`

<br/>

Given the sample name and contents, the IDs map together like this:

**File 1 ( Download sample file)**[](assets/adobe_id_0_12345_1476312152.sync)

| DPID 0 = Adobe Audience Manager UUIDs | DPID 12345 |
|---|---|
| 68079982765673198504052656074456196039 | XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-Trj6E4njaMR.38 |
| 67412682083411995725538770443620307584 | XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 |
| 89159024796760343733111707646026765593 | XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM |
| 66552757407517449462805881945288602094 | XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M |
| 66184778222667870903738139438735041506 | XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw |

Etapa 1: o processo de sincronização de ID sincronizará os [!DNL DPUUID]s de [!DNL DPID] 12345 com os [!DNL Audience Manager] s na coluna [!DNL UUID]esquerda. Observe que o [!DNL DPID] "0" no nome do arquivo representa [!DNL Audience Manager] [!DNL UUID]s.
<br/>

**Arquivo 2** ( [Baixar arquivo](assets/adobe_id_12345_67890_1477846458.sync)de amostra)

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-Trj6E4njaMR.38 | 4598060374 |
| XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 | 4581274262 |
| XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM | 4392434426 |
| XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M | 2351382994 |
| XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw | 4601584763 |

Etapa 2: os [!DNL DPUUID]s do [!DNL DPID] 12345 foram sincronizados na etapa 1 com os Audience Manager [!DNL UUID]s. O que essa sincronização de ID fará é sincronizar os [!DNL DPUUID]s de [!DNL DPID] 67890 com os Audience Manager [!DNL UUID]s da etapa 1.

<br/>

## Outros requisitos de formato {#other-format-reqs}

As IDs de usuário não podem:

* Tem guias na própria ID. As guias são usadas somente para separar IDs individuais no arquivo de dados.
* Contém informações de identificação pessoal ([!UICONTROL PII]).
* Use a [!DNL URL] codificação. Passe somente IDs não codificadas.

Quaisquer linhas que terminem com tabulações ou espaços não serão processadas ou realizadas. Como regra, mantenha o final das linhas limpo.