---
description: Métodos que permitem exibir a taxonomia comum do Audience Manager. Esse esquema de classificação opcional organiza as características em categorias padrão do setor.
seo-description: Methods that let you view the Audience Manager common taxonomy. This optional classification scheme organizes traits into industry standard categories.
seo-title: Taxonomic API Methods
solution: Audience Manager
title: Métodos da API taxonômica
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
exl-id: 8bc6dcbb-7f5b-4a7b-998d-025eaf76c409
TQID: https://experienceleague.adobe.com/LIHEWvF3t-VNHJEviomvCF-dxE2Jy-BFxBynonvwP3w
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
topic_v2: id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 173
ht-degree: 1%

---

# Métodos da API taxonômica {#taxonomic-api-methods}

Métodos que permitem exibir a taxonomia comum do Audience Manager. Esse esquema de classificação opcional organiza as características em categorias padrão do setor.

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
