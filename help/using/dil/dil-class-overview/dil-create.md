---
description: Cria uma instância DIL específica do parceiro.
seo-description: Cria uma instância DIL específica do parceiro.
seo-title: Criar DIL
solution: Audience Manager
title: Criar DIL
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: fc13643681eebec17a95607482f2864e81b95820
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 12%

---


# método DIL create{#dil-create}

## Criar DIL {#dil-create-new}

Cria uma [!UICONTROL DIL] instância específica do parceiro.

**Assinatura da função:** `DIL.create: function (initConfig) {}`

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
   <td colname="col3"> <p>Essa propriedade configura a ID de contêiner usada pelo <span class="keyword">Audience Manager</span> para sincronizações de ID. Você definiria <code> containerNSID </code> se tivesse <span class="wintitle"> DIL </span> implantado em vários sites. Cada um desses sites terá suas próprias sincronizações de ID e ID de container. Quando você tem apenas um site, a ID do container é 0 por padrão e não é necessário defini-la corretamente. Entre em contato com seu consultor para obter uma lista dos seus sites e suas IDs de container. </p> <p>No <a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a>, a propriedade <code> idSyncContainerID </code> corresponde a <code> containerNSID </code> no <span class="wintitle"> DIL </span>. Observe o seguinte se você estiver usando o <span class="wintitle"> DIL </span> e o serviço de ID em vários sites <i></i> : </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Para cada site, defina as mesmas IDs de container em <code> containerNSID </code> e <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Tanto o <span class="wintitle"> DIL </span> quanto o serviço de ID tentarão enviar sincronizações de ID para nosso iFrame de coleta de dados. No entanto, o iFrame garante que o <span class="wintitle"> DIL </span> não dispare uma sincronização de ID. Isso evita a duplicação. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Somente o <span class="wintitle"> DIL </span> envia dados para um destino <a href="../../features/destinations/destinations.md"> de URL </a>. </li> 
     </ul> </p> <p>Consulte também <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> é usado para passar em: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: ID do parceiro de dados atribuída a você por <span class="keyword"> Audience Manager </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: Sua ID exclusiva para um usuário. </li> 
    </ul> <p> <p>Importante:  Use apenas valores não codificados para suas IDs. A codificação das cria identificadores duplamente codificados. </p> </p> <p> <p>Observação:  Se você usar o <a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a>, defina as IDs do cliente com o <code> setCustomerIDs </code> método em vez de <span class="wintitle"> DIL </span>. See <a href="https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html" format="https" scope="external"> Customer IDs and Authentication States </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Se verdadeiro, difere todas as solicitações (IFRAME, chamadas de evento, sincronização de ID e destino) da execução até que o <code> Page Load </code> evento seja acionado. O padrão é <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Falso por padrão, o que significa que <span class="keyword"> Audience Manager </span> define um cookie no domínio do parceiro (define um cookie primário). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante:  Este elemento foi descontinuado com o <span class="wintitle"> DIL </span> versão 8.0 (lançado em agosto de 2018). Em vez disso, use a <code> visitor.disableIdSyncs </code> função <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> </a> no Adobe Experience Platform Identity Service. </p> </p> <p> Se <code> true </code>, não anexará a IFRAME de publicação de destino ao DOM ou acionará destinos. O padrão é <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante:  Este elemento foi descontinuado com o <span class="wintitle"> DIL </span> versão 8.0 (lançado em agosto de 2018). Em vez disso, use a <code> visitor.disableIdSyncs </code> função <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> </a> no Adobe Experience Platform Identity Service. </p> </p> <p>Desativa a sincronização de ID. Você deve desativar as sincronizações de ID ao usar o DIL v6.2+ e o Serviço de ID do Visitante. A <code> visitorService </code> função (consulte o código de amostra abaixo) cuida dessa operação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Defina <code> true </code> para ativar o relatórios de erro para todas as instâncias de <span class="wintitle"> DIL </span> na página. Funciona somente com Booleano <code> true </code> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante:  Este elemento foi descontinuado com o <span class="wintitle"> DIL </span> versão 8.0 (lançado em agosto de 2018). Em vez disso, use a <code> visitor.idSyncSSLUseAkamai </code> função <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external"> </a> no Adobe Experience Platform Identity Service. </p> </p> <p> Especifica se o modelo de publicação de destino deve usar Akamai para as conexões HTTPS. Ativado pelo parceiro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Associa o valor de um par de valores chave a outro. Consulte <a href="../../dil/dil-use-cases.md#map-key-values"> Mapear valores principais para outras chaves </a>. Lançado com v2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>Obrigatório. </p> <p>O par de <code> namespace </code> chave-valor contém sua ID de empresa do <span class="keyword"> Experience Cloud </span> . Se você não tiver essa ID, poderá encontrá-la na seção <span class="wintitle"> Administração </span> do <span class="keyword"> painel </span> . Você precisa de permissões de administrador para visualização deste painel. Consulte as Perguntas frequentes sobre recursos e funções <a href="../../faq/faq-features.md"> do produto </a> e <a href="https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external"> Administração - Gerenciamento de usuários e perguntas frequentes </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>Obrigatório. </p> <p> Nome do parceiro, conforme fornecido pelo <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Remove scripts e retornos de chamada. O padrão é <code> False </code>. Aplica-se somente à instância <span class="wintitle"> DIL atual </span> . Lançado com v3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Define um cookie com a ID de usuário exclusiva retornada do <span class="keyword"> Audience Manager </span>. Consulte Propriedades <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uidCookie </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Obrigatório com <span class="wintitle"> DIL </span> 6.2 ou superior. </p> <p> O DIL depende da <code> setCustomerIDs </code> função no <span class="wintitle"> Adobe Experience Platform Identity Service </span> para passar as IDs declaradas para o <span class="keyword"> Audience Manager </span>. Consulte <a href="https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html" format="https" scope="external">IDs do cliente e Estados de autenticação</a> para obter mais informações. </p> </td> 
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
| `namespace` | String   | Obrigatório. Representa A ID De Organização De Experience Cloud. Isso é necessário para a funcionalidade do serviço Experience Cloud Core. O mesmo parâmetro usado para instanciar a funcionalidade da ID do Visitante. |

**Amostra de código:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
