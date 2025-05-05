---
description: As APIs de DIL no nível da instância permitem criar e trabalhar programaticamente com objetos Audience Manager. Os métodos de nível de instância aprimoram a funcionalidade da API estabelecida pelos métodos de nível de classe.
keywords: criar características;criar característica
seo-description: The instance-level DIL APIs let you programmatically create and work with Audience Manager objects. The instance-level methods enhance API functionality established by the class-level methods.
seo-title: Instance-level DIL Methods
solution: Audience Manager
title: Métodos de DIL em nível de instância
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
feature: DIL Implementation
exl-id: 0342439d-708e-461c-b155-a3ee423f5437
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '1126'
ht-degree: 13%

---

# Métodos de DIL em nível de instância{#instance-level-dil-methods}

>[!WARNING]
>
>A partir de julho de 2023, o Adobe descontinuou o desenvolvimento da extensão [!DNL Data Integration Library (DIL)] e [!DNL DIL].
>
>Os clientes existentes podem continuar usando a implementação [!DNL DIL]. Entretanto, o Adobe não desenvolverá [!DNL DIL] além deste ponto. Os clientes são incentivados a avaliar o [SDK da Web do Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) para sua estratégia de coleta de dados de longo prazo.
>
>Os clientes que desejam implementar novas integrações de coleção de dados após julho de 2023 devem usar o [SDK da Web do Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en).

As APIs do [!UICONTROL DIL] no nível da instância permitem que você crie e trabalhe programaticamente com objetos Audience Manager. Os métodos de nível de instância aprimoram a funcionalidade da API estabelecida pelos métodos de nível de classe.

## Introdução aos Métodos de DIL em nível de instância {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

Ao trabalhar com as APIs [!UICONTROL DIL] no nível da instância:

* O Access exige um nome de parceiro e uma ID de namespace de contêiner (NSID). Entre em contato com o gerente de conta do Audience Manager para obter essas informações.
* Substitua qualquer texto de amostra *em itálico* na documentação da API por valor, ID ou outra variável, conforme exigido pelo método com o qual você está trabalhando.

<!-- 

c_instance_start.xml

 -->

## sinais {#signals}

Adiciona mapeamentos de nível de cliente e plataforma à sequência de consulta de uma solicitação pendente.

<!-- 

r_dil_signals.xml

 -->

**Assinatura da Função:** `signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* Você pode encadear outras chamadas de API a esse método.
>* Se a biblioteca JavaScript do Adobe Experience Cloud estiver na página, `submit()` aguardará que a Nuvem defina um cookie antes de enviar uma solicitação.

**Chaves de solicitação reservadas**

As chaves de solicitação a seguir estão reservadas e não podem ser substituídas por este método:

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Parâmetros**

| Nome | Tipo | Descrição |
|---|---|---|
| `obj` | Objeto | Um objeto que representa os pares de valores chave para mapeamentos no nível da plataforma. O parâmetro aceita strings e matrizes como valores de propriedade no objeto. |
| `prefix` | String   | Opcional. O valor da string prefixado para cada chave do objeto (substitui a chave original). |
| `return` | DIL.api | Retorna o objeto de API da instância DIL atual. |

**Resposta**

Retorna o objeto de API da instância [!UICONTROL DIL] atual.

**Código de exemplo**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
// Method 1 
var obj = { key1 : 1, key2 : 2 }; 
dataLib.api.signals(obj, 'c_').submit(); 
 
// Method 2 
dataLib.api.signals({c_zdid: 54321}).submit(); 
 
// Method 3 
// Will send 'c_key=a&c_key=2&c_key=3' to Audience Manager 
var obj = { key : ['a', 'b', 'c'] }; 
dataLib.api.signals(obj, 'c_').submit(); 
</code></pre>

## traits {#traits}

Adiciona SIDs à sequência de consulta de uma solicitação pendente.

<!-- 

r_dil_traits.xml

 -->

**Assinatura da função:** `traits:function (sids){}`

>[!NOTE]
>
>Você pode encadear outras chamadas de API a esse método.

**Parâmetros**

| Nome | Tipo | Descrição |
|---|---|---|
| `sids` | Matriz | IDs de segmento de característica em uma matriz. |

**Resposta**

Retorna o objeto de API da instância [!UICONTROL DIL] atual.

**Código de exemplo**

<pre><code>
var partnerObject = DIL.create(&lbrace; 
     partner: '<i>partner name</i>', 
     containerNSID: <i>NSID</i> 
&rbrace;); 
partnerObject.api.traits(<i>[123, 456, 789]</i>); 
</code></pre>

## logs {#logs}

Adicionar dados aos arquivos de log na solicitação pendente.

<!-- 

r_dil_logs.xml

 -->

**Assinatura da função:** `logs: function {key1:value1, key2:value2}`

**Resposta**

Retorna o objeto de API da instância [!UICONTROL DIL] atual.

**Código de exemplo**

<pre><code>
var partnerObject = DIL.create(&lbrace; 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
&rbrace;); 
partnerObject.api.logs(&lbrace; 
     file: 'dil.js', 
     message: 'This is the first request' 
&rbrace;);
</code></pre>

## submit {#submit}

Envia todos os dados pendentes para o Audience Manager da instância [!UICONTROL DIL].

<!-- 

r_dil_submit.xml

 -->

**Assinatura da Função:** `submit: function () {}`

>[!NOTE]
>
>Você pode encadear outras chamadas de API a esse método. Além disso, [!UICONTROL DIL] grava dados codificados em um cookie de destino. Por exemplo, espaços são codificados como `%20` e ponto e vírgula como `%3B`.

**Resposta**

Retorna o objeto de API da instância [!UICONTROL DIL] atual.

**Código de exemplo**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits(&lbrack; 
<i>123,456, 789</i>&rbrack;).logs(&lbrace; 
     file: 'dil.js', 
     message: 'This is the first request' 
&rbrace;).signals(&lbrace; 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
&rbrace;).submit();
</code></pre>

## afterResult {#afterresult}

Uma função que é executada após o retorno de chamada de publicação de destino padrão.

<!-- 

r_dil_after_result.xml

 -->

**Assinatura da Função:** `afterResult: function (fn) {}`

>[!NOTE]
>
>Você pode encadear outras chamadas de API a esse método.

**Parâmetros**

| Nome | Tipo | Descrição |
|---|---|---|
| `fn` | Função | A função que você deseja executar depois que o JSON é processado pelo retorno de chamada padrão que lida com a publicação de destino. |

**Resposta**

Retorna um objeto de API da instância [!UICONTROL DIL] atual.

**Código de exemplo**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.signals(&lbrace; 
     c_zdid: <i>54321</i> 
     d_dma: '<i>default</i>' 
&rbrace;).afterResult(function(json)&lbrace; 
     //Do something with the JSON data returned from the server. 
&rbrace;).submit();
</code></pre>

## clearData {#cleardata}

Limpa todos os dados em uma solicitação pendente.

<!-- 

r_dil_clear_data.xml

 -->

**Assinatura da Função:** `clearData: function () {}`

>[!NOTE]
>
>Você pode encadear outras chamadas de API a esse método.

**Resposta**

Retorna o objeto de API da instância [!UICONTROL DIL] atual.

**Código de exemplo**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123,456, 789</i>]).logs(&lbrace; 
     file: 'dil.js' 
     message: 'This is the first request' 
&rbrace;).signals(&lbrace; 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
&rbrace;); 
 
//Reset the pending data 
dataLib.clearData();
</code></pre>

## customQueryParams {#customqueryparams}

Adiciona parâmetros de consulta personalizados não definidos explicitamente pelo servidor de coleta de dados a uma solicitação pendente.

<!-- 

r_dil_custom_query_params.xml

 -->

**Assinatura da Função:** `customQueryParams: function (obj) {}`

>[!NOTE]
>
>Você pode encadear outras chamadas de API a esse método.

**Chaves de solicitação reservadas**

As chaves de solicitação a seguir estão reservadas e não podem ser substituídas por este método:

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Resposta**

Retorna o objeto de API da instância DIL atual.

**Código de exemplo**

<pre><code>
var partnerObject = DIL.create(&lbrace; 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
&rbrace;); 
partnerObject.api.customQueryParams(&lbrace; 
     nid: 54231, 
     ntype: 'default' 
&rbrace;); 
</code></pre>

## getContainerNSID {#getcontainernsid}

Retorna o valor da NSID do contêiner da instância [!UICONTROL DIL]. Útil para depuração e solução de problemas.

<!-- 

r_dil_get_container_nsid.xml

 -->

**Assinatura da Função:** `dil.api.getContainerNSID: function () {}`

**Código de exemplo**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
//Verify the container NSID 
var nsid = dataLib.api.getContainerNSID();
</code></pre>

## getEventLog {#geteventlog}

Retorna dados do log de eventos classificados cronologicamente como uma matriz de cadeias de caracteres. Útil para depuração e solução de problemas.

<!-- 

r_dil_get_event_log.xml

 -->

**Assinatura da Função:** `dil.api.getEventLog: function () {}`

**Código de exemplo**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs(&lbrace; 
     file: 'dil.js', 
     message: 'This is the first request' 
&rbrace;);.signals(&lbrace; 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
&rbrace;);.submit(); 
 
//Check log for messages 
var log = dataLib.api.getEventLog(); 
if (log && log.length) &lbrace; 
     alert(log.join('\n')); 
&rbrace;else&lbrace; 
     alert('No log messages'); 
&rbrace;
</code></pre>

## getPartner {#getpartner}

Retorna o nome do parceiro de uma instância [!UICONTROL DIL]. Útil para depuração e solução de problemas.

<!-- 

r_dil_get_partner.xml

 -->

**Assinatura da Função:** `dil.api.getPartner: function () {}`

**Código de exemplo**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
//Verify the partner name 
var partner = dataLib.api.getPartner();
</code></pre>

## getState {#getstate}

Retorna o estado da instância [!UICONTROL DIL] atual. Útil para depuração e solução de problemas.

<!-- 

r_dil_get_state.xml

 -->

**Assinatura da Função:** `dil.api.getState: function () {}`

**Código de exemplo**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs(&lbrace; 
     file: 'dil.js', 
     message:'This is the first request' 
&rbrace;);.signals(&lbrace; 
     c.zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
&rbrace;);.submit(); 
 
var state = dataLib.api.getState(); 
 
/*Object outline of state 
state = &lbrace; 
     pendingRequest: {<i>pending data for call to server</i>}, 
     otherRequestInfo:&lbrace; 
          firingQueue: [], 
          fired: [], 
          firing: false, 
          errored: [], 
          reservedKeys: &lbrace; 
               sids: true, 
               pdata: true, 
               logdata: true, 
               callback: true, 
               postCallbackFn: true, 
               useImageRequest: true, 
          &rbrace;, 
          firstRequestHasFired: false, 
          num_of_jsonp_responses: 0, 
          num_of_jsonp_errors: 0, 
          num_of_img_responses: 0, 
          num_of_img_errors: 0 
     &rbrace;, 
     destinationPublishingInfo: &lbrace; 
          THROTTLE_START: 3000, 
          throttleTimerSet: false, 
          id: ''destination_publishing_iframe_' + partner + '_' + containerNSID, 
          url: (constants.isHTTPS ? 'https://' : 'https://fast.') + partner + '.demdex.net/dest3.html?d_nsid=' 
          &#x200B;+ containerNSID + '#' + encodeURIComponent(document.location.href), 
               iframe: null, 
               iframeHasLoaded: false, 
               sendingMessages: false, 
               messages: [], 
               messageSendingInterval: constants.POST_MESSAGE_ENABLED ? 15: 100, 
               //Recommend 100ms for IE 6 & 7, 15ms for other browsers 
               jsonProcessed: [] 
     &rbrace; 
&rbrace; 
*/
</code></pre>

## idSync {#idsync}

Consiste em duas funções que permitem aos parceiros de dados trocar e sincronizar IDs de usuário entre eles e o Audience Manager.

<!-- 

r_dil_idsync.xml

 -->

**Assinatura da Função:**

Funciona com [!UICONTROL DIL] versões 2.10 e 3.1 ou superior.

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
   <td colname="col2"> <p>Entre os diferentes parceiros de dados e o Audience Manager. Por exemplo, o parceiro x usaria essa opção para sincronizar uma ID de usuário com o parceiro y e enviá-la para o Audience Manager. </p> <p> <p><b>Importante:</b> este método foi preterido. Use o método <code> idSyncByURL </code> da instância do Adobe Experience Platform Identity Service. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>Quando você já conhece a ID de usuário e deseja enviá-la para o Audience Manager. </p> <p> <p><b>Importante:</b> este método foi preterido. Use o método <code> idSyncByDataSource </code> da instância do Adobe Experience Platform Identity Service. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Elementos de idSync**

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
   <td colname="col3"> <p>A ID única do provedor de dados para o usuário. </p> </td> 
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

* **`%TIMESTAMP%`:** Gera um carimbo de data/hora (em milissegundos). Usado para eliminação de cache.
* **`%DID%`:** Insere a ID do Audience Manager para o usuário.
* **`%HTTP_PROTO%`:** Define o protocolo da página ( `http` ou `https`).

**Resposta**

Ambas as funções retornam `Successfully queued` se bem-sucedidas. Do contrário, elas retornam uma sequência de mensagem de erro.

**Código de exemplo**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">
// Fires url with macros replaced 
dilInstance.api.idSync(&lbrace; 
 dpid: '23', // must be a string 
 url: '//su.addthis.com/red/usync?pid=16&puid=%DID%&url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net 
%2Fibs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7D%7D', 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
&rbrace;);
</code></pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">
// Fires 'https:/https:' + '//dpm.demdex.net/ibs:dpid=&lt;dpid&gt;&dpuuid=&lt;dpuuid&gt;' 
dilInstance.api.aamIdSync(&lbrace; 
 dpid: '23', // must be a string 
 dpuuid: '98765', // must be a string 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
&rbrace;);
</code></pre>

## resultado {#result}

Adiciona um retorno de chamada (que recebe JSON) à solicitação pendente.

<!-- 

r_dil_result.xml

 -->

**Assinatura da Função:** `result: function (callback) {}`

Esse retorno de chamada substitui o retorno de chamada padrão que lida com a publicação de destino.

>[!NOTE]
>
>Você pode encadear outras chamadas de API a esse método.

**Parâmetros**

| Nome | Tipo | Descrição |
|---|---|---|
| `callback` | Função | Função JavaScript executada pelo retorno de chamada JSONP. |

**Resposta**

Retorna o objeto de API da instância [!UICONTROL DIL] atual.

**Código de exemplo**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).result(function(json)&lbrace; 
     //Do something, possibly with the JSON data returned from the server. 
&rbrace;);.submit();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` é um parâmetro booleano que controla como [!UICONTROL DIL] faz chamadas para [!UICONTROL Data Collection Servers (DCS)] e Akamai.

<!-- 

dil-secure-data-collection.xml

 -->

* Quando `secureDataCollection= true` (padrão), [!UICONTROL DIL] sempre faz chamadas HTTPS seguras.

* Quando `secureDataCollection= false`, [!UICONTROL DIL] faz chamadas HTTP ou HTTPS seguindo o protocolo de segurança definido pela página.

>[!IMPORTANT]
>
>Defina `secureDataCollection= false` se você usar visitorAPI.js e [!UICONTROL DIL] na mesma página. Consulte a amostra de código abaixo.

<pre><code class="js">
var dilInstance = DIL.create(&lbrace; 
     ... 
     secureDataCollection: false 
&rbrace;);
</code></pre>

## useCORSOnly {#usecorsonly}

`useCORSOnly` é um parâmetro booliano true/false que controla como o navegador solicita recursos de outros domínios.

<!-- 

dil-use-cors-only.xml

 -->

**Visão geral**

`useCORSOnly` é falso por padrão. Falso significa que o navegador pode executar verificações de recursos com CORS ou JSONP. No entanto, [!UICONTROL DIL] sempre tenta solicitar recursos com o CORS primeiro. Em seguida, reverte para JSONP em navegadores antigos sem suporte ao CORS. Se for necessário forçar o navegador para usar somente o CORS, como em sites com requisitos de alta segurança, defina `useCORSOnly:true`.

**Amostra de código**

<pre><code class="js">
var dilInstance = DIL.create(&lbrace; 
     ... 
     useCORSOnly: true 
&rbrace;);
</code></pre>

>[!IMPORTANT]
>
>* Recomendamos que você defina o `useCORSOnly: true` somente quando tiver certeza de que os visitantes do site têm navegadores que oferecem suporte a esse recurso.
>* Quando `useCORSOnly: true`, [!UICONTROL DIL] não fará chamadas de ID do Internet Explorer versão 9 ou posterior.
>

## useImageRequest {#useimagerequest}

Altera o tipo de solicitação para imagem `<img>` do script `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**Assinatura da Função:** `useImageRequest: function () {}`

>[!NOTE]
>
>Você pode encadear outras chamadas de API a esse método.

**Resposta**

Retorna um objeto de API da instância [!UICONTROL DIL] atual.

**Código de exemplo**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner:'<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).useImageRequest().submit();
</code></pre>

>[!MORELIKETHIS]
>
>* [Requisitos de nome para variáveis-chave](../features/traits/trait-key-name-requirements.md)
>* [Requisitos de prefixo para variáveis-chave](../features/traits/trait-variable-prefixes.md)
>* [Funções de sincronização no Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/idsync.html)
>* [Criar DIL](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Serviço de Identidade da Adobe Experience Platform: UseCORSOnly](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/use-cors-only.html)
>* [Suporte ao CORS no serviço de identidade da Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/reference/cors.html)
