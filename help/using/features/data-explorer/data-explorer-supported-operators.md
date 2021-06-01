---
description: Use operadores lógicos para agrupar pares de valores chave e características de preenchimento retroativo.
seo-description: Use operadores lógicos para agrupar pares de valores chave e características de preenchimento retroativo.
seo-title: Operadores lógicos compatíveis
title: Operadores lógicos compatíveis
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: 'Data Explorer '
exl-id: 5e405390-1c19-4e43-b3f9-598e8aa6bd99
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 10%

---

# Operadores lógicos compatíveis {#supported-logical-operators}

Use operadores lógicos para agrupar pares de valores chave e características de preenchimento retroativo.

## Operadores compatíveis para pesquisa de sinal {#supported-operators-search}

Use os seguintes operadores lógicos compatíveis para procurar pares de valores chave:

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
| **[!UICONTROL Contains]** | O valor em um par de valores chave *contém caracteres* especificados por esse operador. |
| **[!UICONTROL Startswith]** | O valor em um par de valor chave *começa com caracteres* especificados por esse operador. |
| **[!UICONTROL Endswith]** | O valor em um par de valor chave *termina com* os caracteres especificados por esse operador. |

## Operadores compatíveis para preenchimento retroativo de características e estimativa {#supported-operators-backfilling}

É possível preencher retroativamente características que incluem expressões contendo qualquer um dos operadores compatíveis com [!UICONTROL Signal Search]. Além desses operadores, o preenchimento retroativo de características e a estimativa também oferecem suporte aos operadores lógicos [!UICONTROL AND], [!UICONTROL OR] e [!UICONTROL AND NOT], usados para combinar pares de valores-chave nas expressões de características preenchidas retroativamente.
