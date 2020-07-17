---
description: Lista as macros que podem ser usadas para criar modelos de saída. Elas incluem macros de nome de arquivo, macros de cabeçalho e macros de conteúdo.
seo-description: Lista as macros que podem ser usadas para criar modelos de saída. Elas incluem macros de nome de arquivo, macros de cabeçalho e macros de conteúdo.
seo-title: Macros de modelo de saída
solution: Audience Manager
title: Macros de modelo de saída
uuid: dec082d3-306b-4ff5-afb2-418bd543d8d0
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 3%

---


# Macros de modelo de saída {#outbound-template-macros}

Lista as macros que podem ser usadas para criar modelos de saída. Elas incluem macros de nome de arquivo, macros de cabeçalho e macros de conteúdo.

## Macros de nome de arquivo e cabeçalho de arquivo {#file-name-header-macros}

A tabela lista e descreve as macros que podem ser usadas no nome do arquivo e para definir campos de cabeçalho. Para obter exemplos de código, consulte Exemplos [de macro de](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)saída.

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
   <td colname="col2"> <p>Um caractere ASCII não imprimível. Indica o start de uma linha ou de uma seção de conteúdo. Também pode ser usado para separar colunas de dados em um arquivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>ID do provedor de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_DPID </code> </p> </td> 
   <td colname="col2"> <p>ID do provedor de dados da chave de ID do usuário. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NEW_LINE </code> </p> </td> 
   <td colname="col2"> <p> Permite a criação de cabeçalhos de várias linhas para ordens de saída. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>ID do pedido / de destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID_ALIAS </code> </p> </td> 
   <td colname="col2"> <p>Um alias para uma ID de pedido/destino. </p> <p>O alias é definido na interface do usuário do administrador. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> SPLITNUM </code> </p> </td> 
   <td colname="col2"> <p>Indica a divisão de arquivos de saída em várias partes. Substitua a seção SPLITNUM no nome do arquivo pelo número de peça precedido de zeros, garantindo no mínimo três caracteres para a seção SPLITNUM.</p>
   <p>A macro SPLITNUM não precisa ser cercada por caracteres &lt;&gt;.</p><p>Exemplo: <code>&lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;SPLITNUM.csv</code>
<p>s3_123456_9999_full_1566906141001.csv</p> 
<p>s3_123456_9999_full_1566906141002.csv</p> 
<p>s3_123456_999_full_1566906141003.csv</p> 
<p>Os três últimos dígitos (001.002.003) nos exemplos acima são os identificadores SPLITNUM.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>Indica o tipo de sincronização e inclui: </p> 
    <ul id="ul_CA5057DA18144AB8BC17B3EB79891B25"> 
     <li id="li_6DFEE438860D4DB18EF831E3AF525F1E"> <code> full </code>: Sincronização completa. </li> 
     <li id="li_1A7BBBB40AD94FC39B06F4FC49586595"> <code> iter </code>: Sincronização incremental. </li> 
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
   <td colname="col2"> <p>Usada como separador, essa macro insere uma guia entre os campos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>Um carimbo de data e hora de 10 dígitos, UTC, Unix. </p> <p>Ele também pode ser formatado como <code> &lt;TIMESTAMP; format="YYYYMMDDhhmmss"&gt; </code> segue as regras de formatação de data/hora do Java. </p> </td> 
  </tr>

</tbody> 
</table>

## Macros de conteúdo {#content-macros}

Macros usadas para formatar o conteúdo de um arquivo de dados. Para obter exemplos de código, consulte Exemplos [de macro de](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)saída.

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
   <td colname="col2"> <p>Insere um caractere de fechamento entre chaves }. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="term"> Identificador de usuário exclusivo do provedor de dados </span>. </p> <p>Essa é a ID do parceiro de dados para o qual você envia dados em um arquivo externo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID_LIST </code> </p> </td> 
   <td colname="col2"> <p>Retorna uma lista que contém várias IDs para um parceiro de dados. Isso é útil se você tiver uma organização grande com várias subdivisões ou outros grupos organizacionais com os quais você pode compartilhar dados. Essa macro retorna uma lista das IDs para esses grupos secundários. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>ID do provedor de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>A saída dessa macro mapeia a ID do provedor de dados (DPID) para IDs de usuário exclusivas relacionadas (DPUUID). Essa macro deve ter uma string de formatação para controlar sua saída. A saída da amostra seria semelhante ao seguinte: </p> <p> <code> "dpids=dpid1,dpid2,...dpid n|maxMappings= n|format=json" </code> </p> <p>A <code> maxMappings </code> configuração determina quantos mapeamentos você deseja que a macro retorne. Quando <code> maxMappings=0 </code>, essa macro retorna todos os mapeamentos para cada DPID especificado. Os dados são classificados por carimbo de data e hora (o mais recente primeiro) e retorna os resultados com o maior carimbo de data e hora primeiro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if(SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST)endif </code> </p> </td> 
   <td colname="col2"> <p>Essa combinação de macros cria uma declaração condicional que lista os segmentos aos quais os usuários pertencem e dos quais foram removidos. Retorna uma string vazia se ambas as condições não forem atendidas ou não houver dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MCID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Adobe Experience Cloud ID.</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPEN_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Insere um caractere { colchetes abertos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPT_OUT </code> </p> </td> 
   <td colname="col2"> <p>Obsoleto. Não utilizar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>ID do pedido ou de destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Obsoleto. Não utilizar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_VALUE </code> </p> </td> 
   <td colname="col2"> <p>Retorna <code> 1 </code> como um valor estático codificado. </p> </td> 
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
     <li id="li_9BE103EFD8384464B46FAC00422431DB"> <code> type </code>: Retorna <code> 5 </code>, um valor estático codificado que identifica dados como dados de segmento. </li> 
     <li id="li_FE5049089F2944FA9DB9F9D546DBA167"> <code> alias </code>: Obsoleto. Não utilizar. </li> 
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD27"> <code> lastUpdateTime </code>: Um carimbo de data e hora Unix que indica a última vez que um segmento foi realizado. </li> 
    </ul> <p>Coloque essas variáveis entre chaves após a macro. Por exemplo, esse código separa os resultados com um caractere de barra vertical "|": <code> &lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.sid&gt;}; separator=","&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p>Retorna <code> 1 </code>, como um valor estático codificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>Indica o tipo de sincronização e inclui: </p> 
    <ul id="ul_A3ADC37E66F043DABDA9C4066024B6C1"> 
     <li id="li_A1859F63ACF24618884C41F2DAB19ABB"> <code> full </code>: Sincronização completa. </li> 
     <li id="li_520DDED3662B428DB9DB55D494221D97"> <code> iter </code>: Sincronização incremental. </li> 
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
   <td colname="col2"> <p>Usada como separador, essa macro insere uma guia entre os campos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TRAIT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Retorna uma lista de características. Aceita os seguintes argumentos opcionais: </p> 
    <ul id="ul_E9CDC4DD47B9435086FF42143D9E8177"> 
     <li id="li_4BBC57F0D7874F8EA8C6D39DB3572257"> <code> type </code>: Identifica os tipos de características por ID numérica. Devoluções: 
      <ul id="ul_D2357E6CF47B4EBC8D3772D17B2EADA3"> 
       <li id="li_C6C2A019FCD945E085E1ABB564C4EDAD"> <code> 10 </code> que identifica uma característica do DPM (offline, integrada por uma tarefa de entrada). </li> 
       <li id="li_7AFF8A1D0E1140459CC95CF43A97B9B6"> <code> 3 </code> que identifica uma característica baseada em regras (em tempo real, integrada pelo DCS). </li> 
      </ul> </li> 
     <li id="li_1DDE25334CF9479A8C4738F3CB3C40AA"> <code> traitId </code>: ID da característica. </li> 
     <li id="li_DCB89F2A40BB43C98EE3C84B5B3CDD33"> <code> lastRealized </code>: A última vez que o traço foi realizado. Carimbo horário único. </li> 
    </ul> <p>Coloque essas variáveis entre chaves após a macro. Por exemplo, esse código separa os resultados com um caractere de barra vertical "|": <code> &lt;TRAIT_LIST:{trait|&lt;trait.Id&gt;,&lt;trait.lastRealized&gt;};separator="," </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> ID de </span> usuário do Audience Manager. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Exemplos de macro de saída](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

