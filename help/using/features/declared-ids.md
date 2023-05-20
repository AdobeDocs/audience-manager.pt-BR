---
description: Como as IDs declaradas funcionam, configurar procedimentos, exemplos de código e variáveis.
keywords: sincronização de id
seo-description: How declared IDs work, set up procedures, code examples, and variables.
seo-title: Declared IDs
solution: Audience Manager
title: IDs declaradas
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: ID Syncs
exl-id: a480671a-797d-405d-905d-98ab4ef71369
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 9%

---

# [!UICONTROL Declared IDs] {#declared-ids}

Como [!UICONTROL declared IDs] trabalhe, configure procedimentos, exemplos de código e variáveis.

## [!UICONTROL Declared ID] Definição de meta {#declared-id-targeting}

Trocar e sincronizar IDs de usuário com o [!DNL Audience Manager] de dispositivos ou navegadores que não usam ou aceitam mecanismos de armazenamento persistentes, como [!DNL cookies].

## Finalidade de [!UICONTROL Declared ID] Direcionamento {#declared-id-targeting-purpose}

Alguns navegadores e a maioria dos dispositivos móveis não aceitam serviços de [!DNL cookies]. Isso dificulta a retenção de informações sobre visitantes do site ou a atribuição de IDs persistentes. Para resolver esse problema, [!DNL Audience Manager] usos [!UICONTROL DIL] para permitir que você passe [!UICONTROL declared IDs] em uma chamada de evento. Além disso, uma [!UICONTROL declared ID] pode agir como uma ID universal que se aplica ao mesmo usuário em todas as soluções na [!DNL Experience Cloud]. A tabela a seguir descreve o processo de correspondência/direcionamento de ID:

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
   <td colname="col2"> <p>Para trabalhar, você precisa <span class="wintitle"> DIL </span> e a variável <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Serviço de identidade da Adobe Experience Platform </a> na página. <span class="wintitle"> DIL </span> obtém <span class="wintitle"> IDs declaradas </span> do <code> setVisitorID </code> função fornecida pelo <span class="keyword"> Serviço de identidade da Adobe Experience Platform </span> e transmite isso para <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de correspondência</b> </td> 
   <td colname="col2"> <p>O Audience Manager tenta corresponder a ID do cliente e do visitante com uma ID correspondente em nosso sistema. Se uma ID correspondente não existir, o Audience Manager criará uma nova ID e a associará à ID do cliente e do visitante. </p> <p> <p>Observação: o mapeamento mais recente é usado se a ID mapear para mais de uma ID de Audience Manager. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de devolução</b> </td> 
   <td colname="col2"> <p>O Audience Manager grava sua ID sincronizada em um cookie primário (ou outro espaço de armazenamento endereçável) no domínio ou aplicativo cliente. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Chamadas de evento subsequentes</b> </td>
   <td colname="col2"> <p>Chamadas de evento adicionais leem a ID de Audience Manager do domínio do cliente e a enviam para o Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Para começar, você precisa configurar o [!DNL Experience Cloud] Serviço de ID e [!UICONTROL DIL] nas páginas do site que você deseja usar para a coleta de dados. Consulte [criar DIL](../dil/dil-class-overview/dil-create.md#dil-create) e [Variáveis de ID declaradas](../features/declared-ids.md#declared-id-variables).

## Chamadas de recusa {#opt-out-calls}

A variável [!UICONTROL declared ID] o processo respeita as preferências do visitante do site para recusar o [!DNL Audience Manager] direcionamento pelo seu site. Quando [!DNL Audience Manager] recebe uma solicitação de recusa, a variável [!DNL JSON] retornado pelo [!DNL DCS] contém o código de erro 171, com a mensagem `Encountered opt out tag`, em vez de [!DNL Audience Manager] ID de usuário.

* [!DNL Audience Manager] pode passar em um [!UICONTROL declared ID] opt-out junto com um [!DNL Audience Manager] [!UICONTROL UUID] no [!DNL URL].
* A variável [!UICONTROL declared ID] o opt-out é armazenado na variável [!UICONTROL Profile Cache Server] ([!UICONTROL PCS]) por parceiro. Não há recusa em nível de plataforma usando o [!UICONTROL declared IDs]. Além disso, [!DNL Audience Manager] exclui o usuário dessa região específica na borda (a exclusão não cruza com [!DNL DCS] regiões).

Consulte [Privacidade de dados](../overview/data-security-and-privacy/data-privacy.md) para obter mais informações sobre a opção de recusa da coleta de dados.

## [!UICONTROL Declared ID] Exemplos de recusa {#opt-out-examples}

Você pode criar um [!UICONTROL declared ID] solicitações de recusa com a `d_cid` e `d_cid_ic` pares de valor-chave. Os parâmetros herdados como `d_dpid` e `d_dpuuid` ainda funcionam, mas são considerados obsoletos. Consulte [CID substitui DPID e DPUUID](../reference/cid.md). Nos exemplos, *itálico* indica um espaço reservado para variável.

### Opções De Não Participação Com [!UICONTROL CID] e [!UICONTROL CID_IC]

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
   <td colname="col1"> <p>Múltiplo <code> d_cid </code> e <code> d_cid_ic </code> pares de valor-chave. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Opções De Não Participação Com [!UICONTROL DPID], [!UICONTROL DPUUID], e [!UICONTROL UUID] (Obsoleto)

Esses métodos ainda funcionam, mas são considerados obsoletos. Essas informações são fornecidas para fins herdados e referência. As recusas herdadas incluem:

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opção de não participação (obsoleto) </th> 
   <th colname="col2" class="entry"> Amostra de código </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid </code> only </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Recusa em nível de parceiro </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Uma opção de recusa em nível de parceiro é armazenada para o mapeamento mais recente deste <code> dpid </code> + <code> dpuuid </code> emparelhar a um UUID AAM. Se não houver mapeamento existente, o Audience Manager verificará se a solicitação contém uma UUID AAM no cookie e, em caso positivo, usará essa UUID para armazenar a recusa. Caso contrário, o Audience Manager gera um novo UUID AAM e armazena a opção de não participação nele. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> e explícito <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> sempre tem precedência. Se a variável <code> dpid </code> + <code> dpuuid </code> for mapeada para outra UUID do AAM, a opção de não participação será armazenada na UUID do AAM transmitida na solicitação ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variáveis e sintaxe de [!UICONTROL Declared IDs] {#variables-and-syntax}

A tabela a seguir lista os pares de valor-chave transmitidos no [!DNL Audience Manager] ID do provedor de dados e IDs de usuário ou códigos de integração, se usados. Observação: *itálico* indica um espaço reservado para variável. Foram adicionados espaços para facilitar a leitura.

Em cada par de valor-chave:

* A variável `=` separa a chave de seus valores relacionados.
* O não imprimível [!DNL ASCII] caractere `%01` separa os valores.

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
   <td colname="col2"> <p>Contém uma ID de provedor de dados e uma ID de usuário exclusiva associada em um único par de valor-chave. <code> d_cid </code> substitui <code> d_dpid </code> e <code> d_dpuuid </code>, que são considerados obsoletos, mas ainda são compatíveis. Consulte <a href="../reference/cid.md">CID substitui DPID e DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Contém um código de integração e uma ID de usuário exclusiva associada em um único par de valor-chave. <code> d_cid_ic </code> substitui <code> d_dpid </code> e <code> d_dpuuid </code>, que estão obsoletos, mas ainda são compatíveis. Consulte <a href="../reference/cid.md">CID substitui DPID e DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemplo de chamadas de evento {#sample-event-calls}

Dados esses pares de valores chave e sua sintaxe necessária, você faria chamadas de evento conforme mostrado abaixo.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Chamada de evento inclui </th> 
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
   <td colname="col1"> <p>Múltiplo <code> d_cid </code> e <code> d_cid_ic </code> pares de valor-chave. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Variáveis {#declared-id-variables}

Descreve as variáveis de configuração usadas para transmitir [!UICONTROL declared IDs] até [!UICONTROL DIL] para [!DNL Audience Manager.]

## [!UICONTROL DIL] usa o [!DNL Adobe Experience Platform Identity Service] para aprovação [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

Quando usado com o [Serviço de identidade da Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html), você não precisa mais transmitir [!UICONTROL declared IDs] com o obsoleto `dpid` e `dpuuid` variáveis. Em vez disso, as versões atuais do [!UICONTROL DIL] confie na `visitorService` função para obter o [!UICONTROL declared IDs] do `setCustomerIDs` na caixa [!UICONTROL Adobe Experience Platform Identity Service]. Para obter mais informações, consulte [Estados de autenticação e IDs do cliente](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html). Você chamaria `visitorService` in `DIL.create` conforme mostrado abaixo.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

No `namespace` par de valor-chave, `MCORG` é seu [!DNL Experience Cloud] ID da organização. Se você não tiver essa ID, poderá encontrá-la na [!UICONTROL Administration] seção do [!DNL Experience Cloud] painel. Você precisa de permissões de administrador para visualizar este painel. Consulte [Administração: Serviços principais](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html).

## Funções obsoletas {#deprecated-functions}

Com as versões mais recentes da [!UICONTROL DIL] (6.2+), não é necessário usar esses pares de valores chave para transmitir [!UICONTROL declared IDs]. É porque... [!UICONTROL DIL] O agora depende do `visitorService` mostrada na amostra de código acima. Essa função obtém [!UICONTROL declared IDs] do [!UICONTROL Adobe Experience Platform Identity Service]. No entanto, estamos fazendo referência a essas variáveis aqui para fins históricos e herdados. Consulte o código abaixo para obter um exemplo de como configurar `DIL.create` para obter um [!UICONTROL declared ID] do [!UICONTROL Visitor ID Service].
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
   <td colname="col3"> <p>A ID única do provedor de dados para o usuário. </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL DPID] e [!UICONTROL DPUUID]

[!DNL Audience Manager] compara e corresponde a `DPID` e `DPUUID` para uma ID de usuário correspondente em nosso sistema. Se uma ID não existir, [!DNL Audience Manager] cria uma nova ID de usuário e a sincroniza com o `DPID/DPUUID` combinação. Uma vez [!DNL Audience Manager] corresponde ou cria uma ID de usuário (a variável `UUID`) retorna essa ID na variável [!DNL JSON] resposta à [!DNL cookie] no domínio do cliente (primário) [!DNL cookie]) ou outro armazenamento local.

Chame esta função quando estiver usando [!UICONTROL DIL] v6.1 ou anterior. No entanto, essa função foi substituída pela nova versão que recebe [!UICONTROL declared IDs] do [!DNL Adobe Experience Platform Identity Service].

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
>É necessário desenvolver programaticamente o código que fornece os valores de ID para o `d_dpuuid` e `d_dpid` chaves.

### Enviar IDs depois de [!UICONTROL DIL] Instancia

>[!NOTE]
>
>Se você fizer um [!DNL API] chamar com um diferente `declaredID` combinação, a nova combinação será usada somente para essa chamada. Chamadas de evento regulares adicionais usarão o original `DIL.create`  `declaredID` combinação.

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

A resposta retorna a ID de Audience Manager (por exemplo, `UUID`) que é gravado em um cookie próprio no domínio da página.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Não direcionar e recusar chamadas {#do-not-target}

A variável [!UICONTROL declared ID] o processo respeita as preferências do visitante do site para recusar o [!DNL Audience Manager] direcionamento pelo seu site. Quando [!DNL Audience Manager] recebe uma solicitação de recusa, a variável [!DNL DCS] retorna um vazio [!DNL JSON] em vez do [!DNL Audience Manager] ID de usuário.

>[!MORELIKETHIS]
>
>* [CID substitui DPID e DPUUID](../reference/cid.md)

