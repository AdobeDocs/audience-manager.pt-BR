---
description: Amostras de código e descrições para casos de uso de DIL específicos.
seo-description: Amostras de código e descrições para casos de uso de DIL específicos.
seo-title: Casos de uso da DIL e exemplos de código
solution: Audience Manager
title: Casos de uso da DIL e exemplos de código
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
feature: Implementação de DIL
exl-id: 001710be-b377-460a-9e29-7268d25a6305
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 3%

---

# Casos de uso da DIL e exemplos de código{#dil-use-cases-and-code-samples}

Amostras de código e descrições para casos de uso de DIL específicos.

<!-- 

c_dil_use_case.xml

 -->

## Enviar elementos de dados para o Audience Manager com DIL {#send-data-elements-dil}

Crie uma variável de objeto que envia informações sobre elementos de página para o Audience Manager. Isso é útil para a coleta de dados geral ou como uma alternativa para a coleta de dados com as variáveis do Analytics.

<!-- 

c_dil_send_page_objects.xml

 -->

**Descrição**

O código a seguir demonstra como coletar dados de página e enviá-los para o Audience Manager com [!UICONTROL DIL]. Esses exemplos usam uma variável para manter os elementos de dados em uma lista simples ou em uma matriz. Lembre-se de transmitir variáveis como [pares de valores chave](../reference/key-value-pairs-explained.md). Além disso, observe o prefixo `c_` antes da chave no par de valores chave. Esse [prefixo necessário](../features/traits/trait-variable-prefixes.md) identifica informações como dados definidos pelo usuário. No primeiro exemplo, é necessário anexar `c_` manualmente à chave. No segundo exemplo, [!UICONTROL DIL] faz isso automaticamente para você.

**Manter propriedades de valor consistentes**

Lembre-se de manter as propriedades de valor iguais ao transmitir dados. Por exemplo, se você tiver duas chaves idênticas com valores diferentes, o valor do último par de valor chave terá prioridade sobre os objetos de valor anteriores. Por exemplo, transmitir `color:blue` e `color:red` define o valor retornado como vermelho (substitui azul).

**Exemplo 1: Enviar dados como pares de valores-chave**

Esse exemplo básico envia dados de cor e preço para o Audience Manager na forma de pares de valores-chave. O código pode ser semelhante ao seguinte:

<pre class="&ldquo;java&rdquo;"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals({ 
   c_color:"blue", 
   c_price:"900" 
}); 
sample_dil.api.submit();
</code></pre>

**Exemplo 2: Enviar dados em um objeto**

Este exemplo avançado demonstra como enviar dados em um objeto para o Audience Manager. Ao trabalhar com esse método, [!UICONTROL DIL] permite passar um objeto como parâmetro de função para o método [!DNL signals()]. [!UICONTROL DIL] O código pode ser semelhante ao seguinte:

<pre class="java"><code>
var my_object = { 
   color : "blue", 
   price : "900" 
}; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**Exemplo 3: Enviar dados da página em um storage**

Nesse caso, a variável `my_object` usa uma matriz para armazenar dados. Este exemplo baseia-se nas informações passadas pelo método recomendado acima, mas adiciona uma camada adicional para acomodar um tipo de produto e modelo. O código pode ser semelhante ao seguinte:

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
>Esse método funciona somente quando os usuários se movem entre páginas com protocolos semelhantes (HTTP vs HTTPS). Por exemplo, o navegador retém um URL de referência quando você navega de um site seguro para outro site seguro. Os navegadores não retêm o URL de referência quando você se move entre sites seguros e inseguros. Esse comportamento é a funcionalidade normal do navegador e não pode ser contornado por [!UICONTROL DIL].

**Amostra de código**

O código pode ser semelhante ao seguinte:

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## Capturar tipos de mecanismo de pesquisa e termos de pesquisa de palavra-chave {#capture-search-engine-types}

Envie informações sobre o tipo de mecanismo de pesquisa e pesquisas de palavras-chave para o Audience Manager.

>[!IMPORTANT]
>
>Esta seção descreve a funcionalidade herdada, que não é compatível com as versões mais recentes do DIL.

**Mecanismos de pesquisa suportados**

Por padrão, `DIL.getSearchReferrer` reconhece pesquisas desses mecanismos de pesquisa (incluindo variações internacionais):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Descrição**

O código a seguir demonstra como obter o referenciador de pesquisa para qualquer um dos mecanismos de pesquisa compatíveis. Nesse caso, suponhamos que um usuário tenha pesquisado o termo &quot;home&quot; de [!DNL Google] Canadá ( `www.google.ca`). Este código ajudará você a capturar esses termos de pesquisa e enviá-los para o Audience Manager.

**Código básico**

O código básico para obter o referenciador de pesquisa (de `google.com`, por exemplo) tem a seguinte aparência:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Amostra de código do mecanismo de pesquisa listada**

Nesse caso, suponhamos que um usuário tenha pesquisado o termo &quot;home&quot; de [!DNL Google] Canadá ( `www.google.ca`). Observe como o código prefixa o parâmetro `c_` necessário para o mecanismo de pesquisa ( `c_se`) e o termo de pesquisa ( `c_st`). `c_` é um  [prefixo ](../features/traits/trait-variable-prefixes.md) necessário que os identifica como variáveis definidas pelo cliente para o Audience Manager.

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

**Amostra de código do mecanismo de pesquisa não listada**

Nesse caso, suponhamos que um usuário tenha pesquisado o termo &quot;home&quot; de `dogpile.com`. Como [!DNL Dogpile] não é suportado por padrão, você pode configurar o DIL para reconhecer esse mecanismo de pesquisa e retornar os termos de pesquisa para o Audience Manager. O código pode ser semelhante ao seguinte:

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

## Mapear valores principais para outras chaves {#map-key-values}

Associe o valor de um par de valores chave a outra chave.

<!-- 

c_dil_map_keys.xml

 -->

**Descrição**

Em um par de valores chave, o prefixo `c_` anexado à chave identifica o sinal como dados definidos pelo cliente. Os dados definidos pelo cliente são usados para o direcionamento no site específico que passou os dados em uma chamada de evento. No entanto, às vezes você deseja que essas informações estejam disponíveis em todas as propriedades da sua conta do Audience Manager. Para fazer isso, mapeie o valor em um par de valores chave `c_` para uma chave de nível de plataforma. Uma chave de nível de plataforma tem o prefixo `d_` e disponibiliza o sinal para definição de metas em todas as propriedades da sua conta.

Como exemplo, você coleta dados de CEP de um site específico, mas deseja direcioná-los para todas as propriedades do Audience Manager. Para disponibilizar o CEP no nível da plataforma, você pode mapear a chave de código postal definida pelo cliente (por exemplo, `c_zip`) para uma chave definida pela plataforma, conforme mostrado abaixo.

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

Configure e forneça o DIL com uma tag GTM.

<!-- 

t_dil_google_tagmanager.xml

 -->

Esse procedimento pressupõe que você tenha uma conta [!DNL Google Tag Manager], algum conhecimento sobre o funcionamento desse produto e seu arquivo Audience Manager `dil.js`.

Para enviar o tráfego do arquivo `dil.js` no GTM:

1. Crie um novo contêiner ou abra um contêiner existente.
1. Adicione uma nova tag ao container.
1. Abra a tag para editá-la e:

   * Nomeie a tag .
   * Selecione **[!UICONTROL Custom HTML Tag]** na lista suspensa **[!UICONTROL Tag Type]**.
   * No campo HTML, coloque o código [!UICONTROL DIL] (biblioteca + o código personalizado) nas tags de script `<script>DIL code</script>`.
   * Clique em **[!UICONTROL Save]**.

1. Publique o contêiner.
1. Gere o código da tag do container e coloque-o no inventário.

>[!MORELIKETHIS]
>
>* [Centro de ajuda do Google Tag Manager](https://support.google.com/tagmanager#topic=3441530)
>* [Sinais](../dil/dil-instance-methods.md#signals)
* [Requisitos de prefixo para variáveis-chave](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/traits/trait-variable-prefixes.html#prefix-requirements-for-key-variables)

