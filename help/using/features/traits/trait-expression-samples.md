---
description: Exemplos que você pode consultar para criar expressões no editor de código do Expressão Builder.
seo-description: Exemplos que você pode consultar para criar expressões no editor de código do Expressão Builder.
seo-title: Expressões de amostra com operadores booleanos e de comparação
solution: Audience Manager
title: Expressões de amostra com operadores booleanos e de comparação
uuid: ee74c376-2099-4816-8694-43f58845a0ac
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 12%

---


# Expressões de amostra com operadores booleanos e de comparação {#sample-expressions-with-boolean-and-comparison-operators}

Exemplos que você pode consultar para criar expressões no editor de [!UICONTROL Expression Builder] código.

## Visão geral de exemplos de código {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

Crie suas próprias regras de características com o editor de [!UICONTROL Expression Builder] códigos. Os exemplos a seguir podem ajudá-lo a começar. Alguns exemplos apresentam a *`key`* variável como prefácio `c_` para identificá-la como uma variável definida pelo usuário. Inclua o `c_` prefixo (ou qualquer outra convenção de nomenclatura) da *`key`* variável se as chamadas de evento enviarem dados para [!DNL Audience Manager] usar essa sintaxe.

## Expressões booleanas {#boolean-expressions}

### Exemplo AND

A regra estabelece requisitos de qualificação de características usando [!UICONTROL AND] operadores Booleanos.

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
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">Localize o produto de uma página de resultados de pesquisa (pesquisa = "1" ou "true"). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Exemplo OR

Esta regra estabelece requisitos de qualificação de características usando [!DNL Boolean] e [!UICONTROL OR] [!UICONTROL AND] operadores.

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
   <td colname="col2"> Satisfaça as condições definidas por variáveis <code><i>a </i></code> ou <code><i>b </i></code> e <code><i>c </i></code>. </td> 
  </tr> 
 </tbody> 
</table>

## Exemplo de intervalo com maior que, menor que, igual a

Esta regra estabelece os requisitos de qualificação de características usando um intervalo.

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
   <td colname="col2"> Satisfaça qualquer condição de preço entre 1.00 e 100.00. </td> 
  </tr> 
 </tbody> 
</table>