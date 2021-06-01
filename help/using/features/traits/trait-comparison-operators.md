---
description: Este artigo descreve os operadores de comparação usados pelo Construtor de características.
seo-description: Este artigo descreve os operadores de comparação usados pelo Construtor de características.
seo-title: Trabalhar com operadores de comparação no Construtor de características
solution: Audience Manager
title: Trabalhar com operadores de comparação no Construtor de características
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
feature: 'Características '
exl-id: 93181ca3-46c8-45ee-b0fb-da9ceec19a39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 12%

---

# Trabalhar com operadores de comparação no Construtor de características {#working-with-comparison-operators-in-trait-builder}

Este artigo descreve os operadores de comparação usados por [!UICONTROL Trait Builder].

## Finalidade dos operadores de comparação

<!-- c_tb_comparison_operators.xml -->

Os operadores de comparação (ou operadores relacionais) são usados para comparar, testar ou avaliar a relação entre valores diferentes. Em [!UICONTROL Trait Builder], ao criar regras de sinal, os operadores de comparação permitem testar a relação entre pares de valores chave diferentes. Por exemplo, você pode criar uma regra de sinal para definir um público-alvo para compradores de câmera caros. Nesse caso, você pode criar uma câmera/par de valor chave de preço e qualificar um usuário se ele tiver procurado uma câmera com um preço igual ou maior que um valor definido.

## Vantagens dos operadores de comparação

Os operadores de comparação são úteis quando é necessário avaliar e criar características com base em vários valores. Olhar para os preços de bens e serviços pode ilustrar esta condição. Por exemplo, sua empresa pode querer identificar visitantes com base nos preços dos produtos que eles visualizam. No entanto, pode ser administrativamente ineficiente definir segmentos individuais com base em valores específicos. Os operadores de comparação ajudam a superar esse obstáculo com o estabelecimento de acionadores de segmentação com base em limites de preço ou intervalos.

## Operadores de comparação

Você pode criar regras com os seguintes operadores de comparação:

| Operador | Definição |
|---|---|
| **==** | Igual a |
| **!=** | Not equal to |
| **>** | Maior que |
| **&lt;** | Menos que |
| **=>** | Maior que/igual a |
| **&lt;=** | Menor que/igual a |

## Operadores nomeados

Você pode criar regras com os seguintes operadores nomeados:

| Operador | Avalia para [!DNL True] Quando |
|---|---|
| **[!UICONTROL Contains]** | O valor em um par de valores chave *contém caracteres* especificados por esse operador. |
| **[!UICONTROL Matcheswords]** | O valor em um par de valores chave *corresponde a* ao padrão especificado por esse operador. |
| **[!UICONTROL Startswith]** | O valor em um par de valor chave *começa com caracteres* especificados por esse operador. |
| **[!UICONTROL Endswith]** | O valor em um par de valor chave *termina com* os caracteres especificados por esse operador. |
| **[!UICONTROL Matchesregex]** | O valor em um par de valores chave *corresponde a* ao padrão especificado por uma expressão regular. [Saiba ](../../features/traits/trait-builder-regex.md) mais sobre o uso de expressões regulares no  [!UICONTROL Trait Builder]. |

>[!MORELIKETHIS]
>
>* [Expressões booleanas no Construtor de características e segmentos](../../reference/boolean-expressions-tsb.md)
* [Como entender expressões booleanas no TraitBuilder](../../reference/boolean-expressions-tsb.md)
* [Ordem de operações nas expressões do TraitBuilder](../../features/traits/trait-operator-precedence.md)
* [Expressões de amostra com operadores booleanos e de comparação](../../features/traits/trait-expression-samples.md)

