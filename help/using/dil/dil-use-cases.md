---
description: Amostras de código e descrições para casos de uso específicos do DIL.
seo-description: Code samples and descriptions for specific DIL use cases.
seo-title: DIL Use Cases and Code Samples
solution: Audience Manager
title: Casos de uso da DIL e exemplos de código
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
feature: DIL Implementation
exl-id: 001710be-b377-460a-9e29-7268d25a6305
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 1%

---

# Casos de uso da DIL e exemplos de código{#dil-use-cases-and-code-samples}

>[!WARNING]
>
>A partir de julho de 2023, a Adobe descontinuou o desenvolvimento do [!DNL Data Integration Library (DIL)] e da extensão [!DNL DIL].
>
>Os clientes existentes podem continuar usando a implementação [!DNL DIL]. Entretanto, a Adobe não desenvolverá [!DNL DIL] além deste ponto. Os clientes são incentivados a avaliar o [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=pt-BR) para sua estratégia de coleta de dados de longo prazo.
>
>Os clientes que desejam implementar novas integrações de coleta de dados após julho de 2023 devem usar o [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=pt-BR).

Amostras de código e descrições para casos de uso específicos do DIL.

<!-- 

c_dil_use_case.xml

 -->

## Enviar elementos de dados para o Audience Manager com o DIL {#send-data-elements-dil}

Crie uma variável de objeto que envia informações sobre os elementos da página para a Audience Manager. Isso é útil para a coleta de dados gerais ou como uma alternativa para a coleta de dados com as variáveis do Analytics.

<!-- 

c_dil_send_page_objects.xml

 -->

**Descrição**

O código a seguir demonstra como coletar dados de página e enviá-los para o Audience Manager com [!UICONTROL DIL]. Esses exemplos usam uma variável para manter elementos de dados em uma lista simples ou em uma matriz. Lembre-se, passe as variáveis como [pares de valores chave](../reference/key-value-pairs-explained.md). Além disso, observe o prefixo `c_` antes da chave no par de valores chave. Este [prefixo obrigatório](../features/traits/trait-variable-prefixes.md) identifica as informações como dados definidos pelo usuário. No primeiro exemplo, você precisa anexar manualmente `c_` à chave. No segundo exemplo, [!UICONTROL DIL] faz isso automaticamente.

**Manter Propriedades de Valor Consistentes**

Lembre-se de manter as mesmas propriedades de valor ao transmitir os dados. Por exemplo, se você tiver duas chaves idênticas com valores diferentes, o valor do último par de valor-chave terá precedência sobre os objetos de valor anteriores. Por exemplo, transmitir `color:blue` e `color:red` define o valor retornado como vermelho (substitui azul).

**Exemplo 1: Enviar Dados como Pares de Valores-Chave**

Esse exemplo básico envia dados de cor e preço para o Audience Manager na forma de pares de valores-chave. O código pode ser semelhante ao seguinte:

<pre class="java"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals(&lbrace; 
   c_color:"blue", 
   c_price:"900" 
&rbrace;); 
sample_dil.api.submit();
</code></pre>

**Exemplo 2: Enviar Dados em um Objeto**

Este exemplo avançado demonstra como enviar dados em um objeto para o Audience Manager. Ao trabalhar com este método, [!UICONTROL DIL] permite passar um objeto como um parâmetro de função para o método [!DNL signals()]. [!UICONTROL DIL] Seu código pode ser semelhante ao seguinte:

<pre class="java"><code>
var my_object = &lbrace; 
   color : "blue", 
   price : "900" 
&rbrace;; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**Exemplo 3: Enviar Dados de Página em uma Matriz**

Nesse caso, a variável `my_object` usa uma matriz para armazenar dados. Este exemplo se baseia nas informações transmitidas pelo método recomendado acima, mas adiciona uma camada adicional para acomodar um tipo e modelo de produto. O código pode ser semelhante ao seguinte:

<pre class="java"><code>
var my_objects = &lbrack;&lbrace; 
   color : "blue", 
   price : "900" 
&rbrace;, &lbrace; 
   type : "acura", 
   model : "tl" 
&rbrace;&rbrack;; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
 
for (var i = 0; i < my_objects.length; i++) 
//Load the object and append "c_" to all the keys in the key-value pairs.  
&lbrace; 
    sample_dil.api.signals(my_objects[i], "c_"); 
&rbrace; 
sample_dil.api.submit();
</code></pre>

## Capturar URL de referência {#capture-referring-url}

Capture e envie um URL de referência para o Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Esse método funciona somente quando os usuários se movem entre páginas com protocolos semelhantes (HTTP vs. HTTPS). Por exemplo, o navegador retém um URL de referência quando você navega de um site seguro para outro site seguro. Os navegadores não retêm o URL de referência quando você se move entre sites seguros e não seguros. Este comportamento é uma funcionalidade normal do navegador e não pode ser contornado por [!UICONTROL DIL].

**Amostra de código**

O código pode ser semelhante ao seguinte:

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## Capturar Tipos de Mecanismo de Pesquisa e Termos de Pesquisa por Palavra-chave {#capture-search-engine-types}

Envie informações sobre o tipo de mecanismo de pesquisa e pesquisas por palavra-chave para a Audience Manager.

>[!IMPORTANT]
>
>Esta seção descreve a funcionalidade herdada, que não é compatível com as versões mais recentes do DIL.

**Mecanismos de pesquisa com suporte**

Por padrão, o `DIL.getSearchReferrer` reconhece as pesquisas destes mecanismos de pesquisa (incluindo variações internacionais):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Descrição**

O código a seguir demonstra como obter o referenciador de pesquisa para qualquer um dos mecanismos de pesquisa compatíveis. Nesse caso, vamos supor que um usuário tenha pesquisado no termo &quot;homes&quot; do [!DNL Google] Canadá ( `www.google.ca`). Este código ajudará você a capturar esses termos de pesquisa e enviá-los para a Audience Manager.

**Código básico**

O código básico para obter o referenciador de pesquisa (de `google.com`, por exemplo) tem esta aparência:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Amostra de Código do Mecanismo de Pesquisa Listada**

Nesse caso, vamos supor que um usuário tenha pesquisado o termo &quot;homes&quot; do [!DNL Google] Canadá ( `www.google.ca`). Observe como o código prefixa o parâmetro `c_` necessário ao mecanismo de pesquisa ( `c_se`) e ao termo de pesquisa ( `c_st`). `c_` é um [prefixo obrigatório](../features/traits/trait-variable-prefixes.md) que os identifica como variáveis definidas pelo cliente para o Audience Manager.

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(); 
 
if (search_referrer && search_referrer.valid) &lbrace; 
  adobe_dil.api.signals(&lbrace; 
    c_se : se.name, 
    c_st : se.keywords 
  &rbrace;).submit(); 
&rbrace;
</code></pre>

**Amostra de Código do Mecanismo de Pesquisa Não Listada**

Nesse caso, vamos supor que um usuário tenha pesquisado o termo &quot;homes&quot; de `dogpile.com`. Por padrão, não há suporte para [!DNL Dogpile], você pode configurar o DIL para reconhecer esse mecanismo de pesquisa e retornar os termos de pesquisa para o Audience Manager. O código pode ser semelhante ao seguinte:

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(document.referrer, &lbrace;  
    hostPattern:/dogpile\./, 
    queryParam:"q" 
&rbrace;); 
 
if (search_referrer && search_referrer.valid) &lbrace; 
  adobe_dil.api.signals(&lbrace; 
    c_se : se.name, 
    c_st : se.keywords 
  &rbrace;).submit(); 
&rbrace;
</code></pre>

## Mapear valores de chave para outras chaves {#map-key-values}

Associe o valor de um par de valor-chave a outra chave.

<!-- 

c_dil_map_keys.xml

 -->

**Descrição**

Em um par de valor-chave, o prefixo `c_` anexado à chave identifica o sinal como dados definidos pelo cliente. Os dados definidos pelo cliente são usados para direcionamento no site específico que transmitiu dados em uma chamada de evento. No entanto, às vezes você quer que essas informações estejam disponíveis em todas as propriedades na sua conta do Audience Manager. Para fazer isso, mapeie o valor em um par de valor-chave `c_` para uma chave de nível de plataforma. Uma chave de nível de plataforma recebe o prefixo `d_` e disponibiliza o sinal para direcionamento em todas as propriedades da sua conta.

Como exemplo, você coleta dados de CEP de um site específico, mas deseja direcioná-los a todas as suas propriedades do Audience Manager. Para disponibilizar o CEP no nível da plataforma, você pode mapear sua chave de CEP definida pelo cliente (por exemplo, `c_zip`) para uma chave definida pela plataforma, conforme mostrado abaixo.

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

## Tráfego DIL no Google Tag Manager (GTM) {#traffic-dil-gtm}

Configurar e fornecer uma tag do GTM ao DIL.

<!-- 

t_dil_google_tagmanager.xml

 -->

Este procedimento supõe que você tenha uma conta [!DNL Google Tag Manager], algum conhecimento prático desse produto e seu arquivo Audience Manager `dil.js`.

Para traficar o arquivo `dil.js` no GTM:

1. Criar um novo contêiner ou abrir um existente.
1. Adicione uma nova tag ao container.
1. Abra a tag para editá-la e:

   * Nomeie a tag.
   * Selecione **[!UICONTROL Custom HTML Tag]** na lista suspensa **[!UICONTROL Tag Type]**.
   * No campo HTML, coloque o código [!UICONTROL DIL] (biblioteca + o código personalizado) nas tags de script `<script>DIL code</script>`.
   * Clique em **[!UICONTROL Save]**.

1. Publique o container.
1. Gere o código da etiqueta do contêiner e coloque-o no inventário.

>[!MORELIKETHIS]
>
>* [Central de ajuda do Google Tag Manager](https://support.google.com/tagmanager#topic=3441530)
>* [Sinais](../dil/dil-instance-methods.md#signals)
>* [Requisitos de prefixo para variáveis-chave](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/traits/trait-variable-prefixes.html?lang=pt-BR#prefix-requirements-for-key-variables)
