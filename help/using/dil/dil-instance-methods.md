---
description: As APIs DIL de nível de instância permitem que você crie e trabalhe programaticamente com objetos do Audience Manager. Os métodos de nível de instância aprimoram a funcionalidade da API estabelecida pelos métodos de nível de classe.
keywords: criar características;criar característica
seo-description: As APIs DIL de nível de instância permitem que você crie e trabalhe programaticamente com objetos do Audience Manager. Os métodos de nível de instância aprimoram a funcionalidade da API estabelecida pelos métodos de nível de classe.
seo-title: Métodos DIL de nível de instância
solution: Audience Manager
title: Métodos DIL de nível de instância
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Métodos DIL de nível de instância{#instance-level-dil-methods}

As [!UICONTROL DIL] APIs de nível de instância permitem que você crie e trabalhe programaticamente com objetos do Audience Manager. Os métodos de nível de instância aprimoram a funcionalidade da API estabelecida pelos métodos de nível de classe.

## Introdução aos Métodos DIL de nível de instância {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

Ao trabalhar com as [!UICONTROL DIL] APIs de nível de instância:

* O acesso requer um nome de parceiro e uma ID de namespace de contêiner (NSID). Entre em contato com o gerente de conta do Audience Manager para obter essas informações.
* Substitua qualquer amostra de texto *em itálico* na documentação da API por valor, ID ou outra variável, conforme exigido pelo método com o qual você está trabalhando.

<!-- 

c_instance_start.xml

 -->

## sinais {#signals}

Adiciona mapeamentos de nível de cliente e plataforma à sequência de caracteres de consulta de uma solicitação pendente.

<!-- 

r_dil_signals.xml

 -->

**** Assinatura da função: `signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* Você pode encadear outras chamadas de API para este método.
>* Se a biblioteca JavaScript da Adobe Experience Cloud estiver na página, `submit()` aguardará que a Cloud defina um cookie antes de enviar uma solicitação.


**Chaves de solicitação reservadas**

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
| `obj` | Objeto | Um objeto que representa os pares de valor chave para mapeamentos no nível da plataforma. O parâmetro aceita sequências de caracteres e matrizes como valores de propriedade no objeto. |
| `prefix` | String   | Opcional. O valor da string prefixado para cada chave de objeto (substitui a chave original). |
| `return` | DIL.api | Retorna o objeto API da instância DIL atual. |

**Resposta**

Retorna o objeto API da [!UICONTROL DIL] instância atual.

**Código de exemplo**

<pre><code>
var dataLib = DIL.create({ parceiro: '<i>partnerName</i>' containerNSID: <i>containerNSID</i> }); 
 
// Método 1 var obj = { key1 : 1, key2 : 2 }; 
dataLib.api.signal(obj, 'c_').submit(); 
 
// Método 2 dataLib.api.signal({c_zdid: 54321}).submit(); 
 
// Método 3 // Enviará 'c_key=a&amp;c_key=2&amp;c_key=3' para o Audience Manager var obj = { key : ['a', 'b', 'c'] }; 
dataLib.api.signal(obj, 'c_').submit(); 
</code></pre>

>[!MORE_LIKE_THIS]
>
>* [Requisitos de nome para variáveis-chave](../features/traits/trait-key-name-requirements.md)


## traits {#traits}

Adiciona SIDs à string de consulta de uma solicitação pendente.

<!-- 

r_dil_traits.xml

 -->

**** Assinatura da função: `traits:function (sids){}`

>[!NOTE]
>
>Você pode encadear outras chamadas de API para este método.

**Parâmetros**

| Nome | Tipo | Descrição |
|---|---|---|
| `sids` | Matriz | IDs de segmento de características em uma matriz. |

**Resposta**

Retorna o objeto API da [!UICONTROL DIL] instância atual.

**Código de exemplo**

<pre><code>
var partnerObject = DIL.create({ parceiro: 'nome<i>do</i>parceiro', containerNSID: <i>NSID</i> }); 
partnerObject.api.traits(<i>[123, 456, 789]</i>); 
</code></pre>

## logs {#logs}

Adicione dados aos arquivos de log na solicitação pendente.

<!-- 

r_dil_logs.xml

 -->

**** Assinatura da função: `logs: function {key1:value1, key2:value2}`

**Resposta**

Retorna o objeto API da [!UICONTROL DIL] instância atual.

**Código de exemplo**

<pre><code>
var partnerObject = DIL.create({ parceiro: '<i>partner</i>', containerNSID: <i>NSID</i> }); 
partnerObject.api.logs({ arquivo: 'dil.js', mensagem: 'Esta é a primeira solicitação' });
</code></pre>

## submit {#submit}

Envia todos os dados pendentes para o Audience Manager para a [!UICONTROL DIL] instância.

<!-- 

r_dil_submit.xml

 -->

**** Assinatura da função: `submit: function () {}`

>[!NOTE]
>
>Você pode encadear outras chamadas de API para este método. Além disso, [!UICONTROL DIL] grava dados codificados em um cookie de destino. Por exemplo, espaços são codificados como `%20` e ponto-e-vírgula como `%3B`.

**Resposta**

Retorna o objeto API da [!UICONTROL DIL] instância atual.

**Código de exemplo**

<pre><code>
var dataLib = DIL.create({ parceiro: '<i>partnerName</i>', containerNSID: <i>containerNSID</i> }); 
 
dataLib.api.traits([<i>123,456, 789</i>]).logs({ arquivo: 'dil.js', mensagem: 'Esta é a primeira solicitação' }).signal({ c_zdid: <i>1111</i> d_dma: '<i>default</i>' }).submit();
</code></pre>

>[!MORE_LIKE_THIS]
>
>* [Requisitos de prefixo para variáveis-chave](../features/traits/trait-variable-prefixes.md)


## afterResult {#afterresult}

Uma função que é executada após o retorno de chamada de publicação de destino padrão.

<!-- 

r_dil_after_result.xml

 -->

**** Assinatura da função: `afterResult: function (fn) {}`

>[!NOTE]
>
>Você pode encadear outras chamadas de API para este método.

**Parâmetros**

| Nome | Tipo | Descrição |
|---|---|---|
| `fn` | Função | A função que você deseja executar após o JSON ser processada pelo retorno de chamada padrão que lida com a publicação de destino. |

**Resposta**

Retorna um objeto API da [!UICONTROL DIL] instância atual.

**Código de exemplo**

<pre><code>
var dataLib = DIL.create({ parceiro: '<i>partnerName</i>', containerNSID: <i>containerNSID</i> }); 
 
dataLib.api.signal({ c_zdid: <i>54321</i> d_dma: '<i>default</i>' }).afterResult(function(json){ //Faça algo com os dados JSON retornados do servidor. 
}).submit();
</code></pre>

## clearData {#cleardata}

Limpa todos os dados em uma solicitação pendente.

<!-- 

r_dil_clear_data.xml

 -->

**** Assinatura da função: `clearData: function () {}`

>[!NOTE]
>
>Você pode encadear outras chamadas de API para este método.

**Resposta**

Retorna o objeto API da [!UICONTROL DIL] instância atual.

**Código de exemplo**

<pre><code>
var dataLib = DIL.create({ parceiro: '<i>partnerName</i>', containerNSID: <i>containerNSID</i> }); 
 
dataLib.api.traits([<i>123,456, 789</i>]).logs({ arquivo: Mensagem 'dil.js': 'Esta é a primeira solicitação' }).signal({ c_zdid: <i>1111</i> d_dma: '<i>default</i>' }); 
 
//Redefina os dados pendentes dataLib.clearData();
</code></pre>

## customQueryParams {#customqueryparams}

Adiciona parâmetros de consulta personalizados que não são explicitamente definidos pelo servidor de coleta de dados a uma solicitação pendente.

<!-- 

r_dil_custom_query_params.xml

 -->

**** Assinatura da função: `customQueryParams: function (obj) {}`

>[!NOTE]
>
>Você pode encadear outras chamadas de API para este método.

**Chaves de solicitação reservadas**

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

<pre><code>
var partnerObject = DIL.create({ parceiro: '<i>partner</i>', containerNSID: <i>NSID</i> }); 
partnerObject.api.customQueryParams({ nid: 54231, tipo: 'default' }); 
</code></pre>

## getContainerNSID {#getcontainernsid}

Retorna o valor do NSID do contêiner para a [!UICONTROL DIL] instância. Útil para depuração e solução de problemas.

<!-- 

r_dil_get_container_nsid.xml

 -->

**** Assinatura da função: `dil.api.getContainerNSID: function () {}`

**Código de exemplo**

<pre><code>
var dataLib = DIL.create({ parceiro: '<i>partnerName</i>', containerNSID: <i>containerNSID</i> }); 
 
//Verifique o contêiner NSID var nsid = dataLib.api.getContainerNSID();
</code></pre>

## getEventLog {#geteventlog}

Retorna dados de log de eventos classificados cronologicamente como uma matriz de strings. Útil para depuração e solução de problemas.

<!-- 

r_dil_get_event_log.xml

 -->

**** Assinatura da função: `dil.api.getEventLog: function () {}`

**Código de exemplo**

<pre><code>
var dataLib = DIL.create({ parceiro: '<i>partnerName</i>', containerNSID: <i>containerNSID</i> }); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ arquivo: 'dil.js', mensagem: 'Esta é a primeira solicitação' });.signal({ c_zdid: <i>1111</i> d_dma: '<i>default</i>' });.submit(); 
 
//Verifique o log para messages var log = dataLib.api.getEventLog(); 
if (log &amp;&amp; log.length) { alert(log.join('\n'); 
}else{ alert('Sem mensagens de registro'); 
}</code></pre>

## getPartner {#getpartner}

Retorna o nome do parceiro para uma [!UICONTROL DIL] instância. Útil para depuração e solução de problemas.

<!-- 

r_dil_get_partner.xml

 -->

**** Assinatura da função: `dil.api.getPartner: function () {}`

**Código de exemplo**

<pre><code>
var dataLib = DIL.create({ parceiro: '<i>partnerName</i>' containerNSID: <i>containerNSID</i> }); 
 
//Verifique o nome do parceiro var partner = dataLib.api.getPartner();
</code></pre>

## getState {#getstate}

Retorna o estado da [!UICONTROL DIL] instância atual. Útil para depuração e solução de problemas.

<!-- 

r_dil_get_state.xml

 -->

**** Assinatura da função: `dil.api.getState: function () {}`

**Código de exemplo**

<pre><code>
var dataLib = DIL.create({ parceiro: '<i>partnerName</i>', containerNSID: <i>containerNSID</i> }); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ arquivo: 'dil.js', mensagem:'Esta é a primeira solicitação' });.signal({ c.zdid: <i>1111</i> d_dma: '<i>default</i>' });.submit(); 
 
var state = dataLib.api.getState(); 
 
/*Contorno do objeto do estado do estado = { pendenteRequest: {dados<i>pendentes para chamada ao servidor</i>}, otherRequestInfo:{ firingQueue: [], acionado: [], acionamento: falso, com erro: [], reservedKeys: { sids: true, pdata: true, logdata: true, retorno de chamada: true, postCallbackFn: true, useImageRequest: true, }, firstRequestHasFired: false, num_of_jsonp_response: 0, num_of_jsonp_errors: 0, num_of_img_response: 0, num_of_img_errors: 0 }, targetPublishingInfo: { THROTTTLE_START: 3000, throttleTimerSet: false, id: ''destino_publishing_iframe_' + parceiro + '_' + containerNSID, url: (constantes.isHTTPS? "https://' : 'https://fast.') + parceiro + '.demdex.net/dest3.html?d_nsid=' + containerNSID + '#' + encodeURIComponent(document.location.href), iframe: null, iframeHasLoaded: false, sendMessages: false, mensagens: [], messageSendingInterval: constantes.POST_MESSAGE_ENABLED ? 15: 100, //Recommend 100ms for IE 6 &amp; 7, 15ms for other browsers jsonProcessed: [] } */</code></pre>

## idSync {#idsync}

Consiste em duas funções que permitem que os parceiros de dados troquem e sincronizem IDs de usuário entre si e o Audience Manager.

<!-- 

r_dil_idsync.xml

 -->

**Assinatura da função:**

Funciona com [!UICONTROL DIL] as versões 2.10 e 3.1 ou superior.

<table id="table_ADC7501511914805A6A6B24B2DFEBA51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Código </th> 
   <th colname="col2" class="entry"> Sincroniza as IDs do usuário </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.idSync(initConfig) </code> </td> 
   <td colname="col2"> <p>Entre diferentes parceiros de dados e o Audience Manager. Por exemplo, o parceiro x usaria isso para sincronizar uma ID de usuário com o parceiro y e enviá-la para o Audience Manager. </p> <p> <p><b></b> Importante:  Este método está obsoleto. Use o método <code> idSyncByURL </code> da instância do Serviço da Experience Cloud ID. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>Quando você já souber a ID de usuário e desejar enviá-la para o Audience Manager. </p> <p> <p><b></b> Importante:  Este método está obsoleto. Use o método <code> idSyncByDataSource </code> da instância do Serviço da Experience Cloud ID. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**elementos idSync**

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
* **`%HTTP_PROTO%`** : Define o protocolo da página ( `http` ou `https`).

**Resposta**

Ambas as funções retornam `Successfully queued` se bem-sucedidas. Do contrário, elas retornam uma sequência de mensagem de erro.

**Código de exemplo**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">
// Dispara o url com macros substituídas dilInstance.api.idSync({ dpid: '23', // deve ser um url de string: '//su.addthis.com/red/usync?pid=16&amp;puid=%DID%&amp;url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net %2Fibs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7D%7D', minutosTo Live: 20160 // opcional, o padrão é 20160 minutos (14 dias) });
</code></pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">
// Aciona 'https:/https:' + '//dpm.demdex.net/ibs:dpid=&lt;dpid&gt;&amp;dpuuid=&lt;dpuuid&gt;' dilInstance.api.aamIdSync({ dpid: '23', // deve ser uma string dpuuid: '98765', // deve ser uma sequência de caracteres minutosToLive: 20160 // opcional, o padrão é 20160 minutos (14 dias) });
</code></pre>

>[!MORE_LIKE_THIS]
>
>* [Funções de sincronização no serviço da Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsync.html)


## result {#result}

Adiciona um retorno de chamada (que recebe JSON) à solicitação pendente.

<!-- 

r_dil_result.xml

 -->

**** Assinatura da função: `result: function (callback) {}`

Esse retorno de chamada substitui o retorno de chamada padrão que lida com a publicação de destino.

>[!NOTE]
>
>Você pode encadear outras chamadas de API para este método.

**Parâmetros**

| Nome | Tipo | Descrição |
|---|---|---|
| `callback` | Função | Função JavaScript executada pelo retorno de chamada JSONP. |

**Resposta**

Retorna o objeto API da [!UICONTROL DIL] instância atual.

**Código de exemplo**

<pre><code>
var dataLib = DIL.create({ parceiro: '<i>partnerName</i>', containerNSID: <i>containerNSID</i> }); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).result(function(json){ //Faça algo, possivelmente com os dados JSON retornados do servidor. 
});.submit();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` é um parâmetro booleano que controla como [!UICONTROL DIL] faz chamadas para o [!UICONTROL Data Collection Servers (DCS)] e o Akamai.

<!-- 

dil-secure-data-collection.xml

 -->

* Quando `secureDataCollection= true` (padrão), [!UICONTROL DIL] sempre efetua chamadas HTTPS seguras.

* Quando `secureDataCollection= false`, [!UICONTROL DIL] faz chamadas HTTP ou HTTPS seguindo o protocolo de segurança definido pela página.

>[!IMPORTANT]
>
>Defina `secureDataCollection= false` se você usa visitorAPI.js e [!UICONTROL DIL] na mesma página. Consulte a amostra de código abaixo.

<pre><code class="js">
var dilInstance = DIL.create({ ... 
     secureDataCollection: false });
</code></pre>

>[!MORE_LIKE_THIS]
>
>* [Criar DIL](../dil/dil-class-overview/dil-create.md#dil-create)


## useCORSOnly {#usecorsonly}

`useCORSOnly` é um parâmetro booleano true/false que controla como o navegador solicita recursos de outros domínios.

<!-- 

dil-use-cors-only.xml

 -->

**Visão geral**

`useCORSOnly` é false por padrão. False significa que o navegador pode executar verificações de recursos com CORS ou JSONP. No entanto, [!UICONTROL DIL] sempre tenta solicitar recursos com o CORS primeiro. Em seguida, reverte para JSONP em navegadores antigos sem suporte ao CORS. Se você precisar forçar o navegador a usar somente CORS, como com sites que têm requisitos de alta segurança, defina `useCORSOnly:true`.

**Amostra de código**

<pre><code class="js">
var dilInstance = DIL.create({ ... 
     useCORSOnly: true });
</code></pre>

>[!IMPORTANT]
>
>* Recomendamos que você defina `useCORSOnly: true` somente quando tiver certeza de que os visitantes do site têm navegadores compatíveis com esse recurso.
>* Quando `useCORSOnly: true`, [!UICONTROL DIL] não fará chamadas de ID do Internet Explorer versão 9 ou anterior.
>



>[!MORE_LIKE_THIS]
>
>* [Criar DIL](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Serviço da Experience Cloud ID: UseCORSOnly](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-use-cors-only.html)
>* [Suporte para CORS no serviço de Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-cors.html)


## useImageRequest {#useimagerequest}

Altera o tipo de solicitação para imagem `<img>` do script `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**** Assinatura da função: `useImageRequest: function () {}`

>[!NOTE]
>
>Você pode encadear outras chamadas de API para este método.

**Resposta**

Retorna um objeto API da [!UICONTROL DIL] instância atual.

**Código de exemplo**

<pre><code>
var dataLib = DIL.create({ parceiro:'<i>partnerName</i>', containerNSID: <i>containerNSID</i> }); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).useImageRequest().submit();
</code></pre>

