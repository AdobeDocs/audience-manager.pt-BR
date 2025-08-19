---
description: Descreve métodos no namespace DIL.tools. Essas funções de utilitário ajudam você a executar tarefas específicas.
seo-description: Describes methods in the DIL.tools namespace. These utility functions help you perform specific tasks.
seo-title: DIL Tools
solution: Audience Manager
title: Ferramentas do DIL
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: DIL Implementation
exl-id: 1f52eb95-8287-4dd0-b933-00de6926a797
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 2%

---

# Ferramentas do DIL

>[!WARNING]
>
>A partir de julho de 2023, a Adobe descontinuou o desenvolvimento do [!DNL Data Integration Library (DIL)] e da extensão [!DNL DIL].
>
>Os clientes existentes podem continuar usando a implementação [!DNL DIL]. Entretanto, a Adobe não desenvolverá [!DNL DIL] além deste ponto. Os clientes são incentivados a avaliar o [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=pt-BR) para sua estratégia de coleta de dados de longo prazo.
>
>Os clientes que desejam implementar novas integrações de coleta de dados após julho de 2023 devem usar o [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=pt-BR).

Descreve métodos no namespace `DIL.tools`. Essas funções de utilitário ajudam você a executar tarefas específicas.

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

Retorna os termos de pesquisa usados para acessar a página atual.

<!-- 

r_dil_get_search_referrer.xml

 -->

### Finalidade de `getSearchReferrer`

No DIL, `getSearchReferrer` retorna os resultados da pesquisa (nomes e palavras-chave) usados para acessar seu site. Você pode passar termos de pesquisa específicos para esta função ou deixá-la pesquisar os mecanismos de pesquisa compatíveis ( [!DNL AOL], [!DNL Ask], [!DNL Bing], [!DNL Google] e [!DNL Yahoo]) em relação a `document.referrer` por padrão.

### Assinatura de função

Assinatura da função: `DIL.tools.getSearchReferrer(uri, initConfig)`

### Parâmetros de função

`getSearchReferrer` aceita:

* *`{string}`*: *(Opcional)* Uma cadeia de caracteres contendo a URL de pesquisa (usa `document.referrer` se não estiver definida).
* *`{object}`*: *(Opcional)* Um objeto que contém a configuração de `hostPattern`, `queryParam` ou `queryPattern`.

E retorna:

* `{object}` Um objeto que contém nomes e palavras-chave válidos.

### Exemplos

<table id="table_D035276601EC428295E4D619F05BB8D0"> 
 <thead> 
  <tr> 
   <th> Tipo de pesquisa </th> 
   <th> Descrição </th> 
   <th> Amostra de código </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Pesquisa padrão</td> 
   <td> Retorna termos de pesquisa de palavra-chave usados pelos mecanismos de pesquisa AOL, Ask, Bing, Google e Yahoo. </td> 
   <td>
      <code>var&nbsp;results&nbsp;=&nbsp;DIL.tools.getSearchReferrer();</code> 
  </td>
  </tr> 
  <tr> 
   <td>Enviar um URL personalizado</td> 
   <td>Retorna o referenciador de pesquisa com base em um URL personalizado.</td> 
   <td> 
  <code>
        var&nbsp;results&nbsp;= 
        DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>Corresponder o Nome de Host da URL a um Regex Personalizado</b></td> 
   <td> Transmita um regex personalizado para corresponder ao nome do host do URL de referência. </td> 
   <td> 
  <code>
      var results = 
        DIL.tools.getSearchReferrer("https://www.ehow.com/
      search.aspx?q=adobe+rules",&lbrace; 
      &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
      &nbsp;&nbsp;&nbsp;queryParam:"p" 
      &rbrace;); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>Corresponder padrões de pesquisa com um regex personalizado</b> </td> 
   <td> Transmita um regex personalizado para executar uma pesquisa personalizada. </td> 
   <td> 
    <code>
      var&nbsp;results&nbsp;= 
      DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
      &lbrace;
        &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
        &nbsp;&nbsp;&nbsp;search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      &rbrace;);
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## decomporURI

Desmonta um Uniform Resource Identifier ( [!DNL URI]) em seus componentes constituintes: `hash`, `host`, `href`, `pathname`, `protocol`, `search` e `[!DNL uriParams]`.

<!-- 

r_dil_decompose.xml

 -->

Assinatura da função: `DIL.tools.decomposeURI`

### Parâmetros de função

`decomposeURI` aceita:

* *`uri {string}`*: *(Opcional)* Uma cadeia de caracteres contendo o URI. O padrão é `document.location.href`, se não for especificado.

E retorna:

* *`{object}`*: um objeto que contém nomes e palavras-chave válidos.

### Código de exemplo


```javascript
var uriData = DIL.tools.decomposeURI('https://www.adobe.com/?arg1=123&arg2=456#am'); 
{ 
  hash : "#am", 
  host : "www.adobe.com", 
  hostname : "www.adobe.com", 
  href : "https://www.adobe.com/?arg1=123&arg2=456#am", 
  pathname : "", 
  protocol : "https:", 
  search : "?arg1=123&arg2=456", 
  uriParams : { 
    arg1 : "123", 
    arg2 : "456" 
  } 
}
```

## getMetaTags

Pesquisa conteúdo específico definido nas metatags de uma página da Web e retorna esses dados em um objeto.

<!-- 

r_dil_get_metatags.xml

 -->

### Assinatura de função

Assinatura da função: `DIL.tools.getMetaTags( 1 or more parameters)`

### Parâmetros de função

`getMetaTags` aceita um ou mais parâmetros de nome (tipo de sequência de caracteres) para procurar. Ele retorna um objeto composto por pares de valores chave.

### Código de exemplo

<pre class="javascript"><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>', '<i>keywords</i>',  '<i>description</i>'), 'c_').submit();
</code></pre>

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: <i>&grave;partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
