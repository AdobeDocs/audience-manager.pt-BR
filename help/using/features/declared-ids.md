---
description: Como as IDs declaradas funcionam, configuram procedimentos, exemplos de código e variáveis.
keywords: sincronização de id
seo-description: Como as IDs declaradas funcionam, configuram procedimentos, exemplos de código e variáveis.
seo-title: IDs declaradas
solution: Audience Manager
title: IDs declaradas
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: Sincronizações de ID
exl-id: a480671a-797d-405d-905d-98ab4ef71369
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1191'
ht-degree: 10%

---

# [!UICONTROL Declared IDs] {#declared-ids}

Como [!UICONTROL declared IDs] funciona, configure procedimentos, exemplos de código e variáveis.

## [!UICONTROL Declared ID] Direcionamento {#declared-id-targeting}

Troque e sincronize as IDs de usuário com [!DNL Audience Manager] de dispositivos ou navegadores que não usam ou aceitam mecanismos de armazenamento persistentes, como [!DNL cookies] de terceiros.

## Finalidade de [!UICONTROL Declared ID] Direcionamento {#declared-id-targeting-purpose}

Alguns navegadores e a maioria dos dispositivos móveis não aceitam [!DNL cookies] de terceiros. Isso dificulta a retenção de informações sobre visitantes do site ou a atribuição de IDs persistentes. Para resolver esse problema, [!DNL Audience Manager] usa [!UICONTROL DIL] para permitir que você passe [!UICONTROL declared IDs] em uma chamada de evento. Além disso, um [!UICONTROL declared ID] pode agir como uma ID universal que se aplica ao mesmo usuário em todas as soluções no [!DNL Experience Cloud]. A tabela a seguir descreve o processo de direcionamento/correspondência da ID:

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
   <td colname="col2"> <p>Para funcionar, você precisa do <span class="wintitle"> DIL </span> e do código <a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> do Adobe Experience Platform Identity Service </a> na página. <span class="wintitle"> O DIL  </span> obtém IDs  <span class="wintitle"> declaradas  </span> da  <code> setVisitorID </code> função fornecida pelo serviço de identidade da  <span class="keyword"> Adobe Experience Platform  </span> e as transmite para o  <span class="keyword"> Audience Manager  </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID da correspondência</b> </td> 
   <td colname="col2"> <p>O Audience Manager tenta corresponder a ID do cliente e do visitante a uma ID correspondente em nosso sistema. Se uma ID correspondente não existir, o Audience Manager criará uma nova ID e a associará à ID do cliente e do visitante. </p> <p> <p>Observação:  O mapeamento mais recente é usado se a ID do mapear para mais de uma ID de Audience Manager. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de retorno</b> </td> 
   <td colname="col2"> <p>O Audience Manager grava sua ID sincronizada em um cookie próprio (ou outro espaço de armazenamento endereçável) no domínio ou aplicativo do cliente. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Chamadas de evento subsequentes</b> </td>
   <td colname="col2"> <p>Chamadas de evento adicionais leem a ID do Audience Manager do domínio do cliente e enviem-na para o Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Para começar, você precisa configurar o serviço de ID [!DNL Experience Cloud] e [!UICONTROL DIL] nas páginas do site que deseja usar para a coleta de dados. Consulte [DIL create](../dil/dil-class-overview/dil-create.md#dil-create) e [Variáveis de ID declaradas](../features/declared-ids.md#declared-id-variables).

## Chamadas de rejeição {#opt-out-calls}

O processo [!UICONTROL declared ID] respeita as preferências do visitante do site para recusar o [!DNL Audience Manager] direcionamento por seu site. Quando [!DNL Audience Manager] recebe uma solicitação de recusa, o [!DNL JSON] retornado pelo [!DNL DCS] contém o código de erro 171, com a mensagem `Encountered opt out tag`, em vez da [!DNL Audience Manager] ID do usuário.

* [!DNL Audience Manager] O pode transmitir uma  [!UICONTROL declared ID] recusa ao lado de um  [!DNL Audience Manager] [!UICONTROL UUID] no  [!DNL URL].
* A opção de não participação [!UICONTROL declared ID] é armazenada no [!UICONTROL Profile Cache Server] ([!UICONTROL PCS]) com base no parceiro. Não há recusa em nível de plataforma usando [!UICONTROL declared IDs]. Além disso, [!DNL Audience Manager] recusa o usuário dessa região específica na borda (a recusa não cruza [!DNL DCS] regiões).

Consulte [Privacidade de dados](../overview/data-security-and-privacy/data-privacy.md) para obter mais informações sobre a recusa da coleta de dados.

## [!UICONTROL Declared ID] Exemplos de rejeição  {#opt-out-examples}

Você pode fazer solicitações de recusa [!UICONTROL declared ID] com os pares de valores chave `d_cid` e `d_cid_ic` . Os parâmetros herdados como `d_dpid` e `d_dpuuid` ainda funcionam, mas são considerados obsoletos. Consulte [CID substitui DPID e DPUUID](../reference/cid.md). Nos exemplos, *itálico* indica um espaço reservado para variável.

### Opt-Outs com [!UICONTROL CID] e [!UICONTROL CID_IC]

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
   <td colname="col1"> <p>Vários pares de valores-chave <code> d_cid </code> e <code> d_cid_ic </code>. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Opt-Outs With [!UICONTROL DPID], [!UICONTROL DPUUID] e [!UICONTROL UUID] (Obsoleto)

Esses métodos ainda funcionam, mas são considerados obsoletos. Essas informações são fornecidas para fins e referência herdados. As opções de rejeição herdadas incluem:

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
   <td colname="col1"> <p>Opt out de nível de parceiro </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Uma recusa em nível de parceiro é armazenada para o mapeamento mais recente desse par <code> dpid </code> + <code> dpuuid </code> para um UUID AAM. Se não houver mapeamento existente anteriormente, o Audience Manager verificará se a solicitação contém um UUID AAM no cookie e, se sim, usará esse para armazenar a recusa. Caso contrário, o Audience Manager gera um novo UUID de AAM e armazena a opção de não participação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> +  <code> d_dpid </code> e explícito  <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> sempre tem precedência. Se a combinação <code> dpid </code> + <code> dpuuid </code> mapear para outro UUID AAM, a recusa será armazenada no UUID AAM transmitido na solicitação ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variáveis e sintaxe para [!UICONTROL Declared IDs] {#variables-and-syntax}

A tabela a seguir lista os pares de valores chave que passam pela ID do provedor de dados [!DNL Audience Manager] e IDs do usuário ou códigos de integração, se usados. Observação: *itálico* indica um espaço reservado para variável. Os espaços foram adicionados para facilitar a leitura.

Em cada par de valor-chave:

* O símbolo `=` separa a chave de seus valores relacionados.
* O caractere [!DNL ASCII] não imprimível `%01` separa os valores.

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
   <td colname="col2"> <p>Contém uma ID de provedor de dados e uma ID de usuário exclusiva associada em um único par de valor-chave. <code> d_cid </code> substitui  <code> d_dpid </code> e  <code> d_dpuuid </code>, que são considerados obsoletos, mas ainda são compatíveis. Consulte <a href="../reference/cid.md">CID substitui DPID e DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Contém um código de integração e uma ID de usuário exclusiva associada em um único par de valor-chave. <code> d_cid_ic </code> substitui  <code> d_dpid </code> e  <code> d_dpuuid </code>, que são obsoletos, mas ainda são compatíveis. Consulte <a href="../reference/cid.md">CID substitui DPID e DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Chamadas de evento de exemplo {#sample-event-calls}

Considerando esses pares de valores chave e sua sintaxe necessária, você faria chamadas de evento como mostrado abaixo.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Inclusão da chamada de evento </th> 
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
   <td colname="col1"> <p>Vários pares de valores-chave <code> d_cid </code> e <code> d_cid_ic </code>. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Variáveis {#declared-id-variables}

Descreve as variáveis de configuração usadas para passar [!UICONTROL declared IDs] por [!UICONTROL DIL] para [!DNL Audience Manager.]

## [!UICONTROL DIL] O usa o  [!DNL Adobe Experience Platform Identity Service] para enviar  [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

Quando usado com o [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html), não é mais necessário transmitir [!UICONTROL declared IDs] com as variáveis `dpid` e `dpuuid` obsoletas. Em vez disso, as versões atuais de [!UICONTROL DIL] dependem da função `visitorService` para obter [!UICONTROL declared IDs] da função `setCustomerIDs` no [!UICONTROL Adobe Experience Platform Identity Service]. Para obter mais informações, consulte [IDs do cliente e Estados de autenticação](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). Você chamaria `visitorService` em `DIL.create` conforme mostrado abaixo.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

No par de valores chave `namespace`, `MCORG` é a [!DNL Experience Cloud] ID da organização. Se não tiver essa ID, você poderá encontrá-la na seção [!UICONTROL Administration] do painel [!DNL Experience Cloud]. Você precisa de permissões de administrador para exibir este painel. Consulte [Administração: Principais serviços](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html).

## Funções obsoletas {#deprecated-functions}

Com as versões mais recentes de [!UICONTROL DIL] (6.2+), não é necessário usar esses pares de valores chave para transmitir [!UICONTROL declared IDs]. Isso ocorre porque [!UICONTROL DIL] agora depende da função `visitorService` mostrada na amostra de código acima. Essa função obtém [!UICONTROL declared IDs] do [!UICONTROL Adobe Experience Platform Identity Service]. No entanto, estamos fazendo referência a essas variáveis aqui para fins históricos e herdados. Consulte o código abaixo para obter um exemplo de como configurar `DIL.create` para obter um [!UICONTROL declared ID] do [!UICONTROL Visitor ID Service].
A tabela a seguir descreve as variáveis herdadas usadas pelo objeto `declaredId` :

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
   <td colname="col3"> <p>A ID única do provedor de dados para o usuário. </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL DPID] e [!UICONTROL DPUUID]

[!DNL Audience Manager] compara e corresponde o combinado  `DPID` e  `DPUUID` a uma ID de usuário correspondente em nosso sistema. Se uma ID não existir, [!DNL Audience Manager] criará uma nova ID de usuário e a sincronizará com a combinação `DPID/DPUUID`. Quando [!DNL Audience Manager] corresponde ou cria um ID de usuário (o `UUID`), ele retorna esse ID na resposta [!DNL JSON] para o [!DNL cookie] no domínio do cliente (primeiro [!DNL cookie]) ou em outro armazenamento local.

Chame essa função quando estiver usando [!UICONTROL DIL] v6.1 ou anterior. No entanto, essa função foi substituída pela nova versão que recebe [!UICONTROL declared IDs] do [!DNL Adobe Experience Platform Identity Service].

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
>Você precisa desenvolver programaticamente o código que fornece os valores de ID para as chaves `d_dpuuid` e `d_dpid`.

### Transmitir IDs após [!UICONTROL DIL] Instanciações

>[!NOTE]
>
>Se você efetuar uma chamada [!DNL API] com uma combinação diferente de `declaredID`, a nova combinação será usada somente para essa chamada. Outras chamadas de evento regulares usarão a combinação `DIL.create` `declaredID` original.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Exemplos de solicitação/resposta {#request-response-examples}

A solicitação envia um provedor de dados e ID de usuário para [!DNL Audience Manager]:

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

O processo [!UICONTROL declared ID] respeita as preferências do visitante do site para recusar o [!DNL Audience Manager] direcionamento por seu site. Quando [!DNL Audience Manager] recebe uma solicitação de recusa, o [!DNL DCS] retorna um objeto [!DNL JSON] vazio em vez da [!DNL Audience Manager] ID de usuário.

>[!MORELIKETHIS]
>
>* [CID substitui DPID e DPUUID](../reference/cid.md)

