---
description: Como as IDs declaradas funcionam, configurar procedimentos, exemplos de código e variáveis.
keywords: sincronização de id
seo-description: Como as IDs declaradas funcionam, configurar procedimentos, exemplos de código e variáveis.
seo-title: IDs declaradas
solution: Audience Manager
title: IDs declaradas
uuid: 49 bb 4 f 7 e-b 4 a 7-4 d 87-a 29 c-c 3 dca 036 d 2 a 3
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# IDs declaradas {#declared-ids}

Como as IDs declaradas funcionam, configurar procedimentos, exemplos de código e variáveis.

## Definição de direcionamento ID declarada {#declared-id-targeting}

Troque e sincronize as IDs de usuário com o Audience Manager a partir de dispositivos ou navegadores que não usam ou aceitam mecanismos de armazenamento persistentes, como cookies de terceiros.

<!-- declared_id_about.xml -->

## Objetivo da definição de metas ID declarada {#declared-id-targeting-purpose}

Alguns navegadores e a maioria dos dispositivos móveis não aceitam cookies de terceiros. Isso dificulta a retenção de informações sobre os visitantes do site ou a atribuição de IDs persistentes. Para resolver esse problema, o Audience Manager usa [!UICONTROL DIL] o recurso para permitir que você coloque [!UICONTROL declared IDs] uma chamada de evento. Além disso, a [!UICONTROL declared ID] pode atuar como uma ID universal que se aplica ao mesmo usuário em todas as soluções no [!DNL Experience Cloud]. A tabela a seguir descreve o processo de definição de metas/correspondência da ID:

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
   <td colname="col2"> <p>Para trabalhar, você precisa <span class="wintitle"> do DIL </span> e do <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> código do serviço </a> da Experience Cloud ID na página. <span class="wintitle"> O DIL </span> obtém <span class="wintitle"> IDs </span> declaradas da função <code> setvisitorid </code> fornecida pelo serviço <span class="keyword"> da Experience Cloud ID </span> e passa isso para <span class="keyword"> o Audience Manager </span>. </p> </td> 
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

Para começar, é necessário configurar o [!DNL Experience Cloud] serviço de ID e [!UICONTROL DIL] todas as páginas do site que você deseja usar para a coleta de dados. Consulte [Criar](../dil/dil-class-overview/dil-create.md#dil-create) e criar Variáveis de ID [declarada](../features/declared-ids.md#declared-id-variables).

## Chamadas de não participação {#opt-out-calls}

O [!UICONTROL declared ID] processo respeita as preferências do visitante do site para recusar a segmentação do Audience Manager por site. Quando o Audience Manager recebe uma solicitação de não participação, o [!DNL JSON] retornado pelo [!UICONTROL DCS] contém o código de erro 171, com a mensagem "Tag de recusa encontrada", em vez da ID de usuário do Audience Manager.

* O Audience Manager pode passar uma [!UICONTROL declared ID] opção de não participação junto com um Audience Manager [!UICONTROL UUID] no [!DNL URL].
* A [!UICONTROL declared ID] opção de não participação é armazenada no [! UICONTROL Profile Cache ([!UICONTROL PCS]), com base em parceiro. Não [!UICONTROL declared IDs]há nenhuma opção de recusa no nível da plataforma. Além disso, o Audience Manager opta por afastar o usuário daquela região específica na borda (a opção de não participação não se cruza [!UICONTROL DCS] com regiões cruzadas).

Consulte [Privacidade](../overview/data-security-and-privacy/data-privacy.md) de dados para obter mais informações sobre como recusar a coleta de dados.

## Exemplos de não participação da ID declarada {#opt-out-examples}

Você pode fazer uma solicitação [!UICONTROL declared ID] de não participação com pares de valores-chave `d_cid` e `d_cid_ic` de valor. Os parâmetros herdados, como `d_dpid` e `d_dpuuid` ainda funcionam, mas são considerados obsoletos. Consulte [CID substitui DPID e DPUUID](../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

### Opções com CID e CID_ IC

Para obter uma descrição e sintaxe, consulte [Variáveis de URL e Sintaxe para IDs declaradas](../features/declared-ids.md#variables-and-syntax).

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
   <td colname="col1"> <p>Vários <code> pares d_ cid </code> e <code> d_ cid_ ic </code> -value pares. </p> </td> 
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
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= de usuário e d_ dpid = ID do provedor de dados </code> </p> <p>Uma opção de não participação de nível de parceiro é armazenada para o mapeamento mais recente desse <code> dpid </code> + <code> dpuuid </code> par para um UUID AAM. Se não houver um mapeamento existente, o Audience Manager verificará se a solicitação contém um UUID AAM no cookie e, se isso fizer, usa o recurso para armazenar a opção de não participação. Caso contrário, o Audience Manager gera um novo AAM UUID e armazena a opção de não participação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpuuid </code> + <code> d_ dpid </code> e explícitos <code> d_ uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=<i></i>de usuário e d_ dpuuid = ID de usuário e<i>d_ dpid do provedor de dados = ID do provedor de dados</i></code> </p> <p> <code> d_ uuid </code> sempre tem precedência. Se a combinação <code> dpid </code> + <code> dpuuid </code> for mapeada para outro UUID AAM, a opção de não participação será armazenada na UUID AAM transmitida na solicitação ( <code> d_ uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variáveis e sintaxe para IDs declaradas {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

A tabela a seguir lista os pares de valores chave que passam a sua ID do provedor [!DNL Audience Manager] de dados e IDs de usuário ou códigos de integração, se forem usados. Note, *italics* indicates a variable placeholder. Os espaços foram adicionados para facilitar a leitura.

Em cada par de valor chave:

* O `=` símbolo separa a chave de seus valores relacionados.
* O caractere não imprimível [!DNL ASCII]`%01` separa os valores.

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

## Exemplo de chamadas de evento {#sample-event-calls}

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
   <td colname="col1"> <p>Vários <code> pares d_ cid </code> e <code> d_ cid_ ic </code> -value pares. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nome</i>/evento? d_ cid = 123% 01987 &amp; d_ cid_ ic = 456% 01321… </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [CID substitui DPID e DPUUID](../reference/cid.md)


## Variáveis declaradas de ID {#declared-id-variables}

Descreve as variáveis de configuração usadas para passar IDs declaradas até [!UICONTROL DIL] a [!DNL Audience Manager.]

## DIL usa o serviço da Experience Cloud ID para enviar IDs declaradas {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

Quando usada com o serviço [da Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/), você não precisa mais passar [!UICONTROL declared IDs] com as `dpid``dpuuid` variáveis obsoletas e desatualizadas. Em vez disso, as versões atuais [!UICONTROL DIL] dependem da `visitorService` função para obter a [!UICONTROL declared IDs] partir da `setCustomerIDs` função no [!UICONTROL Experience Cloud ID Service]. For more information, see [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). Você chamaria `visitorService` como `DIL.create` mostrado abaixo.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

No par `namespace` de valor chave, `MCORG` é a ID [!DNL Experience Cloud] da organização. Se você não tiver essa ID, poderá encontrá-la na [!UICONTROL Administration] seção do [!DNL Experience Cloud] painel. Você precisa de permissões de administrador para visualizar esse painel. See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

## Funções obsoletas {#deprecated-functions}

Com as versões mais recentes de [!UICONTROL DIL] (6.2 +), você não precisa usar esses pares de valores chave para passar [!UICONTROL declared IDs]. Isso ocorre porque [!UICONTROL DIL] agora depende da `visitorService` função mostrada na amostra de código acima. Essa função provém [!UICONTROL declared IDs] do [!UICONTROL Experience Cloud ID Service]. No entanto, estamos mencionando essas variáveis aqui para fins históricos e herdados. Consulte o código abaixo para ver como configurar `DIL.create` para obter a [!UICONTROL declared ID] partir [!UICONTROL Visitor ID Service]do.
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

### `DPID` e `DPUUID`

O Audience Manager compara e corresponde à ID de usuário combinada `DPID` e `DPUUID` correspondente em nosso sistema. Se uma ID não existir, o Audience Manager criará uma nova ID de usuário e a sincroniza à `DPID/DPUUID` combinação. Quando o Audience Manager corresponde ou cria uma ID de usuário (o) `UUID`retorna essa ID na [!DNL JSON] resposta ao cookie no domínio do cliente (cookie primário) ou outro armazenamento local.

Chame esta função ao usar [!UICONTROL DIL] v 6.1 ou anterior. No entanto, essa função foi substituída por uma nova versão que provém [!UICONTROL declared IDs] do [!UICONTROL Experience Cloud ID Service].

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
>Observe que é necessário desenvolver programaticamente o código que fornece os valores de ID para as chaves `d_dpuuid` e `d_dpid` para as chaves.

### Enviar IDs após Instanciamentos DIL

>[!NOTE]
>
>Se [!DNL API] você fizer uma chamada com `declaredID` uma combinação diferente, a nova combinação será usada apenas para essa chamada. Outras chamadas de evento regulares usarão a `DIL.create``declaredID` combinação original.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Exemplos de solicitação/resposta {#request-response-examples}

A solicitação envia um provedor de dados e uma ID de usuário para o Audience Manager:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

A resposta retorna a ID do Audience Manager (por exemplo `UUID`,) que é gravada em um cookie primário no domínio da página.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Não segmentar e realizar chamadas de não participação {#do-not-target}

O [!UICONTROL declared ID] processo respeita as preferências do visitante do site para recusar a segmentação do Audience Manager por site. Quando o Audience Manager recebe uma solicitação de não participação, o [!UICONTROL DCS] retorna um [!DNL JSON] objeto vazio em vez da ID de usuário do Audience Manager.
