---
description: Cria uma instância DIL específica do parceiro.
seo-description: Cria uma instância DIL específica do parceiro.
seo-title: ' Criar DIL'
solution: Audience Manager
title: ' Criar DIL'
uuid: 6e054600-703c-4a97-af2a-8207c50013db
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Método de criação DIL{#dil-create}

##  Criar DIL {#dil-create-new}

Cria uma [!UICONTROL DIL] instância específica do parceiro.

**** Assinatura da função: `DIL.create: function (initConfig) {}`

**elementos initConfig**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>A `visitorService` propriedade é *sempre* obrigatória. Outras propriedades listadas aqui são opcionais, salvo indicação em contrário.

`initConfig` aceita os seguintes elementos:

<table id="table_1334973505F54B238127FED9845B16C4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> containerNSID </code> </p> </td> 
   <td colname="col2"> <p>Número inteiro </p> </td> 
   <td colname="col3"> <p>Essa propriedade configura a ID de contêiner usada pelo <span class="keyword">Audience Manager</span> para sincronizações de ID. Você definiria <code> containerNSID </code> se você tivesse <span class="wintitle"> DIL </span> implantado em vários sites. Cada um desses sites terá sua própria ID de contêiner e sincronizações de ID. Quando você tem apenas um site, a ID do contêiner é 0 por padrão e não é necessário defini-la corretamente. Entre em contato com o seu consultor para obter uma lista dos seus sites e as IDs do contêiner. </p> <p>No serviço da <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID </a>, a propriedade <code> idSyncContainerID </code> corresponde a <code> containerNSID </code> no <span class="wintitle"> DIL </span>. Observe o seguinte se você estiver usando <span class="wintitle"> DIL </span> e o serviço de ID em vários sites <i></i> : </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Para cada site, defina as mesmas IDs do contêiner em <code> containerNSID </code> e <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">O DIL <span class="wintitle"> </span> e o serviço de ID tentarão enviar sincronizações de ID para o iFrame da coleção de dados. No entanto, o iFrame garante que o <span class="wintitle"> DIL </span> não dispare uma sincronização de ID. Isso evita a duplicação. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Somente <span class="wintitle"> DIL </span> envia dados para um destino <a href="../../features/destinations/destinations.md"> de URL </a>. </li> 
     </ul> </p> <p>Consulte também <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaradaId </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> 
    <draft-comment> 
     <p>Envia as variáveis <a href="../../features/declared-ids.md"> de ID declaradas </a> em cada chamada de evento para o <span class="keyword"> Audience Manager </span>. </p> 
    </draft-comment> <p> <code> delcareId </code> é usado para passar em: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: ID do parceiro de dados atribuída a você pelo <span class="keyword"> Audience Manager </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: Sua ID exclusiva para um usuário. </li> 
    </ul> <p> <p>Importante:  Use apenas valores não codificados para suas IDs. A codificação das cria identificadores duplamente codificados. </p> </p> <p> <p>Observação:  Se você usar o Serviço da <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID </a>, defina as IDs do cliente com o método <code> setCustomerIDs </code> em vez de <span class="wintitle"> DIL </span>. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid-authenticated-state.html" format="https" scope="external"> Customer IDs and Authentication States </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllThroughWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Se verdadeiro, difere a execução de todas as solicitações (IFRAME, chamadas de evento, sincronização de ID e destino) até que o evento <code> Carregamento de página </code> seja acionado. Default is <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclarredUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Falso por padrão, o que significa que <span class="keyword"> o Audience Manager </span> define um cookie no domínio do parceiro (define um cookie primário). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante:  Este elemento foi descontinuado com o <span class="wintitle"> DIL </span> versão 8.0 (lançado em agosto de 2018). Em vez disso, use a função <code> visitor.disableIdSyncs </code> no serviço da Experience Cloud ID <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-disableidsync.html" format="https" scope="external"> </a> . </p> </p> <p> Se <code> verdadeiro </code>, não anexará a IFRAME de publicação de destino ao DOM ou acionará destinos. Default is <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante:  Este elemento foi descontinuado com o <span class="wintitle"> DIL </span> versão 8.0 (lançado em agosto de 2018). Em vez disso, use a função <code> visitor.disableIdSyncs </code> no serviço da Experience Cloud ID <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-disableidsync.html" format="https" scope="external"> </a> . </p> </p> <p>Desativa a sincronização de ID. Você deve desativar as sincronizações de ID ao usar o DIL v6.2+ e o Serviço de ID de visitante. A função <code> visitorService </code> (consulte a amostra de código abaixo) cuida dessa operação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Defina como <code> true </code> para ativar o relatório de erros para todas as <span class="wintitle"> instâncias DIL </span> na página. Funciona somente com Boolean <code> true </code> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante:  Este elemento foi descontinuado com o <span class="wintitle"> DIL </span> versão 8.0 (lançado em agosto de 2018). Em vez disso, use a função <code> visitor.idSyncSSLUseAkamai </code> no serviço da Experience Cloud ID <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idSyncSSLUseAkamai.html" format="https" scope="external"> </a> . </p> </p> <p> Especifica se o modelo de publicação de destino deve usar Akamai para as conexões HTTPS. Ativado pelo parceiro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mapeamentos </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Associa o valor de um par de valores chave a outro. Consulte <a href="../../dil/dil-use-cases.md#map-key-values"> Mapear valores principais para outras chaves </a>. Lançado com v2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>Obrigatório. </p> <p>O par de <code> valores-chave do namespace </code> contém sua <span class="keyword"> Experience Cloud </span> Organization ID. Se você não tiver essa ID, poderá encontrá-la na seção <span class="wintitle"> Administração </span> do <span class="keyword"> Experience Cloud </span> ashboard. Você precisa de permissões de administrador para exibir este painel. Consulte as Perguntas frequentes sobre recursos e funções <a href="../../faq/faq-features.md"> do produto </a> e <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html" format="https" scope="external"> Administração - Gerenciamento de usuários e perguntas frequentes </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> sócio </code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>Obrigatório. </p> <p> Nome do parceiro, conforme fornecido pelo <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Remove scripts e retornos de chamada. Default is <code> False </code>. Aplica-se somente à instância <span class="wintitle"> DIL atual </span> . Lançado com v3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uidCookie </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Define um cookie com a ID de usuário exclusiva retornada pelo <span class="keyword"> Audience Manager </span>. Consulte Propriedades <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uidCookie </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Obrigatório com <span class="wintitle"> DIL </span> 6.2 ou superior. </p> <p> O DIL depende da função <code> setCustomerIDs </code> no serviço da <span class="wintitle"> Experience Cloud ID </span> para passar as IDs declaradas para o <span class="keyword"> Audience Manager </span>. Consulte <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid-authenticated-state.html" format="https" scope="external">IDs do cliente e Estados de autenticação</a> para obter mais informações. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Código de exemplo**

Uma [!UICONTROL DIL] chamada de amostra pode ser semelhante ao seguinte:

```js
var partnerObject1 = DIL.create({ 
  partner: "partner name", 
  visitorService:{ 
    namespace: "INSERT-ORGANIZATION-ID-HERE" 
  }, 
  containerNSID: 3, 
  uuidCookie:{ 
    name:'ad_uuid', 
    days:200, 
    path:'/test', 
    domain:'adobe.com', 
    secure:true 
  } 
}); 
 
var partnerObject2 = DIL.create({ 
  partner: "partner name", 
  visitorService:{ 
    namespace: "INSERT-MCORG-ID-HERE" 
  }, 
  containerNSID: 3 
}); 
```

Uma resposta bem-sucedida retorna a [!UICONTROL DIL] instância. Uma tentativa malsucedida retornará um objeto de erro (não lançado) se o código estiver configurado incorretamente ou sempre que um erro for encontrado.

## Propriedades do uidCookie {#uuidcookie-props}

Define as propriedades usadas pela `uuidCookie` variável. Essa variável faz parte do `DIL.create` método.

`uuidCookie` tem as seguintes propriedades:

<!-- 

r_dil_uuid_cookie.xml

 -->

| Nome | Descrição |
|---|---|
| `name` | The cookie name ( `aam_did` is default). |
| `days` | Duração do cookie (100 dias é padrão). |
| `path` | Caminho do cookie, por exemplo, `'/test'` ( `/` é padrão). |
| `domain` | O domínio em que o cookie está definido, por exemplo, `'adobe.com'` ( `'.'+document.domain` é padrão). |
| `secure` | Define um sinalizador para enviar dados somente por uma conexão HTTPS. |

## propriedades do visitorService {#visitor-service-props}

Define as propriedades usadas pela `visitorService` variável. Essa variável faz parte do `DIL.create` método.

`visitorService` tem as seguintes propriedades:

| Nome | Tipo | Descrição |
|---|---|---|
| `namespace` | String   | Obrigatório. Representa A Experience Cloud Org ID. Isso é necessário para a funcionalidade do serviço principal da Experience Cloud. O mesmo parâmetro usado para instanciar a funcionalidade da ID do visitante. |

**Amostra de código:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
