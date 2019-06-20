---
description: Use operadores lógicos para agrupar pares de valores chave e de preenchimento retroativo.
seo-description: Use operadores lógicos para agrupar pares de valores chave e de preenchimento retroativo.
seo-title: Operadores lógicos compatíveis
title: Operadores lógicos compatíveis
uuid: 645 fcb 6 f -50 ac -49 bc -8 df 9-c 699 c 749 cf 8 f
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# Supported Logical Operators {#supported-logical-operators}

Use operadores lógicos para agrupar pares de valores chave e de preenchimento retroativo.

## Supported Operators for Signal Search {#supported-operators-search}

Use os seguintes operadores lógicos suportados para pesquisar pares de valor chave:

### Operadores de comparação

| Operador | Definição |
|---|---|
| **==** | Igual a |
| **&gt;** | Maior que |
| **&lt;** | Menos que |
| **=&gt;** | Maior que/igual a |
| **&lt;=** | Menor que/igual a |

### Operadores nomeados

| Operador | Evaluates to [!DNL True] When |
|---|---|
| **[!UICONTROL Contains]** | The value in a key-value pair *contains* characters specified by this operator. |
| **[!UICONTROL Startswith]** | The value in a key-value pair *starts with* characters specified by this operator. |
| **[!UICONTROL Endswith]** | The value in a key-value pair *ends with* the characters specified by this operator. |

## Supported Operators for Trait Backfilling and Estimation {#supported-operators-backfilling}

You can backfill traits that include expressions containing any of the operators supported by [!UICONTROL Signal Search]. In addition to these operators, trait backfilling and estimation also support the [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL AND NOT] logical operators, used to combine key-value pairs within the backfilled trait expressions.