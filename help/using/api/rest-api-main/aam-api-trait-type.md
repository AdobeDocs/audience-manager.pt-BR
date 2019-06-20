---
description: Métodos opcionais que permitem atribuir características a um tipo ou categoria definida pelo usuário, normalmente de acordo com a função ou para seus próprios processos internos de relatórios.
seo-description: Métodos opcionais que permitem atribuir características a um tipo ou categoria definida pelo usuário, normalmente de acordo com a função ou para seus próprios processos internos de relatórios.
seo-title: Métodos de tipo de característica
solution: Audience Manager
title: Métodos de tipo de característica
uuid: 082931 d 5-457 b -4622-817 b -86303 f 38 c 26 a
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Trait Type Methods {#trait-type-methods}

Métodos opcionais que permitem atribuir características a um tipo ou categoria definida pelo usuário, normalmente de acordo com a função ou para seus próprios processos internos de relatórios.

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>Trait type methods do not assign traits to categories used by the [common taxonomy](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods). Pense neles como rótulos separados da taxonomia comum.

For visual reference, [!UICONTROL Trait Types] is a dropdown control located in the [!DNL UI] under **[!UICONTROL Traits > Create new trait > Basic Information]**.

## Create a New Trait Type {#create-trait-type}

`POST` Um método que permite criar um novo tipo de característica.

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

## Return Properties for a Trait Type {#return-props}

`GET` Um método que retorna detalhes sobre o tipo de característica especificado.

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

## Return Properties for all Trait Types {#return-props-all}

`GET` Um método que retorna detalhes sobre todos os seus tipos de características em uma matriz.

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
