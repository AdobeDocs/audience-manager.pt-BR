---
description: Define e descreve pares de valores chave padrão e serializados.
keywords: integration code
seo-description: Define e descreve pares de valores chave padrão e serializados.
seo-title: Explicação dos pares de valor-chave
solution: Audience Manager
title: Explicação dos pares de valor-chave
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
feature: reference
translation-type: tm+mt
source-git-commit: 5d6983f5308f1dfd4560ee1b38bcaee3ca6e422f
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 6%

---


# Explicação dos pares de valor-chave{#key-value-pairs-explained}

Define e descreve pares de valores chave padrão e serializados.

<!-- 

c_key_value_explained.xml

 -->

Um par de valores chave consiste em dois elementos de dados relacionados: Uma tecla, que é uma constante que define o conjunto de dados (por exemplo, gênero, cor, preço) e um valor, que é uma variável que pertence ao conjunto (por exemplo, macho/fêmea, verde, 100). Totalmente formado, um par de valores chave poderia ser parecido com estes:

* `gender = male`
* `color = green`
* `price > 100`

## Pares padrão e serializados de valores chave {#standard-serialized-pairs}

Os destinos aceitam dados de valor chave no formato *`standard`* ou *`serialized`*. A formatação padrão organiza os dados em pares de valores chave separados. Cada chave é declarada explicitamente, mesmo quando usada novamente para definir um valor diferente. Por outro lado, a formatação serializada condensa vários valores em um conjunto definido por uma única tecla. Além disso, em um par serializado, um indicador especial é usado para separar os valores dentro do conjunto de valores chave. Finalmente, os valores-chave padrão e serializados podem conter valores únicos ou múltiplos. A tabela a seguir fornece exemplos de formatos padrão e de valores de chave serial.

| Formatação | Chave única | Pares de valor-chave |
|---|---|---|
| **Padrão** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Serializado** | `x=1;2` | `x=1;2&y=3;4` |



## Teclas, delimitadores e separadores {#keys-delimiters-separators}

Ao trabalhar com dados serializados, você deve especificar os caracteres que separam os valores *em* e *entre* os pares de valores chave. Os elementos em pares de valor chave são definidos da seguinte forma:

* **Chave:** Um identificador exclusivo no par de valores chave.
* **Delimitador de valores:** Separa pares de valores chave individuais.
* **Separador de valor-chave:** Separa uma chave dos valores em um par de valor-chave.
* **Separador de série:** Separa valores individuais em pares de valores chave serializados.

## Elementos de valor-chave padrão e serializados {#standard-serialized-key-value-elements}


| Tipo | Exemplo | Chave | Separador de valor-chave | Delimitador de valor-chave | Separador serial |
---------|----------|---------|---------|----------|---------
| **Chave**  única (padrão) | `x=1&x=2` | `x` | `=` | `&` | n/a |
| **Pares**  de valor-chave (padrão) | `x=1&x=2&y=3&y=4` | `x,y` | `=` | `&` | n/d |
| **Chave**  única (serial) | `x=1;2;3` | `x` | `=` | n/d | `;` |
| **Pares**  de valor-chave (serial) | `x=1;2&y=3;4` | `x,y` | `=` | `&` | `;` |
