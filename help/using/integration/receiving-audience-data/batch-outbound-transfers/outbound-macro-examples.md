---
description: Exemplos de como algumas macros comuns são usadas para criar modelos de arquivo externo.
seo-description: Exemplos de como algumas macros comuns são usadas para criar modelos de arquivo externo.
seo-title: Exemplos de macro de saída
solution: Audience Manager
title: Exemplos de macro de saída
uuid: 823 d 85 d 4-d 683-45 cf -9 e 60-c 12 b 7 d 52 a 498
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Exemplos de macro de saída {#outbound-macro-examples}

Exemplos de como algumas macros comuns são usadas para criar modelos de arquivo externo.

>[!NOTE]
>
>In the tables, **boldface** type identifies each macro with its related output. For the format examples, the `<` `>` symbols have been added to help visually separate each macro.

## File Name Macros {#file-name-macros}

For a list of available macros and definitions, see [Outbound Template Macros](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md).

<table id="table_B5073597219B470298EE614902DACAE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Exemplos de formato e saída </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_ &lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Output: <code> ftp_215_ 888_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_ DPID </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_ &lt;MASTER_DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Output: <code> ftp_215_888_ 20915_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ ID </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_ &lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Output: <code> ftp_ 215_888_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_ MODE </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_ &lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Saída: </p> <p> 
     <ul id="ul_F63D7B78AF1246639D6ED85C1621B17C"> 
      <li id="li_4D0D7B4D047345FE861FCBA2BD0408ED">Full: <code> ftp_215_888_ full_1449756724.sync </code> </li> 
      <li id="li_23F4D1F6B2784E599EDA29AA457327E6">Incremental: <code> ftp_215_888_ iter_1449756724.sync </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_ TYPE </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Saída: </p> <p> 
     <ul id="ul_11B14E740E40474F8302BDB809C428FE"> 
      <li id="li_54A3EAA468B44AC8B2528F855E03D04B">FTP: <code> ftp_215_888_iter_1449756724.sync </code> </li> 
      <li id="li_93468C56B661463CA7F62B1F5D3A53FF">https: <code> http_215_888_iter_1449756724.sync </code> </li> 
      <li id="li_8A204C7BEDBC41C096FE953B5F827DEC">S3: <code> s3_215_888_iter_1449756724.sync </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_ &lt;TIMESTAMP&gt;_&lt;admin&gt;&lt;.sync&gt; </code> </p> <p>Output: <code> ftp_215_888_iter_ 1449756724.sync </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Header Row Macros {#header-macros}

For a list of available macros and definitions, see [Outbound Template Macros](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md).

<table id="table_ABC31B3D660D47969E111EBC734D5BBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Exemplos de formato e saída </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;ORDER_ID&gt; &lt;TAB&gt;&lt;SYNC_TYPE&gt; </code> </p> <p>Output: <code> 888 full.sync </code> </p> <p>Na saída, o caractere da guia não impressão separa cada elemento. </p> </td>
  </tr>
 </tbody>
</table>

## File Content Macros {#file-content-macros}

For a list of available macros and definitions, see [Outbound Template Macros](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md).

<table id="table_408C6DD2B9D54550B003EAC93562E64F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Exemplos de formato e saída </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> DP_ UUID </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;DP_UUID&gt;&lt;TAB&gt;&lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>Output: <code> 123456 UUID1 UUID2 UUID3 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_ UUID_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;DP_UUID&gt;&lt;TAB&gt; &lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>Output: <code> 123456 UUID1 UUID2 UUID3 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>Consulte a seção separada abaixo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_ SEGMENT_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;DP_UUID&gt; &lt;REMOVED_SEGMENT_LIST;separator=" "&gt; </code> </p> <p>Output: <code> 123456 105955 101183 101180 101179 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;DP_UUID&gt; &lt;SEGMENT_LIST;separator=" "&gt; </code> </p> <p>Output: <code> 123456 105955 101183 101180 101179 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if (SEGMENT_ LIST &amp; &amp; REMOVED_ SEGMENT_ LIST) endif </code> </p> </td> 
   <td colname="col2"> <p><b>Formato:</b> </p> <p> 
     <code>{"Advertiserid": " &lt; PIDALIAS &gt; "," datacenterid ": 2, "TDID": " &lt; DP_ UUID &gt; "," Data ": [&lt; SEGMENT_ LIST: {seg|&lt; OPEN_ CURLY_ BRACKET &gt; "Name": " &lt; seg. alias &gt; " &lt; CLOSE_ CURLY_ BRACKET &gt;}; separator = "," &gt; &lt; if (SEGMENT_ LIST &amp; &amp; &amp; REMOVED_ SEGMENT_ LIST) &gt; &lt; VÍRA &gt; &lt; endif &gt; &lt; REMOVED_ SEGMENT_ LIST: {seg|&lt; OPEN_ CURLY_ BRACKET &gt; "Name": " &lt; seg. alias &gt; "," ttlinminutes ": 0 &lt; CLOSE_ CURLY_ BRACKET &gt;}; separator = "," &gt;]} </code>
 </p><p><b>Saída:</b></p> <p>
     <code>//First exemplo {"advertiserid": " 12345 "," Datacenterid ": 2, "TDID": " dfd 215 e 4-8 d 6 b -4 fdb -90 b 9-fab 4456 f 2 c 9 d "," Dados ": [{"Nome": " 4321 "}]} //Second exemplo {" advertiserid ": " 12345 "," Datacenterid ": 2, "TDID": " 9099 e 8 fe-abab -5114-abaa -28 bdaa 0539 ca "," Data ": [{"Nome": " 4321 "}, {" Nome ": " 987 "," Ttlinminutes ": 0}, {"Name": " 654 "," Ttlinminutes ": 0}}} </code>
 </p> <p> <p>Note:  In the first example, the macro only returns data for <code> SEGMENT_LIST </code> because <code> REMOVED_SEGMENT_LIST </code> is empty. O segundo exemplo retorna dados para ambas as macros. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p>Formato: </p> <p> <code> &lt; PID &gt; &lt; TAB &gt; &lt; UUID &gt; &lt; TAB &gt; &lt; DP_ UUID &gt; &lt; TAB &gt; &lt; SET_ ATTRIBUTES &gt; &lt; TAB &gt; &lt; OPT_ OUT &gt; &lt; TAB &gt; &lt; SEGMENT_ LIST: {seg|&lt; seg. type &gt;, &lt; seg. alias &gt;, &lt; OUTPUT_ ATTRIBUTE_ VALUE &gt;, &lt; seg. lastupdatetime &gt; &amp;} &gt; </code> </p> <p>Saída: </p> <p> <code> 1159 00088008579683653741516297509717335000 17 t 0 aj 01 b,103714,1,03714,1,13441&amp; 4661000 &amp; 5,103713,1,1343250661000 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;DP_UUID&gt;&lt;TAB&gt;&lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>Output: <code> 123456 UUID1 UUID2 UUID3 </code> </p> <p>Na saída, o caractere da guia não impressão separa cada elemento. </p> </td> 
  </tr>
  <tr>
   <td colname="col1"> <p> <code> TRAIT_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;PID&gt;&lt;TAB&gt;&lt;DP_UUID&gt;&lt;TAB&gt;&lt;SET_ATTRIBUTES&gt;&lt;TAB&gt; &lt;TRAIT_LIST;separator="|"&gt; </code> </p> <p>Output: <code> 1131 12345 1 123|456|789 </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### `DPUUID` Exemplos

To help you understand how the `DPUUID` macro outputs data, lets assume we have 2 `DPID`s mapped to `DPUUID`s as shown below:

* DPID `1111` maps to DPUUIDs `AAAA` (timestamp = 1) and `BBBB` (timestamp = 2).
* DPID `2222` maps to DPUUID `CCCC`.

Considerando essas condições, a tabela a seguir enumera algumas strings de formato possíveis e sua saída.

<table id="table_6A6D94F994C1475BB09126BA0B815B1F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Condição de mapeamento </th> 
   <th colname="col2" class="entry"> Formato macro </th> 
   <th colname="col3" class="entry"> Saída </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Retornar todos os mapeamentos para uma única DPID </p> </td> 
   <td colname="col2"> <p> <code> &lt; DPUUIDS; format = "dpids = 1111 | maxmappings = 0 | format = json" &gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["1111", "AAAA"], ["1111", "BBBB"]] </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Retornar um máximo de 1 mapeamento para todos os dpids </p> </td> 
   <td colname="col2"> <p> <code> &lt; DPUUIDS; format = "dpids = 1111,2222 | maxmappings = 1 | format = json" &gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["1111", "BBBB"], ["2222", "CCCC"]] </code> </p> <p>For DPID <code> 1111 </code>, the macro maps to DPUUID <code> BBBB </code> only because that ID has the larger timestamp. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Retornar um máximo de 2 mapeamentos para uma única DPID </p> </td> 
   <td colname="col2"> <p> <code> &lt; DPUUIDS; format = "dpids = 2222 | maxmappings = 2 | format = json" &gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["2222", "CCCC"]] </code> </p> <p>Even though <code> maxMappings=2 </code>, this macro returns only 1 DPID to DPUUID mapping because the specified DPID has only one DPUUID. </p> </td> 
  </tr> 
 </tbody> 
</table>

[Macros de modelo de saída](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)