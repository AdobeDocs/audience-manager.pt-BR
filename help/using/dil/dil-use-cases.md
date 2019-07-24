---
description: Amostras de código e descrições para casos de uso de DIL específicos.
seo-description: Amostras de código e descrições para casos de uso de DIL específicos.
seo-title: Casos de uso de DIL e amostras de código
solution: Audience Manager
title: Casos de uso de DIL e amostras de código
uuid: 27995 c 2 d -6572-438 e-af 99-b 5477 f 090 ae 9
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DIL Use Cases and Code Samples{#dil-use-cases-and-code-samples}

Amostras de código e descrições para casos de uso de DIL específicos.

<!-- 

c_dil_use_case.xml

 -->

## Send Data Elements to Audience Manager with DIL {#send-data-elements-dil}

Crie uma variável de objeto que envia informações sobre elementos de página para o Audience Manager. Isso é útil para a coleta de dados geral ou como uma alternativa à coleta de dados com variáveis do Analytics.

<!-- 

c_dil_send_page_objects.xml

 -->

**Descrição**

The following code demonstrates how to collect page data and send it to Audience Manager with [!UICONTROL DIL]. Esses exemplos usam uma variável para manter os elementos de dados em uma lista fixa ou em uma matriz. Remember, pass in variables as [key-value pairs](../reference/key-value-pairs-explained.md). Also, note the `c_` prefix before the key in the key-value pair. This [required prefix](../features/traits/trait-variable-prefixes.md) identifies information as user-defined data. In the first example, you need to manually append `c_` to the key. In the second example, [!UICONTROL DIL] does this for you automatically.

**Manter propriedades de valor consistente**

Lembre-se de manter as propriedades do valor iguais ao passar os dados. Por exemplo, se você tiver duas teclas idênticas com valores diferentes, o valor do último par de valor chave terá precedência sobre os objetos de valor anteriores. For example, passing in `color:blue` and `color:red` sets the returned value to red (overwrites blue).

**Exemplo 1: Enviar dados como pares de valores chave**

Esse exemplo básico envia dados de cor e preço para o Audience Manager na forma de pares de valor chave. Seu código pode ser semelhante ao seguinte:

<pre class="&ldquo;java&rdquo;"><code>var sample_ dil = DIL. create ({parceiro: "<i>nome do parceiro</i>"}); 
sample_ dil. api. signals ({ 
 c_ color: " blue ", 
 c_ price: " 900 "}); 
sample_ dil. api. submit ();</code>
</pre>

**Exemplo 2: Enviar dados em um objeto**

Este exemplo avançado demonstra como enviar dados em um objeto para o Audience Manager. When working with this method, [!UICONTROL DIL] lets you pass an object as a function parameter into the [!DNL signals()] method. [!UICONTROL DIL] Seu código pode ser semelhante ao seguinte:

<pre class="java"><code>var my_ object = { 
 cor: " blue ", 
 preço: " 900 "}; 
 
var sample_ dil = DIL. create ({parceiro: "<i>nome do parceiro</i>"}); 
//Load o objeto e anexar "c_" a todas as teclas nos pares chave-valor e enviar dados para o audiencemanager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**Exemplo 3: Enviar dados de página em uma matriz**

In this case, the variable `my_object` uses an array to hold data. Este exemplo cria as informações transmitidas pelo método recomendado acima, mas adiciona uma camada adicional para acomodar um tipo e modelo de produto. Seu código pode ser semelhante ao seguinte:

<pre class="java"><code>var my_ objects = [{ 
 cor: " blue ", 
 preço: " 900 "}, 
{ 
 type: " acura ", 
 modelo: " tl "}]; 
 
var sample_ dil = DIL. create ({parceiro: "<i>nome do parceiro</i>"}); 
 
for (var i = 0; i &lt; my_ objects. length; i + +) 
//Load o objeto e anexar "c_" a todas as teclas nos pares chave-valor. 
{ 
    sample_dil.api.signals(my_objects[i], "c_"); 
} 
sample_dil.api.submit();
</code></pre>

>[!MORE_ LIKE_ THIS]
>
>* [sinais](../dil/dil-instance-methods.md#signals)


## Capture Referring URL {#capture-referring-url}

Capture e envie um URL de referência para o Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Esse método funciona apenas quando os usuários se movimentam entre páginas com protocolos semelhantes (HTTP vs HTTPS). Por exemplo, o navegador retém um URL de referência quando você navega de um site seguro para outro site seguro. Os navegadores não retêm a URL de referência quando você se move entre sites seguros e desprotegidos. This behavior is normal browser functionality and cannot be circumvented by [!UICONTROL DIL].

**Amostra de código**

Seu código pode ser semelhante ao seguinte:

<pre class="java"><code>var adobe_ dil = DIL. create ({parceiro: "<i>nome do parceiro</i>"}); 
adobe_ dil. api. signals ({d_ referer: document. referrer}). submit ();</code>
</pre>

## Capture Search Engine Types and Keyword Search Terms {#capture-search-engine-types}

Envie informações sobre o tipo de mecanismo de pesquisa e pesquisas de palavras-chave para o Audience Manager.

<!-- 

c_dil_search_engine_valid.xml

 -->

**Mecanismos de pesquisa suportados**

By default, `DIL.getSearchReferrer` recognizes searches from these search engines (including international variations):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Descrição**

O código a seguir demonstra como obter o referenciador de pesquisa para qualquer mecanismo de pesquisa compatível. In this case, let's assume a user searched on the term "homes" from [!DNL Google] Canada ( `www.google.ca`). Esse código ajudará você a capturar esses termos de pesquisa e a enviá-los ao Audience Manager.

**Código básico**

Basic code for getting the search referrer (from `google.com`, for example) looks like this:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Amostra de código do mecanismo de pesquisa listada**

In this case, let's assume that a user searched for the term "homes" from [!DNL Google] Canada ( `www.google.ca`). Note how the code prefixes the required `c_` parameter to search engine ( `c_se`) and search term ( `c_st`). `c_` é um [prefixo](../features/traits/trait-variable-prefixes.md) obrigatório que identifica essas variáveis definidas pelo cliente no Audience Manager.

<pre class="java"><code>var adobe_ dil = DIL. create ({parceiro: "<i>nome do parceiro</i>"}); 
var search_ referrer = DIL. tools. getsearchreferrer (); 
 
if (search_ referrer &amp; &amp; search_ referrer. valid) { 
 adobe_ dil. api. signals ({ 
 c_ se: se. name, 
 c_ st: se. keywords 
 })). submit (); 
}}</code>
</pre>

**Exemplo de código de mecanismo de pesquisa não listado**

In this case, let's assume that a user searched for the term "homes" from `dogpile.com`. Because [!DNL Dogpile] is not supported by default, you can configure DIL to recognize this search engine and return the search terms to Audience Manager. Seu código pode ser semelhante ao seguinte:

<pre class="java"><code>var adobe_ dil = DIL. create ({parceiro: "<i>nome do parceiro</i>"}); 
var search_ referrer = DIL. tools. getsearchreferrer (document. referrer, { 
 Hostpattern: /dogpile\./, 
    queryParam:"q" 
}); 
 
if (search_referrer &amp;&amp; search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

## Map Key Values to Other Keys {#map-key-values}

Associe o valor de um par de valor chave a outra chave.

<!-- 

c_dil_map_keys.xml

 -->

**Descrição**

In a key-value pair, the `c_` prefix appended to the key identifies the signal as customer-defined data. Os dados definidos pelo cliente são usados para direcionamento no site específico que passou em dados em uma chamada de evento. No entanto, às vezes você deseja que essas informações sejam disponibilizadas em todas as propriedades na conta do Audience Manager. To do this, map the value in a `c_` key-value pair to a platform level key. A platform level key is prefixed with `d_` and makes the signal available for targeting across all properties in your account.

Por exemplo, você coleta dados de código postal de um site específico, mas quer direcioná-lo a todas as propriedades do Audience Manager. To make the ZIP code available at the platform level, you could map your customer-defined ZIP code key (e.g. `c_zip`) to a platform defined key as shown below.

**Amostra de código**

Seu código pode ser semelhante ao seguinte:

```java
var adobe_dil = DIL.create({ 
    partner : "adobe", 
    mappings : { 
        c_zip : 'd_zip', 
        d_key2 : 'h_dil_key2' 
    } 
}); 
adobe_dil.api.signals({c_zip : '10010'}).submit(); 
// Request will look like /event?c_zip=10010&d_zip=10010
```

>[!MORE_ LIKE_ THIS]
>
>* [Requisitos de prefixo para variáveis principais](https://marketing.adobe.com/resources/help/en_US/aam/r_tb_variable_prefixes.html)


## Traffic DIL in Google Tag Manager (GTM) {#traffic-dil-gtm}

Configure e forneça DIL com uma tag GTM.

<!-- 

t_dil_google_tagmanager.xml

 -->

This procedure assumes you have a [!DNL Google Tag Manager] account, some working knowledge of that product, and your Audience Manager `dil.js` file.

To traffic the `dil.js` file in GTM:

1. Crie um novo contêiner ou abra um contêiner existente.
1. Adicione uma nova tag ao contêiner.
1. Abra a tag para editá-la e:

   * Dê um nome para a tag.
   * Select **[!UICONTROL Custom HTML Tag]** from the **[!UICONTROL Tag Type]** drop-down list.
   * In the HTML field, place the [!UICONTROL DIL] code (library + the custom code) within script tags `<script>DIL code</script>`.
   * Clique em **[!UICONTROL Save]**.

1. Publique o contêiner.
1. Gere o código de tag do contêiner e coloque-o em seu inventário.

>[!MORE_ LIKE_ THIS]
>
>* [Centro de Ajuda do Google Tag Manager](https://support.google.com/tagmanager#topic=3441530)

