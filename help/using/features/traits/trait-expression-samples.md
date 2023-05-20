---
description: Exemplos que você pode consultar para criar expressões no editor de código do Construtor de expressões.
seo-description: Examples you can refer to for creating expressions in the Expression Builder code editor.
seo-title: Sample Expressions With Boolean and Comparison Operators
solution: Audience Manager
title: Expressões de amostra com operadores booleanos e de comparação
uuid: ee74c376-2099-4816-8694-43f58845a0ac
feature: Traits
exl-id: 68041d61-7942-4c2f-9e78-f2b2f803ef59
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 10%

---

# Expressões de amostra com operadores booleanos e de comparação {#sample-expressions-with-boolean-and-comparison-operators}

Exemplos que você pode consultar para criar expressões no [!UICONTROL Expression Builder] editor de código.

## Visão geral de amostras de código {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

Crie suas próprias regras de características com a [!UICONTROL Expression Builder] editor de código. Os exemplos a seguir podem ajudar você a começar. Alguns exemplos apresentam como prefácio o *`key`* variável com `c_` para identificá-la como uma variável definida pelo usuário. Inclua o `c_` prefixo (ou qualquer outra convenção de nomenclatura) para *`key`* se suas chamadas de evento enviarem dados para o [!DNL Audience Manager] usando essa sintaxe.

## Expressões booleanas {#boolean-expressions}

### Exemplo AND

A regra estabelece requisitos de qualificação de característica usando booleano [!UICONTROL AND] operadores.

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Código de exemplo </th> 
   <th colname="col2" class="entry"> Para se qualificar, um visitante deve </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_make=="A") AND (c_model=="B") AND (c_search=="1")</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">Procure uma marca e um modelo específicos. </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">Encontre o produto em uma página de resultados de pesquisa (pesquisa = "1" ou "true"). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Exemplo OR

Essa regra estabelece requisitos de qualificação de características usando [!DNL Boolean] [!UICONTROL OR] e [!UICONTROL AND] operadores.

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Código de exemplo </th> 
   <th colname="col2" class="entry"> Para se qualificar, um visitante deve </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(a== "1" OR b=="1") AND (c=="new")</code> </td> 
   <td colname="col2"> Atender às condições definidas pelas variáveis <code><i>a </i></code> ou <code><i>b </i></code> e <code><i>c </i></code>. </td> 
  </tr> 
 </tbody> 
</table>

## Exemplo de Intervalo com Maior que, Menor que, Igual a

Essa regra estabelece requisitos de qualificação de características usando uma faixa.

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Código de exemplo </th> 
   <th colname="col2" class="entry"> Para se qualificar, um visitante deve </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(price &gt;= 1.00 AND price &lt;= 100.00)</code> </td> 
   <td colname="col2"> Atenda a qualquer condição de preço entre 1,00 e 100,00. </td> 
  </tr> 
 </tbody> 
</table>
