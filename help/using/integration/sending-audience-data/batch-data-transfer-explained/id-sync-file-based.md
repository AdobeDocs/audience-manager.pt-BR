---
description: Descreve os campos obrigatórios, a sintaxe e as convenções de nomenclatura usadas para a sincronização de ID com base em arquivo. Nomeie e organize o conteúdo do arquivo de acordo com essas especificações.
seo-description: Descreve os campos obrigatórios, a sintaxe e as convenções de nomenclatura usadas para a sincronização de ID com base em arquivo. Nomeie e organize o conteúdo do arquivo de acordo com essas especificações.
seo-title: Requisitos de nome e conteúdo para arquivos de sincronização de ID
solution: Audience Manager
title: Requisitos de nome e conteúdo para arquivos de sincronização de ID
uuid: bfe42af9-9149-4da3-830e-f227c4e610c2
feature: Transferência de dados de entrada
exl-id: e6b3a438-f843-4a24-89fd-03ef77d7cf04
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 6%

---

# Requisitos de nome e conteúdo para arquivos de sincronização de ID {#name-and-content-requirements-for-id-synchronization-files}

Descreve os campos obrigatórios, a sintaxe e as convenções de nomenclatura usadas para a sincronização de ID com base em arquivo. Nomeie e organize o conteúdo do arquivo de acordo com essas especificações.

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *itálico*, colchetes `[ ]` `( )` etc.) neste documento, indique elementos e opções de código. Consulte [Convenções de estilo para código e elementos de texto](../../../reference/code-style-elements.md) para obter mais informações.

## Sintaxe do nome do arquivo e exemplos {#file-name-syntax}

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
   <td colname="col2"> <p>Um prefixo estático que identifica o arquivo como um arquivo de sincronização de ID para Destinos com base em pessoas. Use esse prefixo ao corresponder IDs do cliente (DPUUIDs) a endereços de email com hash para destinos com base em pessoas.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> <p>A ID principal do provedor de dados é a ID principal das DPIDs no nome do arquivo. Além disso, a primeira ID de usuário no arquivo de dados corresponde à ID principal. Os DPIDs subsequentes são outros identificadores que pertencem à principal. A sincronização mapeia DPIDs no nome do arquivo para UUIDs no arquivo.</p> <p>Essa DPID deve conter somente IDs de dispositivo, como AAM UUID, GAID, IDFA e assim por diante. Ele não pode conter DPUUIDs. Isso pode resultar em sincronização incorreta.</p>  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>IDs do provedor de dados. Essas IDs representam entidades ou fontes de dados associadas à DPID principal. A sincronização mapeia DPIDs no nome do arquivo para UUIDs no arquivo. </p> <p>O número de DPIDs no nome do arquivo deve corresponder ao número de UUIDs no arquivo de dados. Por exemplo, digamos que o nome do arquivo contenha uma DPID principal e 3 DPIDs. Seu arquivo de dados deve incluir 4 colunas correspondentes de UUIDs, formatadas conforme descrito na seção de conteúdo do arquivo abaixo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>Um carimbo de data e hora UNIX de 10 dígitos, em segundos. O carimbo de data e hora ajuda a tornar cada nome de arquivo exclusivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .sync</code> </p> </td> 
   <td colname="col2"> <p>Indica uma sincronização normal e completa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>.SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Um inteiro. Usado ao dividir arquivos grandes em vários arquivos menores. Isso ajuda a melhorar os tempos de processamento. O número indica qual parte do arquivo original você está enviando. Consulte os exemplos de nome de arquivo abaixo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Especifica que seu arquivo é compactado com compactação gzip opcional. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exemplos de nome de arquivo

Os exemplos a seguir mostram nomes de arquivos formatados corretamente. Os nomes de arquivo podem ser semelhantes.

<ul class="simplelist"> 
 <li> <code> adobe_id_111_222_333_444_1454442149.sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
 <li> <code>c2c_id_123_898_1454442149.sync.gz</code> </li> 
</ul>

>[!NOTE]
> Para nomear o arquivo de sincronização de ID (prefixo c2c) para Destinos com base em pessoas, consulte [Fluxo de trabalho A - Personalização com base em toda a atividade online combinada com dados offline](../../../features/destinations/people-based-destinations-workflow-combined.md) ou [Fluxo de trabalho B - Personalização com base em dados somente offline](../../../features/destinations/people-based-destinations-workflow-offline.md).

## Sintaxe de conteúdo de arquivo e exemplos {#file-content-syntax}

O conteúdo de um arquivo de ID inclui os seguintes elementos:

*`UUID`* `<tab>`*`UUID`*`<tab>`*`UUID`*`<tab>`*`UUID`*

O arquivo contém IDs de usuário ([!DNL UUID]). Em cada linha, separe as IDs com uma guia. O exemplo a seguir mostra um arquivo de ID corretamente formatado. Seu conteúdo pode ser semelhante.

```
abc123 def456 ghi789 xyz987
```

### Considerações sobre conteúdo de arquivo {#considerations}

Ao criar seus arquivos de entrada, verifique se a primeira coluna é preenchida apenas com IDs de dispositivo, como [!DNL AAM UUID], [!DNL GAID], [!DNL IDFA], e assim por diante. Consulte [Índice de IDs no Audience Manager](../../../reference/ids-in-aam.md) para obter uma explicação detalhada das IDs suportadas pelo Audience Manager.

>[!IMPORTANT]
>
>Não use [DPUUIDs](../../../reference/ids-in-aam.md) na primeira coluna. Isso pode resultar em sincronização incorreta.

## A sincronização corresponde DPUUIDs a UUIDs {#sync-matches-dpuuids-uuids}

A finalidade de um arquivo de sincronização de ID é sincronizar as [DPUUIDs](../../../reference/ids-in-aam.md) de suas próprias fontes de dados com [!DNL Audience Manager] UUIDs. A sincronização mapeia os [!DNL DPUUID]s do [!DNL DPID] principal e seus [!DNL DPID]s relacionados para os [!DNL Audience Manager] [!DNL UUID]s. Onde você coloca as IDs no nome e no corpo do arquivo determina como esses identificadores são mapeados uns para os outros. Por exemplo, pegue os dois arquivos de amostra mostrados aqui:

* **Arquivo 1:** `adobe_id_0_12345_1476312152.sync`

* **Arquivo 2:**  `adobe_id_12345_67890_1476312876.sync`

<br/>

Dado o nome e o conteúdo da amostra, as IDs são mapeadas da seguinte forma:

**Arquivo 1** (  [Baixar arquivo de amostra](assets/adobe_id_0_12345_1476312152.sync))

| DPID 0 = UUIDs do Adobe Audience Manager | DPID 12345 |
|---|---|
| 6807998276567319850405265607456196039 | XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-Trj6E4njaMR38 |
| 674126820834119957255387043620307584 | XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 |
| 8915902479676034373311707646026765593 | XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYIwd0A2OlM |
| 66552757407517449462805881945288602094 | XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M |
| 6618477822667870903738139438735041506 | XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw |

Etapa 1: o processo de sincronização de ID sincronizará os [!DNL DPUUID]s de [!DNL DPID] 12345 com os [!DNL Audience Manager] [!DNL UUID]s na coluna esquerda. Observe que [!DNL DPID] &quot;0&quot; no nome do arquivo representa [!DNL Audience Manager] [!DNL UUID]s.
<br/>

**Arquivo 2** (  [Baixar arquivo de amostra](assets/adobe_id_12345_67890_1477846458.sync))

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-Trj6E4njaMR38 | 4598060374 |
| XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 | 4581274262 |
| XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYIwd0A2OlM | 439243426 |
| XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M | 2351382994 |
| XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw | 4601584763 |

Etapa 2: os [!DNL DPUUID]s de [!DNL DPID] 12345 foram sincronizados na etapa 1 com o Audience Manager [!DNL UUID]s. O que essa sincronização de ID fará é sincronizar os [!DNL DPUUID]s de [!DNL DPID] 67890 com o Audience Manager [!DNL UUID]s da etapa 1.

<br/>

## Outros requisitos de formato {#other-format-reqs}

As IDs de usuário não podem:

* Ter guias na própria ID. Guias são usadas apenas para separar IDs individuais no arquivo de dados.
* Contém informações de identificação pessoal ([!UICONTROL PII]).
* Use a codificação [!DNL URL]. Transmita somente IDs não codificadas.

As linhas que terminarem com guias ou espaços não serão processadas ou realizadas. Como regra, mantenha o final das linhas limpo.
