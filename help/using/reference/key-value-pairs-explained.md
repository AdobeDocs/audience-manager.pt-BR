---
description: Define e descreve pares de valor chave padrão e serializado.
keywords: código de integração
seo-description: Define e descreve pares de valor chave padrão e serializado.
seo-title: Pares de valores chave explicados
solution: Audience Manager
title: Pares de valores chave explicados
uuid: f 1435742-81 ca -4964-8370-accf 2 f 1 c 47 a 5
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Key-Value Pairs Explained{#key-value-pairs-explained}

Define e descreve pares de valor chave padrão e serializado.

<!-- 

c_key_value_explained.xml

 -->

Um par de valor chave consiste em dois elementos de dados relacionados: Uma chave, que é uma constante que define o conjunto de dados (por exemplo, sexo, cor, preço) e um valor, que é uma variável que pertence ao conjunto (por exemplo, masculino/feminino, verde, 100). Completamente formado, um par de valor chave seria parecido com:

* `gender = male`
* `color = green`
* `price > 100`

## Standard and Serialized Key-Value Pairs {#standard-serialized-pairs}

Destinations accept key-value data in *`standard`* or *`serialized`* format. A formatação padrão organiza os dados em pares de valor chave separados. Cada chave é declarada explicitamente, mesmo quando usada novamente para definir um valor diferente. Por outro lado, a formatação serializada permite vários valores em um conjunto definido por uma única chave. Além disso, em um par serializado, um indicador especial é usado para separar os valores dentro do conjunto de valores chave. Por fim, os valores de chave padrão e serializados podem conter valores únicos ou múltiplos. A tabela a seguir fornece exemplos de formatos padrão e de valor de chave de série.

| Formatação | Chave única | Pares de valores chave |
|---|---|---|
| **Padrão** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Serializado** | `x=1;2` | `x=1;2&y=3;4` |



## Keys, Delimiters, and Separators {#keys-delimiters-separators}

When working with serialized data, you must specify the characters that separate values *within* and *between* the key-value pairs. Os elementos em pares de valor chave são definidos da seguinte maneira:

* **Chave:** Um identificador exclusivo no par de valor chave.
* **Delimitador de valor:** Separa pares de valores chave individuais.
* **Separador de valor chave:** Separa uma chave dos valores dentro de um par de valor chave.
* **Separador de série:** Separa valores individuais em pares de valor chave serializado.

## Standard and Serialized Key-Value Elements {#standard-serialized-key-value-elements}

<table id="table_62B0498441034A719C9DB57276777D40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo </th> 
   <th colname="col2" class="entry"> Exemplo </th> 
   <th colname="col3" class="entry"> Chave </th> 
   <th colname="col4" class="entry"> Separador de valores chave </th> 
   <th colname="col5" class="entry"> Delimitador de valor chave </th> 
   <th colname="col6" class="entry"> Separador de série </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Chave única</b> <p>(padrão) </p> </td> 
   <td colname="col2"> <code> x = 1 &amp; x = 2 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col4" morerows="3"> = </td> 
   <td colname="col5" morerows="1"> &amp; </td> 
   <td colname="col6" morerows="1"> n/a </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pares de valores chave</b> <p>(padrão) </p> </td> 
   <td colname="col2"> <code> x = 1 &amp; x = 2 &amp; y = 3 &amp; y = 4 </code> </td> 
   <td colname="col3"> x, y </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Chave única</b> <p>(serial) </p> </td> 
   <td colname="col2"> <code> x = 1; 2; 3 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col5"> n/a </td> 
   <td colname="col6" morerows="1"> ; </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pares de valores chave</b> (serial) </td> 
   <td colname="col2"> <code> x = 1; 2 &amp; y = 3; 4 </code> </td> 
   <td colname="col3"> x, y </td> 
   <td colname="col5"> &amp; </td> 
  </tr> 
 </tbody> 
</table>

