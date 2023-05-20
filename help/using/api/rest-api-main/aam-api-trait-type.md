---
description: Métodos opcionais que permitem atribuir características a um tipo ou categoria definida pelo usuário, geralmente de acordo com a função ou para seus próprios processos internos de relatório.
seo-description: Optional methods that let you to assign traits to a user-defined type or category, usually according to function or for your own internal reporting processes.
seo-title: Trait Type Methods
solution: Audience Manager
title: Métodos do tipo de característica
uuid: 082931d5-457b-4622-817b-86303f38c26a
feature: API
exl-id: d450f9ce-2abb-4a8b-b8db-2962b84fb341
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 9%

---

# Métodos do tipo de característica {#trait-type-methods}

Métodos opcionais que permitem atribuir características a um tipo ou categoria definida pelo usuário, geralmente de acordo com a função ou para seus próprios processos internos de relatório.

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>Os métodos do tipo de característica não atribuem características a categorias usadas pelo [taxonomia comum](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods). Pense nisso como rótulos separados da taxonomia comum.

Para referência visual, [!UICONTROL Trait Types] é um controle suspenso localizado na [!DNL UI] em **[!UICONTROL Traits > Create new trait > Basic Information]**.

## Criar um novo tipo de característica {#create-trait-type}

A `POST` que permite criar um novo tipo de característica.

<!-- r_rest_api_create_trait_type.xml -->

### Solicitação

`POST https://api.demdex.com/v1/customer-trait-types`

### Solicitação de exemplo

```
{
"name":"Custom trait type"
}
```

### Resposta

```
{
    "pixelType": 34,
    "pid": 1099,
    "name": "Custom type",
    "description": null,
    "crUID": 694,
    "upUID": 694,
    "createTime": 1358297352000,
    "updateTime": 1358297352000
}
```

## Propriedades de retorno para um tipo de característica {#return-props}

A `GET` que retorna detalhes sobre o tipo de característica especificado.

<!-- r_rest_api_get_trait_type.xml -->

### Solicitação

`GET https://api.demdex.com/v1/customer-trait-types/`*`<customerTraitTypeId>`*

### Resposta

```
{
    "pixelType": 4,
    "pid": 0,
    "name": "Delivery Event",
    "description": "Delivery Event",
    "crUID": 158,
    "upUID": 158,
    "createTime": 1299115496000,
    "updateTime": 1299115496000
}
```

## Propriedades de retorno para todos os tipos de características {#return-props-all}

A `GET` que retorna detalhes sobre todos os tipos de características em uma matriz.

<!-- r_rest_api_get_trait_types.xml -->

### Solicitação

`GET https://api.demdex.com/v1/customer-trait-types/`

### Resposta

```
[
    {
        "pixelType": 200,
        "pid": 1099,
        "name": "Customer Specific Trait Type",
        "description": "Test",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1349990458000,
        "updateTime": 1349990458000
    },
    {
        "pixelType": 1,
        "pid": 0,
        "name": "User Trait",
        "description": "User Trait",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1299115492000,
        "updateTime": 1299115492000
    },
    {
        "pixelType": 2,
        "pid": 0,
        "name": "Site Visitor",
        "description": "Site Visitor",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1299115493000,
        "updateTime": 1299115493000
    }
]
```
