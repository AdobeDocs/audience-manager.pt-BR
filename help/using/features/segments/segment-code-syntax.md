---
description: O Construtor de segmentos permite que você crie regras de características para um segmento usando um editor de código. Clique na guia Expressões de segmentos (Visualização de código) no painel Características para acessar esse recurso.
seo-description: O Construtor de segmentos permite que você crie regras de características para um segmento usando um editor de código. Clique na guia Expressões de segmentos (Visualização de código) no painel Características para acessar esse recurso.
seo-title: Sintaxe de código usada no Editor de expressão de segmentos
solution: Audience Manager
title: Sintaxe de código usada no Editor de expressão de segmentos
uuid: 7b4b06ca-7879-4501-8ba7-b2b6467b8a3b
feature: 'Segmentos '
exl-id: 64fa6f03-cef9-4187-866f-28c54f45f72e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 11%

---

# Sintaxe de código usada no Editor de expressão de segmentos {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] permite criar regras de características para um segmento usando um editor de código. Clique na guia **[!UICONTROL Segment Expressions (Code View)]** no painel [!UICONTROL Traits] para acessar esse recurso.

## Sintaxe de código do Construtor de expressões

Você pode adicionar regras de características a um segmento com código em vez de usar os recursos de arrastar e soltar. Ao codificar, substitua os elementos em itálico no exemplo por uma expressão ou valor real. O código base usa a seguinte sintaxe:

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>Por padrão, as condições [!DNL Boolean] [!UICONTROL OR] se aplicam a várias características *dentro de* uma expressão.

### Unir segmentos com operadores booleanos

Para criar grupos de segmentos, vincule a função de frequência entre parênteses e defina a relação *entre* cada expressão com um operador [!DNL Boolean] ([!UICONTROL AND], [!UICONTROL OR] e [!UICONTROL NOT]).

### Parâmetros

>[!NOTE]
>
>Todos os parâmetros são necessários, a menos que observado o contrário.

| Nome ou variável | Descrição |
|---|---|
| `FREQUENCY` | Um literal que deve preceder a expressão. |
| ` [`&lt;`traitID`>`T]` | Uma matriz de IDs de características seguidas pela letra `T`. Separe várias características com uma vírgula. Por exemplo, `[123T, 456T]`. |
| ` <Recency Operator><Numeric Value>D` | *(Opcional)* Define regras de recenticidade sobre as características no segmento. A letra `D` indica recenticidade em dias. |
| ` <Frequency Operator><Numeric Value>` | Define regras de frequência em características no segmento. |

### Operadores de recenticidade e frequência permitidos

Defina os intervalos [recenticidade e frequência](../../features/segments/recency-and-frequency.md) com um operador de comparação e um número inteiro. [!UICONTROL Segment Builder] usa expressões padrão como  &lt;> (maior que), == (igual), etc. No entanto, os tipos de operadores permitidos variam quando você define recenticidade ou frequência. A tabela abaixo lista os operadores de recenticidade/frequência permitidos.

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
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt;= (maior que/igual a) </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt;&gt; </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt;= (maior que/igual a) </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt;&gt; </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">== (igual a) </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Recenticidade e frequência](../../features/segments/recency-and-frequency.md)
* [Expressões booleanas no Construtor de características e segmentos](../../reference/boolean-expressions-tsb.md)
* [Trabalhar com operadores de comparação no TraitBuilder](../../features/traits/trait-comparison-operators.md)
* [Ordem de operações nas expressões do TraitBuilder](../../features/traits/trait-operator-precedence.md)

