---
description: Métodos que permitem exibir a taxonomia comum do Audience Manager. Esse esquema de classificação opcional organiza características nas categorias padrão do setor.
seo-description: Métodos que permitem exibir a taxonomia comum do Audience Manager. Esse esquema de classificação opcional organiza características nas categorias padrão do setor.
seo-title: Métodos de API taxonomia
solution: Audience Manager
title: Métodos de API taxonomia
uuid: 4 ee 29 ba 5-e 9 ba -4498-a 6 ee -7343227 dd 7 ba
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Taxonomic API Methods {#taxonomic-api-methods}

Métodos que permitem exibir a taxonomia comum do Audience Manager. Esse esquema de classificação opcional organiza características nas categorias padrão do setor.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>Não é possível criar novas categorias taxômicas ou classificar características com esses métodos. To classify a trait, specify the appropriate `categoryId` with a trait create or update method.

## Return a Specific Taxonomy {#return-specific-taxonomy}

`GET` Um método que retorna detalhes sobre a categoria taxonomômica especificada.

<!-- r_rest_api_taxonomy.xml -->

### Solicitação

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### Resposta

A successful response returns `200 OK` and the category for the specified ID. An unsuccessful request returns `404 No Content` if the ID does not exist.

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

## Return all Taxonomic Categories {#return-all-taxonomy-categories}

`GET` Um método que retorna uma lista das categorias de nível superior em uma matriz.

<!-- r_rest_api_taxonomies.xml -->

### Solicitação

`GET https://api.demdex.com/v1/taxonomies/0/`

### Resposta

Truncado para facilitar a execução.

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

## Return Taxonomic Sub-Categories {#return-taxonomy-sub-categories}

`GET` Um método que retorna subcategorias para a categoria pai especificada em uma matriz.

<!-- r_rest_api_taxonomy_sub.xml -->

### Solicitação

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### Resposta

A successful response returns `200 OK` and the category for the specified ID. An unsuccessful request returns `404 No Content` if the ID does not exist. Truncado para facilitar a execução.

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
