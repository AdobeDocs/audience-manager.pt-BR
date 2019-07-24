---
description: Como as IDs declaradas funcionam, configurar procedimentos, exemplos de código e variáveis.
keywords: sincronização de id
seo-description: Como as IDs declaradas funcionam, configurar procedimentos, exemplos de código e variáveis.
seo-title: IDs declaradas
solution: Audience Manager
title: IDs declaradas
uuid: 49 bb 4 f 7 e-b 4 a 7-4 d 87-a 29 c-c 3 dca 036 d 2 a 3
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# Declared IDs {#declared-ids}

Como as IDs declaradas funcionam, configurar procedimentos, exemplos de código e variáveis.

## Definição de direcionamento ID declarada {#declared-id-targeting}

Troque e sincronize as IDs de usuário com o Audience Manager a partir de dispositivos ou navegadores que não usam ou aceitam mecanismos de armazenamento persistentes, como cookies de terceiros.

<!-- declared_id_about.xml -->

## Purpose of Declared ID Targeting {#declared-id-targeting-purpose}

Alguns navegadores e a maioria dos dispositivos móveis não aceitam cookies de terceiros. Isso dificulta a retenção de informações sobre os visitantes do site ou a atribuição de IDs persistentes. To resolve this issue, Audience Manager uses [!UICONTROL DIL] to let you pass in [!UICONTROL declared IDs] on an event call. Also, a [!UICONTROL declared ID] can act as a universal ID that applies to the same user across all the solutions in the [!DNL Experience Cloud]. A tabela a seguir descreve o processo de definição de metas/correspondência da ID:

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Processo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Chamada de evento</b> </td> 
   <td colname="col2"> <p>To work, you need <span class="wintitle"> DIL </span> and the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID service </a> code on the page. <span class="wintitle"> O DIL </span> obtém <span class="wintitle"> IDs </span> declaradas da função <code> setvisitorid </code> fornecida pelo serviço <span class="keyword"> da Experience Cloud ID </span> e passa isso para <span class="keyword"> o Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de correspondência</b> </td> 
   <td colname="col2"> <p>O Audience Manager tenta corresponder o cliente e a ID de visitante com uma ID correspondente em nosso sistema. Se uma ID correspondente não existir, o Audience Manager criará uma nova ID e a associará ao cliente e à ID de visitante. </p> <p> <p>Observação: O mapeamento mais recente é usado se a ID mapeia para mais de uma ID do Audience Manager. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de retorno</b> </td> 
   <td colname="col2"> <p>O Audience Manager grava sua ID sincronizada a um cookie primário (ou outro espaço de armazenamento endereçável) no domínio do cliente ou aplicativo. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Chamadas de evento subsequentes</b> </td>
   <td colname="col2"> <p>Chamadas de evento adicionais leiam a ID do Audience Manager do domínio do cliente e enviam-a para o Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

To get started, you need to configure the [!DNL Experience Cloud] ID service and [!UICONTROL DIL] across the pages on your site that you want to use for data collection. See [DIL create](../dil/dil-class-overview/dil-create.md#dil-create) and [Declared ID Variables](../features/declared-ids.md#declared-id-variables).

## Opt-out Calls {#opt-out-calls}

The [!UICONTROL declared ID] process honors site visitor preferences to opt-out of Audience Manager targeting by your website. When Audience Manager receives an opt-out request, the [!DNL JSON] returned by the [!UICONTROL DCS] contains the error code 171, with the message "Encountered opt out tag", instead of the Audience Manager user ID.

* Audience Manager can pass in a [!UICONTROL declared ID] opt-out alongside an Audience Manager [!UICONTROL UUID] in the [!DNL URL].
* The [!UICONTROL declared ID] opt-out is stored in the [!UICONTROL Profile Cache Serveîr ([!UICONTROL PCS]) on a per-partner basis. There is no platform-level opt-out using [!UICONTROL declared IDs]. Additionally, Audience Manager opts the user out from that particular region on the edge (the opt-out does not cross [!UICONTROL DCS] regions).

See [Data Privacy](../overview/data-security-and-privacy/data-privacy.md) for more information about opting-out of data collection.

## Declared ID Opt-Out Examples {#opt-out-examples}

You can make a [!UICONTROL declared ID] opt-out requests with the `d_cid` and `d_cid_ic` key-value pairs. The legacy parameters like `d_dpid` and `d_dpuuid` still work, but are considered deprecated. Consulte [CID substitui DPID e DPUUID](../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

### Opções com CID e CID_ IC

For a description and syntax, see [URL Variables and Syntax for Declared IDs](../features/declared-ids.md#variables-and-syntax).

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opção de não participação </th> 
   <th colname="col2" class="entry"> Amostra de código </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Uma ID do provedor de dados e uma ID de usuário. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>o nome</i>/demoptout.jpg? d_ cid = 123% 01987… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Um código de integração e uma ID de usuário. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>name</i>/demoptout? d_ cid_ ic = 456% 01321… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Multiple <code> d_cid </code> and <code> d_cid_ic </code> key-value pairs. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>name</i>/demoptout? d_ cid = 123% 01987 &amp; d_ cid_ ic = 456% 01321… </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Opções com DPID, DPUUID e UUID (obsoleto)

Esses métodos ainda funcionam, mas são considerados obsoletos. Essas informações são fornecidas para fins herdados e referência. As opções herdadas incluem:

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opção de não participação (obsoleto) </th> 
   <th colname="col2" class="entry"> Amostra de código </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ uuid </code> somente </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=AAM<i></i>ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Opção de não participação do parceiro </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= de usuário e d_ dpid = ID do provedor de dados </code> </p> <p>A partner level opt-out gets stored for the latest mapping of this <code> dpid </code> + <code> dpuuid </code> pair to an AAM UUID. Se não houver um mapeamento existente, o Audience Manager verificará se a solicitação contém um UUID AAM no cookie e, se isso fizer, usa o recurso para armazenar a opção de não participação. Caso contrário, o Audience Manager gera um novo AAM UUID e armazena a opção de não participação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpuuid </code> + <code> d_ dpid </code> e explícitos <code> d_ uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=<i></i>de usuário e d_ dpuuid = ID de usuário e<i>d_ dpid do provedor de dados = ID do provedor de dados</i></code> </p> <p> <code> d_ uuid </code> sempre tem precedência. If the <code> dpid </code> + <code> dpuuid </code> combination maps to another AAM UUID, the opt-out is stored under the AAM UUID passed in the request ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables and Syntax for Declared IDs {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

The following table lists the key-value pairs that pass in your [!DNL Audience Manager] data provider ID and user IDs or integration codes, if used. Note, *italics* indicates a variable placeholder. Os espaços foram adicionados para facilitar a leitura.

Em cada par de valor chave:

* The `=` symbol separates the key from its related values.
* The non-printing [!DNL ASCII] character `%01` separates the values.

<table id="table_DFA9A584A5DE40669EAF0DB62DDC5AAF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variável </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ cid =<i>ID do provedor de dados</i> % 01 ID<i>de usuário</i></code> </p> </td> 
   <td colname="col2"> <p>Contém uma ID do provedor de dados e uma ID de usuário exclusiva associada em um único par de valor chave. <code> d_ cid </code> substitui <code> d_ dpid </code> e <code> d_ dpuuid </code>, que são considerados obsoletos, mas ainda oferecem suporte. Consulte <a href="../reference/cid.md">CID substitui DPID e DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ cid_ ic =<i>código de integração</i> % 01 ID<i>de usuário</i></code> </p> </td> 
   <td colname="col2"> <p>Contém um código de integração e uma ID de usuário exclusiva associada em um único par de valores chave. <code> d_ cid_ ic </code> substitui <code> d_ dpid </code> e <code> d_ dpuuid </code>, que estão obsoletos, mas ainda oferecem suporte. Consulte <a href="../reference/cid.md">CID substitui DPID e DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sample Event Calls {#sample-event-calls}

Considerando estes pares de valor chave e sua sintaxe obrigatória, você faria chamadas de evento como mostrado abaixo.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Chamada de evento inclui </th> 
   <th colname="col2" class="entry"> Amostra de código </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Uma ID do provedor de dados e uma ID de usuário. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nome</i>/evento? d_ cid = 123% 01987… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Um código de integração e uma ID de usuário. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nome</i>/evento? d_ cid_ ic = 456% 01321… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Multiple <code> d_cid </code> and <code> d_cid_ic </code> key-value pairs. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nome</i>/evento? d_ cid = 123% 01987 &amp; d_ cid_ ic = 456% 01321… </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [CID substitui DPID e DPUUID](../reference/cid.md)


## Declared ID Variables {#declared-id-variables}

Describes the configuration variables used to pass declared IDs through [!UICONTROL DIL] to [!DNL Audience Manager.]

## DIL Uses the Experience Cloud ID Service to Pass Declared IDs {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

When used with the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), you no longer need to pass in [!UICONTROL declared IDs] with the deprecated `dpid` and `dpuuid` variables. Instead, the current versions of [!UICONTROL DIL] rely on the `visitorService` function to get the [!UICONTROL declared IDs] from the `setCustomerIDs` function in the [!UICONTROL Experience Cloud ID Service]. For more information, see [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). You would call `visitorService` in `DIL.create` as shown below.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

In the `namespace` key-value pair, `MCORG` is your [!DNL Experience Cloud] Organization ID. If you don't have this ID, you can find it in the [!UICONTROL Administration] section of the [!DNL Experience Cloud] dashboard. Você precisa de permissões de administrador para visualizar esse painel. See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

## Deprecated Functions {#deprecated-functions}

With the latest versions of [!UICONTROL DIL] (6.2+), you don't need to use these key-value pairs to pass in [!UICONTROL declared IDs]. That's because [!UICONTROL DIL] now relies on the `visitorService` function shown in the code sample above. This function gets [!UICONTROL declared IDs] from the [!UICONTROL Experience Cloud ID Service]. No entanto, estamos mencionando essas variáveis aqui para fins históricos e herdados. See the code below for an example of how to configure `DIL.create` to get a [!UICONTROL declared ID] from the [!UICONTROL Visitor ID Service].
The following table describes the legacy variables used by the `declaredId` object:

<table id="table_A1884B72950F4BBDA87F17DDFF173628"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> String   </td> 
   <td colname="col3"> <p>ID do parceiro de dados atribuída pelo Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> Sequência de caracteres </td> 
   <td colname="col3"> <p>A ID exclusiva do provedor de dados para o usuário. </p> </td> 
  </tr> 
 </tbody> 
</table>

### `DPID` e `DPUUID`

Audience Manager compares and matches the combined `DPID` and `DPUUID` to a corresponding user ID in our system. If an ID does not exist, Audience Manager creates a new user ID and synchronizes it to the `DPID/DPUUID` combination. Once Audience Manager matches or creates a user ID (the `UUID`) it returns that ID in the [!DNL JSON] response to the cookie in the client's domain (first-party cookie) or other local storage.

Call this function when you're using [!UICONTROL DIL] v6.1 or earlier. However, this function has been deprecated in favor of the new version that gets [!UICONTROL declared IDs] from the [!UICONTROL Experience Cloud ID Service].

<pre class="js"><code>DIL. create ({ 
 parceiro: " nome do parceiro ", 
 Declaredid: {{ 
 dpuuid: <i>dpuuid</i>, 
 DPID: <i>dpid</i> 
 }} 
 });</code>
</pre>

>[!NOTE]
>
>Note, you need to programmatically develop the code that supplies the ID values for the `d_dpuuid` and `d_dpid` keys.

### Enviar IDs após Instanciamentos DIL

>[!NOTE]
>
>If you make an [!DNL API] call with a different `declaredID` combination, the new combination will be used for that call only. Further regular event calls will use the original `DIL.create`  `declaredID` combination.

<pre class="js"><code>DIL. getdil (' partner name '). api. signals ({…}). declaredid ({ 
 dpuuid:<i>dpuuid</i> 
 dpid:<i>dpid</i> }). 
submit ();</code>
</pre>

## Request/Response Examples {#request-response-examples}

A solicitação envia um provedor de dados e uma ID de usuário para o Audience Manager:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

The response returns the Audience Manager ID (e.g., `UUID`) which is written to a first-party cookie in the page domain.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Do Not Target and Opt-Out Calls {#do-not-target}

The [!UICONTROL declared ID] process honors site visitor preferences to opt-out of Audience Manager targeting by your website. When Audience Manager receives an opt-out request, the [!UICONTROL DCS] returns an empty [!DNL JSON] object instead of the Audience Manager user ID.