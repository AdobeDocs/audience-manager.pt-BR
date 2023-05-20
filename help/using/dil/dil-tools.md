---
description: Descreve métodos no namespace DIL.tools. Essas funções de utilitário o ajudam a executar tarefas específicas.
seo-description: Describes methods in the DIL.tools namespace. These utility functions help you perform specific tasks.
seo-title: DIL Tools
solution: Audience Manager
title: Ferramentas da DIL
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: DIL Implementation
exl-id: 1f52eb95-8287-4dd0-b933-00de6926a797
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 5%

---

# Ferramentas da DIL

Descreve métodos na variável `DIL.tools` namespace. Essas funções de utilitário o ajudam a executar tarefas específicas.

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

Retorna os termos de pesquisa usados para acessar a página atual.

<!-- 

r_dil_get_search_referrer.xml

 -->

### Finalidade de `getSearchReferrer`

No DIL, `getSearchReferrer` retorna os resultados da pesquisa (nomes e palavras-chave) usados para acessar seu site. Você pode transmitir termos de pesquisa específicos para esta função ou permitir que ela pesquise nos mecanismos de pesquisa compatíveis ( [!DNL AOL], [!DNL Ask], [!DNL Bing], [!DNL Google], e [!DNL Yahoo]) contra `document.referrer` por padrão.

### Assinatura de função

Assinatura da função: `DIL.tools.getSearchReferrer(uri, initConfig)`

### Parâmetros de função

`getSearchReferrer` aceita:

* *`{string}`*: *(Opcional)* Uma string contendo o URL de pesquisa (usa `document.referrer` se indefinido).
* *`{object}`*: *(Opcional)* Um objeto que contém a configuração do `hostPattern`, `queryParam`ou `queryPattern`.

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
      <code>var&amp;nbsp;results&amp;nbsp;=&amp;nbsp;DIL.tools.getSearchReferrer();</code> 
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
   <td> <b>Combinar nome de host de URL com um regex personalizado</b></td> 
   <td> Transmita um regex personalizado para corresponder ao nome do host do URL de referência. </td> 
   <td> 
  <code>
      var results = 
        DIL.tools.getSearchReferrer("https://www.ehow.com/
      search.aspx?q=adobe+rules",{ 
      &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
      &nbsp;&nbsp;&nbsp;queryParam:"p" 
      }); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>Combinar padrões de pesquisa com um regex personalizado</b> </td> 
   <td> Transmita um regex personalizado para executar uma pesquisa personalizada. </td> 
   <td> 
    <code>
      var&nbsp;results&nbsp;= 
      DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
      {
        &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
        &nbsp;&nbsp;&nbsp;search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      });
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## decomporURI

Desmonta um Identificador Uniforme de Recurso ( [!DNL URI]) nos seus componentes: `hash`, `host`, `href`, `pathname`, `protocol`, `search`, e `[!DNL uriParams]`.

<!-- 

r_dil_decompose.xml

 -->

Assinatura da função: `DIL.tools.decomposeURI`

### Parâmetros de função

`decomposeURI` aceita:

* *`uri {string}`*: *(Opcional)* Uma string contendo o URI. O padrão é `document.location.href` se não especificado.

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

`getMetaTags` aceita um ou mais parâmetros de nome (tipo string) para procurar. Ele retorna um objeto composto por pares de valores chave.

### Código de exemplo

<pre class="&ldquo;javascript&rdquo;"><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>', '<i>keywords</i>',  '<i>description</i>'), 'c_').submit();
</code></pre>

<pre><code>
var dataLib = DIL.create({ 
     partner: <i>`partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
