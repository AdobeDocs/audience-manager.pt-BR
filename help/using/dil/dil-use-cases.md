---
description: Amostras de código e descrições para casos de uso de DIL específicos.
seo-description: Code samples and descriptions for specific DIL use cases.
seo-title: DIL Use Cases and Code Samples
solution: Audience Manager
title: Casos de uso da DIL e exemplos de código
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
feature: DIL Implementation
exl-id: 001710be-b377-460a-9e29-7268d25a6305
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 2%

---

# Casos de uso da DIL e exemplos de código{#dil-use-cases-and-code-samples}

Amostras de código e descrições para casos de uso de DIL específicos.

<!-- 

c_dil_use_case.xml

 -->

## Enviar elementos de dados para o Audience Manager com o DIL {#send-data-elements-dil}

Crie uma variável de objeto que envia informações sobre os elementos da página para o Audience Manager. Isso é útil para a coleta de dados gerais ou como uma alternativa para a coleta de dados com as variáveis do Analytics.

<!-- 

c_dil_send_page_objects.xml

 -->

**Descrição**

O código a seguir demonstra como coletar dados de página e enviá-los para o Audience Manager com [!UICONTROL DIL]. Esses exemplos usam uma variável para manter elementos de dados em uma lista simples ou em uma matriz. Lembre-se, transmita as variáveis como [pares de valor-chave](../reference/key-value-pairs-explained.md). Além disso, observe o `c_` prefixo antes da chave no par de valores chave. Este [prefixo obrigatório](../features/traits/trait-variable-prefixes.md) identifica informações como dados definidos pelo usuário. No primeiro exemplo, é necessário anexar manualmente `c_` à chave. No segundo exemplo, [!UICONTROL DIL] O faz isso automaticamente.

**Manter propriedades de valor consistentes**

Lembre-se de manter as mesmas propriedades de valor ao transmitir os dados. Por exemplo, se você tiver duas chaves idênticas com valores diferentes, o valor do último par de valor-chave terá precedência sobre os objetos de valor anteriores. Por exemplo, transmitir `color:blue` e `color:red` define o valor retornado como vermelho (substitui azul).

**Exemplo 1: Enviar dados como pares de valores chave**

Esse exemplo básico envia dados de cor e preço para o Audience Manager na forma de pares de valores chave. O código pode ser semelhante ao seguinte:

<pre class="&ldquo;java&rdquo;"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals({ 
   c_color:"blue", 
   c_price:"900" 
}); 
sample_dil.api.submit();
</code></pre>

**Exemplo 2: Enviar dados em um objeto**

Este exemplo avançado demonstra como enviar dados em um objeto para o Audience Manager. Ao trabalhar com este método, [!UICONTROL DIL] permite passar um objeto como um parâmetro de função para a variável [!DNL signals()] método. [!UICONTROL DIL] O código pode ser semelhante ao seguinte:

<pre class="java"><code>
var my_object = { 
   color : "blue", 
   price : "900" 
}; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**Exemplo 3: enviar dados de página em um storage**

Nesse caso, a variável `my_object` O usa uma matriz para armazenar dados. Este exemplo se baseia nas informações transmitidas pelo método recomendado acima, mas adiciona uma camada adicional para acomodar um tipo e modelo de produto. O código pode ser semelhante ao seguinte:

<pre class="java"><code>
var my_objects = [{ 
   color : "blue", 
   price : "900" 
}, { 
   type : "acura", 
   model : "tl" 
}]; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
 
for (var i = 0; i < my_objects.length; i++) 
//Load the object and append "c_" to all the keys in the key-value pairs.  
{ 
    sample_dil.api.signals(my_objects[i], "c_"); 
} 
sample_dil.api.submit();
</code></pre>

## Capturar URL de referência {#capture-referring-url}

Capture e envie um URL de referência para o Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Esse método funciona somente quando os usuários se movem entre páginas com protocolos semelhantes (HTTP vs. HTTPS). Por exemplo, o navegador retém um URL de referência quando você navega de um site seguro para outro site seguro. Os navegadores não retêm o URL de referência quando você se move entre sites seguros e não seguros. Esse comportamento é uma funcionalidade normal do navegador e não pode ser contornado pelo [!UICONTROL DIL].

**Amostra de código**

O código pode ser semelhante ao seguinte:

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## Capturar Tipos de Mecanismo de Pesquisa e Termos de Pesquisa por Palavra-chave {#capture-search-engine-types}

Envie informações sobre o tipo de mecanismo de pesquisa e pesquisas por palavra-chave para o Audience Manager.

>[!IMPORTANT]
>
>Esta seção descreve a funcionalidade herdada, que não é compatível com as versões mais recentes do DIL.

**Mecanismos de pesquisa compatíveis**

Por padrão, `DIL.getSearchReferrer` O reconhece pesquisas desses mecanismos de pesquisa (incluindo variações internacionais):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Descrição**

O código a seguir demonstra como obter o referenciador de pesquisa para qualquer um dos mecanismos de pesquisa compatíveis. Nesse caso, vamos supor que um usuário pesquisou o termo &quot;homes&quot; de [!DNL Google] Canadá ( `www.google.ca`). Este código ajudará você a capturar esses termos de pesquisa e enviá-los para o Audience Manager.

**Código básico**

Código básico para obter o referenciador de pesquisa (de `google.com`, por exemplo) tem esta aparência:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Amostra de código do mecanismo de pesquisa listada**

Nesse caso, vamos supor que um usuário pesquisou o termo &quot;homes&quot; de [!DNL Google] Canadá ( `www.google.ca`). Observe como o código adiciona os prefixos necessários `c_` parâmetro para mecanismo de pesquisa ( `c_se`) e termo de pesquisa ( `c_st`). `c_` é um [prefixo obrigatório](../features/traits/trait-variable-prefixes.md) que as identifica como variáveis definidas pelo cliente para o Audience Manager.

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(); 
 
if (search_referrer && search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

**Amostra de código de mecanismo de pesquisa não listada**

Nesse caso, vamos supor que um usuário pesquisou o termo &quot;homes&quot; de `dogpile.com`. Porque [!DNL Dogpile] não é suportado por padrão, você pode configurar o DIL para reconhecer esse mecanismo de pesquisa e retornar os termos de pesquisa para o Audience Manager. O código pode ser semelhante ao seguinte:

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(document.referrer, {  
    hostPattern:/dogpile\./, 
    queryParam:"q" 
}); 
 
if (search_referrer && search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

## Mapear valores de chave para outras chaves {#map-key-values}

Associe o valor de um par de valor-chave a outra chave.

<!-- 

c_dil_map_keys.xml

 -->

**Descrição**

Em um par de valor-chave, a variável `c_` O prefixo anexado à chave identifica o sinal como dados definidos pelo cliente. Os dados definidos pelo cliente são usados para direcionamento no site específico que transmitiu dados em uma chamada de evento. No entanto, às vezes você quer que essas informações estejam disponíveis em todas as propriedades na sua conta Audience Manager. Para fazer isso, mapeie o valor em um `c_` par de valor-chave para uma chave de nível de plataforma. Uma chave de nível de plataforma recebe o prefixo `d_` e disponibiliza o sinal para direcionamento em todas as propriedades em sua conta.

Como exemplo, você coleta dados de código postal de um site específico, mas deseja direcioná-los a todas as propriedades do Audience Manager. Para disponibilizar o código postal no nível da plataforma, você pode mapear a chave de código postal definida pelo cliente (por exemplo, `c_zip`) para uma chave definida pela plataforma, conforme mostrado abaixo.

**Amostra de código**

O código pode ser semelhante ao seguinte:

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

## DIL de tráfego no Google Tag Manager (GTM) {#traffic-dil-gtm}

Configure e disponibilize o DIL com uma tag do GTM.

<!-- 

t_dil_google_tagmanager.xml

 -->

Este procedimento pressupõe que você tenha uma [!DNL Google Tag Manager] conta, algum conhecimento prático desse produto e sua Audience Manager `dil.js` arquivo.

Para rastrear o `dil.js` arquivo no GTM:

1. Criar um novo contêiner ou abrir um existente.
1. Adicione uma nova tag ao container.
1. Abra a tag para editá-la e:

   * Nomeie a tag.
   * Selecionar **[!UICONTROL Custom HTML Tag]** do **[!UICONTROL Tag Type]** lista suspensa.
   * No campo HTML, coloque a variável [!UICONTROL DIL] código (biblioteca + o código personalizado) nas tags de script `<script>DIL code</script>`.
   * Clique em **[!UICONTROL Save]**.

1. Publique o container.
1. Gere o código da etiqueta do contêiner e coloque-o no inventário.

>[!MORELIKETHIS]
>
>* [Central de ajuda do Google Tag Manager](https://support.google.com/tagmanager#topic=3441530)
>* [Sinais](../dil/dil-instance-methods.md#signals)
>* [Requisitos de prefixo para variáveis-chave](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/traits/trait-variable-prefixes.html#prefix-requirements-for-key-variables)

