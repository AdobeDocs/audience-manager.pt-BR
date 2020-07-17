---
description: Descreve os campos obrigatórios, a sintaxe e as convenções de nomenclatura usadas para sincronização de ID com base em arquivo. Nomeie e organize o conteúdo do arquivo de acordo com essas especificações.
seo-description: Descreve os campos obrigatórios, a sintaxe e as convenções de nomenclatura usadas para a sincronização de ID baseada em arquivo. Nomeie e organize o conteúdo do arquivo de acordo com essas especificações.
seo-title: Requisitos de nome e conteúdo para arquivos de sincronização de ID
solution: Audience Manager
title: Requisitos de nome e conteúdo para arquivos de sincronização de ID
uuid: bfe42af9-9149-4da3-830e-f227c4e610c2
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 7%

---


# Requisitos de nome e conteúdo para arquivos de sincronização de ID {#name-and-content-requirements-for-id-synchronization-files}

Descreve os campos obrigatórios, a sintaxe e as convenções de nomenclatura usadas para sincronização de ID com base em arquivo. Nomeie e organize o conteúdo do arquivo de acordo com essas especificações.

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *itálico*, colchetes `[ ]` `( )` etc.) neste documento, indique os elementos de código e as opções. Consulte [Convenções de estilo para código e elementos de texto](../../../reference/code-style-elements.md) para obter mais informações.

## Sintaxe de nome de arquivo e exemplos {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

Os nomes de arquivo de ID contêm os seguintes elementos obrigatórios e opcionais:

*`[adobe_id_]`* *`[c2c_id_]`*`MASTERDPID_DPID`*`[_DPID]`*`_TIMESTAMP.sync`*`[.SPLIT_NUMBER]`*`[.gz]`

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
   <td colname="col2"> <p>Um prefixo estático que identifica o arquivo como um arquivo de sincronização de ID. Use esse prefixo ao corresponder IDs de dispositivo a outras IDs de dispositivo ou IDs de cliente (DPUUIDs).  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> c2c_id</code> </p> </td> 
   <td colname="col2"> <p>Um prefixo estático que identifica o arquivo como um arquivo de sincronização de ID para Destinos Baseados em Pessoas. Use esse prefixo ao corresponder IDs de cliente (DPUUIDs) a endereços de email com hash para Destinos baseados em pessoas.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> A ID principal do provedor de dados é a ID pai dos DPIDs no nome do arquivo. Além disso, a primeira ID de usuário no arquivo de dados corresponde à ID principal. Os DPIDs subsequentes são outros identificadores que pertencem ao principal. A sincronização mapeia DPIDs no nome do arquivo para UUIDs no arquivo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>IDs do provedor de dados. Essas IDs representam entidades ou fontes de dados associadas ao DPID principal. A sincronização mapeia DPIDs no nome do arquivo para UUIDs no arquivo. </p> <p>O número de DPIDs no nome do arquivo deve corresponder ao número de UUIDs no arquivo de dados. Por exemplo, digamos que seu nome de arquivo contenha um DPID principal e 3 DPIDs. Seu arquivo de dados deve incluir 4 colunas correspondentes de UUIDs, formatadas conforme descrito na seção de conteúdo do arquivo abaixo. </p> </td> 
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
> Para a nomeação de arquivos de sincronização de ID (prefixo c2c) para Destinos baseados em pessoas, consulte [Fluxo de trabalho A - Personalização baseada em toda a Atividade online combinada com dados](../../../features/destinations/people-based-destinations-workflow-combined.md) offline ou [fluxo de trabalho B - Personalização baseada em dados](../../../features/destinations/people-based-destinations-workflow-offline.md)somente offline.

## Sintaxe de conteúdo de arquivo e exemplos {#file-content-syntax}

O conteúdo de um arquivo de ID inclui os seguintes elementos:

*`UUID`* `<tab>`*`UUID`* `<tab>`*`UUID`*`<tab>` *`UUID`*

O arquivo contém IDs de usuário ([!DNL UUID]). Em cada linha, separe as IDs com uma guia. O exemplo a seguir mostra um arquivo de ID formatado corretamente. Seu conteúdo pode parecer semelhante.

```
abc123 def456 ghi789 xyz987
```

## A sincronização corresponde DPUUIDs a UUIDs {#sync-matches-dpuuids-uuids}

A finalidade de um arquivo de sincronização de ID é sincronizar os [DPUUIDs](../../../reference/ids-in-aam.md) de suas próprias Fontes de Dados com [!DNL Audience Manager] UUIDs. A sincronização mapeia os [!DNL DPUUID]s do principal [!DNL DPID] e seus relacionados [!DNL DPID]aos [!DNL Audience Manager] [!DNL UUID]s. Quando você coloca as IDs no nome e no corpo do arquivo, determina como esses identificadores são mapeados entre si. Por exemplo, pegue os dois arquivos de amostra mostrados aqui:

* **Arquivo 1:** `adobe_id_0_12345_1476312152.sync`

* **Arquivo 2:**  `adobe_id_12345_67890_1476312876.sync`

<br/>

Dado o nome e o conteúdo da amostra, as IDs são mapeadas juntas desta forma:

**Arquivo 1** ( [Baixar arquivo](assets/adobe_id_0_12345_1476312152.sync)de amostra)

| DPID 0 = Adobe Audience Manager UIDs | DPID 12345 |
|---|---|
| 68079982765673198504052656074456196039 | XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-Trj6E4njaMR.38 |
| 67412682083411995725538770443620307584 | XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 |
| 89159024796760343733111707646026765593 | XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM |
| 66552757407517449462805881945288602094 | XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M |
| 66184778222667870903738139438735041506 | XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw |

Etapa 1: o processo de sincronização de ID sincronizará os [!DNL DPUUID]s de [!DNL DPID] 12345 com os [!DNL Audience Manager] s na coluna [!DNL UUID]esquerda. Observe que o [!DNL DPID] &quot;0&quot; no nome do arquivo representa [!DNL Audience Manager] [!DNL UUID]s.
<br/>

**Arquivo 2** ( [Baixar arquivo](assets/adobe_id_12345_67890_1477846458.sync)de amostra)

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-Trj6E4njaMR.38 | 4598060374 |
| XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 | 4581274262 |
| XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM | 4392434426 |
| XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M | 2351382994 |
| XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw | 4601584763 |

Etapa 2: os [!DNL DPUUID]s de [!DNL DPID] 12345 foram sincronizados na etapa 1 com os Audience Manager [!DNL UUID]s. O que essa sincronização de ID fará é sincronizar os [!DNL DPUUID]s de [!DNL DPID] 67890 com os Audience Manager [!DNL UUID]da etapa 1.

<br/>

## Outros requisitos de formato {#other-format-reqs}

As IDs de usuário não podem:

* Tem guias na própria ID. As guias são usadas somente para separar IDs individuais no arquivo de dados.
* Contém informações de identificação pessoal ([!UICONTROL PII]).
* Use a [!DNL URL] codificação. Passe somente IDs não codificadas.

Quaisquer linhas que terminem com tabulações ou espaços não serão processadas ou realizadas. Como regra, mantenha o final das linhas limpo.