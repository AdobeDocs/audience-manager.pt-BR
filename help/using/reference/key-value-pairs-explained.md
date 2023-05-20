---
description: Define e descreve pares de valores chave padrão e serializados.
keywords: código de integração
seo-description: Defines and describes standard and serialized key-value pairs.
seo-title: Key-Value Pairs Explained
solution: Audience Manager
title: Explicação dos pares de valor-chave
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
feature: Reference
exl-id: de4e6fdb-2d6d-4fed-9255-9438b42b2570
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 6%

---

# Explicação dos pares de valor-chave{#key-value-pairs-explained}

Define e descreve pares de valores chave padrão e serializados.

<!-- 

c_key_value_explained.xml

 -->

Um par de valor-chave consiste em dois elementos de dados relacionados: uma chave, que é uma constante que define o conjunto de dados (por exemplo, gênero, cor, preço), e um valor, que é uma variável que pertence ao conjunto (por exemplo, masculino/feminino, verde, 100). Totalmente formado, um par de valores-chave pode ser semelhante a:

* `gender = male`
* `color = green`
* `price > 100`

## Pares de valor-chave padrão e serializados {#standard-serialized-pairs}

Os destinos aceitam dados de valores-chave no *`standard`* ou *`serialized`* formato. A formatação padrão organiza os dados em pares de valores chave separados. Cada chave é declarada explicitamente, mesmo quando usada novamente para definir um valor diferente. Por outro lado, a formatação serializada condensa vários valores em um conjunto definido por uma única chave. Além disso, em um par serializado, um indicador especial é usado para separar os valores no conjunto de valores chave. Finalmente, valores-chave padrão e serializados podem conter um ou vários valores. A tabela a seguir fornece exemplos de formatos de valor-chave padrão e serial.

| Formatação | Tecla única | Pares de valor-chave |
|---|---|---|
| **Padrão** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Serializado** | `x=1;2` | `x=1;2&y=3;4` |



## Chaves, delimitadores e separadores {#keys-delimiters-separators}

Ao trabalhar com dados serializados, você deve especificar os caracteres que separam valores *no prazo de* e *entre* os pares chave-valor. Os elementos em pares de valor-chave são definidos da seguinte maneira:

* **Chave:** Um identificador exclusivo no par de valor-chave.
* **Delimitador de valor:** Separa pares de valor-chave individuais.
* **Separador de valor-chave:** Separa uma chave dos valores em um par de valores chave.
* **Separador serial:** Separa valores individuais em pares de valores chave serializados.

## Elementos de valor-chave padrão e serializados {#standard-serialized-key-value-elements}


| Tipo | Exemplo | Chave | Separador de valor-chave | Delimitador de valor-chave | Separador serial |
|---------|----------|---------|---------|----------|---------|
| **Chave única** (padrão) | `x=1&x=2` | `x` | `=` | `&` | n/a |
| **Pares de valor-chave** (padrão) | `x=1&x=2&y=3&y=4` | `x,y` | `=` | `&` | n/a |
| **Chave única** (serial) | `x=1;2;3` | `x` | `=` | n/a | `;` |
| **Pares de valor-chave** (serial) | `x=1;2&y=3;4` | `x,y` | `=` | `&` | `;` |
