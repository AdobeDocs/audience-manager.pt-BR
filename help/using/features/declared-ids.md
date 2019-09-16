---
description: Como as IDs declaradas funcionam, configurar procedimentos, exemplos de código e variáveis.
keywords: id sync
seo-description: Como as IDs declaradas funcionam, configurar procedimentos, exemplos de código e variáveis.
seo-title: IDs declaradas
solution: Audience Manager
title: IDs declaradas
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# IDs declaradas {#declared-ids}

Como as IDs declaradas funcionam, configurar procedimentos, exemplos de código e variáveis.

## Definição de direcionamento ID declarada {#declared-id-targeting}

Troque e sincronize IDs de usuários com o Audience Manager de dispositivos ou navegadores que não usam ou aceitam mecanismos de armazenamento persistentes, como cookies de terceiros.

<!-- declared_id_about.xml -->

## Objetivo da segmentação declarada da ID {#declared-id-targeting-purpose}

Alguns navegadores e a maioria dos dispositivos móveis não aceitam cookies de terceiros. Isso dificulta a retenção de informações sobre os visitantes do site ou a atribuição de IDs persistentes. Para resolver esse problema, o Audience Manager usa [!UICONTROL DIL] para permitir que você passe [!UICONTROL declared IDs] em uma chamada de evento. Além disso, uma [!UICONTROL declared ID] pode agir como uma ID universal que se aplica ao mesmo usuário em todas as soluções no [!DNL Experience Cloud]. A tabela a seguir descreve o processo de definição de metas/correspondência de ID:

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
   <td colname="col2"> <p>Para funcionar, você precisa do <span class="wintitle"> DIL </span> e do código do serviço da <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID </a> na página. <span class="wintitle"> O DIL </span> obtém IDs <span class="wintitle"> declaradas </span> da função <code> setVisitorID </code> fornecida pelo serviço da <span class="keyword"> Experience Cloud ID </span> e as transmite para o <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de correspondência</b> </td> 
   <td colname="col2"> <p>O Audience Manager tenta corresponder a ID do cliente e do visitante com uma ID correspondente em nosso sistema. Se uma ID correspondente não existir, o Audience Manager criará uma nova ID e a associará à ID do cliente e visitante. </p> <p> <p>Observação:  O mapeamento mais recente é usado se sua ID mapear para mais de uma ID do Audience Manager. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de retorno</b> </td> 
   <td colname="col2"> <p>O Audience Manager grava sua ID sincronizada em um cookie primário (ou outro espaço de armazenamento endereçável) no domínio do cliente ou aplicativo. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Chamadas de evento subsequentes</b> </td>
   <td colname="col2"> <p>Chamadas de evento adicionais leem a ID do Audience Manager do domínio do cliente e enviam-na para o Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Para começar, é necessário configurar o serviço de [!DNL Experience Cloud] ID e [!UICONTROL DIL] entre as páginas do site que deseja usar para a coleta de dados. Consulte Criar [e](../dil/dil-class-overview/dil-create.md#dil-create) declarar variáveis [de ID da](../features/declared-ids.md#declared-id-variables)DIL.

## Chamadas de cancelamento {#opt-out-calls}

O [!UICONTROL declared ID] processo atende às preferências do visitante do site para excluir a definição de metas do Audience Manager por seu site. Quando o Audience Manager recebe uma solicitação de recusa, a solicitação [!DNL JSON] retornada pelo [!UICONTROL DCS] contém o código de erro 171, com a mensagem "Encontrada tag de recusa", em vez da ID de usuário do Audience Manager.

* O Audience Manager pode enviar uma [!UICONTROL declared ID] opção de não participação ao lado de um Audience Manager [!UICONTROL UUID] no [!DNL URL].
* A [!UICONTROL declared ID] opção de não participação é armazenada no [!UICONTROL Profile Cache Server ([!UICONTROL PCS]) por parceiro. Não há cancelamento de nível de plataforma usando [!UICONTROL declared IDs]. Além disso, o Audience Manager recusa o usuário daquela região específica na borda (a opção de não participação não atravessa [!UICONTROL DCS] regiões).

Consulte Privacidade [de](../overview/data-security-and-privacy/data-privacy.md) dados para obter mais informações sobre como recusar a coleta de dados.

## Exemplos de cancelamento de ID declarada {#opt-out-examples}

É possível fazer solicitações de [!UICONTROL declared ID] recusa com os pares de valor-chave `d_cid` e valor- `d_cid_ic` chave. Os parâmetros herdados como `d_dpid` e `d_dpuuid` ainda funcionam, mas são considerados obsoletos. Consulte [CID substitui DPID e DPUUID](../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

### Opções com CID e CID_IC

Para obter uma descrição e sintaxe, consulte Variáveis e sintaxe [URL para IDs](../features/declared-ids.md#variables-and-syntax)declaradas.

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opção de não participação usando </th> 
   <th colname="col2" class="entry"> Amostra de código </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Uma ID de provedor de dados e ID de usuário. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domínio</i>/demoptout.jpg?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Um código de integração e ID de usuário. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domínio nome</i>/demoptout?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vários pares <code> d_cid </code> e <code> d_cid_ic de </code> valores chave. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domínio nome</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Opções com DPID, DPUUID e UUID (obsoleto)

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
   <td colname="col1"> <p> <code> d_uuid </code> apenas </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=ID do AAM </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Opção de não participação no nível do parceiro </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= ID de usuário do DPS&amp;d_dpid= ID do provedor de dados </code> </p> <p>Uma opção de não participação em nível de parceiro é armazenada para o mapeamento mais recente desse <code> par dpid </code> + <code> dpuuid </code> para um UUID do AAM. Se não houver mapeamento existente anteriormente, o Audience Manager verificará se a solicitação contém um UUID do AAM no cookie e, se houver, o usará para armazenar a opção de não participação. Caso contrário, o Audience Manager gera um novo UUID do AAM e armazena a opção de não participação sob ele. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> e d_uuid explícita <code></code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= ID do usuário&amp;d_dpuuid= ID<i></i> do provedor de dados </code> </p> <p> <code> d_uuid </code> sempre tem prioridade. Se a combinação <code> dpid </code> + <code> dpuuid </code> mapear para outro UUID do AAM, a opção de não participação será armazenada no UUID do AAM passado na solicitação ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variáveis e sintaxe para IDs declaradas {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

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
   <td colname="col1"> <p> <code> d_cid = ID<i>do provedor de</i> dados %01ID<i>do</i> usuário </code> </p> </td> 
   <td colname="col2"> <p>Contém uma ID de provedor de dados e uma ID de usuário exclusiva associada em um único par de valores chave. <code> d_cid </code> substitui <code> d_dpid </code> e <code> d_dpuuid </code>, que são considerados obsoletos, mas ainda são suportados. Consulte <a href="../reference/cid.md">CID substitui DPID e DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic = código<i>de</i> integração %01ID<i></i> de usuário </code> </p> </td> 
   <td colname="col2"> <p>Contém um código de integração e uma ID de usuário exclusiva associada em um único par de valor chave. <code> d_cid_ic </code> substitui <code> d_dpid </code> e <code> d_dpuuid </code>, que estão obsoletos, mas ainda são compatíveis. Consulte <a href="../reference/cid.md">CID substitui DPID e DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Chamadas de Evento de Exemplo {#sample-event-calls}

Considerando esses pares de valores chave e sua sintaxe necessária, você faria chamadas de evento, como mostrado abaixo.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> A chamada de evento inclui </th> 
   <th colname="col2" class="entry"> Amostra de código </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Uma ID de provedor de dados e ID de usuário. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domínio nome</i>/evento?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Um código de integração e ID de usuário. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domínio nome</i>/evento?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vários pares <code> d_cid </code> e <code> d_cid_ic de </code> valores chave. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domínio nome</i>/evento?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [CID substitui DPID e DPUUID](../reference/cid.md)


## Variáveis de ID declaradas {#declared-id-variables}

Descreve as variáveis de configuração usadas para passar as IDs declaradas [!UICONTROL DIL] para [!DNL Audience Manager.]

## A DIL usa o serviço da Experience Cloud ID para passar as IDs declaradas {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

Quando usado com o serviço [da](https://marketing.adobe.com/resources/help/en_US/mcvid/)Experience Cloud ID, não é mais necessário passar [!UICONTROL declared IDs] com as variáveis obsoletas `dpid` e `dpuuid` . Em vez disso, as versões atuais de [!UICONTROL DIL] dependem da `visitorService` função para obter o [!UICONTROL declared IDs] da `setCustomerIDs` função no [!UICONTROL Experience Cloud ID Service]. For more information, see [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). Você faria uma chamada `visitorService` como mostrado `DIL.create` abaixo.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

No par de `namespace` chave-valor, `MCORG` está a ID da [!DNL Experience Cloud] organização. Se você não tiver essa ID, poderá encontrá-la na [!UICONTROL Administration] seção do [!DNL Experience Cloud] painel. Você precisa de permissões de administrador para exibir este painel. See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

## Funções obsoletas {#deprecated-functions}

Com as versões mais recentes de [!UICONTROL DIL] (6.2+), você não precisa usar esses pares de valor chave para passar [!UICONTROL declared IDs]. Isso ocorre porque [!UICONTROL DIL] agora depende da `visitorService` função mostrada na amostra de código acima. Esta função é [!UICONTROL declared IDs] da [!UICONTROL Experience Cloud ID Service]. Entretanto, estamos referenciando essas variáveis aqui para fins históricos e herdados. Consulte o código abaixo para obter um exemplo de como configurar `DIL.create` para obter um [!UICONTROL declared ID] do [!UICONTROL Visitor ID Service].
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

O Audience Manager compara e corresponde à ID de usuário combinada `DPID` e `DPUUID` a correspondente no sistema. Se uma ID não existir, o Audience Manager criará uma nova ID de usuário e a sincronizará com a `DPID/DPUUID` combinação. Quando o Audience Manager corresponde ou cria uma ID de usuário (a), ela retorna essa ID na `UUID`[!DNL JSON] resposta ao cookie no domínio do cliente (cookie primário) ou em outro armazenamento local.

Chame essa função quando estiver usando [!UICONTROL DIL] v6.1 ou anterior. No entanto, essa função foi descontinuada em favor da nova versão obtida [!UICONTROL declared IDs] do [!UICONTROL Experience Cloud ID Service].

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
>Observe que é necessário desenvolver programaticamente o código que fornece os valores de ID para as chaves `d_dpuuid` e `d_dpid` .

### Enviar IDs após as instâncias DIL

>[!NOTE]
>
>Se você fizer uma [!DNL API] chamada com uma `declaredID` combinação diferente, a nova combinação será usada apenas para essa chamada. Outras chamadas regulares de evento usarão a `DIL.create` `declaredID` combinação original.

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

A resposta retorna a ID do Audience Manager (por exemplo, `UUID`) que é gravada em um cookie primário no domínio da página.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Não direcionar e recusar chamadas {#do-not-target}

O [!UICONTROL declared ID] processo atende às preferências do visitante do site para excluir a definição de metas do Audience Manager por seu site. Quando o Audience Manager recebe uma solicitação de recusa, o [!UICONTROL DCS] [!DNL JSON] retorna um objeto vazio em vez da ID de usuário do Audience Manager.
