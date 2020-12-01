---
description: Este artigo descreve os operadores de comparação usados pelo Construtor de características.
seo-description: Este artigo descreve os operadores de comparação usados pelo Construtor de características.
seo-title: Trabalhar com operadores de comparação no Construtor de características
solution: Audience Manager
title: Trabalhar com operadores de comparação no Construtor de características
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 11%

---


# Trabalhar com operadores de comparação no Construtor de características {#working-with-comparison-operators-in-trait-builder}

Este artigo descreve os operadores de comparação usados por [!UICONTROL Trait Builder].

## Finalidade dos operadores de comparação

<!-- c_tb_comparison_operators.xml -->

Os operadores de comparação (ou operadores relacionais) são usados para comparar, testar ou avaliar a relação entre valores diferentes. Em [!UICONTROL Trait Builder], ao criar regras de sinal, os operadores de comparação permitem que você teste a relação entre diferentes pares de valores chave. Por exemplo, você pode criar uma regra de sinal para definir uma audiência para compradores de câmeras caras. Neste caso, você pode criar um par de câmera/preço chave-valor e qualificar um usuário se ele tiver procurado por uma câmera com um preço igual ou superior a um valor definido.

## Vantagens dos operadores de comparação

Os operadores de comparação são úteis quando você precisa avaliar e criar características com base em vários valores. Olhar para os preços dos bens e serviços pode ilustrar esta condição. Por exemplo, sua empresa pode querer identificar visitantes com base nos preços dos produtos que visualização. No entanto, pode ser administrativamente ineficiente definir segmentos individuais com base em valores específicos. Os operadores de comparação ajudam a superar esse obstáculo estabelecendo acionadores de segmentação com base em limites de preços ou intervalos.

## Operadores de comparação

Você pode criar regras com os seguintes operadores de comparação:

| Operador | Definição |
|---|---|
| **==** | Igual a |
| **!=** | Diferente de |
| **>** | Maior que |
| **&lt;** | Menos que |
| **=>** | Maior que/igual a |
| **&lt;=** | Menor que/igual a |

## Operadores nomeados

Você pode criar regras com os seguintes operadores nomeados:

| Operador | Avalia para [!DNL True] Quando |
|---|---|
| **[!UICONTROL Contains]** | O valor em um par de chave-valor *contém* caracteres especificados por esse operador. |
| **[!UICONTROL Matcheswords]** | O valor em um par de chave-valor *corresponde* ao padrão especificado por esse operador. |
| **[!UICONTROL Startswith]** | O valor em um par de chave-valor *start com* caracteres especificados por esse operador. |
| **[!UICONTROL Endswith]** | O valor em um par de chave-valor *termina com* os caracteres especificados por esse operador. |
| **[!UICONTROL Matchesregex]** | O valor em um par de chave-valor *corresponde* ao padrão especificado por uma expressão regular. [Saiba ](../../features/traits/trait-builder-regex.md) mais sobre como usar expressões regulares no  [!UICONTROL Trait Builder]. |

>[!MORELIKETHIS]
>
>* [Expressões booleanas no Construtor de características e segmentos](../../reference/boolean-expressions-tsb.md)
>* [Noções básicas sobre Expressões booleanas no TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Ordem de operações nas Expressões do TraitBuilder](../../features/traits/trait-operator-precedence.md)
>* [Expressões de amostra com operadores booleanos e de comparação](../../features/traits/trait-expression-samples.md)

