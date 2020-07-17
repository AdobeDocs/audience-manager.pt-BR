---
description: Use operadores lógicos para agrupar pares de valores chave e características de preenchimento retroativo.
seo-description: Use operadores lógicos para agrupar pares de valores chave e características de preenchimento retroativo.
seo-title: Operadores lógicos compatíveis
title: Operadores lógicos compatíveis
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 9%

---


# Operadores lógicos compatíveis {#supported-logical-operators}

Use operadores lógicos para agrupar pares de valores chave e características de preenchimento retroativo.

## Operadores suportados para pesquisa de sinal {#supported-operators-search}

Use os seguintes operadores lógicos suportados para procurar pares de valores chave:

### Operadores de comparação

| Operador | Definição |
|---|---|
| **==** | Igual a |
| **>** | Maior que |
| **&lt;** | Menos que |
| **=>** | Maior que/igual a |
| **&lt;=** | Menor que/igual a |

### Operadores nomeados

| Operador | Avalia para [!DNL True] Quando |
|---|---|
| **[!UICONTROL Contains]** | O valor em um par de chave-valor *contém* caracteres especificados por esse operador. |
| **[!UICONTROL Startswith]** | O valor em um par de valor chave *start com* caracteres especificados por esse operador. |
| **[!UICONTROL Endswith]** | O valor em um par de valor chave *termina com* os caracteres especificados por esse operador. |

## Operadores suportados para preenchimento retroativo e estimativa de características {#supported-operators-backfilling}

É possível preencher retroativamente características que incluem expressões que contêm qualquer um dos operadores suportados por [!UICONTROL Signal Search]. Além desses operadores, o preenchimento retroativo e a estimativa de características também suportam os operadores [!UICONTROL AND], [!UICONTROL OR]e [!UICONTROL AND NOT] lógicos, usados para combinar pares de valores chave nas expressões de característica pré-preenchida.