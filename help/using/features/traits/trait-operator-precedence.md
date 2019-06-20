---
description: O Construtor de traços avalia as expressões de acordo com a ordem das operações listadas abaixo, de precedência alta para baixa. Os elementos de característica definidos por operadores de alta prioridade são avaliados primeiro, antes de outros operadores de precedência. Esta seção classifica cada operador de acordo com precedência, de alto para baixo.
seo-description: O Construtor de traços avalia as expressões de acordo com a ordem das operações listadas abaixo, de precedência alta para baixa. Os elementos de característica definidos por operadores de alta prioridade são avaliados primeiro, antes de outros operadores de precedência. Esta seção classifica cada operador de acordo com precedência, de alto para baixo.
seo-title: Ordem das operações no Construtor de características
solution: Audience Manager
title: Ordem das operações no Construtor de características
uuid: df 325047-af 62-45 ad -9 ca 1-046 bfcbe 5341
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Order of Operations in Trait Builder {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] avalia expressões de acordo com a ordem das operações listadas abaixo, de precedência alta para baixa. Os elementos de característica definidos por operadores de alta prioridade são avaliados primeiro, antes de outros operadores de precedência. Esta seção classifica cada operador de acordo com precedência, de alto para baixo.

<!-- c_tb_operator_precedence.xml -->

<table id="table_F0FA45B652C7464B90D35526817110FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Precedência do operador </th> 
   <th colname="col2" class="entry"> Símbolo </th> 
   <th colname="col3" class="entry"> Comentários </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Parêntese </td> 
   <td colname="col2"> ( ) </td> 
   <td colname="col3"> As expressões entre parênteses são sempre avaliadas primeiro e seguem a ordem de precedência. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operadores de comparação </td> 
   <td colname="col2"> &lt; &gt; &lt;= &gt;= </td> 
   <td colname="col3"> Menor que, maior que/igual a/igual a, maior que/igual a são avaliados em seguida. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operadores de igualdade </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> Igual a, não é igual a serem avaliados após os operadores anteriores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Booleano AND</span> </td> 
   <td colname="col2"><span class="wintitle"> AND</span> </td> 
   <td colname="col3" morerows="1"> n/a </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolean <span class="wintitle"> OR</span> </td> 
   <td colname="col2"><span class="wintitle"> OU</span> </td> 
   <td colname="col3" morerows="1"> n/a </td> 
  </tr> 
 </tbody>
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Trabalhar com Expressões Booleanas (AND, OR, NOT) no traitbuilder](../../reference/boolean-expressions-tsb.md)
>* [Trabalhar com operadores de comparação no traitbuilder](../../features/traits/trait-comparison-operators.md)

