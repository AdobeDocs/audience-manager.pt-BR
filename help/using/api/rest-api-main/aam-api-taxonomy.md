---
description: Métodos que permitem visualização a taxonomia Audience Manager comum. Este sistema de classificação opcional organiza características em categorias padrão do setor.
seo-description: Métodos que permitem visualização a taxonomia Audience Manager comum. Este sistema de classificação opcional organiza características em categorias padrão do setor.
seo-title: Métodos da API taxonômica
solution: Audience Manager
title: Métodos da API taxonômica
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 7%

---


# Métodos da API taxonômica {#taxonomic-api-methods}

Métodos que permitem visualização a taxonomia Audience Manager comum. Este sistema de classificação opcional organiza características em categorias padrão do setor.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>Não é possível criar novas categorias taxonômicas ou classificar características com esses métodos. Para classificar uma característica, especifique a apropriada `categoryId` com um método de criação ou atualização de característica.

## Devolver uma Taxonomia Específica {#return-specific-taxonomy}

Um `GET` método que retorna detalhes sobre a categoria taxonômica especificada.

<!-- r_rest_api_taxonomy.xml -->

### Solicitação

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### Resposta

Uma resposta bem-sucedida retorna `200 OK` e a categoria para a ID especificada. Uma solicitação com falha retornará `404 No Content` se a ID não existir.

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

## Retornar todas as Categorias taxonômicas {#return-all-taxonomy-categories}

Um `GET` método que retorna uma lista das categorias de nível superior em um storage.

<!-- r_rest_api_taxonomies.xml -->

### Solicitação

`GET https://api.demdex.com/v1/taxonomies/0/`

### Resposta

Truncado para brevidade.

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

## Retornar Categorias taxonômicas {#return-taxonomy-sub-categories}

Um `GET` método que retorna subcategorias para a categoria pai especificada em uma matriz.

<!-- r_rest_api_taxonomy_sub.xml -->

### Solicitação

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### Resposta

Uma resposta bem-sucedida retorna `200 OK` e a categoria para a ID especificada. Uma solicitação com falha retornará `404 No Content` se a ID não existir. Truncado para brevidade.

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
