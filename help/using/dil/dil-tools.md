---
description: Descreve métodos no namespace DIL. tools. Essas funções do utilitário ajudam a executar tarefas específicas.
seo-description: Descreve métodos no namespace DIL. tools. Essas funções do utilitário ajudam a executar tarefas específicas.
seo-title: Ferramentas DIL
solution: Audience Manager
title: Ferramentas DIL
uuid: 2 bc 62 ce 2-16 bd -4 e 80-b 493-c 816 ba 643 b 59
translation-type: tm+mt
source-git-commit: ac9e4f24a896ecae2ebf36dcf34a4ac8fab00cd8

---


# Ferramentas DIL

Describes methods in the `DIL.tools` namespace. Essas funções do utilitário ajudam a executar tarefas específicas.

<!-- 

c_dil_functions.xml

 -->

## Getsearchreferrer

Retorna os termos de pesquisa usados para alcançar a página atual.

<!-- 

r_dil_get_search_referrer.xml

 -->

### Purpose of `getSearchReferrer`

In DIL, `getSearchReferrer` returns search results (names and key words) used to reach your site. You can pass in specific search terms to this function or let it search the supported search engines ( [!DNL AOL], [!DNL Ask], [!DNL Bing], [!DNL Google], and [!DNL Yahoo]) against `document.referrer` by default.

### Assinatura da função

Function signature: `DIL.tools.getSearchReferrer(uri, initConfig)`

### Parâmetros de função

`getSearchReferrer` aceita:

* *`{string}`*: *(Opcional)* Uma string contendo o URL de pesquisa (usa `document.referrer` se não estiver definido).
* *`{object}`*: *(Opcional)* Um objeto que contém a configuração para o `hostPattern`, `queryParam`ou `queryPattern`.

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
      <code>var &amp; amp; nbsp; resultados e amp; nbsp; = &amp; amp; nbsp; DIL. tools. getsearchreferrer ();</code> 
  </td>
  </tr> 
  <tr> 
   <td>Enviar um URL personalizado</td> 
   <td>Retorna o referenciador de pesquisa com base em um URL personalizado.</td> 
   <td> 
  <code>
        var results = 
    DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>Corresponder nome do host do URL com um Regex personalizado</b></td> 
   <td> Passe um regex personalizado para corresponder ao nome de host da URL de referência. </td> 
   <td> 
  <code>
      var results = 
    DIL.tools.getSearchReferrer("https://www.ehow.com/
    search.aspx?q=adobe+rules",{ 
       hostPattern:/ehow\./, 
         queryParam:"p" 
      }); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>Corresponder padrões de pesquisa com um Regex personalizado</b> </td> 
   <td> Passe um regex personalizado para realizar uma pesquisa personalizada. </td> 
   <td> 
    <code>
      var results = 
    DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
    {
       hostPattern:/ehow\./, 
           search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      });
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## Decomposeuri

Disassembles a Uniform Resource Identifier ( [!DNL URI]) into its constituent components: `hash`, `host`, `href`, `pathname`, `protocol`, `search`, and `[!DNL uriParams]`.

<!-- 

r_dil_decompose.xml

 -->

Function signature: `DIL.tools.decomposeURI`

### Parâmetros de função

`decomposeURI` aceita:

* *`uri {string}`*: *(Opcional)* Uma string contendo a URI. Defaults to `document.location.href` if not specified.

E retorna:

* *`{object}`*: Um objeto que contém nomes e palavras-chave válidos.

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

## Getmetatags

Pesquisa conteúdo específico definido nas tags meta em uma página da Web e retorna esses dados em um objeto.

<!-- 

r_dil_get_metatags.xml

 -->

### Assinatura da função

Function signature: `DIL.tools.getMetaTags( 1 or more parameters)`

### Parâmetros de função

`getMetaTags` aceita um ou mais parâmetros de nome (tipo de string) para pesquisar. Retorna um objeto composto por pares chave-valor.

### Código de exemplo

<pre class="&ldquo;javascript&rdquo;"><code>var datalib = DIL. create ({ 
 parceiro: '<i>Partnername '</i>, 
 Containernsid: <i>Containernsid</i> }); 
Datalib. api. signals (DIL. tools. getmetatags ('<i>application</i>','<i>keywords</i>','<i>description</i>'),' c_'). submit ();</code>
</pre>

<pre><code>
var dataLib = DIL.create({ 
     partner: <i>`partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 
dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
