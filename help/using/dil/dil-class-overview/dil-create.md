---
description: Cria uma instância DIL específica do parceiro.
seo-description: Cria uma instância DIL específica do parceiro.
seo-title: Criar DIL
solution: Audience Manager
title: Criar DIL
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: Implementação de DIL
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 11%

---

# método DIL create{#dil-create}

## Criar DIL {#dil-create-new}

Cria uma instância [!UICONTROL DIL] específica do parceiro.

**Assinatura da função:** `DIL.create: function (initConfig) {}`

**Elementos de initConfig**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>A propriedade `visitorService` é *sempre* necessária. Outras propriedades listadas aqui são opcionais, salvo indicação em contrário.

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
   <td colname="col3"> <p>Essa propriedade configura a ID de contêiner usada pelo <span class="keyword">Audience Manager</span> para sincronizações de ID. Você definiria <code> containerNSID </code> se tivesse <span class="wintitle"> DIL </span> implantado em vários sites. Cada um desses sites terá sua própria ID de contêiner e sincronizações de ID. Quando você tem apenas 1 site, a ID do contêiner é 0 por padrão e não é necessário definir isso corretamente. Entre em contato com seu consultor para obter uma lista dos sites e as IDs do contêiner. </p> <p>No <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a>, a propriedade <code> idSyncContainerID </code> corresponde a <code> containerNSID </code> no <span class="wintitle"> DIL </span>. Observe o seguinte se estiver usando <span class="wintitle"> DIL </span> <i>e</i> o serviço de ID em vários sites: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Para cada site, defina as mesmas IDs de contêiner em <code> containerNSID </code> e <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Tanto o <span class="wintitle"> DIL </span> quanto o serviço de ID tentarão enviar sincronizações de ID para nosso iFrame de coleta de dados. No entanto, o iFrame garante que <span class="wintitle"> DIL </span> não acione uma sincronização de ID. Isso evita a duplicação. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Somente <span class="wintitle"> DIL </span> envia dados para um <a href="../../features/destinations/destinations.md"> destino de URL </a>. </li> 
     </ul> </p> <p>Consulte também <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> é usado para transmitir qualquer um dos seguintes itens: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: ID do parceiro de dados atribuída a você pelo  <span class="keyword"> Audience Manager  </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: Sua ID exclusiva para um usuário. </li> 
    </ul> <p> <p>Importante:  Use apenas valores não codificados para suas IDs. A codificação das cria identificadores duplamente codificados. </p> </p> <p> <p>Observação:  Se você usar o <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a>, defina as IDs do cliente com o método <code> setCustomerIDs </code> em vez de <span class="wintitle"> DIL </span>. Consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external"> IDs do cliente e Estados de autenticação </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Se verdadeiro, adia a execução de todas as solicitações (IFRAME, chamadas de evento, sincronização de ID e destino) até que o evento <code> Page Load </code> seja acionado. O padrão é <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Falso por padrão, o que significa <span class="keyword"> Audience Manager </span> define um cookie no domínio do parceiro (define um cookie próprio). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante:  Este elemento foi descontinuado com <span class="wintitle"> DIL </span> versão 8.0 (lançado em agosto de 2018). Em vez disso, use a função <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> </a> no Adobe Experience Platform Identity Service. </p> </p> <p> Se <code> true </code>, o não anexará o IFRAME de publicação de destino aos destinos DOM ou fire. O padrão é <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante:  Este elemento foi descontinuado com <span class="wintitle"> DIL </span> versão 8.0 (lançado em agosto de 2018). Em vez disso, use a função <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> </a> no Adobe Experience Platform Identity Service. </p> </p> <p>Desativa a sincronização de ID. Você deve desativar as sincronizações de ID ao usar o DIL v6.2+ e o Serviço de ID de visitante. A função <code> visitorService </code> (consulte o código de amostra abaixo) cuida dessa operação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Defina como <code> true </code> para ativar o relatório de erros para todas as instâncias <span class="wintitle"> DIL </span> na página. Funciona somente com Booleano <code> true </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante:  Este elemento foi descontinuado com <span class="wintitle"> DIL </span> versão 8.0 (lançado em agosto de 2018). Em vez disso, use a função <code> visitor.idSyncSSLUseAkamai </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external"> </a> no Adobe Experience Platform Identity Service. </p> </p> <p> Especifica se o modelo de publicação de destino deve usar Akamai para as conexões HTTPS. Ativado pelo parceiro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Associa o valor de um par de valores chave a outro. Consulte <a href="../../dil/dil-use-cases.md#map-key-values"> Mapear valores principais para outras chaves </a>. Lançado com v2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>Obrigatório. </p> <p>O par de valor da chave <code> namespace </code> contém a ID da organização <span class="keyword"> Experience Cloud </span>. Se não tiver essa ID, poderá encontrá-la na seção <span class="wintitle"> Administração </span> do painel <span class="keyword"> Experience Cloud </span>. Você precisa de permissões de administrador para exibir este painel. Consulte as <a href="../../faq/faq-features.md"> Perguntas frequentes sobre recursos e funções do produto </a> e <a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external"> Administração - Gerenciamento de usuários e perguntas frequentes </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>Obrigatório. </p> <p> Nome do parceiro, conforme fornecido por <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Remove scripts e retornos de chamada. O padrão é <code> False </code>. Aplica-se somente à instância <span class="wintitle"> DIL </span> atual. Lançado com v3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Define um cookie com a ID de usuário exclusiva retornada de <span class="keyword"> Audience Manager </span>. Consulte <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> Propriedades do uuidCookie </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Obrigatório com <span class="wintitle"> DIL </span> 6.2 ou superior. </p> <p> O DIL depende da função <code> setCustomerIDs </code> no <span class="wintitle"> Adobe Experience Platform Identity Service </span> para transmitir IDs declaradas para <span class="keyword"> Audience Manager </span>. Consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external">IDs do cliente e Estados de autenticação</a> para obter mais informações. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Código de exemplo**

Um exemplo de chamada [!UICONTROL DIL] pode ser semelhante ao seguinte:

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

Uma resposta bem-sucedida retorna a instância [!UICONTROL DIL]. Uma tentativa malsucedida retorna um objeto de erro (não lançado) se o código for configurado incorretamente ou sempre que um erro for encontrado.

## Propriedades de uuidCookie {#uuidcookie-props}

Define as propriedades usadas pela variável `uuidCookie`. Essa variável faz parte do método `DIL.create`.

`uuidCookie` tem as seguintes propriedades:

<!-- 

r_dil_uuid_cookie.xml

 -->

| Nome | Descrição |
|---|---|
| `name` | O nome do cookie ( `aam_did` é padrão). |
| `days` | Duração do cookie (100 dias é padrão). |
| `path` | Caminho do cookie, por exemplo, `'/test'` ( `/` é padrão). |
| `domain` | O domínio em que o cookie é definido, por exemplo, `'adobe.com'` ( `'.'+document.domain` é padrão). |
| `secure` | Define um sinalizador para enviar dados somente por uma conexão HTTPS. |

## Propriedades do visitorService {#visitor-service-props}

Define as propriedades usadas pela variável `visitorService`. Essa variável faz parte do método `DIL.create`.

`visitorService` tem as seguintes propriedades:

| Nome | Tipo | Descrição |
|---|---|---|
| `namespace` | String   | Obrigatório. Representa A ID De Organização Do Experience Cloud. Isso é necessário para a funcionalidade do Experience Cloud Core Service. O mesmo parâmetro usado para instanciar a funcionalidade da ID de visitante. |

**Amostra de código:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
