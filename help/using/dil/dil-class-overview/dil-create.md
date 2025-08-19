---
description: Cria uma instância do DIL específica do parceiro.
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: DIL create
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 4%

---

# método de criação do DIL{#dil-create}

>[!WARNING]
>
>A partir de julho de 2023, a Adobe descontinuou o desenvolvimento do [!DNL Data Integration Library (DIL)] e da extensão [!DNL DIL].
>
>Os clientes existentes podem continuar usando a implementação [!DNL DIL]. Entretanto, a Adobe não desenvolverá [!DNL DIL] além deste ponto. Os clientes são incentivados a avaliar o [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=pt-BR) para sua estratégia de coleta de dados de longo prazo.
>
>Os clientes que desejam implementar novas integrações de coleta de dados após julho de 2023 devem usar o [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=pt-BR).

## DIL create {#dil-create-new}

Cria uma instância [!UICONTROL DIL] específica do parceiro.

**Assinatura da Função:** `DIL.create: function (initConfig) {}`

**Elementos initConfig**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>A propriedade `visitorService` é *sempre* necessária. Outras propriedades listadas aqui são opcionais, a menos que indicado de outra forma.

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
   <td colname="col3"> <p>Esta propriedade define a ID de contêiner usada pelo <span class="keyword"> Audience Manager </span> para sincronizações de ID. Você definiria <code> containerNSID </code> se tiver o <span class="wintitle"> DIL </span> implantado em vários sites. Cada um desses sites terá sua própria ID de contêiner e sincronizações de ID. Quando você tem apenas um site, a ID do contêiner é 0 por padrão e você não precisa defini-lo corretamente. Entre em contato com seu consultor da para obter uma lista dos sites e suas IDs de contêiner. </p> <p>No Serviço de Identidade do Adobe Experience Platform <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR" format="https" scope="external"> </a>, a propriedade <code> idSyncContainerID </code> corresponde a <code> containerNSID </code> em <span class="wintitle"> DIL </span>. Observe o seguinte se você estiver usando o <span class="wintitle"> DIL </span> <i> e</i> o serviço de ID em vários sites: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Para cada site, defina as mesmas IDs de contêiner em <code> containerNSID </code> e <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">O <span class="wintitle"> DIL </span> e o serviço de ID tentarão enviar sincronizações de ID para nosso iFrame de coleta de dados. No entanto, o iFrame garante que o <span class="wintitle"> DIL </span> não acione uma sincronização de ID. Isso evita a duplicação. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Somente o <span class="wintitle"> DIL </span> envia dados para um <a href="../../features/destinations/destinations.md"> destino de URL </a>. </li> 
     </ul> </p> <p>Consulte também <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html?lang=pt-BR" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> é usado para transmitir: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: ID do parceiro de dados atribuída a você por <span class="keyword"> Audience Manager </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: seu identificador exclusivo para um usuário. </li> 
    </ul> <p> <p>Importante: use apenas valores não codificados para suas IDs. A codificação criará identificadores com codificação dupla. </p> </p> <p> <p>Observação: se você usar o <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR" format="https" scope="external"> Adobe Experience Platform Identity Service </a>, defina IDs do cliente com o método <code> setCustomerIDs </code> em vez de <span class="wintitle"> DIL </span>. Consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=pt-BR" format="https" scope="external"> IDs do cliente e Estados de autenticação </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Se verdadeiro, adia todas as solicitações (IFRAME, chamadas de evento, sincronização de ID e destino) da execução até o evento <code> Page Load </code> ser disparado. O padrão é <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Falso por padrão, o que significa que o <span class="keyword"> Audience Manager </span> define um cookie no domínio do parceiro (define um cookie próprio). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: este elemento foi descontinuado com o <span class="wintitle"> DIL </span> versão 8.0 (lançado em agosto de 2018). Em vez disso, use a função <code> visitor.disableIdSyncs </code> de <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=pt-BR" format="https" scope="external"> </a> no Serviço de Identidade da Adobe Experience Platform. </p> </p> <p> Se <code> true </code>, não anexará o IFRAME de publicação de destino aos destinos DOM ou fire. O padrão é <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: este elemento foi descontinuado com o <span class="wintitle"> DIL </span> versão 8.0 (lançado em agosto de 2018). Em vez disso, use a função <code> visitor.disableIdSyncs </code> de <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=pt-BR" format="https" scope="external"> </a> no Serviço de Identidade da Adobe Experience Platform. </p> </p> <p>Desativa a sincronização de ID. Você deve desativar as sincronizações de ID ao usar o DIL v6.2+ e o Serviço de ID de visitante. A função <code> visitorService </code> (veja o código de exemplo abaixo) controla essa operação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Defina como <code> true </code> para habilitar o relatório de erros para todas as instâncias <span class="wintitle"> do DIL </span> na página. Funciona somente com <code> true </code> booleano. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: este elemento foi descontinuado com o <span class="wintitle"> DIL </span> versão 8.0 (lançado em agosto de 2018). Em vez disso, use a função <code> visitor.idSyncSSLUseAkamai </code> de <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html?lang=pt-BR" format="https" scope="external"> </a> no Serviço de Identidade da Adobe Experience Platform. </p> </p> <p> Especifica se o modelo de publicação de destino deve usar Akamai para conexões HTTPS. Ativado pelo parceiro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Associa o valor de um par de valor-chave a outro. Consulte <a href="../../dil/dil-use-cases.md#map-key-values"> Mapear valores de chave para outras chaves </a>. Lançado com a v2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>Obrigatório. </p> <p>O par de valor-chave <code> namespace </code> contém sua ID da organização <span class="keyword"> do Experience Cloud </span>. Se você não tiver essa ID, poderá encontrá-la na seção <span class="wintitle"> Administração </span> do painel <span class="keyword"> Experience Cloud </span>. Você precisa de permissões de administrador para visualizar este painel. Consulte as Perguntas Frequentes sobre Recursos e Funções do Produto <a href="../../faq/faq-features.md"> </a> e Administração do <a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html?lang=pt-BR" format="https" scope="external"> - Gerenciamento de Usuários e Perguntas Frequentes </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>Obrigatório. </p> <p> Nome do parceiro fornecido por <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Remove scripts e retornos de chamada. O padrão é <code> False </code>. Aplica-se somente à instância <span class="wintitle"> do DIL </span> atual. Lançado com a v3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Define um cookie com a ID de usuário exclusiva retornada do <span class="keyword"> Audience Manager </span>. Consulte <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> Propriedades de uuidCookie </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Exigido com <span class="wintitle"> DIL </span> 6.2 ou superior. </p> <p> O DIL depende da função <code> setCustomerIDs </code> no <span class="wintitle"> Serviço de Identidade Adobe Experience Platform </span> para transmitir IDs declaradas para o <span class="keyword"> Audience Manager </span>. Consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=pt-BR" format="https" scope="external"> IDs do cliente e Estados de autenticação </a> para obter mais informações. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Código de exemplo**

Uma chamada de exemplo [!UICONTROL DIL] pode ser semelhante ao seguinte:

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

Define as propriedades usadas pela variável `uuidCookie`. Esta variável faz parte do método `DIL.create`.

`uuidCookie` tem as seguintes propriedades:

<!-- 

r_dil_uuid_cookie.xml

 -->

| Nome | Descrição |
|---|---|
| `name` | O nome do cookie ( `aam_did` é padrão). |
| `days` | Tempo de vida do cookie (100 dias é o padrão). |
| `path` | Caminho do cookie, por exemplo, `'/test'` ( `/` é padrão). |
| `domain` | O domínio em que o cookie está definido, por exemplo, `'adobe.com'` ( `'.'+document.domain` é o padrão). |
| `secure` | Define um sinalizador para enviar dados somente por uma conexão HTTPS. |

## Propriedades do visitorService {#visitor-service-props}

Define as propriedades usadas pela variável `visitorService`. Esta variável faz parte do método `DIL.create`.

`visitorService` tem as seguintes propriedades:

| Nome | Tipo | Descrição |
|---|---|---|
| `namespace` | String   | Obrigatório. Representa A ID Da Organização Experience Cloud. Isso é necessário para a funcionalidade do Serviço principal da Experience Cloud. Mesmo parâmetro usado para instanciar a funcionalidade ID de visitante. |

**Amostra de código:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
