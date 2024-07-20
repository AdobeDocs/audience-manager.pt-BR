---
description: O Construtor de características avalia as expressões de acordo com a ordem de operações listada abaixo, de alta a baixa precedência. Os elementos de característica definidos por operadores de alta precedência são avaliados primeiro, antes de outros operadores de precedência. Esta seção classifica cada operador de acordo com a precedência, de cima para baixo.
seo-description: Trait Builder evaluates expressions according to the order-of-operations listed below, from high to low precedence. Trait elements defined by high-precedence operators are evaluated first, before other precedence operators. This section ranks each operator according to precedence, from high to low.
seo-title: Order of Operations in Trait Builder
solution: Audience Manager
title: Ordem de operações no Construtor de características
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
feature: Traits
exl-id: 90700479-4a8e-4a07-81ef-2e9d8a1d9f15
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 3%

---

# Ordem de operações no Construtor de características {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] avalia expressões de acordo com a ordem de operações listada abaixo, de alta a baixa precedência. Os elementos de característica definidos por operadores de alta precedência são avaliados primeiro, antes de outros operadores de precedência. Esta seção classifica cada operador de acordo com a precedência, de cima para baixo.

<!-- c_tb_operator_precedence.xml -->

<table id="table_F0FA45B652C7464B90D35526817110FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Prioridade de operador </th> 
   <th colname="col2" class="entry"> Símbolo </th> 
   <th colname="col3" class="entry"> Comentários </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Parênteses </td> 
   <td colname="col2"> ( ) </td> 
   <td colname="col3"> As expressões entre parênteses são sempre avaliadas primeiro e seguem a ordem de precedência. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operadores de comparação </td> 
   <td colname="col2"> &lt; &gt; &lt;= &gt;= </td> 
   <td colname="col3"> Menor que, maior que, menor que/igual a, maior que/igual a são avaliados a seguir. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operadores de igualdade </td> 
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
   <td colname="col3" morerows="1"> n/a </td> 
  </tr> 
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Trabalhando com expressões booleanas (AND, OR, NOT) no TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Trabalhando com Operadores de Comparação no TraitBuilder](../../features/traits/trait-comparison-operators.md)
