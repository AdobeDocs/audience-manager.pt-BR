---
description: Lista e descreve a sintaxe e os atributos suportados (ou pares de valores chave) que podem ser passados para os Servidores de coleta de dados (DCS). Essas informações podem ajudar a formatar as solicitações DCS e compreender os parâmetros retornados por esse sistema.
seo-description: Lists and describes the syntax and supported attributes (or key-value pairs) you can pass in to the Data Collection Servers (DCS). This information can help you format your DCS requests and understand the parameters returned by this system.
seo-title: Supported Attributes for DCS API Calls
solution: Audience Manager
title: Atributos compatíveis com chamadas de DCS API
keywords: d_caller, d_cb, d_cid, d_cid_ic, d_coppa, d_cts=1, d_cts=2, d_tdpid, d_dst=1, d_dst_filter, d_mid, d_ptfm, d_nsid, d_rs, d_rtbd=json, d_tdpid_id
uuid: 0b98ed11-314b-4500-afde-45a041112150
feature: DCS
exl-id: 1bdd7dcd-9411-4b0a-a236-059eb5faf00d
source-git-commit: e10211057a87622340fd2c61737c7c7a45c0e99c
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 4%

---

# Atributos compatíveis para [!DNL DCS] [!DNL API] Chamadas {#supported-attributes-for-dcs-api-calls}

Lista e descreve a sintaxe e os atributos suportados (ou pares de valores chave) que podem ser passados para a [!UICONTROL Data Collection Servers] ([!DNL DCS]). Essas informações podem ajudar a formatar a [!DNL DCS] e entender os parâmetros retornados por esse sistema.

## Prefixos de atributos {#attribute-prefixes}

O [!DNL DCS] O depende de prefixos específicos adicionados às chaves em pares de valores chave para classificar o tipo de dados que você está transmitindo.

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
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> atributos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> h_</code> </p> </td> 
   <td colname="col2"> <p>Dados do cabeçalho HTTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> p_</code> </p> </td> 
   <td colname="col2"> <p>Atributos privados definidos pelo cliente. </p> <p> O DCS aceita seus próprios dados privados quando a chave tiver uma <code> p_</code> prefixo. Os dados privados são usados para avaliação de características, mas não serão registrados ou armazenados em nosso sistema. Por exemplo, digamos que você tenha uma característica definida como <code> customers = p_age&lt;25</code> e você passa <code> p_age=23</code> em uma chamada de evento. Dadas essas condições, o usuário que atende aos critérios de qualificação com base na idade se qualifica para a característica, mas o par de valor-chave é descartado depois <span class="keyword"> Audience Manager</span> O recebe a solicitação e não é registrado. </p> </td>
  </tr> 
 </tbody> 
</table>

## [!DNL d_] Atributos {#d-attributes}

Todos esses itens são opcionais, a menos que você deseje uma resposta do [!DNL DCS]. Se desejar que a variável [!DNL DCS] para retornar uma resposta, `d_rtbd=json` é obrigatório.

<table id="table_FCCE4F9D796648899772A191981EFDE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Atributo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> d_caller</code> </p> </td> 
   <td colname="col2"> <p>Usado para identificar o chamador que está fazendo a chamada para o <span class="wintitle"> DCS</span> API. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cb</code> </p> </td> 
   <td colname="col2"> <p>Especifica uma função JavaScript que você deseja executar usando o <span class="wintitle"> DCS</span> como parâmetro de função da função de retorno de chamada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cid</code> </p> </td> 
   <td colname="col2"> <p>Contém um ou mais pares de IDs de provedor de dados (<code> DPID</code>) e IDs de usuário do provedor de dados (<code> DPUUID</code>) atribuído por <span class="keyword"> Audience Manager</span>. Se você usar vários pares de <code> DPID</code>s e <code> DPUUID</code>s, separe cada par com o caractere não imprimível <code> %01</code>. Por exemplo: <code><i>DPID</i>%01<i>DPUUUID</i></code>. </p> <p><code> d_cid</code> replace <code> d_dpid</code> e <code> d_dpuuid</code>, que estão obsoletas, mas ainda são compatíveis. Consulte <a href="../../../reference/cid.md">CID substitui DPID e DPUUID</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cid_ic</code> </p> </td> 
   <td colname="col2"> <p>Contém um código de integração e uma ID de usuário exclusiva associada em um único par de valor-chave. </p> <p><code> d_cid_ic</code> replace <code> d_dpid</code> e <code> d_dpuuid</code>, que estão obsoletas, mas ainda são compatíveis. Consulte <a href="../../../reference/cid.md">CID substitui DPID e DPUUID</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_coppa</code> </p> </td> 
   <td colname="col2"> <p>Desative o uso de cookies de terceiros para cumprir com as regulamentações de proteção infantil. Esse parâmetro é definido dinamicamente pelo Adobe Adobe Experience Platform Identity Service e depende do <code> idSyncDisable3rdPartySyncing</code> configuração. Consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/coppa.html" format="https" scope="external"> Suporte para COPPA no serviço de identidade da Adobe Experience Platform</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cts=1</code> </p> <p><code> d_cts=2</code> </p> </td> 
   <td colname="col2"> <p>Opcional. Ativado na solicitação do cliente. Entre em contato com seu consultor da Adobe Audience Manager ou com o Atendimento ao cliente. </p> <p>Indica que características e segmentos devem ser retornados dentro da variável <code> JSON</code> resposta. </p> <p> 
     <ul id="ul_8B936ACB18724681B959783421ACF026"> 
      <li id="li_792A6248F49141C0B4B214C754D5F5C5"> <p><code> d_cts=1</code> devoluções <a href="../../../reference/ids-in-aam.md"> IDs de segmento herdadas</a> para os segmentos. </p> </li>
      <li id="li_F304CA651F3C444A9A24576726925D87"> <p><code> d_cts=2</code> retorna IDs de segmento para os segmentos. </p> </li>
     </ul> </p> <p>Uma resposta de amostra pode ser semelhante à abaixo: </p> <p>
     <code class="syntax javascript">
      {
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"07955261652886032950143702505894272138",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"traits":&nbsp;[420020,&nbsp;5421506],
      &nbsp;&nbsp;&nbsp;&nbsp;"segments":&nbsp;[984263,&nbsp;985264],
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      }
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpid</code> </p> </td> 
   <td colname="col2"> <p>Obsoleto. Consulte <code> d_cid</code> e <code> d_cid_ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpuuid</code> </p> </td> 
   <td colname="col2"> <p>Obsoleto. Consulte <code> d_cid</code> e <code> d_cid_ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst=1</code> </p> </td> 
   <td colname="col2"> <p>Retorna os dados de destino do URL no <code> JSON</code> resposta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst_filter</code> </p> </td> 
   <td colname="col2"> <p><code> d_dst_filter</code> é um atributo reservado, usado na integração entre o Adobe Analytics e o Audience Manager. </p> <p>Não recomendamos criar características que usam atributos reservados. O Adobe pode alterar atributos reservados a qualquer momento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_jsonv=1|0</code> </p> </td> 
   <td colname="col2"> <p>Indica o <code> JSON</code> para usar na resposta. Normalmente, você deve definir essa opção como <code> d_jsonv=1</code>. Configuração <code> d_jsonv=0</code> desativa sincronizações de ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_mid</code> </p> </td> 
   <td colname="col2"> <p>Especifica o conjunto de ID de Experience Cloud e usado pelo <span class="keyword"> Experience Cloud</span> Serviço de ID. Para obter mais informações sobre a ECID, consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies e o serviço de identidade do Experience Cloud</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_nsid</code> </p> </td> 
   <td colname="col2"> <p>ID do espaço do nome. Indica qual contêiner do JavaScript é usado. Usado por <span class="wintitle"> DIL</span> para sincronização de id. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ptfm </code> </p> </td> 
   <td colname="col2"> <p>Permite que o Audience Manager distinga solicitações móveis de solicitações de desktop. Os valores compatíveis incluem: </p> <p> 
     <ul id="ul_A01D4B15C89F4713A39E08377924D632"> 
      <li id="li_E17CC839265B4EB9AC44A3DA31A23857"> <code> ios</code> </li> 
      <li id="li_468F5903CD3048B5AE02A3FDA9B3C4F1"> <code> android</code> </li> 
      <li id="li_57090DAC3BDA41DFB4BA0DD328754D55"> <code> browser</code> </li> 
      <li id="li_DA4E93A831FE4FD8971CECD508AF992F"> <code> all</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rs</code> </p> </td> 
   <td colname="col2"> <p>Obsoleto. <code> d_rs</code> é um atributo reservado, usado na integração herdada entre <span class="keyword"> Adobe Analytics</span> e <span class="keyword"> Audience Manager</span>. </p> <p>Não recomendamos criar características que usam atributos reservados. O Adobe pode alterar atributos reservados a qualquer momento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rtbd=json</code> </p> </td> 
   <td colname="col2"> <p>Obrigatório se desejar uma <code> JSON</code> da <span class="wintitle"> DCS</span>. </p> <p> 
     <ul id="ul_9EA00BD822504BCA8ECB59C1634DB91A"> 
      <li id="li_7CB890F92C4A4C6AA8B4EE32E1AD4564">Se você omitir isso, a variável <span class="wintitle"> DCS</span> retorna um pixel no cabeçalho. </li> 
      <li id="li_824C23B4C7AA4B5EBADF73D26016A18E">Se você incluir isso, a variável <span class="wintitle"> DCS</span> retorna um <code> JSON</code> no corpo da resposta. Veja o exemplo abaixo. Sua resposta pode ser mais complexa. </li> 
     </ul> </p> <p> 
     <code class="syntax javascript">
      {
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"22920112968019678612904394744954398990",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      }
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_sid</code> </p> </td> 
   <td colname="col2"> <p><code> SID</code> significa <span class="term"> ID da pontuação</span>. Essa é uma ID exclusiva para uma característica ou um segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid</code> </p> </td> 
   <td colname="col2"> <p>Passa uma fonte de dados para avaliação de característica. Somente as características dessa fonte de dados são avaliadas. </p> <p>Por exemplo, digamos que você tenha: </p> <p> 
     <ul id="ul_6230777E16C14DCB83025A101A4ECA14"> 
      <li id="li_71F3970417BC4B93881A3E12DADE4120"><b>Característica T1</b> com: </li> 
      <li id="li_66125E035F524A958C6F4BFAABA2A0D2">Regra de característica: "<code> key1 == val1</code>" </li> 
      <li id="li_4EE486E02CF54AEA876ABC005094E9E4">Fonte de dados (<a href="../../../reference/ids-in-aam.md"> DPID</a>): 1 </li> 
      <li id="li_3E6BBDEAE5C644C6A96CB49766CDA988">Código de integração DPID: ic1 </li> 
     </ul> 
     <ul id="ul_0C30A8AE349D43A08490DA76CB4B06FA"> 
      <li id="li_F1E8DB26168B471FA35D82F4DD3AC601"><b>Característica T2</b> com: </li> 
      <li id="li_1C943F84A4A149A0A86ABC92761D3E9E">Regra de característica: "<code> key2 == val2</code>" </li> 
      <li id="li_F2AA086C87B7484F8BFE1D5C09E8EBDF">Fonte de dados (DPID): 2 </li> 
      <li id="li_877CAAAE996A4707BEE74F7042708481">Código de integração DPID: ic2 </li> 
     </ul> </p> <p>Em uma chamada de exemplo, <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid=1</code>, somente a característica T1 é retornada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid_ic</code> </p> </td> 
   <td colname="col2"> <p>O objetivo é idêntico ao <code> d_tdpid</code> parâmetro descrito acima. No entanto, nesse caso, a fonte de dados é passada usando o código de integração. </p> <p>Mantendo as características descritas acima, considere a chamada de amostra: </p> <p>Para <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid_ic=ic2</code>, somente a característica T2 é retornada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_uuid</code> </p> </td> 
   <td colname="col2"> <p>ID exclusiva do usuário. Identifica um visitante quando esse valor não está disponível a partir de um cookie. </p> </td> 
  </tr>
 </tbody>
</table>

## h_ Atributos

Esses cabeçalhos contêm informações como solicitações de dados e respostas em uma chamada HTTP.

| Atributo | Descrição |
| --- | --- | 
| `h_host` | Isso é definido como o nome do host de coleta de dados específico do cliente. Aparece como `host name .demdex.net`. Consulte [Compreensão das chamadas para o domínio Demdex](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=en). |
| `h_user-agent` | Defina como `User-Agent` valor do cabeçalho. |
| `h_accept-language` | Defina como  `Accept-Language`  valor do cabeçalho. |
| `h_referer` | Defina como `Referer` valor do cabeçalho. |
| `h_referrer` | Defina como `Referrer` valor do cabeçalho. |
| `h_date` | Defina como `Date` valor do cabeçalho. |