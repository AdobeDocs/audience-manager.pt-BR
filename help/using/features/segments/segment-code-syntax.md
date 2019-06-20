---
description: O Construtor de segmentos permite criar regras de características para um segmento usando um editor de código. Clique na guia Expressões de segmento (Exibição de código) no painel Características para acessar esse recurso.
seo-description: O Construtor de segmentos permite criar regras de características para um segmento usando um editor de código. Clique na guia Expressões de segmento (Exibição de código) no painel Características para acessar esse recurso.
seo-title: Sintaxe de código usada no Editor de expressões de segmento
solution: Audience Manager
title: Sintaxe de código usada no Editor de expressões de segmento
uuid: 7 b 4 b 06 ca -7879-4501-8 ba 7-b 2 b 6467 b 8 a 3 b
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Code Syntax Used in the Segment Expression Editor {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] permite criar regras de características para um segmento usando um editor de código. Click the **[!UICONTROL Segment Expressions (Code View)]** tab in the [!UICONTROL Traits] panel to access this feature.

## Sintaxe do código do Construtor de expressões

É possível adicionar regras de características a um segmento com código em vez de usar recursos de arrastar e soltar. Durante a codificação, substitua os elementos itálicos no exemplo por uma expressão ou valor real. O código base usa a seguinte sintaxe:

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>By default, [!DNL Boolean] [!UICONTROL OR] conditions apply to multiple traits *within* an expression.

### Unir segmentos com operadores booleanos

To build groups of segments, wrap the frequency function in parenthesis and set the relationship *between* each expression with a [!DNL Boolean] operator ([!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT]).

### Parâmetros

>[!NOTE]
>
>Todos os parâmetros são necessários, a menos que seja observado contrário.

| Nome ou variável | Descrição |
|---|---|
| `FREQUENCY` | Um literal que deve preceder a expressão. |
| ` [`&lt;`traitID`&gt;`T]` | An array of trait IDs followed by the letter `T`. Separe várias características com uma vírgula. Por exemplo, `[123T, 456T]`. |
| ` <Recency Operator><Numeric Value>D` | *(Opcional)* Define regras de recenticidade em características no segmento. The letter `D` indicates recency in days. |
| ` <Frequency Operator><Numeric Value>` | Define regras de frequência em características no segmento. |

### Tempo decorrido e operadores de frequência permitidos

Set [recency and frequency](../../features/segments/recency-and-frequency.md) intervals with a comparison operator and an integer. [!UICONTROL Segment Builder] usa expressões padrão como &lt; (menor que), &gt; (maior que), = = (igual), etc. No entanto, os tipos de operadores permitidos variam quando você define a atualidade ou frequência. A tabela abaixo lista os operadores de recenticidade/frequência permitidos.

<table id="table_2F92617CB472442BA5639E24DB4E43D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Operadores de recenticidade </th> 
   <th colname="col2" class="entry"> Operadores de frequência </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_66D11A34097648A997BA5C6CCC38503A"> 
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt; = (maior que/igual a) </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt; = (menor que/igual a) </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt; = (maior que/igual a) </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt; = (menor que/igual a) </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">= = (igual a) </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Recenticidade e frequência](../../features/segments/recency-and-frequency.md)
>* [Expressões booleanas em características e no construtor de segmentos](../../reference/boolean-expressions-tsb.md)
>* [Trabalhar com operadores de comparação no traitbuilder](../../features/traits/trait-comparison-operators.md)
>* [Ordem de operações nas expressões do traitbuilder](../../features/traits/trait-operator-precedence.md)

