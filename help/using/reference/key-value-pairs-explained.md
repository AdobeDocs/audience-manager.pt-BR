---
description: Define e descreve pares de valores chave padrão e serializados.
keywords: integration code
seo-description: Define e descreve pares de valores chave padrão e serializados.
seo-title: Explicação dos pares de valor-chave
solution: Audience Manager
title: Explicação dos pares de valor-chave
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 7%

---


# Explicação dos pares de valor-chave{#key-value-pairs-explained}

Define e descreve pares de valores chave padrão e serializados.

<!-- 

c_key_value_explained.xml

 -->

Um par de valores chave consiste em dois elementos de dados relacionados: Uma tecla, que é uma constante que define o conjunto de dados (por exemplo, gênero, cor, preço) e um valor, que é uma variável que pertence ao conjunto (por exemplo, macho/fêmea, verde, 100). Totalmente formado, um par de valores chave poderia ser parecido com estes:

* `gender = male`
* `color = green`
* `price > 100`

## Standard and Serialized Key-Value Pairs {#standard-serialized-pairs}

Os destinos aceitam dados de valor chave no *`standard`* formato ou *`serialized`* . A formatação padrão organiza os dados em pares de valores chave separados. Cada chave é declarada explicitamente, mesmo quando usada novamente para definir um valor diferente. Por outro lado, a formatação serializada condensa vários valores em um conjunto definido por uma única tecla. Além disso, em um par serializado, um indicador especial é usado para separar os valores dentro do conjunto de valores chave. Finalmente, os valores-chave padrão e serializados podem conter valores únicos ou múltiplos. A tabela a seguir fornece exemplos de formatos padrão e de valores de chave serial.

| Formatação | Chave única | Pares de valor-chave |
|---|---|---|
| **Padrão** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Serializado** | `x=1;2` | `x=1;2&y=3;4` |



## Teclas, delimitadores e separadores {#keys-delimiters-separators}

Ao trabalhar com dados serializados, você deve especificar os caracteres que separam valores *dentro* e *entre* os pares de valores chave. Os elementos em pares de valor chave são definidos da seguinte forma:

* **Chave:** Um identificador exclusivo no par de chave-valor.
* **Delimitador de valores:** Separa pares de valores chave individuais.
* **Separador de valor-chave:** Separa uma chave dos valores em um par de valores chave.
* **Separador de série:** Separa valores individuais em pares de valores chave serializados.

## Elementos de valor-chave padrão e serializados {#standard-serialized-key-value-elements}

<table id="table_62B0498441034A719C9DB57276777D40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo </th> 
   <th colname="col2" class="entry"> Exemplo </th> 
   <th colname="col3" class="entry"> Chave </th> 
   <th colname="col4" class="entry"> Separador de valor-chave </th> 
   <th colname="col5" class="entry"> Delimitador de valor-chave </th> 
   <th colname="col6" class="entry"> Separador serial </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Tecla única</b> <p>(padrão) </p> </td> 
   <td colname="col2"> <code> x=1&amp;x=2 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col4" morerows="3"> = </td> 
   <td colname="col5" morerows="1"> &amp; </td> 
   <td colname="col6" morerows="1"> n/a </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pares de valor-chave</b> <p>(padrão) </p> </td> 
   <td colname="col2"> <code> x=1&amp;x=2&amp;y=3&amp;y=4 </code> </td> 
   <td colname="col3"> x, y </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Tecla única</b> <p>(serial) </p> </td> 
   <td colname="col2"> <code> x=1;2;3 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col5"> n/a </td> 
   <td colname="col6" morerows="1"> ; </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pares</b> de valor-chave (serial) </td> 
   <td colname="col2"> <code> x=1;2&amp;y=3;4 </code> </td> 
   <td colname="col3"> x, y </td> 
   <td colname="col5"> &amp; </td> 
  </tr> 
 </tbody> 
</table>

