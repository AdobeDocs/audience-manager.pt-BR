---
description: Métodos que permitem visualizar a taxonomia comum de Audience Manager. Esse esquema de classificação opcional organiza as características em categorias padrão do setor.
seo-description: Methods that let you view the Audience Manager common taxonomy. This optional classification scheme organizes traits into industry standard categories.
seo-title: Taxonomic API Methods
solution: Audience Manager
title: Métodos da API taxonômica
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
exl-id: 8bc6dcbb-7f5b-4a7b-998d-025eaf76c409
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 1%

---

# Métodos da API taxonômica {#taxonomic-api-methods}

Métodos que permitem visualizar a taxonomia comum de Audience Manager. Esse esquema de classificação opcional organiza as características em categorias padrão do setor.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>Não é possível criar novas categorias taxonômicas ou classificar características com esses métodos. Para classificar uma característica, especifique o `categoryId` apropriado com um método de criação ou atualização de característica.

## Retornar uma taxonomia específica {#return-specific-taxonomy}

Um método `GET` que retorna detalhes sobre a categoria taxonômica especificada.

<!-- r_rest_api_taxonomy.xml -->

### Solicitação

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### Resposta

Uma resposta bem-sucedida retorna `200 OK` e a categoria da ID especificada. Uma solicitação sem sucesso retorna `404 No Content` se a ID não existir.

```
{
    "crUID": 158,
    "name": "Arts & Entertainment",
    "upUID": 158,
    "description": "Arts & Entertainment",
    "categoryID": 1,
    "parentCategoryID": 0
}
```

## Retornar todas as categorias taxonômicas {#return-all-taxonomy-categories}

Um método `GET` que retorna uma lista das categorias de nível superior em uma matriz.

<!-- r_rest_api_taxonomies.xml -->

### Solicitação

`GET https://api.demdex.com/v1/taxonomies/0/`

### Resposta

Truncado por brevidade.

```
[
    {
        "crUID": 158,
        "name": "Arts & Entertainment",
        "upUID": 158,
        "description": "Arts & Entertainment",
        "categoryID": 1,
        "parentCategoryID": 0
    },
    {
        "crUID": 158,
        "name": "Automotive",
        "upUID": 158,
        "description": "Automotive",
        "categoryID": 2,
        "parentCategoryID": 0
    },
    {
        "crUID": 158,
        "name": "Business",
        "upUID": 158,
        "description": "Business",
        "categoryID": 3,
        "parentCategoryID": 0
    }
]
```

## Retornar subcategorias taxonômicas {#return-taxonomy-sub-categories}

Um método `GET` que retorna subcategorias para a categoria pai especificada em uma matriz.

<!-- r_rest_api_taxonomy_sub.xml -->

### Solicitação

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### Resposta

Uma resposta bem-sucedida retorna `200 OK` e a categoria da ID especificada. Uma solicitação sem sucesso retorna `404 No Content` se a ID não existir. Truncado por brevidade.

```
[
    {
        "crUID": 158,
        "name": "Books & Literature",
        "upUID": 158,
        "description": "Books & Literature",
        "categoryID": 25,
        "parentCategoryID": 1
    },
    {
        "crUID": 158,
        "name": "Celebrity Fan/Gossip",
        "upUID": 158,
        "description": "Celebrity Fan/Gossip",
        "categoryID": 49,
        "parentCategoryID": 1
    },
    {
        "crUID": 158,
        "name": "Fine Art",
        "upUID": 158,
        "description": "Fine Art",
        "categoryID": 72,
        "parentCategoryID": 1
    }
]
```
