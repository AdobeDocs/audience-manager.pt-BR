---
description: O Construtor de características avalia expressões de acordo com a ordem de operações listada abaixo, de alta a baixa precedência. Os elementos de característica definidos por operadores de alta precedência são avaliados primeiro, antes de outros operadores de precedência. Esta seção classifica cada operador de acordo com a precedência, de alto para baixo.
seo-description: O Construtor de características avalia expressões de acordo com a ordem de operações listada abaixo, de alta a baixa precedência. Os elementos de característica definidos por operadores de alta precedência são avaliados primeiro, antes de outros operadores de precedência. Esta seção classifica cada operador de acordo com a precedência, de alto para baixo.
seo-title: Ordem de operações no Construtor de características
solution: Audience Manager
title: Ordem de operações no Construtor de características
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
feature: 'Características '
exl-id: 90700479-4a8e-4a07-81ef-2e9d8a1d9f15
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 13%

---

# Ordem de operações no Construtor de características {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] O avalia expressões de acordo com a ordem de operações listada abaixo, de alta a baixa precedência. Os elementos de característica definidos por operadores de alta precedência são avaliados primeiro, antes de outros operadores de precedência. Esta seção classifica cada operador de acordo com a precedência, de alto para baixo.

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
   <td colname="col2"> &lt;&gt; &lt;&gt;= </td> 
   <td colname="col3"> Less than, greater than, less than/equal to, greater than/equal to são avaliados em seguida. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operadores da igualdade </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> Equal to, not equal to são avaliados após os operadores anteriores. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Booleano <span class="wintitle"> AND</span> </td> 
   <td colname="col2"><span class="wintitle"> E</span> </td> 
   <td colname="col3" morerows="1"> n/a </td> 
  </tr> 
  <tr> 
   <td colname="col1">Booleano <span class="wintitle"> OR</span> </td> 
   <td colname="col2"><span class="wintitle"> OU</span> </td> 
   <td colname="col3" morerows="1"> n/d </td> 
  </tr> 
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Trabalhar com expressões booleanas (AND, OR, NOT) no TraitBuilder](../../reference/boolean-expressions-tsb.md)
* [Trabalhar com operadores de comparação no TraitBuilder](../../features/traits/trait-comparison-operators.md)

