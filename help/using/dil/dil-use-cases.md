---
description: Amostras de código e descrições para casos de uso de DIL específicos.
seo-description: Amostras de código e descrições para casos de uso de DIL específicos.
seo-title: Casos de uso de DIL e amostras de código
solution: Audience Manager
title: Casos de uso de DIL e amostras de código
uuid: 27995 c 2 d -6572-438 e-af 99-b 5477 f 090 ae 9
translation-type: tm+mt
source-git-commit: 8763bff3960e2033951cf68e65f5ad44377b2917

---


# Casos de uso de DIL e amostras de código{#dil-use-cases-and-code-samples}

Amostras de código e descrições para casos de uso de DIL específicos.

<!-- 

c_dil_use_case.xml

 -->

## Enviar elementos de dados para o Audience Manager com DIL {#send-data-elements-dil}

Crie uma variável de objeto que envia informações sobre elementos de página para o Audience Manager. Isso é útil para a coleta de dados geral ou como uma alternativa à coleta de dados com variáveis do Analytics.

<!-- 

c_dil_send_page_objects.xml

 -->

**Descrição**

O código a seguir demonstra como coletar dados de página e enviá-los para o Audience Manager com [!UICONTROL DIL]. Esses exemplos usam uma variável para manter os elementos de dados em uma lista fixa ou em uma matriz. Lembre-se, passe variáveis como pares [de valores chave](../reference/key-value-pairs-explained.md). Além disso, observe o `c_` prefixo antes da chave no par de valor chave. Esse [prefixo necessário](../features/traits/trait-variable-prefixes.md) identifica informações como dados definidos pelo usuário. No primeiro exemplo, é necessário anexar `c_` manualmente à chave. No segundo exemplo, [!UICONTROL DIL] isso é feito automaticamente para você.

**Manter propriedades de valor consistente**

Lembre-se de manter as propriedades do valor iguais ao passar os dados. Por exemplo, se você tiver duas teclas idênticas com valores diferentes, o valor do último par de valor chave terá precedência sobre os objetos de valor anteriores. Por exemplo, passar e `color:blue``color:red` definir o valor retornado como vermelho (sobrescrever azul).

**Exemplo 1: Enviar dados como pares de valores chave**

Esse exemplo básico envia dados de cor e preço para o Audience Manager na forma de pares de valor chave. Seu código pode ser semelhante ao seguinte:

<pre class="&ldquo;java&rdquo;"><code>var sample_ dil = DIL. create ({parceiro: "<i>nome do parceiro</i>"}); 
sample_ dil. api. signals ({ 
 c_ color: " blue ", 
 c_ price: " 900 "}); 
sample_ dil. api. submit ();</code>
</pre>

**Exemplo 2: Enviar dados em um objeto**

Este exemplo avançado demonstra como enviar dados em um objeto para o Audience Manager. Ao trabalhar com esse método, [!UICONTROL DIL] permite que você passe um objeto como um parâmetro de função no [!DNL signals()] método. [!UICONTROL DIL] Seu código pode ser semelhante ao seguinte:

<pre class="java"><code>var my_ object = { 
 cor: " blue ", 
 preço: " 900 "}; 
 
var sample_ dil = DIL. create ({parceiro: "<i>nome do parceiro</i>"}); 
//Load o objeto e anexar "c_" a todas as teclas nos pares chave-valor e enviar dados para o audiencemanager. 
sample_ dil. api. signals (my_ object, "c_"). submit ();</code>
</pre>

**Exemplo 3: Enviar dados de página em uma matriz**

Nesse caso, a variável `my_object` usa uma matriz para manter os dados. Este exemplo cria as informações transmitidas pelo método recomendado acima, mas adiciona uma camada adicional para acomodar um tipo e modelo de produto. Seu código pode ser semelhante ao seguinte:

<pre class="java"><code>var my_ objects = [{ 
 cor: " blue ", 
 preço: " 900 "}, 
{ 
 type: " acura ", 
 modelo: " tl "}]; 
 
var sample_ dil = DIL. create ({parceiro: "<i>nome do parceiro</i>"}); 
 
for (var i = 0; i &lt; my_ objects. length; i + +) 
//Load o objeto e anexar "c_" a todas as teclas nos pares chave-valor. 
{{ 
 sample_ dil. api. signals (my_ objects [i], "c_"); 
} 
sample_ dil. api. submit ();</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [sinais](../dil/dil-instance-methods.md#signals)


## Captura de URL de referência {#capture-referring-url}

Capture e envie um URL de referência para o Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Esse método funciona apenas quando os usuários se movimentam entre páginas com protocolos semelhantes (HTTP vs HTTPS). Por exemplo, o navegador retém um URL de referência quando você navega de um site seguro para outro site seguro. Os navegadores não retêm a URL de referência quando você se move entre sites seguros e desprotegidos. Esse comportamento é uma funcionalidade normal do navegador e não pode ser contornada [!UICONTROL DIL]por.

**Amostra de código**

Seu código pode ser semelhante ao seguinte:

<pre class="java"><code>var adobe_ dil = DIL. create ({parceiro: "<i>nome do parceiro</i>"}); 
adobe_ dil. api. signals ({d_ referer: document. referrer}). submit ();</code>
</pre>

## Capturar tipos de mecanismos de pesquisa e pesquisar palavras-chave {#capture-search-engine-types}

Envie informações sobre o tipo de mecanismo de pesquisa e pesquisas de palavras-chave para o Audience Manager.

>[!IMPORTANT]
>
>Esta seção descreve a funcionalidade herdada, que não é compatível com as versões mais recentes do DIL.

**Mecanismos de pesquisa suportados**

Por padrão `DIL.getSearchReferrer` , reconhece pesquisas desses mecanismos de pesquisa (incluindo variações internacionais):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Descrição**

O código a seguir demonstra como obter o referenciador de pesquisa para qualquer mecanismo de pesquisa compatível. Nesse caso, vamos supor que um usuário pesquisou no termo "domicílios" de [!DNL Google] Canadá ( `www.google.ca`). Esse código ajudará você a capturar esses termos de pesquisa e a enviá-los ao Audience Manager.

**Código básico**

O código básico para obter o referenciador de pesquisa (de `google.com`, por exemplo) é desta forma:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Amostra de código do mecanismo de pesquisa listada**

Nesse caso, vamos supor que um usuário pesquisou pelo termo "domicílios" de [!DNL Google] Canadá ( `www.google.ca`). Observe como o código coloca o parâmetro obrigatório `c_` no parâmetro de pesquisa ( `c_se`) e no termo de pesquisa ( `c_st`). `c_` é um [prefixo](../features/traits/trait-variable-prefixes.md) obrigatório que identifica essas variáveis definidas pelo cliente no Audience Manager.

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

Nesse caso, vamos supor que um usuário pesquisou pelo termo "domiciliar". `dogpile.com` Como [!DNL Dogpile] não é suportado por padrão, você pode configurar o DIL para reconhecer este mecanismo de pesquisa e retornar os termos de pesquisa ao Audience Manager. Seu código pode ser semelhante ao seguinte:

<pre class="java"><code>var adobe_ dil = DIL. create ({parceiro: "<i>nome do parceiro</i>"}); 
var search_ referrer = DIL. tools. getsearchreferrer (document. referrer, { 
 Hostpattern: /dogpile\./, 
 Queryparam: " q "}); 
 
if (search_ referrer &amp; &amp; search_ referrer. valid) { 
 adobe_ dil. api. signals ({ 
 c_ se: se. name, 
 c_ st: se. keywords 
 })). submit (); 
}}</code>
</pre>

## Mapear valores chave para outras teclas {#map-key-values}

Associe o valor de um par de valor chave a outra chave.

<!-- 

c_dil_map_keys.xml

 -->

**Descrição**

Em um par de valor chave, o `c_` prefixo anexado à chave identifica o sinal como dados definidos pelo cliente. Os dados definidos pelo cliente são usados para direcionamento no site específico que passou em dados em uma chamada de evento. No entanto, às vezes você deseja que essas informações sejam disponibilizadas em todas as propriedades na conta do Audience Manager. Para fazer isso, mapeie o valor em um par `c_` de valor chave para uma tecla de nível de plataforma. Uma tecla de nível de plataforma tem o prefixo `d_` e torna o sinal disponível para definição de metas em todas as propriedades em sua conta.

Por exemplo, você coleta dados de código postal de um site específico, mas quer direcioná-lo a todas as propriedades do Audience Manager. Para tornar o código ZIP disponível no nível da plataforma, é possível mapear a chave de código ZIP definida pelo cliente (ex: `c_zip`) a uma chave definida da plataforma, como mostrado abaixo.

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


## Tráfego DIL no Google Tag Manager (GTM) {#traffic-dil-gtm}

Configure e forneça DIL com uma tag GTM.

<!-- 

t_dil_google_tagmanager.xml

 -->

Este procedimento considera que você tem [!DNL Google Tag Manager] uma conta, um conhecimento de trabalho desse produto e seu `dil.js` arquivo do Audience Manager.

Para carregar o `dil.js` arquivo no GTM:

1. Crie um novo contêiner ou abra um contêiner existente.
1. Adicione uma nova tag ao contêiner.
1. Abra a tag para editá-la e:

   * Dê um nome para a tag.
   * Select **[!UICONTROL Custom HTML Tag]** from the **[!UICONTROL Tag Type]** drop-down list.
   * No campo HTML, coloque o [!UICONTROL DIL] código (biblioteca + o código personalizado) nas tags `<script>DIL code</script>`de script.
   * Clique em **[!UICONTROL Save]**.

1. Publique o contêiner.
1. Gere o código de tag do contêiner e coloque-o em seu inventário.

>[!MORE_ LIKE_ THIS]
>
>* [Centro de Ajuda do Google Tag Manager](https://support.google.com/tagmanager#topic=3441530)

