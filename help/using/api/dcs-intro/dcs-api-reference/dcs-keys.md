---
description: Lista e descreve a sintaxe e os atributos suportados (ou pares de valores chave) que você pode passar para os Servidores de coleta de dados (DCS). Essas informações podem ajudar você a formatar suas solicitações do DCS e compreender os parâmetros retornados por este sistema.
seo-description: Lista e descreve a sintaxe e os atributos suportados (ou pares de valores chave) que você pode passar para os Servidores de coleta de dados (DCS). Essas informações podem ajudar você a formatar suas solicitações do DCS e compreender os parâmetros retornados por este sistema.
seo-title: Atributos compatíveis para chamadas de API DCS
solution: Audience Manager
title: Atributos compatíveis para chamadas de API DCS
uuid: 0 b 98 ed 11-314 b -4500-afde -45 a 041112150
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Supported Attributes for DCS API Calls {#supported-attributes-for-dcs-api-calls}

Lists and describes the syntax and supported attributes (or key-value pairs) you can pass in to the [!UICONTROL Data Collection Servers] ([!UICONTROL DCS]). This information can help you format your [!UICONTROL DCS] requests and understand the parameters returned by this system.

## Attribute Prefixes {#attribute-prefixes}

[!UICONTROL DCS] A depende de prefixos específicos adicionados às teclas em pares de valores chave para classificar o tipo de dados que você está passando.

<table id="table_23B7E15EC13749E9A245DFB543822DB7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Prefixo da chave </th> 
   <th colname="col2" class="entry"> Reservado para </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> c_</code> </p> </td> 
   <td colname="col2"> <p>Atributos definidos pelo cliente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Atributos do Audience Manager</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> h_</code> </p> </td> 
   <td colname="col2"> <p>Dados do cabeçalho HTTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> p_</code> </p> </td> 
   <td colname="col2"> <p>Atributos privados e definidos pelo cliente. </p> <p> The DCS accepts your own, private data when the key has a <code> p_</code> prefix. Os dados privados são usados para a avaliação de características, mas não serão registrados ou armazenados em nosso sistema. For example, lets say you have a trait defined as <code> customers = p_age&lt;25</code> and you pass in <code> p_age=23</code> in an event call. Given these conditions, the user who meets the age-based qualification criteria qualifies for the trait, but the key-value pair is dropped after <span class="keyword"> Audience Manager</span> receives the request and is not logged. </p> </td>
  </tr> 
 </tbody> 
</table>

## d_ Attributes {#d-attributes}

All of these are optional, unless you want a response from the [!UICONTROL DCS]. If you want the [!UICONTROL DCS] to return a response, then `d_rtbd=json` is required.

<table id="table_FCCE4F9D796648899772A191981EFDE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Atributo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> d_ caller</code> </p> </td> 
   <td colname="col2"> <p>Used to identify the caller who is making the call to the <span class="wintitle"> DCS</span> API. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cb</code> </p> </td> 
   <td colname="col2"> <p>Specifies a JavaScript function you want to execute using the <span class="wintitle"> DCS</span> response as a function parameter of the callback function. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cid</code> </p> </td> 
   <td colname="col2"> <p>Contains one or more pairs of data provider IDs (<code> DPID</code>) and data provider user IDs (<code> DPUUID</code>) assigned by <span class="keyword"> Audience Manager</span>. If you use multiple pairs of <code> DPID</code>s and <code> DPUUID</code>s, separate each pair with the non-printing character <code> %01</code>. For example: <code><i>DPID</i>%01<i>DPUUUID</i></code>. </p> <p><code> d_ cid</code> substitui <code> d_ dpid</code> e <code> d_ dpuuid</code>, que são obsoletos, mas ainda oferecem suporte. Consulte <a href="../../../reference/cid.md">CID substitui DPID e DPUUID</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_ cid_ ic</code> </p> </td> 
   <td colname="col2"> <p>Contém um código de integração e uma ID de usuário exclusiva associada em um único par de valores chave. </p> <p><code> d_ cid_ ic</code> substitui <code> d_ dpid</code> e <code> d_ dpuuid</code>, que estão obsoletos, mas ainda oferecem suporte. Consulte <a href="../../../reference/cid.md">CID substitui DPID e DPUUID</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ coppa</code> </p> </td> 
   <td colname="col2"> <p>Desabilite o uso de cookies de terceiros para manter-se em conformidade com as regulamentações de proteção infantil. This parameter is dynamically set by the Adobe Experience Cloud ID service and depends on the <code> idSyncDisable3rdPartySyncing</code> configuration. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_coppa.html" format="https" scope="external"> COPPA Support in the Experience Cloud ID Service</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_ cts = 1</code> </p> <p><code> d_ cts = 2</code> </p> </td> 
   <td colname="col2"> <p>Opcional. Ativado na solicitação do cliente. Entre em contato com o consultor do Adobe Audience Manager ou com o Atendimento ao cliente. </p> <p>Indicates that traits and segments should be returned inside the <code> JSON</code> response. </p> <p> 
     <ul id="ul_8B936ACB18724681B959783421ACF026"> 
      <li id="li_792A6248F49141C0B4B214C754D5F5C5"> <p><code> d_ cts = 1</code> retorna <a href="../../../reference/ids-in-aam.md"> IDs de segmento herdadas</a> para os segmentos. </p> </li>
      <li id="li_F304CA651F3C444A9A24576726925D87"> <p><code> d_ cts = 2</code> retorna IDs de segmento para os segmentos. </p> </li>
     </ul> </p> <p>Uma resposta de amostra pode ser semelhante a: </p> <p>
     <code class="syntax javascript">{"stuff": [], "uuid": " 07955261652886032950143702505894272138 "," dcs_ region ": 7, "características": [420020, 5421506], "segmentos": [984263, 985264], "tid": " ss 3 otqpiqp 0 = "} </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ dpid</code> </p> </td> 
   <td colname="col2"> <p>Obsoleto. See <code> d_cid</code> and <code> d_cid_ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ dpuuid</code> </p> </td> 
   <td colname="col2"> <p>Obsoleto. See <code> d_cid</code> and <code> d_cid_ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ dst = 1</code> </p> </td> 
   <td colname="col2"> <p>Returns URL destination data in the <code> JSON</code> response. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst_filter</code> </p> </td> 
   <td colname="col2"> <p><code> d_ dst_ filter</code> é um atributo reservado, usado na integração entre o Adobe Analytics e o Audience Manager. </p> <p>Recomendamos a criação de características que usam atributos reservados. A Adobe pode alterar atributos reservados a qualquer momento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ jsonv = 1|0</code> </p> </td> 
   <td colname="col2"> <p>Indicates the <code> JSON</code> version to use in the response. Normally, you should set this to <code> d_jsonv=1</code>. Setting <code> d_jsonv=0</code> disables ID syncs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_mid</code> </p> </td> 
   <td colname="col2"> <p>Specifies the Experience Cloud ID set and used by the <span class="keyword"> Experience Cloud</span> ID service. For more information about the ECID, see <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ nsid</code> </p> </td> 
   <td colname="col2"> <p>ID do espaço de nome. Indica qual contêiner javascript é usado. Used by <span class="wintitle"> DIL</span> to for id-syncing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ ptfm </code> </p> </td> 
   <td colname="col2"> <p>Permite que o Audience Manager diferencie solicitações móveis das solicitações de desktop. Os valores compatíveis incluem: </p> <p> 
     <ul id="ul_A01D4B15C89F4713A39E08377924D632"> 
      <li id="li_E17CC839265B4EB9AC44A3DA31A23857"> <code> ios</code> </li> 
      <li id="li_468F5903CD3048B5AE02A3FDA9B3C4F1"> <code> android</code> </li> 
      <li id="li_57090DAC3BDA41DFB4BA0DD328754D55"> <code> navegador</code> </li> 
      <li id="li_DA4E93A831FE4FD8971CECD508AF992F"> <code> all</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rs</code> </p> </td> 
   <td colname="col2"> <p>Obsoleto. <code> d_ rs</code> é um atributo reservado, usado na integração herdada entre <span class="keyword"> o Adobe Analytics</span> e <span class="keyword"> o Audience Manager</span>. </p> <p>Recomendamos a criação de características que usam atributos reservados. A Adobe pode alterar atributos reservados a qualquer momento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ rtbd = json</code> </p> </td> 
   <td colname="col2"> <p>Required if you want a <code> JSON</code> response from the <span class="wintitle"> DCS</span>. </p> <p> 
     <ul id="ul_9EA00BD822504BCA8ECB59C1634DB91A"> 
      <li id="li_7CB890F92C4A4C6AA8B4EE32E1AD4564">If you omit this, the <span class="wintitle"> DCS</span> returns a pixel in the header. </li> 
      <li id="li_824C23B4C7AA4B5EBADF73D26016A18E">If you include this, the <span class="wintitle"> DCS</span> returns a <code> JSON</code> object in the body of the response. Consulte o exemplo abaixo. Sua resposta pode ser mais complexa. </li> 
     </ul> </p> <p> 
     <code class="syntax javascript">{"stuff": [], "uuid": " 22920112968019678612904394744954398990 "," dcs_ region ": 7, "tid": " ss 3 otqpiqp 0 = "} </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ sid</code> </p> </td> 
   <td colname="col2"> <p><code> A SID</code> é a ID <span class="term"> da pontuação</span>. Essa é uma ID exclusiva para um traço ou segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ tdpid</code> </p> </td> 
   <td colname="col2"> <p>Envia uma fonte de dados para a avaliação de características. Apenas características dessa fonte de dados são avaliadas. </p> <p>Por exemplo, digamos que você tenha: </p> <p> 
     <ul id="ul_6230777E16C14DCB83025A101A4ECA14"> 
      <li id="li_71F3970417BC4B93881A3E12DADE4120"><b>Característica T 1</b> com: </li> 
      <li id="li_66125E035F524A958C6F4BFAABA2A0D2">Trait rule: "<code> key1 == val1</code>" </li> 
      <li id="li_4EE486E02CF54AEA876ABC005094E9E4">Data Source (<a href="../../../reference/ids-in-aam.md"> DPID</a>): 1 </li> 
      <li id="li_3E6BBDEAE5C644C6A96CB49766CDA988">Código de integração DPID: ic 1 </li> 
     </ul> 
     <ul id="ul_0C30A8AE349D43A08490DA76CB4B06FA"> 
      <li id="li_F1E8DB26168B471FA35D82F4DD3AC601"><b>Característica T 2</b> com: </li> 
      <li id="li_1C943F84A4A149A0A86ABC92761D3E9E">Trait rule: "<code> key2 == val2</code>" </li> 
      <li id="li_F2AA086C87B7484F8BFE1D5C09E8EBDF">Fonte de Dados (DPID): 2 </li> 
      <li id="li_877CAAAE996A4707BEE74F7042708481">Código de integração DPID: ic 2 </li> 
     </ul> </p> <p>In a sample call, <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid=1</code>, only trait T1 is returned. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ tdpid_ ic</code> </p> </td> 
   <td colname="col2"> <p>The purpose is identical to the <code> d_tdpid</code> parameter described above. No entanto, nesse caso, a fonte de dados é transmitida usando o código de integração. </p> <p>Manter as características descritas acima, considere a chamada de amostra: </p> <p>For <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid_ic=ic2</code>, only trait T2 is returned. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ uuid</code> </p> </td> 
   <td colname="col2"> <p>ID de usuário exclusiva. Identifica um visitante quando este valor não está disponível em um cookie. </p> </td> 
  </tr>
 </tbody>
</table>