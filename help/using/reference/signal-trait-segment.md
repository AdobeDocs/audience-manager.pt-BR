---
description: Descreve os componentes de um segmento do Audience Manager, as expressões usadas para definir os critérios de qualificação do público-alvo e como os dados são transmitidos em uma chamada de evento.
seo-description: Descreve os componentes de um segmento do Audience Manager, as expressões usadas para definir os critérios de qualificação do público-alvo e como os dados são transmitidos em uma chamada de evento.
seo-title: Sinais, características e segmentos
solution: Audience Manager
title: Sinais, características e segmentos
uuid: 485 fcc 5 c-b 289-463 b-a 610-0 d 727 df 90 f 3 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Signals, Traits, and Segments{#signals-traits-and-segments}

Descreve os componentes de um segmento do Audience Manager, as expressões usadas para definir os critérios de qualificação do público-alvo e como os dados são transmitidos em uma chamada de evento.

<!-- 

c_signal_trait_segment.xml

 -->

**Composição e propósito**

[!DNL Audience Manager] é formado por sinais, características, segmentos e regras de qualificação relacionadas. Os elementos de dados e as regras combinam para criar segmentos. Os segmentos organizam visitantes do site em grupos relacionados. The following table defines the three principal components in an [!DNL Audience Manager] segment.

<table id="table_E8373A01C3414C42B4983A59BF0F0669"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Consiste de </th> 
   <th colname="col3" class="entry"> Exemplo </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Sinal</b> </td> 
   <td colname="col2"> <p>Signals are the smallest data units in <span class="keyword"> Audience Manager</span> and are expressed as <a href="../reference/key-value-pairs-explained.md"> key-value pairs</a>. </p> 
    <ul id="ul_728347E325284B9FA0B4E05DE8CF4570"> 
     <li id="li_89574A3B4A734726AD43405AE6D85FF5">A chave é uma constante que define um conjunto de dados (por exemplo, gênero, cor, preço). </li> 
     <li id="li_D35601B33EE24EC5857F45D9577254D4">O valor é uma variável relacionada à constante (por exemplo, masculino/feminino, verde, 100). </li> 
    </ul> <p>Os operadores de comparação ingressam no par de valores chave e definem a relação entre eles. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A6D8D30A37C94437A7BF38736C6F8556"> 
     <li id="li_74C87C34FA254783AC0DEBBC69B35AC4"><code> product = camera</code> </li> 
     <li id="li_C1727B9136024E56B60374597A7DCA00"><code> preço &gt; 1000</code> </li> 
     <li id="li_B2E7798768EE444AB978F3F27B0BC0B5"><code> type = digital SLR</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Características</b> </td> 
   <td colname="col2"> <p>Combinações de um ou mais sinais. </p> <p>As expressões booleanas e os operadores de comparação permitem que você crie regras de qualificação de características. </p> <p>Crie requisitos de qualificação precisos com combinações de características e grupos de características. </p> </td> 
   <td colname="col3"> <p>Nos sinais disponíveis, é possível criar uma regra «Navegador de câmera alta» expressa como: </p> <p><code> product = camera AND &gt; 1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Segmento</b> </td> 
   <td colname="col2"> <p>Usuários que compartilham um conjunto de atributos comuns e qualificados para características relacionadas. </p> <p>Expressões booleanas, juntamente com requisitos de recenticidade/frequência, permitem criar regras de qualificação de segmento. </p> <p>Crie requisitos de qualificação precisos com combinações de regras de características e segmentos. </p> </td> 
   <td colname="col3"> <p>Das características e sinais disponíveis, é possível criar uma regra de segmento expressa como: </p> <p><code> (product = camera AND type = digital SLR) OR (price &gt; 1000)</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Use o diagrama abaixo para manter uma nota mental da relação entre sinais, características e segmentos.

![](assets/signals-traits-segments.png)

**Criar características e regras de segmento com ferramentas visuais e editores de código**

Clients manage traits and segments with visual tools and code editors in the [!DNL Audience Manager] user interface. As ferramentas visuais permitem que você crie regras usando recursos de pesquisa, opções pop-up, menus suspensos e arrastar e soltar funcionalidades. Os editores de código fornecem aos usuários avançados uma maneira de desenvolver programaticamente os critérios de segmentação do público-alvo.

**Chamadas de evento enviam dados para o Audience Manager**

An event call sends data from your website to [!DNL Audience Manager]. A chamada contém os dados de sinal, característica e segmento em uma solicitação HTTP. The event itself is everything after the `/event` part of a URL string. As shown in the example below, this process requires only a single event call to pass in multiple variables to [!DNL Audience Manager].

```
https://<domain>/event?product=camera&price>100
```

>[!MORE_ LIKE_ THIS]
>
>* [Segmentos: Finalidade, composição e regras](../features/segments/segments-purpose.md)

