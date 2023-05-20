---
description: Lista as macros que você pode usar para criar modelos de saída. Isso inclui macros de nome de arquivo, macros de cabeçalho e macros de conteúdo.
seo-description: Lists the macros you can use to create outbound templates. These include file name macros, header macros, and content macros.
seo-title: Outbound Template Macros
solution: Audience Manager
title: Macros de modelo de saída
uuid: dec082d3-306b-4ff5-afb2-418bd543d8d0
feature: Outbound Data Transfers
exl-id: 6988d0e5-7a99-4291-91d3-bcd3a15630fd
source-git-commit: d76505fda1ba448a1aaa3a756ef3bcf193a2718a
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 3%

---

# Macros de modelo de saída {#outbound-template-macros}

Lista as macros que você pode usar para criar modelos de saída. Isso inclui macros de nome de arquivo, macros de cabeçalho e macros de conteúdo.

## Macros de nome de arquivo e cabeçalho de arquivo {#file-name-header-macros}

A tabela lista e descreve as macros que você pode usar no nome do arquivo e para definir campos de cabeçalho. Para obter amostras de código, consulte [Exemplos de macro de saída](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md).

<table id="table_C353AF028E0A4944A8727FD01C94FDB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ASCII_SOH </code> </p> </td> 
   <td colname="col2"> <p>Um caractere ASCII não imprimível. Ele indica o início de uma linha ou de uma seção de conteúdo. Ele também pode ser usado para separar colunas de dados em um arquivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>ID do provedor de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_DPID </code> </p> </td> 
   <td colname="col2"> <p>ID do usuário Provedor de dados chave. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NEW_LINE </code> </p> </td> 
   <td colname="col2"> <p> Permite a criação de cabeçalhos de várias linhas para ordens de saída. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>ID do pedido/destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID_ALIAS </code> </p> </td> 
   <td colname="col2"> <p>Um alias para uma ID de pedido/destino. </p> <p>O alias é definido na interface do usuário do administrador. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> SPLITNUM </code> </p> </td> 
   <td colname="col2"> <p>Indica a divisão de arquivos de saída em várias partes. Substitua a seção SPLITNUM no nome do arquivo pelo número da peça precedido por zeros, garantindo no mínimo três caracteres para a seção SPLITNUM.</p>
   <p>A macro SPLITNUM não precisa estar entre &lt;&gt; caracteres.</p><p>Exemplo: <code>&lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;SPLITNUM.csv</code>
<p>s3_123456_9999_full_1566906141001.csv</p> 
<p>s3_123456_9999_full_1566906141002.csv</p> 
<p>s3_123456_9999_full_1566906141003.csv</p> 
<p>Os três últimos dígitos (001,002,003) nos exemplos acima são os identificadores SPLITNUM.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>Indica o tipo de sincronização e inclui: </p> 
    <ul id="ul_CA5057DA18144AB8BC17B3EB79891B25"> 
     <li id="li_6DFEE438860D4DB18EF831E3AF525F1E"> <code> full </code>: Sincronização completa. </li> 
     <li id="li_1A7BBBB40AD94FC39B06F4FC49586595"> <code> iter </code>: sincronização incremental. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Indica o método de transferência de dados e inclui: </p> 
    <ul id="ul_24DD8DCA18B34A8590FC66431FD720AB"> 
     <li id="li_88EC08F7406641698920F879EB5E9520"> <code> ftp </code> </li> 
     <li id="li_188CE2FDA31949BBB141F57B574301BC"> <code> http </code> </li> 
     <li id="li_0649D3F0F3BE405D89118A7F6F4D8082"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Usada como separador, essa macro insere uma guia entre campos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>Um carimbo de data e hora de 10 dígitos, UTC e Unix. </p> <p>Também pode ser formatado como <code> &lt;TIMESTAMP; format="YYYYMMDDhhmmss"&gt; </code> seguindo as regras de formatação de data/hora do Java. </p> </td> 
  </tr>

</tbody> 
</table>

## Macros de conteúdo {#content-macros}

Macros usadas para formatar o conteúdo de um arquivo de dados. Para obter amostras de código, consulte [Exemplos de macro de saída](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md).

<table id="table_5C6F9678CFF34C5EB67BA1DEA0479F1D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> CLOSE_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Insere uma chave de fechamento <code>}</code> caractere. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="term"> Identificador de usuário exclusivo do provedor de dados </span>. </p> <p>Essa é a ID do parceiro de dados para o qual você envia dados em um arquivo de saída. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID_LIST </code> </p> </td> 
   <td colname="col2"> <p>Retorna uma lista que contém várias IDs para um parceiro de dados. Isso é útil se você tiver uma grande organização com várias subdivisões ou outros grupos organizacionais com os quais poderá compartilhar dados. Esta macro retorna uma lista de IDs para esses grupos secundários. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>ID do provedor de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>A saída dessa macro mapeia a ID do provedor de dados (DPID) para IDs de usuário exclusivas relacionadas (DPUUID). Esta macro deve ter uma sequência de formatação para controlar sua saída. O exemplo de saída seria semelhante ao seguinte: </p> <p> <code> "dpids=dpid1,dpid2,...dpid n|maxMappings= n|format=json" </code> </p> <p>A variável <code> maxMappings </code> determina quantos mapeamentos você deseja que a macro retorne. Quando <code> maxMappings=0 </code>, essa macro retorna todos os mapeamentos para cada DPID especificado. Os dados são classificados por carimbo de data e hora (o mais recente primeiro) e retornam os resultados com o maior carimbo de data e hora primeiro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if(SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST)endif </code> </p> </td> 
   <td colname="col2"> <p>Essa combinação de macros cria uma declaração condicional que lista os segmentos aos quais os usuários pertencem e dos quais foram removidos. Ele retorna uma string vazia se ambas as condições não forem atendidas ou se não houver dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MCID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Adobe Experience Cloud ID.</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPEN_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Insere uma chave de abertura <code>{</code> caractere. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPT_OUT </code> </p> </td> 
   <td colname="col2"> <p>Obsoleto. Não use. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>ID do pedido ou destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Obsoleto. Não use. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_VALUE </code> </p> </td> 
   <td colname="col2"> <p>Devoluções <code> 1 </code> como um valor estático codificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID </code> </p> </td> 
   <td colname="col2"> <p>ID do parceiro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PIDALIAS </code> </p> </td> 
   <td colname="col2"> <p>Um alias para uma ID de pedido/destino. </p> <p>O alias é definido na interface do usuário do administrador. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Retorna uma lista de segmentos, se houver, que foram removidos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Retorna uma lista de segmentos em uma lista. Aceita os seguintes argumentos opcionais: </p> 
    <ul id="ul_B111AA0D6C18445598A1444B8B7E9325"> 
     <li id="li_8603B40229624856AF1FBC434DB8F16A"> <code> segmentId </code>: ID do segmento. Obsoleto. Use <code> sid </code>. </li> 
     <li id="li_1EF40DDCA3C5447586904CF021D8F912"> <code> csegid </code>: ID do segmento do cliente. Obsoleto. Use <code> sid </code>. </li> 
     <li id="li_D85F0A5D16AE4DAFB55C17DBB35EA66E"> <code> sid </code>: ID do segmento </li> 
     <li id="li_9BE103EFD8384464B46FAC00422431DB"> <code> type </code>: Devoluções <code> 5 </code>- um valor estático codificado que identifica dados como dados de segmento. </li> 
     <li id="li_FE5049089F2944FA9DB9F9D546DBA167"> <code> alias </code>: Obsoleto. Não use. </li>
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD27"> <code> lastUpdateTime </code>: um carimbo de data e hora Unix que indica a última vez que o status de associação do segmento foi atualizado. </li>
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD28"> <code> lastRealizationTime </code>: um carimbo de data e hora Unix que indica a última vez que um segmento foi realizado. </li>
    </ul> <p>Coloque essas variáveis entre chaves após a macro. Por exemplo, este código separa os resultados com um caractere de barra vertical "|": <code> &lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.sid&gt;}; separator=","&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p>Devoluções <code> 1 </code>, como um valor estático codificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>Indica o tipo de sincronização e inclui: </p> 
    <ul id="ul_A3ADC37E66F043DABDA9C4066024B6C1"> 
     <li id="li_A1859F63ACF24618884C41F2DAB19ABB"> <code> full </code>: Sincronização completa. </li> 
     <li id="li_520DDED3662B428DB9DB55D494221D97"> <code> iter </code>: sincronização incremental. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Indica o método de transferência de dados e inclui: </p> 
    <ul id="ul_13BE35BBBF7C4C67AEFC514C5D192902"> 
     <li id="li_195FE9B4C5494600BD17D7172A8FB630"> <code> ftp </code> </li> 
     <li id="li_751AD59C4C934D66BC530D9806B500AF"> <code> http </code> </li> 
     <li id="li_4638AF7D1FB54E2C890045048B85309C"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Usada como separador, essa macro insere uma guia entre campos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TRAIT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Retorna uma lista de características. Aceita os seguintes argumentos opcionais: </p> 
    <ul id="ul_E9CDC4DD47B9435086FF42143D9E8177"> 
     <li id="li_4BBC57F0D7874F8EA8C6D39DB3572257"> <code> type </code>: identifica tipos de características por ID numérica. Devoluções: 
      <ul id="ul_D2357E6CF47B4EBC8D3772D17B2EADA3"> 
       <li id="li_C6C2A019FCD945E085E1ABB564C4EDAD"> <code> 10 </code> que identifica uma característica do DPM (offline, integrado por um trabalho de entrada). </li> 
       <li id="li_7AFF8A1D0E1140459CC95CF43A97B9B6"> <code> 3 </code> que identifica uma característica com base em regras (tempo real, integrado por meio do DCS). </li> 
      </ul> </li> 
     <li id="li_1DDE25334CF9479A8C4738F3CB3C40AA"> <code> traitId </code>: ID da característica. </li> 
     <li id="li_DCB89F2A40BB43C98EE3C84B5B3CDD33"> <code> lastRealized </code>: a última vez que a característica foi realizada. Carimbo de data e hora Unix. </li> 
    </ul> <p>Coloque essas variáveis entre chaves após a macro. Por exemplo, este código separa os resultados com um caractere de barra vertical "|": <code> &lt;TRAIT_LIST:{trait|&lt;trait.Id&gt;,&lt;trait.lastRealized&gt;};separator="," </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager </span> ID de usuário. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Exemplos de macro de saída](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

