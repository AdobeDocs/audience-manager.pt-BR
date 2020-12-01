---
description: O Construtor de características avalia as expressões de acordo com a ordem de operações listada abaixo, de alta a baixa precedência. Os elementos de características definidos por operadores de alta prioridade são avaliados primeiro, antes de outros operadores de precedência. Esta seção classifica cada operador de acordo com a precedência, de alto a baixo.
seo-description: O Construtor de características avalia as expressões de acordo com a ordem de operações listada abaixo, de alta a baixa precedência. Os elementos de características definidos por operadores de alta prioridade são avaliados primeiro, antes de outros operadores de precedência. Esta seção classifica cada operador de acordo com a precedência, de alto a baixo.
seo-title: Ordem de operações no Construtor de características
solution: Audience Manager
title: Ordem de operações no Construtor de características
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 13%

---


# Ordem de operações no Construtor de características {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] avalia expressões de acordo com a ordem de operações listada abaixo, de alta a baixa precedência. Os elementos de características definidos por operadores de alta prioridade são avaliados primeiro, antes de outros operadores de precedência. Esta seção classifica cada operador de acordo com a precedência, de alto a baixo.

<!-- c_tb_operator_precedence.xml -->

<table id="table_F0FA45B652C7464B90D35526817110FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Prioridade do operador </th> 
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
   <td colname="col3"> Menor que, maior que, menor que/igual a, maior que/igual a é avaliado em seguida. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operadores da igualdade </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> Igual a, diferente de é avaliado após os operadores anteriores. </td> 
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
>* [Trabalhar com Expressões booleanas (AND, OR, NOT) no TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Trabalhar com operadores de comparação no TraitBuilder](../../features/traits/trait-comparison-operators.md)

