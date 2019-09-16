---
description: Descreve os componentes de um segmento do Audience Manager, as expressões usadas para definir critérios de qualificação de público-alvo e como os dados são transmitidos em uma chamada de evento.
seo-description: Descreve os componentes de um segmento do Audience Manager, as expressões usadas para definir critérios de qualificação de público-alvo e como os dados são transmitidos em uma chamada de evento.
seo-title: Sinais, características e segmentos
solution: Audience Manager
title: Sinais, características e segmentos
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Sinais, características e segmentos{#signals-traits-and-segments}

Descreve os componentes de um segmento do Audience Manager, as expressões usadas para definir critérios de qualificação de público-alvo e como os dados são transmitidos em uma chamada de evento.

<!-- 

c_signal_trait_segment.xml

 -->

**Composição e finalidade**

[!DNL Audience Manager] os dados consistem em sinais, características, segmentos e regras de qualificação relacionadas. Os elementos de dados e as regras se combinam para criar segmentos. Os segmentos organizam os visitantes do site em grupos relacionados. A tabela a seguir define os três componentes principais em um [!DNL Audience Manager] segmento.

<table id="table_E8373A01C3414C42B4983A59BF0F0669"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Consiste em </th> 
   <th colname="col3" class="entry"> Exemplo </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Sinal</b> </td> 
   <td colname="col2"> <p>Os sinais são as menores unidades de dados no <span class="keyword"> Audience Manager</span> e são expressos como pares <a href="../reference/key-value-pairs-explained.md"> de</a>valor chave. </p> 
    <ul id="ul_728347E325284B9FA0B4E05DE8CF4570"> 
     <li id="li_89574A3B4A734726AD43405AE6D85FF5">A chave é uma constante que define um conjunto de dados (por exemplo, gênero, cor, preço). </li> 
     <li id="li_D35601B33EE24EC5857F45D9577254D4">O valor é uma variável relacionada à constante (por exemplo, macho/fêmea, verde, 100). </li> 
    </ul> <p>Os operadores de comparação ingressam no par de valores chave e definem a relação entre eles. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A6D8D30A37C94437A7BF38736C6F8556"> 
     <li id="li_74C87C34FA254783AC0DEBBC69B35AC4"><code> product=camera</code> </li> 
     <li id="li_C1727B9136024E56B60374597A7DCA00"><code> price&gt;1000</code> </li> 
     <li id="li_B2E7798768EE444AB978F3F27B0BC0B5"><code> type=digital SLR</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Características</b> </td> 
   <td colname="col2"> <p>Combinações de um ou mais sinais. </p> <p>As expressões booleanas e os operadores de comparação permitem criar regras de qualificação de característica. </p> <p>Crie requisitos de qualificação precisos com combinações de características e grupos de características. </p> </td> 
   <td colname="col3"> <p>A partir dos sinais disponíveis, você pode criar uma regra "Navegador de câmera sofisticado" expressa como: </p> <p><code> product=camera AND price&gt;1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Segmento</b> </td> 
   <td colname="col2"> <p>Usuários que compartilham um conjunto de atributos comuns e se qualificam para características relacionadas. </p> <p>Expressões booleanas, juntamente com requisitos de recenticidade/frequência, permitem que você crie regras de qualificação de segmentos. </p> <p>Crie requisitos de qualificação precisos com combinações de características e regras de segmentos. </p> </td> 
   <td colname="col3"> <p>A partir das características e sinais disponíveis, é possível criar uma regra de segmento expressa como: </p> <p><code> (product=camera AND type=digital SLR) OU (price&gt;1000)</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Use o diagrama abaixo para manter uma nota mental da relação entre sinais, características e segmentos.

![](assets/signals-traits-segments.png)

**Criar características e regras de segmento com ferramentas visuais e editores de código**

Os clientes gerenciam características e segmentos com ferramentas visuais e editores de código na interface do [!DNL Audience Manager] usuário. As ferramentas visuais permitem criar regras usando recursos de pesquisa, opções de pop-up, menus suspensos e a funcionalidade arrastar e soltar. Os editores de código fornecem aos usuários avançados uma maneira de desenvolver de forma programática os critérios de segmentação do público-alvo.

**Chamadas de evento Enviar dados para o Audience Manager**

Uma chamada de evento envia dados de seu site para [!DNL Audience Manager]. A chamada contém dados de sinal, característica e segmento em uma solicitação HTTP. O evento em si é tudo depois da parte `/event` de uma string de URL. Como mostrado no exemplo abaixo, esse processo requer apenas uma chamada de evento para transmitir várias variáveis para [!DNL Audience Manager].

```
https://<domain>/event?product=camera&price>100
```

>[!MORE_LIKE_THIS]
>
>* [Segmentos: Finalidade, composição e regras](../features/segments/segments-purpose.md)

