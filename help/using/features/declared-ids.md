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
source-wordcount: '1148'
ht-degree: 8%

---

# [!UICONTROL Declared IDs] {#declared-ids}

Como o [!UICONTROL declared IDs] funciona, configure procedimentos, exemplos de código e variáveis.

## [!UICONTROL Declared ID] Definição de meta {#declared-id-targeting}

Troque e sincronize IDs de usuário com [!DNL Audience Manager] de dispositivos ou navegadores que não usam ou aceitam mecanismos de armazenamento persistentes, como [!DNL cookies] de terceiros.

## Propósito do Direcionamento [!UICONTROL Declared ID] {#declared-id-targeting-purpose}

Alguns navegadores e a maioria dos dispositivos móveis não aceitam o [!DNL cookies] de terceiros. Isso dificulta a retenção de informações sobre visitantes do site ou a atribuição de IDs persistentes. Para resolver esse problema, [!DNL Audience Manager] usa [!UICONTROL DIL] para permitir que você passe [!UICONTROL declared IDs] em uma chamada de evento. Além disso, um [!UICONTROL declared ID] pode agir como uma ID universal que se aplica ao mesmo usuário em todas as soluções no [!DNL Experience Cloud]. A tabela a seguir descreve o processo de correspondência/direcionamento de ID:

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
   <td colname="col2"> <p>Para funcionar, você precisa do código <span class="wintitle"> DIL </span> e do <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> serviço de identidade da Adobe Experience Platform </a> na página. O DIL <span class="wintitle"> </span> obtém <span class="wintitle"> IDs declaradas </span> da função <code> setVisitorID </code> fornecida pelo Serviço de Identidade do Adobe Experience Platform <span class="keyword"> </span> e transmite-as para o Audience Manager <span class="keyword"> </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Identificação de Correspondência</b> </td> 
   <td colname="col2"> <p>O Audience Manager tenta corresponder a ID do cliente e do visitante com uma ID correspondente em nosso sistema. Se uma ID correspondente não existir, o Audience Manager criará uma nova ID e a associará à ID do cliente e do visitante. </p> <p> <p>Observação: o mapeamento mais recente é usado se a ID mapear para mais de uma ID de Audience Manager. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de Retorno</b> </td> 
   <td colname="col2"> <p>O Audience Manager grava sua ID sincronizada em um cookie primário (ou outro espaço de armazenamento endereçável) no domínio ou aplicativo cliente. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Chamadas de evento subsequentes</b> </td>
   <td colname="col2"> <p>Chamadas de evento adicionais leem a ID de Audience Manager do domínio do cliente e a enviam para o Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Para começar, você precisa configurar o serviço de ID do [!DNL Experience Cloud] e o [!UICONTROL DIL] em todas as páginas do site que deseja usar para a coleta de dados. Consulte [DIL create](../dil/dil-class-overview/dil-create.md#dil-create) e [Variáveis de ID declaradas](../features/declared-ids.md#declared-id-variables).

## Chamadas de recusa {#opt-out-calls}

O processo [!UICONTROL declared ID] respeita as preferências do visitante do site para recusar o direcionamento do [!DNL Audience Manager] por seu site. Quando [!DNL Audience Manager] recebe uma solicitação de recusa, a [!DNL JSON] retornada por [!DNL DCS] contém o código de erro 171, com a mensagem `Encountered opt out tag`, em vez da ID de usuário [!DNL Audience Manager].

* [!DNL Audience Manager] pode enviar uma opção de recusa de [!UICONTROL declared ID] junto com um [!DNL Audience Manager] [!UICONTROL UUID] no [!DNL URL].
* A opção de não participação do [!UICONTROL declared ID] é armazenada no [!UICONTROL Profile Cache Server] ([!UICONTROL PCS]) com base no parceiro. Não há recusa em nível de plataforma usando [!UICONTROL declared IDs]. Além disso, [!DNL Audience Manager] recusa o usuário nessa região específica na borda (a opção de não participação não passa de [!DNL DCS] regiões).

Consulte [Privacidade de dados](../overview/data-security-and-privacy/data-privacy.md) para obter mais informações sobre a não participação na coleta de dados.

## Exemplos de recusa do [!UICONTROL Declared ID] {#opt-out-examples}

Você pode fazer uma solicitação de recusa de [!UICONTROL declared ID] com os pares de valor-chave `d_cid` e `d_cid_ic`. Os parâmetros herdados como `d_dpid` e `d_dpuuid` ainda funcionam, mas são considerados obsoletos. Consulte [CID substitui DPID e DPUUID](../reference/cid.md). Nos exemplos, *itálico* indica um espaço reservado para variável.

### Opções de não participação com [!UICONTROL CID] e [!UICONTROL CID_IC]

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
   <td colname="col1"> <p>Vários pares de valor-chave <code> d_cid </code> e <code> d_cid_ic </code>. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Opções de não participação com [!UICONTROL DPID], [!UICONTROL DPUUID] e [!UICONTROL UUID] (obsoleto)

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
   <td colname="col1"> <p> Somente <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Recusa em nível de parceiro </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Uma recusa em nível de parceiro é armazenada para o mapeamento mais recente deste par <code> dpid </code> + <code> dpuuid </code> para uma UUID AAM. Se não houver mapeamento existente, o Audience Manager verificará se a solicitação contém uma UUID AAM no cookie e, em caso positivo, usará essa UUID para armazenar a recusa. Caso contrário, o Audience Manager gera um novo UUID AAM e armazena a opção de não participação nele. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> e <code> d_uuid </code> explícito </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> sempre tem prioridade. Se a combinação <code> dpid </code> + <code> dpuuid </code> for mapeada para outra UUID AAM, a recusa será armazenada na UUID AAM transmitida na solicitação ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variáveis e Sintaxe para [!UICONTROL Declared IDs] {#variables-and-syntax}

A tabela a seguir lista os pares de valores chave que passam na ID do provedor de dados do [!DNL Audience Manager] e nas IDs do usuário ou nos códigos de integração, se usados. Observe que *itálico* indica um espaço reservado para variável. Foram adicionados espaços para facilitar a leitura.

Em cada par de valor-chave:

* O símbolo `=` separa a chave de seus valores relacionados.
* O [!DNL ASCII] caractere `%01` não imprimível separa os valores.

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
   <td colname="col2"> <p>Contém uma ID de provedor de dados e uma ID de usuário exclusiva associada em um único par de valor-chave. <code> d_cid </code> substitui <code> d_dpid </code> e <code> d_dpuuid </code>, que são considerados obsoletos, mas ainda têm suporte. Consulte <a href="../reference/cid.md"> CID substitui DPID e DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Contém um código de integração e uma ID de usuário exclusiva associada em um único par de valor-chave. <code> d_cid_ic </code> substitui <code> d_dpid </code> e <code> d_dpuuid </code>, que estão obsoletos, mas ainda têm suporte. Consulte <a href="../reference/cid.md"> CID substitui DPID e DPUUID </a>. </p> </td> 
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
   <td colname="col1"> <p>Vários pares de valor-chave <code> d_cid </code> e <code> d_cid_ic </code>. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Variáveis {#declared-id-variables}

Descreve as variáveis de configuração usadas para passar [!UICONTROL declared IDs] através de [!UICONTROL DIL] para [!DNL Audience Manager.]

## [!UICONTROL DIL] usa [!DNL Adobe Experience Platform Identity Service] para Passar [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

Quando usado com o [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html), você não precisa mais transmitir [!UICONTROL declared IDs] com as variáveis `dpid` e `dpuuid` obsoletas. Em vez disso, as versões atuais de [!UICONTROL DIL] dependem da função `visitorService` para obter [!UICONTROL declared IDs] da função `setCustomerIDs` em [!UICONTROL Adobe Experience Platform Identity Service]. Para obter mais informações, consulte [IDs do cliente e Estados de autenticação](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html). Você chamaria `visitorService` em `DIL.create` como mostrado abaixo.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

No par de valor-chave `namespace`, `MCORG` é a sua ID da organização [!DNL Experience Cloud]. Se você não tiver essa ID, poderá encontrá-la na seção [!UICONTROL Administration] do painel [!DNL Experience Cloud]. Você precisa de permissões de administrador para visualizar este painel. Consulte [Administração: Serviços Principais](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html).

## Funções obsoletas {#deprecated-functions}

Com as versões mais recentes do [!UICONTROL DIL] (6.2+), você não precisa usar esses pares de valores chave para transmitir [!UICONTROL declared IDs]. Isso ocorre porque [!UICONTROL DIL] agora depende da função `visitorService` mostrada no exemplo de código acima. Esta função obtém [!UICONTROL declared IDs] de [!UICONTROL Adobe Experience Platform Identity Service]. No entanto, estamos fazendo referência a essas variáveis aqui para fins históricos e herdados. Consulte o código abaixo para obter um exemplo de como configurar o `DIL.create` para obter um [!UICONTROL declared ID] do [!UICONTROL Visitor ID Service].
A tabela a seguir descreve as variáveis herdadas usadas pelo objeto `declaredId`:

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

[!DNL Audience Manager] compara e corresponde o `DPID` e `DPUUID` combinados a uma ID de usuário correspondente em nosso sistema. Se uma ID não existir, [!DNL Audience Manager] cria uma nova ID de usuário e a sincroniza com a combinação `DPID/DPUUID`. Quando [!DNL Audience Manager] corresponde ou cria uma ID de usuário (o `UUID`), ele retorna essa ID na resposta [!DNL JSON] ao [!DNL cookie] no domínio do cliente ([!DNL cookie] primário) ou outro armazenamento local.

Chame esta função quando estiver usando o [!UICONTROL DIL] v6.1 ou anterior. No entanto, essa função foi substituída pela nova versão que obtém [!UICONTROL declared IDs] do [!DNL Adobe Experience Platform Identity Service].

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

### Passar IDs Após [!UICONTROL DIL] Instanciações

>[!NOTE]
>
>Se você fizer uma chamada [!DNL API] com uma combinação `declaredID` diferente, a nova combinação será usada somente para essa chamada. Mais chamadas de evento regulares usarão a combinação original `DIL.create` `declaredID`.

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

A resposta retorna a ID de Audience Manager (por exemplo, `UUID`) que é gravada em um cookie próprio no domínio da página.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Não direcionar e recusar chamadas {#do-not-target}

O processo [!UICONTROL declared ID] respeita as preferências do visitante do site para recusar o direcionamento do [!DNL Audience Manager] por seu site. Quando [!DNL Audience Manager] recebe uma solicitação de recusa, [!DNL DCS] retorna um objeto [!DNL JSON] vazio em vez da ID de usuário [!DNL Audience Manager].

>[!MORELIKETHIS]
>
>* [CID substitui DPID e DPUUID](../reference/cid.md)
