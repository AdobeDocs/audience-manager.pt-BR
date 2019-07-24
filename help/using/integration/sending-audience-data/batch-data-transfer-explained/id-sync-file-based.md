---
description: Descreve os campos obrigatórios, as convenções de sintaxe e nomenclatura usadas para sincronização de ID baseada em arquivo. Nomeie e organize o conteúdo de seu arquivo de acordo com essas especificações.
seo-description: Descreve os campos obrigatórios, as convenções de sintaxe e nomenclatura usadas para sincronização de ID baseada em arquivo. Nomeie e organize o conteúdo de seu arquivo de acordo com essas especificações.
seo-title: Requisitos de nome e conteúdo para arquivos de sincronização de ID
solution: Audience Manager
title: Requisitos de nome e conteúdo para arquivos de sincronização de ID
uuid: bfe 42 af 9-9149-4 da 3-830 e-f 227 c 4 e 610 c 2
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# Requisitos de nome e conteúdo para arquivos de sincronização de ID {#name-and-content-requirements-for-id-synchronization-files}

Descreve os campos obrigatórios, as convenções de sintaxe e nomenclatura usadas para sincronização de ID baseada em arquivo. Nomeie e organize o conteúdo de seu arquivo de acordo com essas especificações.

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *itálico*, colchetes `[ ]` `( )` etc.) neste documento indica elementos e opções do código. Consulte [Convenções de estilo para código e elementos de texto](../../../reference/code-style-elements.md) para obter mais informações.

## File Name Syntax and Examples {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

Os nomes de arquivo de ID contêm os seguintes elementos obrigatórios e opcionais:

`adobe_id_`*`MASTERDPID_DPID[_DPID_DPID`*`]_`*`TIMESTAMP`*`.sync[.`*`SPLIT_NUMBER`*`][.gz]`

<table id="table_727A465D7C38419CA0750EF32DEDA2FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> adobe_ id</code> </p> </td> 
   <td colname="col2"> <p>Um prefixo estático que identifica o arquivo como um arquivo de ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> A ID do provedor de dados mestre é a ID principal dos dpids no nome do arquivo. Além disso, a primeira ID de usuário no arquivo de dados corresponde à ID mestre. Os dpids subsequentes são outros identificadores que pertencem à mestre. A sincronização mapeia dpids no nome do arquivo para uuids no arquivo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>IDs do provedor de dados. Essas IDs representam entidades ou fontes de dados associadas à DPID mestre. A sincronização mapeia dpids no nome do arquivo para uuids no arquivo. </p> <p>O número de dpids no nome do arquivo deve corresponder ao número de uuids no arquivo de dados. Por exemplo, digamos que o nome do arquivo contenha uma DPID mestre e 3 dpids. Seu arquivo de dados deve incluir 4 colunas correspondentes de uuids, formatadas conforme descrito na seção do conteúdo do arquivo abaixo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>Um carimbo de data e hora de 10 dígitos, UNIX, em segundos. O carimbo de data e hora ajuda a tornar cada nome de arquivo exclusivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> . sync</code> </p> </td> 
   <td colname="col2"> <p>Indica uma sincronização normal e completa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>. SPLIT_ NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Um número inteiro. Usado quando você divide arquivos grandes em vários arquivos menores. Isso ajuda a melhorar os tempos de processamento. O número indica qual parte do arquivo original está sendo enviado. Consulte os exemplos de nome do arquivo abaixo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Especifica que o arquivo é compactado com compactação gzip opcional. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exemplos de nome de arquivo

Os exemplos a seguir mostram nomes de arquivos formatados corretamente. Seus nomes de arquivo podem ser semelhantes.

<ul class="simplelist"> 
 <li> <code> adobe_ id_ 111_ 222_ 333_ 444_ 1454442149. sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
</ul>

## File Content Syntax and Examples {#file-content-syntax}

O conteúdo de um arquivo de ID inclui os seguintes elementos:

*`UUID`* `<tab>`*`UUID`* `<tab>`*`UUID`*`<tab>` *`UUID`*

The file contains user IDs ([!DNL UUID]). Em cada linha, separe as IDs com uma guia. O exemplo a seguir mostra um arquivo de ID formatado corretamente. Seu conteúdo pode parecer parecido.

```
abc123 def456 ghi789 xyz987
```

## Synchronization Matches DPUUIDs to UUIDs {#sync-matches-dpuuids-uuids}

The purpose of an ID sync file is to sync the [DPUUIDs](../../../reference/ids-in-aam.md) from your own Data Sources with [!DNL Audience Manager] UUIDs. Synchronization maps the [!DNL DPUUID]s from the master [!DNL DPID] and its related [!DNL DPID]s to the [!DNL Audience Manager] [!DNL UUID]s. Where you put the IDs in the file name and body determines how these identifiers are mapped to each other. Por exemplo, use os dois arquivos de amostra mostrados aqui:

* **Arquivo 1:**`adobe_id_0_12345_1476312152.sync`

* **Arquivo 2:**`adobe_id_12345_67890_1476312876.sync`

<br/>

Com o nome e o conteúdo da amostra, o mapa IDs é mapeado como este:

**Arquivo 1** ( [Arquivo de exemplo de download](assets/adobe_id_0_12345_1476312152.sync))

| DPID 0 = uuids do Adobe Audience Manager | DPID 12345 |
|---|---|
| 68079982765673198504052656074456196039 | XYZ 3017 D_ 2 kzktoxkfyiagwbajoqwrcqkxl-ttrj 6 E 4 njamr 38 |
| 67412682083411995725538770443620307584 | XYZ 3017 BBR 4 dafjwfm 6 D 4 Gb 4 ln_ T 5 jk_ f 7 rdecqns 9 wfna 7 h 70 |
| 89159024796760343733111707646026765593 | XYZ 3017 prypid 8 tzfhkee-GE 034 LI -53 Jde 0 utcyciwd 0 A 2 olm |
| 66552757407517449462805881945288602094 | XYZ 3017 qvbddd-bljs 28 dpxiqufmibxe 3_ 55 bcolhjmlwu 2 M |
| 66184778222667870903738139438735041506 | XYZ 3017 q 9 r 60 kuhpoca_ Ek-btcn 2 iu 1 hyvaue 0 rd 412 tzbycmw |

Step 1: the ID sync process will sync the [!DNL DPUUID]s from [!DNL DPID] 12345 with the [!DNL Audience Manager] [!DNL UUID]s in the left column. Note that the [!DNL DPID] "0" in the file name represents [!DNL Audience Manager] [!DNL UUID]s.
<br/>

**Arquivo 2** ( [Arquivo de exemplo de download](assets/adobe_id_12345_67890_1477846458.sync))

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ 3017 D_ 2 kzktoxkfyiagwbajoqwrcqkxl-ttrj 6 E 4 njamr 38 | 4598060374 |
| XYZ 3017 BBR 4 dafjwfm 6 D 4 Gb 4 ln_ T 5 jk_ f 7 rdecqns 9 wfna 7 h 70 | 4581274262 |
| XYZ 3017 prypid 8 tzfhkee-GE 034 LI -53 Jde 0 utcyciwd 0 A 2 olm | 4392434426 |
| XYZ 3017 qvbddd-bljs 28 dpxiqufmibxe 3_ 55 bcolhjmlwu 2 M | 2351382994 |
| XYZ 3017 q 9 r 60 kuhpoca_ Ek-btcn 2 iu 1 hyvaue 0 rd 412 tzbycmw | 4601584763 |

Step 2: the [!DNL DPUUID]s from [!DNL DPID] 12345 have been synced in step 1 with the Audience Manager [!DNL UUID]s. What this ID sync will do is sync the [!DNL DPUUID]s from [!DNL DPID] 67890 with the Audience Manager [!DNL UUID]s from step 1.

<br/>

## Other Format Requirements {#other-format-reqs}

As IDs de usuário não podem:

* Tenha guias na própria ID. As guias são usadas apenas para separar IDs individuais no arquivo de dados.
* Contain personally identifiable information ([!UICONTROL PII]).
* Use [!DNL URL] encoding. Enviar apenas para IDs não codificadas.

Todas as linhas que terminam com guias ou espaços não serão processadas ou observadas. Como regra, certifique-se de manter o fim das linhas claras.