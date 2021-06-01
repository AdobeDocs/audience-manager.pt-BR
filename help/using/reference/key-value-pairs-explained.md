---
description: Define e descreve pares de valores-chave padrão e serializados.
keywords: código de integração
seo-description: Define e descreve pares de valores-chave padrão e serializados.
seo-title: Explicação dos pares de valor-chave
solution: Audience Manager
title: Explicação dos pares de valor-chave
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
feature: 'Referência '
exl-id: de4e6fdb-2d6d-4fed-9255-9438b42b2570
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 7%

---

# Explicação dos pares de valor-chave{#key-value-pairs-explained}

Define e descreve pares de valores-chave padrão e serializados.

<!-- 

c_key_value_explained.xml

 -->

Um par de valores chave consiste em dois elementos de dados relacionados: Uma chave, que é uma constante que define o conjunto de dados (por exemplo, gênero, cor, preço) e um valor, que é uma variável que pertence ao conjunto (por exemplo, masculino/feminino, verde, 100). Totalmente formado, um par de valores chave pode ser semelhante a:

* `gender = male`
* `color = green`
* `price > 100`

## Pares padrão e serializados de valores-chave {#standard-serialized-pairs}

Os destinos aceitam dados de valor-chave no formato *`standard`* ou *`serialized`*. A formatação padrão organiza os dados em pares de valores chave separados. Cada chave é declarada explicitamente, mesmo quando usada novamente para definir um valor diferente. Por outro lado, a formatação serializada condensa vários valores em um único conjunto definido por uma única chave. Além disso, em um par serializado, um indicador especial é usado para separar os valores no conjunto de valores chave. Finalmente, os valores-chave padrão e serializados podem conter valores únicos ou múltiplos. A tabela a seguir fornece exemplos de formatos padrão e de valores-chave serial.

| Formatação | Chave única | Pares de valor-chave |
|---|---|---|
| **Padrão** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Serializado** | `x=1;2` | `x=1;2&y=3;4` |



## Chaves, delimitadores e separadores {#keys-delimiters-separators}

Ao trabalhar com dados serializados, você deve especificar os caracteres que separam valores *dentro de* e *entre* os pares de valores chave. Os elementos em pares de valores chave são definidos da seguinte maneira:

* **Chave:** um identificador exclusivo no par de valor chave.
* **Delimitador de valor:** Separa pares de valores chave individuais.
* **Separador de valor-chave:** separa uma chave dos valores em um par de valor-chave.
* **Separador de série:** separa valores individuais em pares de valores chave serializados.

## Elementos de valor-chave padrão e serializado {#standard-serialized-key-value-elements}


| Tipo | Exemplo | Chave | Separador de valor-chave | Delimitador de valor-chave | Separador serial |
---------|----------|---------|---------|----------|---------
| **Chave única**  (padrão) | `x=1&x=2` | `x` | `=` | `&` | n/a |
| **Pares de valor-chave**  (padrão) | `x=1&x=2&y=3&y=4` | `x,y` | `=` | `&` | n/d |
| **Chave**  única (serial) | `x=1;2;3` | `x` | `=` | n/d | `;` |
| **Pares**  de valor-chave (serial) | `x=1;2&y=3;4` | `x,y` | `=` | `&` | `;` |
