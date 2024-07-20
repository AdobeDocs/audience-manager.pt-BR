---
description: Crie destinos com esses métodos de API RESTful.
seo-description: Create destinations with these RESTful API methods.
seo-title: Create Destinations
solution: Audience Manager
title: Criar destinos
uuid: 12f04151-ad0e-4cb6-8f3b-b5c427dc2cef
feature: API
exl-id: bae0f304-0ff3-4c5f-b432-19aef61d9d10
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 6%

---

# Criar destinos {#create-destinations}

Crie destinos com estes [!UICONTROL RESTful API] métodos.

<!-- c_create_destinations.xml -->

## Tipos de destino suportados: somente URL e cookie

Os métodos `POST` disponíveis permitem criar somente [!UICONTROL URL] e [!UICONTROL cookie destinations]. Atualmente, você não pode criar [!UICONTROL server-to-server destinations] com estes [!DNL REST API] métodos. No entanto, os métodos de destino `GET` relacionados permitem recuperar informações sobre [!UICONTROL server-to-server destinations] criadas na interface do usuário.

## Criar um destino de URL não serial {#create-nonserial-dest}

Um método `POST` que permite criar um destino que aceite segmentos compostos de pares de valores chave únicos (por exemplo, `gender=male` ou `gender=female`).

<!-- r_create_nonserial_destination.xml -->

### Solicitação

`POST https://api.demdex.com/v1/destinations/`

### Solicitação de exemplo

Esta solicitação cria um único destino. Todos os valores de solicitação são obrigatórios, salvo indicação contrária.

```
{ 
   "name":"Sample URL Destination (not serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### Resposta

Uma solicitação bem-sucedida retorna `201 created` e o destino.

```
{ 
   "destinationType":"PUSH", 
   "destinationId":4033, 
   "dataSourceId":null, 
   "pid":1099, 
   "name":"Sample URL Destination (not serialized)", 
   "description":"", 
   "startDate":null, 
   "endDate":null, 
   "status":"ACTIVE", 
   "destinationType":"PUSH", 
   "createTime":1338937116000, 
   "updateTime":1338937116000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "tagType":0, 
   "serializationEnabled":false, 
   "urlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "secureUrlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "delimiter":null,
   "mappings":null
} 
```

## Criar um destino de URL serializado {#create-serial-url-dest}

Um método `POST` que permite criar um destino que aceita vários valores associados a uma única chave (por exemplo, `color=blue, red, green`).

<!-- r_create_serial_url_destination.xml -->

### Solicitação

`POST https://api.demdex.com/v1/destinations/`

### Solicitação de exemplo

Especifique o [!DNL URL] e o delimitador seguros para o par de valores chave passado para o destino. Todos os valores de solicitação são obrigatórios, salvo indicação contrária.

```
{ 
   "name":"Sample URL Destination (Serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":true,
   "urlFormatString":"https://www.adobe.com/send?data=%ALIAS%",
   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%",
   "delimiter":","
}
```

### Resposta

Uma atualização bem-sucedida retorna o código de resposta `201 created` e o destino.

```
{ 
   "destinationType":"PUSH", 
   "destinationId":4034, 
   "dataSourceId":null, 
   "pid":1099, 
   "name":"Sample URL Destination (Serialized)", 
   "description":"", 
   "startDate":null, 
   "endDate":null, 
   "status":"active", 
   "destinationType":"PUSH", 
   "createTime":1338937420000, 
   "updateTime":1338937420000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "tagType":0, 
   "serializationEnabled":true, 
   "urlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%", 
   "delimiter":"-", 
   "mappings":null 
}
```

## Criar um destino de cookie: chave única, não serializado {#create-cookie-dest-single}

Um método `POST` que permite criar um [!UICONTROL cookie destination] que aceita segmentos compostos de pares de valor-chave únicos (por exemplo, `gender=male` ou `gender=female`).

<!-- r_cookie_destination_singlekey_noserial.xml -->

### Solicitação

`POST https://api.demdex.com/v1/destinations/`

### Solicitação de exemplo

Todos os valores de solicitação são obrigatórios, salvo indicação contrária.

```
{ 
   "name":"Cookie Destination Single Key Not Serialized",
   "destinationType":"ADS",
   "adServerTypeID":1,
   "cookieName":"adobe",
   "cnameDomain":"adobe.com",
   "maxSize":"2048",
   "ttl":"0",
   "domainRestrictions":"inclusion",
   "siteIDs":[
      312
   ],
   "formatType":"single_key",
   "singleKey":"key",
   "keySeparator":"=",
   "valueSeparator":",",
   "serializationEnabled":false
}
```

### Resposta

Uma atualização bem-sucedida retorna o código de resposta `201 created` e o destino.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4035, 
   "pid":1099, 
   "name":"Cookie Destination Single Key Not Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338937984000, 
   "updateTime":1338937984000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"inclusion", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "singleKey":"key", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"single_key", 
   "transferMethod":0, 
   "serializationEnabled":false, 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
      312 
   ], 
   "uparamEnabled":false
} 
```

## Criar um destino de cookie: chave única, serializado {#create-cookie-dest-single-serial}

Um método `POST` que permite criar um destino que aceita vários valores associados a uma única chave (por exemplo, `color=blue, red, green`).

<!-- r_cookie_destination_singlekey_serial.xml -->

### Solicitação

`POST https://api.demdex.com/v1/destinations/`

### Solicitação de exemplo

Todos os valores de solicitação são obrigatórios, salvo indicação contrária.

```
{ 
   "name":"Cookie Destination Single Key Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
 
   ], 
   "formatType":"single_key", 
   "singleKey":"k", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":true, 
   "serializationSeparator":"#" 
}
```

### Resposta

Uma atualização bem-sucedida retorna o código de resposta `201 created` e o destino.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4036, 
   "pid":1099, 
   "name":"Cookie Destination Single Key Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338938329000, 
   "updateTime":1338938329000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "singleKey":"k", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"single_key", 
   "transferMethod":0, 
   "serializationEnabled":true, 
   "serializationSeparator":"#", 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
 
   ], 
   "uparamEnabled":false
}
```

## Criar um destino de cookie: várias chaves, não serializado {#create-cookie-dest-multi}

Um método `POST` que permite criar um destino que aceita segmentos que contêm várias chaves com valores diferentes (por exemplo, `gender=male; gender=female; color=blue; color=red`).

<!-- r_create_cookie_multikey_noserial.xml -->

### Solicitação

`POST https://api.demdex.com/v1/destinations/`

### Solicitação de exemplo

Todos os valores de solicitação são obrigatórios, salvo indicação contrária.

```
{ 
   "name":"Ad Server Multi-Key Not Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
  
   ], 
   "formatType":"key_value", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":false 
}
```

### Resposta

Uma atualização bem-sucedida retorna o código de resposta `201 created` e o destino.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4037, 
   "pid":1099, 
   "name":"Ad Server Multi-Key Not Serialized", 
   "status":1, 
   "destinationType":"ADS", 
   "createTime":1338938666000, 
   "updateTime":1338938666000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"key_value", 
   "transferMethod":0, 
   "serializationEnabled":false, 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
  
   ], 
   "uparamEnabled":false 
}
```

## Criar um destino de cookie: multichave, serializado {#create-cookie-dest-multi-serial}

Um método `POST` que permite criar um destino que aceita segmentos que contêm várias chaves e valores (por exemplo, `gender=male, female; color=blue, red, green`).

<!-- r_cookie_destination_multikey_serial.xml -->

### Solicitação

`POST https://api.demdex.com/v1/destinations/`

### Solicitação de exemplo

Todos os valores de solicitação são obrigatórios, salvo indicação contrária.

```
{ 
   "name":"Cookie Destination Multi-Key Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains",
   "siteIDs":[ 
 
   ], 
   "formatType":"key_value", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":true, 
   "serializationSeparator":"#" 
}
```

### Resposta

Uma atualização bem-sucedida retorna o código de resposta `201 created` e o destino.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4038, 
   "pid":1099, 
   "name":"Ad Server Multi-Key Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338938872000, 
   "updateTime":1338938872000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"key_value", 
   "transferMethod":0, 
   "serializationEnabled":true, 
   "serializationSeparator":"#", 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
 
   ], 
   "uparamEnabled":false 
}
```

>[!MORELIKETHIS]
>
>* [Destinos](../../../features/destinations/destinations.md)
>* [Serialização de Destino](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Explicação dos pares de valor-chave](../../../reference/key-value-pairs-explained.md)
