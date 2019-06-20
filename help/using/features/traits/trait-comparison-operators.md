---
description: Este artigo descreve os operadores de comparação usados pelo Construtor de traços.
seo-description: Este artigo descreve os operadores de comparação usados pelo Construtor de traços.
seo-title: Trabalhar com operadores de comparação no Construtor de características
solution: Audience Manager
title: Trabalhar com operadores de comparação no Construtor de características
uuid: 41 bec 3 b 3-e 5 df -4 f-abb 0-80 ce 4 c 75 f 5 e 7
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Working with Comparison Operators in Trait Builder {#working-with-comparison-operators-in-trait-builder}

This article describes the comparison operators used by [!UICONTROL Trait Builder].

## Finalidade dos operadores de comparação

<!-- c_tb_comparison_operators.xml -->

Os operadores de comparação (ou operadores relacionais) são usados para comparar, testar ou avaliar a relação entre valores diferentes. In [!UICONTROL Trait Builder], when building signal rules, comparison operators let you test the relationship between different key-value pairs. Por exemplo, você pode criar uma regra de sinal para definir um público-alvo para compradores caros de câmera. Nesse caso, você pode criar um par de valores de chave de câmera/preço e qualificar um usuário se tiver procurado uma câmera com um preço igual ou maior que um valor definido.

## Vantagens dos operadores de comparação

Os operadores de comparação são úteis quando você precisa avaliar e criar características com base em vários valores. Olhar os preços em bens e serviços pode ilustrar essa condição. Por exemplo, sua empresa pode querer identificar visitantes com base nos preços dos produtos que eles visualizam. No entanto, pode ser administrativamente ineficaz para definir segmentos individuais com base em valores específicos. Os operadores de comparação ajudam a resolver esse obstáculo estabelecendo acionadores de segmentação com base em limites de preço ou intervalos.

## Operadores de comparação

Você pode criar regras com os seguintes operadores de comparação:

| Operador | Definição |
|---|---|
| **==** | Igual a |
| **!=** | Não é igual a |
| **&gt;** | Maior que |
| **&lt;** | Menos que |
| **=&gt;** | Maior que/igual a |
| **&lt;=** | Menor que/igual a |

## Operadores nomeados

Você pode criar regras com os seguintes operadores nomeados:

| Operador | Evaluates to [!DNL True] When |
|---|---|
| **[!UICONTROL Contains]** | The value in a key-value pair *contains* characters specified by this operator. |
| **[!UICONTROL Matcheswords]** | The value in a key-value pair *matches* the pattern specified by this operator. |
| **[!UICONTROL Startswith]** | The value in a key-value pair *starts with* characters specified by this operator. |
| **[!UICONTROL Endswith]** | The value in a key-value pair *ends with* the characters specified by this operator. |
| **[!UICONTROL Matchesregex]** | The value in a key-value pair *matches* the pattern specified by a regular expression. [Saiba mais](../../features/traits/trait-builder-regex.md) sobre como usar expressões regulares.[!UICONTROL Trait Builder] |

>[!MORE_ LIKE_ THIS]
>
>* [Expressões booleanas em características e no construtor de segmentos](../../reference/boolean-expressions-tsb.md)
>* [Noções básicas de expressões booleanas no traitbuilder](../../reference/boolean-expressions-tsb.md)
>* [Ordem de operações nas expressões do traitbuilder](../../features/traits/trait-operator-precedence.md)
>* [Expressões de amostra com operadores booleanos e de comparação](../../features/traits/trait-expression-samples.md)

