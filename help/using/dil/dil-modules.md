---
description: Descreve métodos na namespace DIL.modules. Esses módulos permitem que você colete dados de forma programática e trabalhe com objetos Audience Manager.
seo-description: Descreve métodos na namespace DIL.modules. Esses módulos permitem que você colete dados de forma programática e trabalhe com objetos Audience Manager.
seo-title: Módulos da DIL
solution: Audience Manager
title: Módulos da DIL
uuid: d4c0d8dd-79f8-448e-b17c-c935415dd449
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 4%

---


# Módulos da DIL{#dil-modules}

Descreve métodos na namespace `DIL.modules`. Esses módulos permitem que você colete dados de forma programática e trabalhe com objetos Audience Manager.

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

Funciona com [!UICONTROL DIL] para enviar [!DNL Analytics] elementos de tags (variáveis, props, eVars etc.) para Audience Manager. Retorna dados em uma lista separada por vírgulas. Disponível na versão 2.6.

**Assinatura da função:** `DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>Você deve colocar esse código na página *antes de* a função `s.t();`.

<!-- 

r_dil_sc_init.xml

 -->

**Parâmetros**

<table id="table_A8CF8D298D944A608E2F49719F2732A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nomes </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> names </code> </td> 
   <td colname="col2"> String   </td> 
   <td colname="col3"> <p>Uma matriz de strings que contém variáveis <span class="keyword"> do Analytics </span> não enumeradas, como <code> pageName </code>, <code> channel </code>, <code> campaign </code>, <code> product </code> etc. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> iteratedNames </code> </td> 
   <td colname="col2"> Objeto </td> 
   <td colname="col3"> <p>Uma matriz de objetos que contém variáveis <span class="keyword"> do Analytics </span> enumeradas, como props e evars (por exemplo, <code> prop1 </code>, <code> prop2 </code>, <code> evar3 </code>, <code> evar4 </code>). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> maxIndex </code> </td> 
   <td colname="col2"> Número inteiro </td> 
   <td colname="col3"> <p>Indica quantos nomes repetidos você deseja retornar. Por exemplo, para retornar duas props ou evars, defina <code> maxIndex:2 </code>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> siteCatalystReportingSuite </code> </td> 
   <td colname="col2"> Objeto </td> 
   <td colname="col3"> <p>Um objeto que representa o objeto <span class="keyword"> do Analytics </span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dilInstance </code> </td> 
   <td colname="col2"> Objeto </td> 
   <td colname="col3"> <p>Um objeto que representa <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> options </code> </td> 
   <td colname="col2"> Objeto </td> 
   <td colname="col3"> <p>Opções adicionais: </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> replaceContextDataPeriodsWith </code> </p> <p>Se você não especificar outra coisa, os pontos serão substituídos pelo sublinhado padrão ( _ ). </p> <p>Por exemplo, <code> s.contextData = {abc.def = '123'} </code>resultaria em <code> c_contextData_abc_def=123 </code> na sequência de query da chamada do evento. </p> <p>Essa opção está disponível somente na versão 5.0 ou posterior do <span class="wintitle"> DIL </span> ou &lt;a0/&gt;. </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> filterFromContextVariables </code> </p> <p>Por exemplo, <code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code> resultaria na filtragem da matriz de sequências de caracteres da coleta de dados de contexto. Essa opção exclui as Informações pessoais identificáveis (PII). </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Dados capturados pelo siteCatalyst.init**

Esta função retorna detalhes sobre as seguintes propriedades [!DNL Analytics]:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `eVar` (1 - 250)
* `prop` (1 - 75)
* `pe`
* `pev1`
* `pev2`
* `pev3`

**Código de exemplo**

Esse código cria uma lista separada por vírgulas de [!DNL Analytics] eventos (props, eVars etc.) se houver valores para eles.

```
// Get the Site Catalyst object instance: 
var s = s_gi(s_account); 
  
// Instantiate DIL code: 
var scDil = DIL.create({ 
        partner: 'adobe', 
        containerNSID: 5 
}); 
 
// Use the module: 
DIL.modules.siteCatalyst.init(s, scDil, { 
        //Specify the Site Catalyst variables you want to capture: 
        names: ['pageName', 'channel', 'campaign'], 
        //Use this to create iterated variable names: 
        iteratedNames: [{ 
               name: 'eVar', 
               maxIndex: 75 
        }, { 
               name: 'prop', 
               maxIndex: 75 
        }] 
});
```

Para rastrear todos os pontos de dados [!DNL Analytics] monitorados sem a função adicional mostrada acima, chame `siteCatalyst.init` por si mesmo assim:

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

A função `GA.submitUniversalAnalytics();` envia dados de [!DNL Universal Analytics] do Google para o Audience Manager. Esta função [!UICONTROL DIL] foi projetada para funcionar com `analytics.js`, que é a biblioteca de códigos mais recente do Google [!DNL Universal Analytics].

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] não tem nenhum insight ou controle sobre a biblioteca de  `analytics.js` códigos do Google. Você deve verificar se a coleta de dados [!UICONTROL DIL] ainda está funcionando se ou quando o Google lançar novas versões do `analytics.js`.
   >
   >
* Você não poderá usar `GA.submitUniversalAnalytics();` se ainda estiver trabalhando com o código de rastreamento herdado do Google Analytics (por exemplo, `ga.js` ou `dc.js`). Em vez disso, consulte [GA.init](../dil/dil-modules.md#ga-init).

>



**Assinatura da função:** `DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**Propriedades**

A função `GA.submitUniversalAnalytics();` aceita as seguintes propriedades.

<table id="table_8E0C1E4B17D541259E72B88F02BE4503"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Propriedade </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> gaObject </code> </p> </td> 
   <td colname="col2"> <p>A variável global para sua instância de <span class="keyword"> Google Analytics </span>. Normalmente, isso é <code> ga </code> por padrão, a menos que você tenha personalizado seu código <span class="keyword"> Google Analytics </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance </code> </p> </td> 
   <td colname="col2"> <p>A variável que representa a sua instância de <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> internalPropertyName </code> </p> </td> 
   <td colname="col2"> <p> <i>(Opcional)</i> Na  <code> analytics.js </code> biblioteca, a propriedade interna é a variável minified  <code> 'b' </code>. Essa variável contém dados <span class="keyword"> Google Analytics </span>. </p> <p>Essa propriedade é opcional, pois não é necessário defini-la a menos que o Google altere o nome de sua variável interna. Por exemplo, se essa variável minified mudou para <code> 'a' </code>, você chamaria <code> GA.submitUniversalAnalytics(); </code> desta forma: </p> <p> <code> DIL.modules.GAsubmitUniversalAnalytics(ga, DilInstance, 'a'); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemplo**

Lembre-se de definir o objeto [!DNL Google Analytics] `ga` primeiro, antes de chamar [!UICONTROL DIL] e `GA.submitUniversalAnalytics();`. Seu código pode ser semelhante a este:

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

## GA.init {#ga-init}

A função `GA.init()` envia dados da versão herdada/obsoleta de [!DNL Google Analytics] para o Audience Manager.

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` funciona somente com o código de rastreamento do Google Analytics herdado  `ga.js` ou  `dc.js`. Não é possível invocar essa função [!UICONTROL DIL] se você usar `analytics.js`, que é a biblioteca de códigos mais recente para o Google [!DNL Universal Analytics]. [!DNL Audience Manager] clientes que usam  [!UICONTROL DIL] e  [!DNL Universal Analytics] devem ver  [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics).

**Assinatura da função:** `DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**Parâmetros**

| Nome | Tipo | Descrição |
|---|---|---|
| `_gaq` | Matriz | Um storage que contém comandos GA. |
| `dilInstance` | Objeto | Um objeto que contém a instância DIL. |
| `trackVars` | Objeto | *(Opcional)* Um objeto que consiste na  `names` propriedade. Essa propriedade é uma matriz de nomes de comando GA que você deseja rastrear. |

**Chamadas de função GA suportadas**

Por padrão, `GA.init` captura dados das seguintes funções:

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL cria chaves para dados GA**

O Audience Manager aceita dados na forma de pares de valores chave enquanto o GA trabalha com itens em um storage. Para trabalhar com dados GA, [!UICONTROL DIL] cria automaticamente um par de valores chave e forma uma chave como esta: `c_ <key name>`. Além disso, os itens em arrays GA são exibidos em uma ordem específica. Como resultado, você deve fornecer todos os parâmetros nessa ordem, mesmo quando eles não contêm dados. [!UICONTROL DIL] mapeia chaves para os seguintes métodos GA:

```js
// Tracking Social Interactions 
_gaq.push(['_trackSocial', 
    'facebook',                        // c_socialNetwork 
    'like',                            // c_socialAction 
    'https://www.adobe.com/cool.php',   // c_socialTarget 
    '/cool.php'                        // c_socialPagePath 
]);  
 
// Tracking a Transaction 
_gaq.push(['_addTrans', 
   '1234',           // c_transOrderId 
   'Womens Apparel', // c_transAfflication 
   '28.28',          // c_transTotal 
   '1.29',           // c_tranTax 
   '15.00',          // c_transShipping 
   'San Jose',       // c_transCity 
   'California',     // c_transState 
   'USA'             // c_transCountry 
]); 
 
// Tracking an item 
_gaq.push(['_addItem', 
   '1234',           // c_itemOrderId=1234 
   'DD44',           // c_itemSku 
   'T-Shirt',        // c_itemName 
   'Olive Medium',   // c_itemCategory 
   '11.99',          // c_itemPrice 
   '1'               // c_itenQuantity 
]);
```

**Código de exemplo**

```js
// DIL JavaScript library needs to be loaded and executed here 
var dilInstance = DIL.create({ 
    partner : "adobe" 
}); 
 
// Assume ga.js has not loaded 
var _gaq = _gaq || []; 
_gaq.push( 
  ['_setAccount', 'UA-XXXXX-X'], 
  ['_setDomainName', 'example.com'], 
  ['_setCustomVar', 1, 'Section', 'Life & Style', 3], 
  ['_trackPageview'] 
); 
_gaq.push([ 
  '_addItem', 
  '1234',         // order ID - necessary to associate item with transaction 
  'DD44',         // SKU/code - required 
  'T-Shirt',      // product name - necessary to associate revenue with product 
  'Olive Medium', // category or variation 
  '11.99',        // unit price - required 
  '1'             // quantity - required 
]); 
```

Para rastrear todas as métricas GA monitoradas sem a função adicional mostrada acima, chame `GA.init` por si mesmo assim:

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**Chamada de Evento de exemplo**

A chamada de evento de URL para Audience Manager pode ser semelhante a:

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORELIKETHIS]
>
>* [Código de rastreamento de Google Analytics](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [Atualização completa na Web: ga.js/dc.js ao analytics.js](https://developers.google.com/analytics/devguides/collection/upgrade/reference/gajs-analyticsjs)
>* [Adicionar analytics.js ao seu site](https://developers.google.com/analytics/devguides/collection/analyticsjs/)
>* [referência dos métodos do objeto ga](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)

