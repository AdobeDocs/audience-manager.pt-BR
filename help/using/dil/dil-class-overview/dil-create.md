---
description: Cria uma instância DIL específica do parceiro.
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: Criar DIL
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 10%

---

# método de criação DIL{#dil-create}

>[!WARNING]
>
>A partir de julho de 2023, a Adobe interrompeu o desenvolvimento do [!DNL Data Integration Library (DIL)] e a variável [!DNL DIL] extensão.
>
>Os clientes existentes podem continuar usando seus [!DNL DIL] execução. No entanto, o Adobe não estará em desenvolvimento [!DNL DIL] além deste ponto. Os clientes são incentivados a avaliar [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) para a sua estratégia de recolha de dados a longo prazo.
>
>Os clientes que desejam implementar novas integrações de coleta de dados após julho de 2023 devem usar [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) em vez disso.

## Criar DIL {#dil-create-new}

Cria uma conta específica do parceiro [!UICONTROL DIL] instância.

**Assinatura da Função:** `DIL.create: function (initConfig) {}`

**Elementos initConfig**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>A variável `visitorService` propriedade é *sempre* obrigatório. Outras propriedades listadas aqui são opcionais, a menos que indicado de outra forma.

`initConfig` O aceita os seguintes elementos:

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
   <td colname="col3"> <p>Essa propriedade configura a ID de contêiner usada pelo <span class="keyword">Audience Manager</span> para sincronizações de ID. Você definiria <code> containerNSID </code> se você tiver <span class="wintitle"> DIL </span> implantado em vários sites. Cada um desses sites terá sua própria ID de contêiner e sincronizações de ID. Quando você tem apenas um site, a ID do contêiner é 0 por padrão e você não precisa defini-lo corretamente. Entre em contato com seu consultor da para obter uma lista dos sites e suas IDs de contêiner. </p> <p>No <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Serviço de identidade da Adobe Experience Platform </a>, a propriedade <code> idSyncContainerID </code> corresponde a <code> containerNSID </code> in <span class="wintitle"> DIL </span>. Observe o seguinte se estiver usando <span class="wintitle"> DIL </span> <i>e</i> o serviço de ID em vários sites: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Para cada site, defina as mesmas IDs de contêiner em <code> containerNSID </code> e <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Ambos <span class="wintitle"> DIL </span> e o serviço de ID tentará enviar sincronizações de ID para nosso iFrame de coleta de dados. No entanto, o iFrame garante que <span class="wintitle"> DIL </span> não acionará uma sincronização de ID. Isso evita a duplicação. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Somente <span class="wintitle"> DIL </span> envia dados a um <a href="../../features/destinations/destinations.md"> Destino do URL </a>. </li> 
     </ul> </p> <p>Consulte também, <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> é usado para transmitir: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: ID do parceiro de dados atribuída a você por <span class="keyword"> Audience Manager </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: seu identificador exclusivo para um usuário. </li> 
    </ul> <p> <p>Importante: use apenas valores não codificados para suas IDs. A codificação das cria identificadores duplamente codificados. </p> </p> <p> <p>Observação: se você usar a variável <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Serviço de identidade da Adobe Experience Platform </a>, defina as IDs do cliente com o <code> setCustomerIDs </code> método em vez de <span class="wintitle"> DIL </span>. Consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external"> Estados de autenticação e IDs do cliente </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Se verdadeiro, adia todas as solicitações (IFRAME, chamadas de evento, sincronização de ID e destino) da execução até a variável <code> Page Load </code> evento é acionado. O padrão é <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Falso por padrão, o que significa <span class="keyword"> Audience Manager </span> define um cookie no domínio do parceiro (define um cookie primário). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: este elemento foi descontinuado com <span class="wintitle"> DIL </span> versão 8.0 (lançada em agosto de 2018). Use o <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> função </a> no Serviço de identidade da Adobe Experience Platform. </p> </p> <p> Se <code> true </code>, não anexará o IFRAME de publicação de destino aos destinos DOM ou fire. O padrão é <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: este elemento foi descontinuado com <span class="wintitle"> DIL </span> versão 8.0 (lançada em agosto de 2018). Use o <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> função </a> no Serviço de identidade da Adobe Experience Platform. </p> </p> <p>Desativa a sincronização de ID. Você deve desativar as sincronizações de ID ao usar o DIL v6.2+ e o Serviço de ID de visitante. A variável <code> visitorService </code> A função (consulte código de amostra abaixo) cuida dessa operação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Defina como <code> true </code> para ativar o relatório de erros para todos <span class="wintitle"> DIL </span> instâncias na página. Funciona com booleano <code> true </code> somente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: este elemento foi descontinuado com <span class="wintitle"> DIL </span> versão 8.0 (lançada em agosto de 2018). Use o <code> visitor.idSyncSSLUseAkamai </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external"> função </a> no Serviço de identidade da Adobe Experience Platform. </p> </p> <p> Especifica se o modelo de publicação de destino deve usar Akamai para as conexões HTTPS. Ativado pelo parceiro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Associa o valor de um par de valor-chave a outro. Consulte <a href="../../dil/dil-use-cases.md#map-key-values"> Mapear valores de chave para outras chaves </a>. Lançado com a v2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>Obrigatório. </p> <p>A variável <code> namespace </code> O par de valor-chave contém o <span class="keyword"> Experience Cloud </span> ID da organização. Se você não tiver essa ID, poderá encontrá-la na <span class="wintitle"> Administração </span> seção do <span class="keyword"> Experience Cloud </span> painel. Você precisa de permissões de administrador para visualizar este painel. Consulte a <a href="../../faq/faq-features.md"> Perguntas frequentes sobre recursos e funções do produto </a> e <a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external"> Administração - Gerenciamento de usuários e Perguntas frequentes </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>Obrigatório. </p> <p> Nome do parceiro conforme fornecido por <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Remove scripts e retornos de chamada. O padrão é <code> False </code>. Aplica-se ao atual <span class="wintitle"> DIL </span> somente instância. Lançado com a v3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Define um cookie com a ID de usuário exclusiva retornada de <span class="keyword"> Audience Manager </span>. Consulte <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> Propriedades de uuidCookie </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Obrigatório com <span class="wintitle"> DIL </span> 6.2 ou superior. </p> <p> O DIL depende do <code> setCustomerIDs </code> na caixa <span class="wintitle"> Serviço de identidade da Adobe Experience Platform </span> para transmitir IDs declaradas para o <span class="keyword"> Audience Manager </span>. Consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external">IDs do cliente e Estados de autenticação</a> para obter mais informações. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Código de exemplo**

Uma amostra [!UICONTROL DIL] A chamada do pode ser semelhante ao seguinte:

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

Uma resposta bem-sucedida retorna a variável [!UICONTROL DIL] instância. Uma tentativa malsucedida retorna um objeto de erro (não lançado) se o código for configurado incorretamente ou sempre que um erro for encontrado.

## Propriedades de uuidCookie {#uuidcookie-props}

Define as propriedades usadas pela variável `uuidCookie` variável. Essa variável faz parte da variável `DIL.create` método.

`uuidCookie` tem as seguintes propriedades:

<!-- 

r_dil_uuid_cookie.xml

 -->

| Nome | Descrição |
|---|---|
| `name` | O nome do cookie ( `aam_did` é padrão). |
| `days` | Tempo de vida do cookie (100 dias é o padrão). |
| `path` | Caminho do cookie, por exemplo, `'/test'` ( `/` é padrão). |
| `domain` | O domínio em que o cookie está definido, por exemplo, `'adobe.com'` ( `'.'+document.domain` é padrão). |
| `secure` | Define um sinalizador para enviar dados somente por uma conexão HTTPS. |

## Propriedades do visitorService {#visitor-service-props}

Define as propriedades usadas pela variável `visitorService` variável. Essa variável faz parte da variável `DIL.create` método.

`visitorService` tem as seguintes propriedades:

| Nome | Tipo | Descrição |
|---|---|---|
| `namespace` | String   | Obrigatório. Representa A ID Da Organização Experience Cloud. Isso é necessário para a funcionalidade do Serviço principal de Experience Cloud. Mesmo parâmetro usado para instanciar a funcionalidade ID de visitante. |

**Amostra de código:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
