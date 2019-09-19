---
description: Amostras de código e descrições para casos de uso de DIL específicos.
seo-description: Amostras de código e descrições para casos de uso de DIL específicos.
seo-title: Casos de uso DIL e exemplos de código
solution: Audience Manager
title: Casos de uso DIL e exemplos de código
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
translation-type: tm+mt
source-git-commit: 8763bff3960e2033951cf68e65f5ad44377b2917

---


# Casos de uso DIL e exemplos de código{#dil-use-cases-and-code-samples}

Amostras de código e descrições para casos de uso de DIL específicos.

<!-- 

c_dil_use_case.xml

 -->

## Enviar elementos de dados para o Audience Manager com DIL {#send-data-elements-dil}

Crie uma variável de objeto que envia informações sobre elementos de página para o Audience Manager. Isso é útil para a coleta geral de dados ou como uma alternativa para a coleta de dados com as variáveis do Analytics.

<!-- 

c_dil_send_page_objects.xml

 -->

**Descrição**

O código a seguir demonstra como coletar dados da página e enviá-los para o Audience Manager com [!UICONTROL DIL]. Esses exemplos usam uma variável para conter elementos de dados em uma lista simples ou em uma matriz. Lembre-se, passe variáveis como pares [de valor](../reference/key-value-pairs-explained.md)chave. Além disso, observe o `c_` prefixo antes da chave no par de valores chave. Esse prefixo [](../features/traits/trait-variable-prefixes.md) necessário identifica as informações como dados definidos pelo usuário. No primeiro exemplo, é necessário anexar manualmente `c_` à chave. No segundo exemplo, [!UICONTROL DIL] faz isso automaticamente para você.

**Manter propriedades de valor consistentes**

Lembre-se de manter as propriedades de valor iguais ao transmitir dados. Por exemplo, se você tiver duas chaves idênticas com valores diferentes, o valor do último par de valores chave terá prioridade sobre os objetos de valor anteriores. Por exemplo, transmitir `color:blue` e `color:red` definir o valor retornado como vermelho (substitui azul).

**Exemplo 1: Enviar dados como pares de valores chave**

Este exemplo básico envia dados de cor e preço para o Audience Manager na forma de pares de valor chave. Seu código pode ser semelhante ao seguinte:

<pre class="&ldquo;java&rdquo;"><code>
var sample_dil = DIL.create({parceiro:"nome<i>do</i>parceiro"}); 
sample_dil.api.signal({ c_color:"blue", c_price:"900" }); 
sample_dil.api.submit();
</code></pre>

**Exemplo 2: Enviar dados em um objeto**

Este exemplo avançado demonstra como enviar dados em um objeto para o Audience Manager. Ao trabalhar com esse método, [!UICONTROL DIL] permite que você passe um objeto como parâmetro de função para o [!DNL signals()] método. [!UICONTROL DIL] Seu código pode ser semelhante ao seguinte:

<pre class="java"><code>
var my_object = { color : "azul", preço : "900" }; 
 
var sample_dil = DIL.create({ parceiro : "nome<i>do</i>parceiro" }); 
//Carregue o objeto e anexe "c_" a todas as chaves nos pares de valores chave e envie dados para o AudienceManager. 
sample_dil.api.signal(my_object,"c_").submit();
</code></pre>

**Exemplo 3: Enviar dados da página em um storage**

Nesse caso, a variável `my_object` usa uma matriz para armazenar dados. Este exemplo baseia-se nas informações passadas pelo método recomendado acima, mas adiciona uma camada adicional para acomodar um tipo de produto e modelo. Seu código pode ser semelhante ao seguinte:

<pre class="java"><code>
var my_objects = [{ color : "azul", preço : "900" }, { tipo : "acura", modelo: "tl" }]; 
 
var sample_dil = DIL.create({ parceiro : "nome<i>do</i>parceiro" }); 
 
for (var i = 0; i &lt; my_objects.length; i++) //Carregue o objeto e anexe "c_" a todas as teclas nos pares de valores chave.  
{ sample_dil.api.signal(my_objects[i], "c_"); 
} sample_dil.api.submit();
</code></pre>

>[!MORE_LIKE_THIS]
>
>* [sinais](../dil/dil-instance-methods.md#signals)


## Capturar URL de referência {#capture-referring-url}

Capture e envie um URL de referência para o Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Esse método funciona somente quando os usuários se movem entre páginas com protocolos semelhantes (HTTP vs HTTPS). Por exemplo, o navegador retém um URL de referência quando você navega de um site seguro para outro site seguro. Os navegadores não retêm o URL de referência quando você se move entre sites seguros e não protegidos. Esse comportamento é a funcionalidade normal do navegador e não pode ser contornado por [!UICONTROL DIL].

**Amostra de código**

Seu código pode ser semelhante ao seguinte:

<pre class="java"><code>
var adobe_dil = DIL.create({ parceiro : "nome<i>do</i>parceiro" }); 
adobe_dil.api.signal({ d_referer : document.referrer }).submit();
</code></pre>

## Capturar tipos de mecanismo de pesquisa e termos de pesquisa de palavra-chave {#capture-search-engine-types}

Envie informações sobre pesquisas de tipos de mecanismos de pesquisa e palavras-chave para o Audience Manager.

>[!IMPORTANT]
>
>Esta seção descreve a funcionalidade herdada, que não é suportada nas versões mais recentes do DIL.

**Mecanismos de pesquisa suportados**

Por padrão, `DIL.getSearchReferrer` reconhece pesquisas desses mecanismos de pesquisa (incluindo variações internacionais):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Descrição**

O código a seguir demonstra como obter o referenciador de pesquisa para qualquer um dos mecanismos de pesquisa suportados. Nesse caso, vamos supor que um usuário pesquisou o termo "casas" do [!DNL Google] Canadá ( `www.google.ca`). Este código ajudará você a capturar esses termos de pesquisa e enviá-los para o Audience Manager.

**Código básico**

O código básico para obter o referenciador de pesquisa (de `google.com`, por exemplo) é semelhante a:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Exemplo de código do mecanismo de pesquisa listado**

Nesse caso, suponhamos que um usuário tenha procurado o termo "casas" do [!DNL Google] Canadá ( `www.google.ca`). Observe como o código prefixa o parâmetro necessário `c_` para o mecanismo de pesquisa ( `c_se`) e o termo de pesquisa ( `c_st`). `c_` é um prefixo [](../features/traits/trait-variable-prefixes.md) necessário que identifica como variáveis definidas pelo cliente para o Audience Manager.

<pre class="java"><code>
var adobe_dil = DIL.create({parceiro:"nome<i>do</i>parceiro"}); 
var search_referrer = DIL.tools.getSearchReferrer(); 
 
if (search_referrer &amp;&amp; search_referrer.valid) { adobe_dil.api.signal({ c_se : se.name, c_st : se.keywords }).submit(); 
}</code></pre>

**Amostra de código do mecanismo de pesquisa não listada**

Nesse caso, vamos supor que um usuário buscou o termo "casas" de `dogpile.com`. Como não [!DNL Dogpile] é suportado por padrão, você pode configurar o DIL para reconhecer esse mecanismo de pesquisa e retornar os termos de pesquisa ao Audience Manager. Seu código pode ser semelhante ao seguinte:

<pre class="java"><code>
var adobe_dil = DIL.create({parceiro:"nome<i>do</i>parceiro"}); 
var search_referrer = DIL.tools.getSearchReferrer(document.referrer, { hostPattern:/dogpile\./, queryParam:"q" }); 
 
if (search_referrer &amp;&amp; search_referrer.valid) { adobe_dil.api.signal({ c_se : se.name, c_st : se.keywords }).submit(); 
}</code></pre>

## Mapear valores principais para outras chaves {#map-key-values}

Associe o valor de um par de valores chave a outra chave.

<!-- 

c_dil_map_keys.xml

 -->

**Descrição**

Em um par de valor chave, o `c_` prefixo anexado à chave identifica o sinal como dados definidos pelo cliente. Os dados definidos pelo cliente são usados para direcionamento no site específico que passou os dados em uma chamada de evento. No entanto, às vezes você deseja que essas informações fiquem disponíveis em todas as propriedades da sua conta do Audience Manager. Para fazer isso, mapeie o valor em um par de valor- `c_` chave para uma chave de nível de plataforma. Uma chave de nível de plataforma tem o prefixo `d_` e disponibiliza o sinal para definição de metas em todas as propriedades da sua conta.

Por exemplo, você coleta dados de código ZIP de um site específico, mas deseja direcioná-los para todas as propriedades do Audience Manager. Para disponibilizar o código ZIP no nível da plataforma, é possível mapear a chave de código ZIP definida pelo cliente (por exemplo, `c_zip`) para uma chave definida pela plataforma, conforme mostrado abaixo.

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

>[!MORE_LIKE_THIS]
>
>* [Requisitos de prefixo para variáveis-chave](https://marketing.adobe.com/resources/help/en_US/aam/r_tb_variable_prefixes.html)


##  Tráfego DIL no Google Tag Manager (GTM) {#traffic-dil-gtm}

Configure e forneça DIL com uma tag GTM.

<!-- 

t_dil_google_tagmanager.xml

 -->

Este procedimento supõe que você tenha uma [!DNL Google Tag Manager] conta, algum conhecimento prático desse produto e seu arquivo do Audience Manager `dil.js` .

Para fazer o tráfego do `dil.js` arquivo no GTM:

1. Crie um novo contêiner ou abra um contêiner existente.
1. Adicione uma nova tag ao contêiner.
1. Abra a tag para editá-la e:

   * Nomeie a tag .
   * Select **[!UICONTROL Custom HTML Tag]** from the **[!UICONTROL Tag Type]** drop-down list.
   * No campo HTML, coloque o [!UICONTROL DIL] código (biblioteca + o código personalizado) nas tags de script `<script>DIL code</script>`.
   * Clique em **[!UICONTROL Save]**.

1. Publique o contêiner.
1. Gere o código da tag do contêiner e coloque-o no seu inventário.

>[!MORE_LIKE_THIS]
>
>* [Centro de ajuda do Google Tag Manager](https://support.google.com/tagmanager#topic=3441530)

