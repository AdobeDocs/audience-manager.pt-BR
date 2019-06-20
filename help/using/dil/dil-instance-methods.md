---
description: As apis DIL de nível de instância permitem criar programaticamente e trabalhar com objetos do Audience Manager. Os métodos de nível de instância aprimoram a funcionalidade da API estabelecida pelos métodos de nível de classe.
keywords: criar características; criar característica
seo-description: As apis DIL de nível de instância permitem criar programaticamente e trabalhar com objetos do Audience Manager. Os métodos de nível de instância aprimoram a funcionalidade da API estabelecida pelos métodos de nível de classe.
seo-title: Métodos de DIL de nível de instância
solution: Audience Manager
title: Métodos de DIL de nível de instância
uuid: aa 5147 bb -51 d 5-41 d 4-a 78 a-e 550 f 7492056
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Instance-level DIL Methods{#instance-level-dil-methods}

The instance-level [!UICONTROL DIL] APIs let you programmatically create and work with Audience Manager objects. Os métodos de nível de instância aprimoram a funcionalidade da API estabelecida pelos métodos de nível de classe.

## Getting started with Instance-level DIL Methods {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

When working with the instance-level [!UICONTROL DIL] APIs:

* O acesso requer um nome de parceiro e ID de namespace de contêiner (NSID). Entre em contato com o gerente da conta do Audience Manager para obter essas informações.
* Replace any sample *italicized* text in the API documentation with value, ID, or other variable as required by the method you&#39;re working with.

<!-- 

c_instance_start.xml

 -->

## signals {#signals}

Adiciona mapeamentos de nível de cliente e plataforma à sequência de consulta de uma solicitação pendente.

<!-- 

r_dil_signals.xml

 -->

**Assinatura da função:**`signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* Você pode colocar outras chamadas de API para este método.
>* If the Adobe Experience Cloud JavaScript library is on the page, `submit()` waits for the Cloud to set a cookie before sending a request.


**Teclas de solicitação reservadas**

As seguintes chaves de solicitação são reservadas e não podem ser substituídas por este método:

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Parâmetros**

| Nome | Tipo | Descrição |
|---|---|---|
| `obj` | Objeto | Um objeto que representa os pares de chave-valor para mapeamentos em nível de plataforma. O parâmetro aceita sequências e matrizes como valores de propriedade no objeto. |
| `prefix` | String   | Opcional. O valor da string prefixado para cada chave de objeto (substitui a tecla original). |
| `return` | DIL. api | Retorna o objeto API da instância DIL atual. |

**Resposta**

Returns the API object of the current [!UICONTROL DIL] instance.

**Código de exemplo**

<pre><code>var datalib = DIL. create ({ 
 parceiro: '<i>Partnername</i>' 
 Containernsid: <i>Containernsid</i> }); 
 
// Method 1 
var obj = {key 1: 1, chave 2: 2}; 
Datalib. api. signals (obj,' c_'). submit (); 
 
// Método 2 
datalib. api. signals ({c_ zdid: 54321}). submit (); 
 
// método // enviará'c_ key = a &amp; c_ key = 2 &amp; c_ key = 3 ' para var manager 
var obj = {key: [' a ',' b ',' c ']}; 
Datalib. api. signals (obj,' c_'). submit ();</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [Requisitos de nome para variáveis principais](../features/traits/trait-key-name-requirements.md)


## traits {#traits}

Adiciona sids à string de consulta de uma solicitação pendente.

<!-- 

r_dil_traits.xml

 -->

**Assinatura da função:**`traits:function (sids){}`

>[!NOTE]
>
>Você pode colocar outras chamadas de API para este método.

**Parâmetros**

| Nome | Tipo | Descrição |
|---|---|---|
| `sids` | Matriz | IDs de segmento de característica em uma matriz. |

**Resposta**

Returns the API object of the current [!UICONTROL DIL] instance.

**Código de exemplo**

<pre><code>var partnerobject = DIL. create ({ 
 parceiro: '<i>nome do parceiro</i>', 
 Containernsid: <i>NSID</i> }); 
Partnerobject. api. características (<i>[123, 456, 789]</i>);</code>
</pre>

## logs {#logs}

Adicionar dados a arquivos de registro na solicitação pendente.

<!-- 

r_dil_logs.xml

 -->

**Assinatura da função:**`logs: function {key1:value1, key2:value2}`

**Resposta**

Returns the API object of the current [!UICONTROL DIL] instance.

**Código de exemplo**

<pre><code>var partnerobject = DIL. create ({ 
 parceiro: '<i>partner</i>', 
 Containernsid: <i>NSID</i> }); 
Partnerobject. api. logs ({ 
 arquivo: ' dil. js ', 
 mensagem: ' Esta é a primeira solicitação '});</code>
</pre>

## submit {#submit}

Submits all pending data to Audience Manager for the [!UICONTROL DIL] instance.

<!-- 

r_dil_submit.xml

 -->

**Assinatura da função:**`submit: function () {}`

>[!NOTE]
>
>Você pode colocar outras chamadas de API para este método. Also, [!UICONTROL DIL] writes encoded data to a destination cookie. For example, spaces are encoded as `%20` and semicolons as `%3B`.

**Resposta**

Returns the API object of the current [!UICONTROL DIL] instance.

**Código de exemplo**

<pre><code>var datalib = DIL. create ({ 
 parceiro: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. características ([<i>123,456, 
789</i>]). logs ({ 
 arquivo: ' dil. js ', 
 mensagem: ' Esta é a primeira solicitação '}). 
sinais ({ 
 c_ zdid: <i>1111</i> 
 d_ dma: '<i>default</i>'}). 
submit ();</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [Requisitos de prefixo para variáveis principais](../features/traits/trait-variable-prefixes.md)


## afterResult {#afterresult}

Uma função executada depois do retorno de chamada de publicação de destino padrão.

<!-- 

r_dil_after_result.xml

 -->

**Assinatura da função:**`afterResult: function (fn) {}`

>[!NOTE]
>
>Você pode colocar outras chamadas de API para este método.

**Parâmetros**

| Nome | Tipo | Descrição |
|---|---|---|
| `fn` | Função | A função que você deseja executar depois que JSON é processada pelo retorno padrão que lida com a publicação de destino. |

**Resposta**

Returns an API object of the current [!UICONTROL DIL] instance.

**Código de exemplo**

<pre><code>var datalib = DIL. create ({ 
 parceiro: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. signals ({ 
 c_ zdid: <i>54321</i> 
 d_ dma: '<i>default</i>'}). 
afterresult (function (json) { 
 //Do algo com os dados JSON retornados do servidor. 
}).submit();
</code></pre>

## clearData {#cleardata}

Apaga todos os dados em uma solicitação pendente.

<!-- 

r_dil_clear_data.xml

 -->

**Assinatura da função:**`clearData: function () {}`

>[!NOTE]
>
>Você pode colocar outras chamadas de API para este método.

**Resposta**

Returns the API object of the current [!UICONTROL DIL] instance.

**Código de exemplo**

<pre><code>var datalib = DIL. create ({ 
 parceiro: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. características ([<i>123,456, 789</i>]). logs ({ 
 arquivo: ' dil. js ' 
 mensagem: ' Esta é a primeira solicitação '}). 
sinais ({ 
 c_ zdid: <i>1111</i> 
 d_ dma: '<i>default</i>'}); 
 
//Reset os dados 
pendentes datalib. cleardata ();</code>
</pre>

## customQueryParams {#customqueryparams}

Adiciona parâmetros de consulta personalizados que não são definidos explicitamente pelo servidor de coleta de dados a uma solicitação pendente.

<!-- 

r_dil_custom_query_params.xml

 -->

**Assinatura da função:**`customQueryParams: function (obj) {}`

>[!NOTE]
>
>Você pode colocar outras chamadas de API para este método.

**Teclas de solicitação reservadas**

As seguintes chaves de solicitação são reservadas e não podem ser substituídas por este método:

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Resposta**

Retorna o objeto API da instância DIL atual.

**Código de exemplo**

<pre><code>var partnerobject = DIL. create ({ 
 parceiro: '<i>partner</i>', 
 Containernsid: <i>NSID</i> }); 
Partnerobject. api. customqueryparams ({ 
 nid: 54231, 
 ntype: ' default '});</code>
</pre>

## getContainerNSID {#getcontainernsid}

Returns the value of the container NSID for the [!UICONTROL DIL] instance. Útil para depuração e solução de problemas.

<!-- 

r_dil_get_container_nsid.xml

 -->

**Assinatura da função:**`dil.api.getContainerNSID: function () {}`

**Código de exemplo**

<pre><code>var datalib = DIL. create ({ 
 parceiro: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
//Verify the container NSID 
var nsid = datalib. api. getcontainernsid ();</code>
</pre>

## getEventLog {#geteventlog}

Retorna dados de log de evento classificados cronologicamente como uma matriz de strings. Útil para depuração e solução de problemas.

<!-- 

r_dil_get_event_log.xml

 -->

**Assinatura da função:**`dil.api.getEventLog: function () {}`

**Código de exemplo**

<pre><code>var datalib = DIL. create ({ 
 parceiro: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. características ([<i>123, 456, 789</i>]). logs ({ 
 arquivo: ' dil. js ', 
 mensagem: ' Esta é a primeira solicitação '}); . sinais ({ 
 c_ zdid: <i>1111</i> 
 d_ dma: '<i>default</i>'}); . submit (); 
 
//Check log for messages 
var log = datalib. api. geteventlog (); 
if (log &amp; &amp; log. length) { 
 alert (log. join ('\ n ')); 
} else { 
 alert (' Sem mensagens de registro '); 
}}</code>
</pre>

## getPartner {#getpartner}

Returns the partner name for a [!UICONTROL DIL] instance. Útil para depuração e solução de problemas.

<!-- 

r_dil_get_partner.xml

 -->

**Assinatura da função:**`dil.api.getPartner: function () {}`

**Código de exemplo**

<pre><code>var datalib = DIL. create ({ 
 parceiro: '<i>Partnername</i>' 
 Containernsid: <i>Containernsid</i> }); 
 
//Verify o nome 
do parceiro var parceiro = datalib. api. getpartner ();</code>
</pre>

## getState {#getstate}

Returns the state of the current [!UICONTROL DIL] instance. Útil para depuração e solução de problemas.

<!-- 

r_dil_get_state.xml

 -->

**Assinatura da função:**`dil.api.getState: function () {}`

**Código de exemplo**

<pre><code>var datalib = DIL. create ({ 
 parceiro: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. características ([<i>123, 456, 789</i>]). logs ({ 
 arquivo: ' dil. js ', 
 mensagem: ' Esta é a primeira solicitação '}); . sinais ({ 
 c. zdid: <i>1111</i> 
 d_ dma: '<i>default</i>'}); . submit (); 
 
var state = datalib. api. getstate (); 
 
/* Contorno do objeto de estado estado 
= { 
 Pendingrequest: {<i>dados pendentes para chamada ao servidor</i>}, 
 Otherrequestinfo: {{ 
 Firingqueue: [], 
 acionada: [], 
 acionando: false, 
 erroked: [], 
 Tecdkeys: {{ 
 sids: true, 
 pdata: true, 
 logdata: true, 
 retorno de chamada: true, 
 Postcallbackfn: true, 
 Useimagerequest: true, 
 }, 
 Firstrequesthasfired: false, 
 num_ of_ jsonp_ responses: 0, 
 num_ of_ jsonp_ errors: 0, 
 num_ of_ img_ responses: 0, 
 num_ of_ img_ errors: 0 
 }, 
 Destinationpublishinginfo: {{ 
 THROTTLE_ START: , 000, 
 Throttletimerset: false, 
 id: " destination_ publishing_ iframe_' + partner +'_' + containernsid, 
 url: (constantes. ishttps? ' https://': ' https://fast.') + parceiro +' .demdex.net/dest3.html?d_nsid=' 
 + Containernsid +' #' + encodeuricomponent (document. location. href), 
 iframe: null, 
 Iframehasloaded: false, 
 Sendingmessages: false, 
 mensagens: [], 
 Messagesendinginterval: constantes. POST_ MESSAGE_ ENABLED? 15: 100, 
               //Recommend 100ms for IE 6 &amp; 7, 15ms for other browsers 
               jsonProcessed: [] 
     } 
} 
*/
</code></pre>

## idSync {#idsync}

Consiste de duas funções que permitem que os parceiros de dados trocem e sincronizem as IDs de usuário entre si e o Audience Manager.

<!-- 

r_dil_idsync.xml

 -->

**Assinatura da função:**

Works with [!UICONTROL DIL] versions 2.10 and 3.1 or higher.

<table id="table_ADC7501511914805A6A6B24B2DFEBA51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Código </th> 
   <th colname="col2" class="entry"> Sincroniza as IDs do usuário </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil. Instance. api. idsync (initconfig) </code> </td> 
   <td colname="col2"> <p>Entre parceiros de dados diferentes e Audience Manager. Por exemplo, o parceiro x usaria essa opção para sincronizar uma ID de usuário com o parceiro y e enviá-la para o Audience Manager. </p> <p> <p><b>Importante:</b> Esse método está obsoleto. Please use the <code> idSyncByURL </code> method of the Experience Cloud ID Service instance. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil. Instance. api. aamidsync (initconfig) </code> </td> 
   <td colname="col2"> <p>Quando você já conhece a ID de usuário e deseja enviá-la para o Audience Manager. </p> <p> <p><b>Importante:</b> Esse método está obsoleto. Please use the <code> idSyncByDataSource </code> method of the Experience Cloud ID Service instance. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Elementos idsync**

`idSync` pode consistir no seguinte:

<table id="table_5343BE784E694C67B09A0A8878CF8001"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> Sequência de caracteres </td> 
   <td colname="col3"> <p>A ID do provedor de dados atribuída pelo Audience Manager. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> Sequência de caracteres </td> 
   <td colname="col3"> <p>A ID exclusiva do provedor de dados para o usuário. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> minutesToLive </code> </td> 
   <td colname="col2"> Número </td> 
   <td colname="col3"> <p><i>(Opcional)</i> Define o tempo de expiração do cookie. Deve ser um inteiro. O padrão é de 20160 minutos (14 dias). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> url </code> </td> 
   <td colname="col2"> Sequência de caracteres </td> 
   <td colname="col3"> <p>URL de Destino. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Macros**

`idSync` aceita as seguintes macros:

* **`%TIMESTAMP%`:** gera um carimbo de data e hora (em milissegundos). Usado para eliminação de cache.
* **`%DID%`:** insere a ID do Audience Manager para o usuário.
* **`%HTTP_PROTO%`:** Define o protocolo de página ( `http` ou `https`).

**Resposta**

Both functions return `Successfully queued` if successful. Do contrário, elas retornam uma sequência de mensagem de erro.

**Código de exemplo**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">// Fires url with macros substituiu 
dilinstance. api. idsync ({ 
 dpid: ' 23 ', // deve ser uma string 
 url: '//su.addthis.com/red/usync?pid=16&amp;puid=%DID%&amp;url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net 
% 2 Fibs % 3 Adpid % 3 D 420% 26 dpuuid % 3 D % 7 B % 7 Buid % 7 D % 7 D ', 
 Minutestolive: 20160 // opcional, assume 20160 minutos (14 dias)};</code>
</pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">// Fires ' https:/https:' +'//dpm.demdex.net/ibs:dpid= &lt; dpid &gt; &amp; dpuuid = &lt; dpuuid &gt;' 
dilinstance. api. aamidsync ({ 
 dpid: ' 23 ', // deve ser uma string 
 dpuuid: ' 98765 ', // deve ser uma string 
 Minutestolive: 20160 // opcional, assume 20160 minutos (14 dias)};</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [Funções de sincronização no serviço da Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsync.html)


## result {#result}

Adiciona um retorno de chamada (que recebe JSON) à solicitação pendente.

<!-- 

r_dil_result.xml

 -->

**Assinatura da função:**`result: function (callback) {}`

Esse retorno de chamada substitui o retorno padrão que lida com a publicação de destino.

>[!NOTE]
>
>Você pode colocar outras chamadas de API para este método.

**Parâmetros**

| Nome | Tipo | Descrição |
|---|---|---|
| `callback` | Função | Função javascript executada pelo retorno de chamada JSONP. |

**Resposta**

Returns the API object of the current [!UICONTROL DIL] instance.

**Código de exemplo**

<pre><code>var datalib = DIL. create ({ 
 parceiro: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. características ([<i>123, 456, 789</i>]). result (function (json) { 
 //Do algo, possivelmente com os dados JSON retornados do servidor. 
});.submit();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` é um parâmetro booleano que controla como [!UICONTROL DIL] faz chamadas para o [!UICONTROL Data Collection Servers (DCS)] e Akamai.

<!-- 

dil-secure-data-collection.xml

 -->

* When `secureDataCollection= true` (default), [!UICONTROL DIL] always makes secure, HTTPS calls.

* When `secureDataCollection= false`, [!UICONTROL DIL] makes either HTTP or HTTPS calls by following the security protocol set by the page.

>[!IMPORTANT]
>
>Set `secureDataCollection= false` if you use visitorAPI.js and [!UICONTROL DIL] on the same page. Consulte a amostra de código abaixo.

<pre><code class="js">var dilinstance = DIL. create ({ 
 … 
 Securedatacollection: false});</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [Criação de DIL](../dil/dil-class-overview/dil-create.md#dil-create)


## useCORSOnly {#usecorsonly}

`useCORSOnly` é um parâmetro booleano verdadeiro/falso que controla como o navegador solicita recursos de outros domínios.

<!-- 

dil-use-cors-only.xml

 -->

**Visão geral**

`useCORSOnly` é falso por padrão. Falso significa que o navegador pode realizar verificações de recursos com CORS ou JSONP. However, [!UICONTROL DIL] always tries to request resources with CORS first. Em seguida, reverte para JSONP em navegadores antigos sem suporte ao CORS. If you need to force the browser to use CORS only, such as with sites that have high-security requirements, set `useCORSOnly:true`.

**Amostra de código**

<pre><code class="js">var dilinstance = DIL. create ({ 
 … 
 Usecorsonly: true});</code>
</pre>

>[!IMPORTANT]
>
>* We recommend that you set `useCORSOnly: true` only when you&#39;re sure that your site visitors have browsers that support this feature.
>* When `useCORSOnly: true`, [!UICONTROL DIL] will not make ID calls from Internet Explorer version 9 or older.
>



>[!MORE_ LIKE_ THIS]
>
>* [Criação de DIL](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Serviço da Experience Cloud ID: Usecorsonly](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-use-cors-only.html)
>* [Suporte para CORS no serviço de Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-cors.html)


## useImageRequest {#useimagerequest}

Changes the request type to image `<img>` from script `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**Assinatura da função:**`useImageRequest: function () {}`

>[!NOTE]
>
>Você pode colocar outras chamadas de API para este método.

**Resposta**

Returns an API object of the current [!UICONTROL DIL] instance.

**Código de exemplo**

<pre><code>var datalib = DIL. create ({ 
 parceiro: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. traits ([<i>123, 456, 789</i>]). useimagerequest (). submit ();</code>
</pre>

