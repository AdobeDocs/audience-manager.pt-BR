---
description: Mapeie segmentos para destinos com esses métodos RESTful API.
seo-description: Mapeie segmentos para destinos com esses métodos RESTful API.
seo-title: Mapear segmentos para um destino
solution: Audience Manager
title: Mapear segmentos para um destino
uuid: 35358ace-3082-4e86-a6eb-d77281af6d7e
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 11%

---


# Mapear segmentos para um destino {#map-segments-to-a-destination}

Mapeie segmentos para destinos com esses métodos [!DNL RESTful API].

<!-- c_api_map_seg_dest.xml -->

## Tipos de Destino Suportados: URL e somente cookie

Os métodos disponíveis `POST` permitem mapear segmentos somente para [!UICONTROL URL] e [!UICONTROL cookie destinations]. Atualmente, não é possível mapear segmentos para [!UICONTROL server-to-server destinations] com esses métodos [!DNL REST API]. Em vez disso, use a interface do usuário. No entanto, os métodos de destino relacionados `GET` permitem que você recupere informações sobre [!UICONTROL server-to-server destinations] criadas na interface do usuário.

## Mapear um segmento para um destino de URL não serializado {#map-segment-non-serial}

Um método `POST` que permite mapear um segmento para um destino [!UICONTROL URL] não serial.

<!-- r_map_noserial_url.xml -->

### Solicitação

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Solicitação de exemplo

Todos os valores de solicitação são obrigatórios, a menos que seja indicado o contrário.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-07-04"
}
```

### Resposta

```
{
   "mappingId":65334,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4033,
   "elementName":"Sample games",
   "elementDescription":"Sample games pixel",
   "elementStatus":"active",
   "createTime":1338940094000,
   "updateTime":1338940094000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "url":"https://adobe.com",
   "secureUrl":null,
   "tagCode":null,
   "secureTagCode":null,
   "traitAlias":null
}
```

## Mapear um segmento para um destino de URL serializado {#map-segment-serial}

Um método `POST` que permite mapear um segmento para um destino [!UICONTROL URL] serializado.

<!-- r_map_serialized_url.xml -->

### Solicitação

`POST https://api.demdex.com/v1/destinations/`*`<dataOrderId>`*`/traits/`

### Solicitação de exemplo

Na solicitação, `traitAlias` corresponde à chave em um par de valor chave. Todos os valores de solicitação são obrigatórios, a menos que seja indicado o contrário.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"123"
}
```

### Resposta

```
{
   "mappingId":65335,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4034,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338940401000,
   "updateTime":1338940401000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "url":"123",
   "secureUrl":"123",
   "tagCode":null,
   "secureTagCode":null,
   "traitAlias":"123"
}
```

## Mapeie um segmento para um destino de cookie: Chave única, não serializada {#map-segment-cookie-noserial}

Um método `POST` que permite mapear um segmento para um destino [!UICONTROL cookie] de chave única e não serializado.

<!-- r_map_cookie_noserial.xml -->

### Solicitação

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Solicitação de exemplo

Na solicitação, `valueAlias` corresponde ao valor em um par de valor chave. Todos os valores de solicitação são obrigatórios, a menos que seja indicado o contrário.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "valueAlias":"123"
}
```

### Resposta

```
{
   "destinationMappingId":65336,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4035,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338940704000,
   "updateTime":1338940704000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":1,
   "traitAlias":null,
   "valueAlias":"123"
}
```

## Mapeie um segmento para um destino de cookie: Multi-Key, Não Serializado {#map-segment-cookie-multi-noserial}

Um método `POST` que permite mapear um segmento para um destino [!UICONTROL cookie] multichave e não serializado.

<!-- r_map_cookie_multikey_noserial.xml -->

### Solicitação

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Solicitação de exemplo

Na solicitação, `traitAlias` e `valueAlias` definem a chave e o valor respectivamente em um par de valores chave. Todos os valores de solicitação são obrigatórios, a menos que seja indicado o contrário.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"type",
   "valueAlias":"123"
}
```

### Resposta

```
{
   "mappingId":65338,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4037,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338941092000,
   "updateTime":1338941092000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":1,
   "traitAlias":"type",
   "valueAlias":"123"
}
```

## Mapeie um segmento para um destino de cookie: Multi-Chave, Serializado {#map-segment-cookie-multi-serial}

Um método `POST` que permite mapear um segmento para um [!UICONTROL cookie destination] serializado e com várias teclas.

<!-- r_map_cookie_multikey_serialized.xml -->

### Solicitação

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Solicitação de exemplo

Na solicitação, `traitAlias` e `valueAlias` definem a chave e o valor em um par de valores chave. Todos os valores de solicitação são obrigatórios, a menos que seja indicado o contrário.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"type",
   "valueAlias":"123"
}
```

### Resposta

```
{
   "destinationMappingId":65340,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4038,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338941273000,
   "updateTime":1338941273000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":2,
   "traitAlias":"type",
   "valueAlias":"123"
}
```

## Mapear um segmento para um destino de servidor para servidor {#map-segment-s2s}

Um método `POST` que permite mapear um segmento para um destino [!UICONTROL server-to-server] existente. Observe, no entanto, que não é possível criar [!UICONTROL server-to-server] destinos com esses métodos [!DNL API] atualmente disponíveis.

<!-- r_map_segment_s2s.xml -->

### Solicitação

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Solicitação de exemplo

Na solicitação, `traitAlias` corresponde à chave em um par de valor chave. Todos os valores de solicitação são obrigatórios, a menos que seja indicado o contrário.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"123"
}
```

### Resposta

```
{
   "destinationMappingId":65341,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":566,
   "elementName":"Sample",
   "elementDescription":"",
   "elementStatus":"active",
   "createTime":1338942118000,
   "updateTime":1338942118000,
   "crUID":308,
   "upUID":308,
   "sid":84326,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "traitAlias":"123"
}
```

## Criar Mapeamentos de Destino em Massa {#bulk-create}

Um método `POST` que permite que você passe em uma matriz de [!UICONTROL cookie] ou [!UICONTROL URL] mapeamentos de destino.

<!-- r_bulk_create.xml -->

### Solicitação

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/bulk-create`

### Solicitação de exemplo

Todos os valores de solicitação são obrigatórios, a menos que seja indicado o contrário.

```
[
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
},
{
   "sid": 121070,
   "traitType":"SEGMENT",
   "url":"https://my.adobeconnect.com",
   "startDate":"2012-11-21"
}
]
```

### Resposta

Uma resposta bem-sucedida retorna a matriz de mapeamentos criados.

```
[
    {
        "mappingId": 103454,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Case of the Mondays",
        "elementDescription": "test",
        "elementStatus": "active",
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 105123,
        "startDate": "2012-11-19",
        "endDate": null,
        "priority": null,
        "url": "https://adobe.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    },
    {
        "mappingId": 103455,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "orderId": 780,
        "elementName": "Test Trait",
        "elementDescription": "This trait",
        "elementStatus": 1,
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 121070,
        "startDate": "2012-11-20",
        "endDate": null,
        "priority": null,
        "url": "https://my.adobeconnect.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    }
]
```

## Adicionar vários segmentos a um destino {#add-segments-dest}

Um método `POST` que permite mapear vários segmentos para um destino.

<!-- r_add_segments_to_destination.xml -->

### Solicitação

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`bulk-create`

### Solicitação de exemplo

Crie vários mapeamentos de destino em uma matriz. Todos os valores de solicitação são obrigatórios, a menos que seja indicado o contrário.

```
[
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
},
{
   "sid": 121070,
   "traitType":"SEGMENT",
   "url":"https://my.adobeconnect.com",
   "startDate":"2012-11-21"
}
]
```

### Resposta

Retorna uma matriz de mapeamentos criados.

```
[
    {
        "destinationMappingId": 103454,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Case of the Mondays",
        "elementDescription": "test",
        "elementStatus": "active",
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 105123,
        "startDate": "2012-11-19",
        "endDate": null,
        "priority": null,
        "url": "https://adobe.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    },
    {
        "traitToDataOrderId": 103455,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Test Trait",
        "elementDescription": "This trait",
        "elementStatus": 1,
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 121070,
        "startDate": "2012-11-20",
        "endDate": null,
        "priority": null,
        "url": "https://my.adobeconnect.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    }
]
```

## Atualizar uma ID de destino por destino {#update-dest-data-order}

Um método `PUT` que permite atualizar um destino existente por `destinationId`.

<!-- r_update_destination_data_order_id.xml -->

### Solicitação

`PUT https://api.demdex.com/v1/destinations/`*`<destinationId>`*

### Solicitação de exemplo

Todos os valores de solicitação são obrigatórios, a menos que seja indicado o contrário.

```
{
   "name":"Updated URL Destination (not serialized)",
   "description":"new description",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### Resposta

```
{
    "destinationType": "PUSH",
    "destinationId": 780,
    "dataSourceId": null,
    "pid": 1099,
    "name": "Updated URL Destination (not serialized)",
    "description": "new description",
    "startDate": null,
    "endDate": null,
    "status": 1,
    "createTime": 1348851790000,
    "updateTime": 1353372029000,
    "crUID": 884,
    "upUID": 1065,
    "domainRestrictions":"all_domains",
    "tagType": 0,
    "serializationEnabled": false,
    "urlFormatString": null,
    "secureUrlFormatString": null,
    "delimiter": null,
    "mappings": null
}
```

## Atualizar um mapeamento para um destino mapeando a ID {#update-mapping-dest-id}

Um método `PUT` que permite atualizar um mapeamento para um destino pelo `mappingId` especificado.

<!-- r_update_destination_trait_data_order_id.xml -->

### Solicitação

`PUT https://api.demdex.com/v1/destinations/mappings/`*`<mappingId>`*

### Solicitação de exemplo

Todos os valores de solicitação são obrigatórios, a menos que seja indicado o contrário.

```
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
}
```

### Resposta

```
{
    "mappingId": 103453,
    "traitType": "SEGMENT",
    "traitValue": 0,
    "destinationId": 780,
    "elementName": "sample",
    "elementDescription": "test",
    "elementStatus": "active",
    "createTime": 1353373005000,
    "updateTime": 1353373005000,
    "crUID": 1065,
    "upUID": 1065,
    "sid": 105123,
    "startDate": "2012-11-19",
    "endDate": null,
    "priority": null,
    "url": "https://www.adobe.com/send?%ALIAS%",
    "secureUrl": null,
    "tagCode": null,
    "secureTagCode": null,
    "traitAlias": null
}
```

>[!MORELIKETHIS]
>
>* [Destinos ](../../../features/destinations/destinations.md)
>* [Serialização do destino](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Explicação dos pares de valor-chave](../../../reference/key-value-pairs-explained.md)

