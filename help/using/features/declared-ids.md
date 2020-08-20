---
description: Como as IDs declaradas funcionam, configurar procedimentos, exemplos de código e variáveis.
keywords: id sync
seo-description: Como as IDs declaradas funcionam, configurar procedimentos, exemplos de código e variáveis.
seo-title: IDs declaradas
solution: Audience Manager
title: IDs declaradas
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: ID Syncs
translation-type: tm+mt
source-git-commit: 29708d5fc528ac9da08f4c5a7f2bcaa11b240d8b
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 10%

---


# [!UICONTROL Declared IDs] {#declared-ids}

Como [!UICONTROL declared IDs] trabalhar, configurar procedimentos, exemplos de código e variáveis.

## [!UICONTROL Declared ID] Direcionamento {#declared-id-targeting}

Troque e sincronize IDs de usuários com [!DNL Audience Manager] de dispositivos ou navegadores que não usam ou aceitam mecanismos de armazenamento persistentes, como de terceiros [!DNL cookies].

## Finalidade da [!UICONTROL Declared ID] definição de metas {#declared-id-targeting-purpose}

Alguns navegadores e a maioria dos dispositivos móveis não aceitam [!DNL cookies]navegadores de terceiros. Isso dificulta a retenção de informações sobre visitantes do site ou a atribuição de IDs persistentes. Para resolver esse problema, [!DNL Audience Manager] usa [!UICONTROL DIL] o para permitir que você passe [!UICONTROL declared IDs] em uma chamada de evento. Além disso, uma [!UICONTROL declared ID] pode agir como uma ID universal que se aplica ao mesmo usuário em todas as soluções no [!DNL Experience Cloud]. A tabela a seguir descreve o processo de definição de metas/correspondência de ID:

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
   <td colname="col2"> <p>Para funcionar, você precisa de <span class="wintitle"> DIL </span> e o <a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> código do Adobe Experience Platform Identity Service </a> na página. <span class="wintitle"> O DIL </span> obtém IDs <span class="wintitle"> declaradas </span> da <code> setVisitorID </code> função fornecida pelo Adobe Experience Platform Identity Service <span class="keyword"> e as transmite para </span> Audience Manager <span class="keyword"> </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de correspondência</b> </td> 
   <td colname="col2"> <p>O Audience Manager tenta corresponder a ID do cliente e do visitante a uma ID correspondente em nosso sistema. Se uma ID correspondente não existir, o Audience Manager criará uma nova ID e a associará à ID do cliente e do visitante. </p> <p> <p>Observação:  O mapeamento mais recente é usado se sua ID mapear para mais de uma ID de Audience Manager. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de retorno</b> </td> 
   <td colname="col2"> <p>A Audience Manager grava sua ID sincronizada em um cookie primário (ou outro espaço de armazenamento endereçável) no domínio ou aplicativo do cliente. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Chamadas de Evento subsequentes</b> </td>
   <td colname="col2"> <p>Chamadas de evento adicionais leem a ID de Audience Manager do domínio do cliente e enviam-na para a Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Para começar, é necessário configurar o serviço de [!DNL Experience Cloud] ID e [!UICONTROL DIL] entre as páginas do site que deseja usar para a coleta de dados. Consulte [DIL criar](../dil/dil-class-overview/dil-create.md#dil-create) e [Declarar variáveis](../features/declared-ids.md#declared-id-variables)de ID.

## Chamadas de cancelamento {#opt-out-calls}

O [!UICONTROL declared ID] processo atende às preferências de visitante do site para recusar a [!DNL Audience Manager] definição de metas por seu site. When [!DNL Audience Manager] receives an opt-out request, the [!DNL JSON] returned by the [!DNL DCS] contains the error code 171, with the message `Encountered opt out tag`, instead of the [!DNL Audience Manager] user ID.

* [!DNL Audience Manager] pode passar por uma [!UICONTROL declared ID] opção de não participação ao lado de uma [!DNL Audience Manager] opção [!UICONTROL UUID] no [!DNL URL].
* A [!UICONTROL declared ID] opção de não participação é armazenada no [!UICONTROL Profile Cache Server] ([!UICONTROL PCS]) por parceiro. Não há cancelamento de nível de plataforma usando [!UICONTROL declared IDs]. Além disso, [!DNL Audience Manager] rejeita o usuário daquela região específica na borda (a opção de não participação não atravessa [!DNL DCS] regiões).

Consulte Privacidade [de](../overview/data-security-and-privacy/data-privacy.md) dados para obter mais informações sobre como recusar a coleta de dados.

## [!UICONTROL Declared ID] Exemplos de opção de não participação {#opt-out-examples}

You can make a [!UICONTROL declared ID] opt-out requests with the `d_cid` and `d_cid_ic` key-value pairs. Os parâmetros herdados como `d_dpid` e `d_dpuuid` ainda funcionam, mas são considerados obsoletos. Consulte [CID substitui DPID e DPUUID](../reference/cid.md). Nos exemplos, *itálico* indica um espaço reservado para variável.

### Opt-out com [!UICONTROL CID] e [!UICONTROL CID_IC]

Para obter uma descrição e sintaxe, consulte [Variáveis e sintaxe de URL para IDs declaradas](../features/declared-ids.md#variables-and-syntax).

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recusa de uso </th> 
   <th colname="col2" class="entry"> Amostra de código </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Uma ID de provedor de dados e ID de usuário. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout.jpg?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Um código de integração e ID de usuário. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vários pares <code> d_cid </code> e <code> d_cid_ic </code> valores chave. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Opções com [!UICONTROL DPID], [!UICONTROL DPUUID]e [!UICONTROL UUID] (obsoleto)

Esses métodos ainda funcionam, mas são considerados obsoletos. Essas informações são fornecidas para fins herdados e referência. As opções de não participação herdadas incluem:

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recusar (Obsoleto) </th> 
   <th colname="col2" class="entry"> Amostra de código </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid </code> only </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Opção de não participação no nível do parceiro </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Uma opção de não participação em nível de parceiro é armazenada para o mapeamento mais recente desse par <code> dpid </code> + <code> dpuuid </code> para um UUID AAM. Se não houver mapeamento existente anteriormente, o Audience Manager verifica se a solicitação contém um UUID AAM no cookie e, se houver, o usa para armazenar a opção de não participação. Caso contrário, o Audience Manager gera um novo UUID AAM e armazena a opção de não participação sob ele. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> e explícito <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> sempre tem precedência. Se a combinação <code> dpid </code> + <code> dpuuid </code> mapear para outro UUID AAM, a opção de não participação será armazenada no UUID AAM passado na solicitação ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variáveis e sintaxe para [!UICONTROL Declared IDs] {#variables-and-syntax}

A tabela a seguir lista os pares de valores chave que passam pela ID do provedor de [!DNL Audience Manager] dados e IDs de usuário ou códigos de integração, se usados. Note, *italics* indicates a variable placeholder. Os espaços foram adicionados para facilitar a leitura.

Em cada par de valor chave:

* O `=` símbolo separa a chave de seus valores relacionados.
* O caractere não imprimível [!DNL ASCII] `%01` separa os valores.

<table id="table_DFA9A584A5DE40669EAF0DB62DDC5AAF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variável </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid =<i>data provider ID</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Contém uma ID de provedor de dados e uma ID de usuário exclusiva associada em um único par de valores chave. <code> d_cid </code> substitui <code> d_dpid </code> e <code> d_dpuuid </code>, que são considerados obsoletos, mas ainda são suportados. Consulte <a href="../reference/cid.md">CID substitui DPID e DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Contém um código de integração e uma ID de usuário exclusiva associada em um único par de valor chave. <code> d_cid_ic </code> substitui <code> d_dpid </code> e <code> d_dpuuid </code>, que são obsoletos, mas ainda são compatíveis. Consulte <a href="../reference/cid.md">CID substitui DPID e DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Chamadas de Evento de exemplo {#sample-event-calls}

Considerando esses pares de valor chave e sua sintaxe necessária, você faria chamadas de evento, como mostrado abaixo.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> A chamada do evento inclui </th> 
   <th colname="col2" class="entry"> Amostra de código </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Uma ID de provedor de dados e ID de usuário. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Um código de integração e ID de usuário. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vários pares <code> d_cid </code> e <code> d_cid_ic </code> valores chave. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Variáveis {#declared-id-variables}

Descreve as variáveis de configuração usadas para passar [!UICONTROL declared IDs] para [!UICONTROL DIL] [!DNL Audience Manager.]

## [!UICONTROL DIL] usa a opção [!DNL Adobe Experience Platform Identity Service] para passar [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

Quando usado com o [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html), não é mais necessário passar [!UICONTROL declared IDs] com as variáveis `dpid` e `dpuuid` desaprovadas. Em vez disso, as versões atuais de [!UICONTROL DIL] dependem da `visitorService` função para obter o [!UICONTROL declared IDs] da `setCustomerIDs` função no [!UICONTROL Adobe Experience Platform Identity Service]. For more information, see [Customer IDs and Authentication States](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). Você faria uma chamada `visitorService` como mostrado `DIL.create` abaixo.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

No par de `namespace` chave-valor, `MCORG` está a ID da [!DNL Experience Cloud] organização. Se você não tiver essa ID, poderá encontrá-la na [!UICONTROL Administration] seção do [!DNL Experience Cloud] painel. Você precisa de permissões de administrador para visualização deste painel. See [Administration: Core Services](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html).

## Funções obsoletas {#deprecated-functions}

Com as versões mais recentes de [!UICONTROL DIL] (6.2+), você não precisa usar esses pares de valor chave para passar [!UICONTROL declared IDs]. Isso ocorre porque [!UICONTROL DIL] agora depende da `visitorService` função mostrada na amostra de código acima. Esta função é [!UICONTROL declared IDs] da [!UICONTROL Adobe Experience Platform Identity Service]. Entretanto, estamos referenciando essas variáveis aqui para fins históricos e herdados. Consulte o código abaixo para obter um exemplo de como configurar `DIL.create` para obter um [!UICONTROL declared ID] do [!UICONTROL Visitor ID Service].
A tabela a seguir descreve as variáveis herdadas usadas pelo `declaredId` objeto:

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

### [!UICONTROL DPID] e [!UICONTROL DPUUID]

[!DNL Audience Manager] compara e corresponde à ID combinada `DPID` e `DPUUID` a correspondente do usuário em nosso sistema. Se uma ID não existir, [!DNL Audience Manager] criará uma nova ID de usuário e a sincronizará com a `DPID/DPUUID` combinação. Uma vez que [!DNL Audience Manager] corresponde ou cria uma ID de usuário (a), ela retorna essa ID na `UUID`resposta ao [!DNL JSON] domínio do cliente (primário [!DNL cookie] [!DNL cookie]) ou outro armazenamento local.

Chame essa função quando estiver usando [!UICONTROL DIL] v6.1 ou anterior. No entanto, essa função foi descontinuada em favor da nova versão obtida [!UICONTROL declared IDs] do [!DNL Adobe Experience Platform Identity Service].

```js
DIL.create({
    partner : "partner name",
    declaredId : {
       dpuuid : dpuuid,
       DPID : dpid
    }
 });
```

>[!NOTE]
>
>É necessário desenvolver programaticamente o código que fornece os valores de ID para as chaves `d_dpuuid` e `d_dpid` .

### Enviar IDs após [!UICONTROL DIL] Instanciações

>[!NOTE]
>
>Se você fizer uma [!DNL API] chamada com uma `declaredID` combinação diferente, a nova combinação será usada apenas para essa chamada. Outras chamadas regulares de evento usarão a `DIL.create` combinação original `declaredID` .

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Exemplos de solicitação/resposta {#request-response-examples}

A solicitação envia um provedor de dados e uma ID de usuário para [!DNL Audience Manager]:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

A resposta retorna a ID do Audience Manager (por exemplo, `UUID`) que é gravada em um cookie primário no domínio da página.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Não Público alvo e Chamadas de Recusa {#do-not-target}

O [!UICONTROL declared ID] processo atende às preferências de visitante do site para recusar a [!DNL Audience Manager] definição de metas por seu site. Quando [!DNL Audience Manager] recebe uma solicitação de não participação, a [!DNL DCS] retorna um objeto vazio em vez da ID de [!DNL JSON] [!DNL Audience Manager] usuário.

>[!MORELIKETHIS]
>
>* [CID substitui DPID e DPUUID](../reference/cid.md)

