---
description: Um método GET que retorna o destino para o destinationId especificado.
seo-description: A GET method that returns the destination for the specified destinationId.
seo-title: Return A Destination by Destination ID
solution: Audience Manager
title: Retornar um destino por ID de destino
uuid: abce7426-55a5-4045-93a7-0487652a7189
feature: API
exl-id: c0850e71-7830-4635-b773-e9a28ab5bd68
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 7%

---

# Retornar um destino por ID de destino {#return-a-destination-by-destination-id}

A `GET` que retorna o destino para o item especificado `destinationId`.

<!-- r_get_all_destinations_order_id.xml -->

## Solicitação

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*

>[!NOTE]
>
>Para preencher o `mappings` campo de aprovação `includeMappings=true` no URL.

## Resposta

```
{
   "destinationType":"PUSH",
   "destinationId":314,
   "dataSourceId":null,
   "pid":1099,
   "name":"sample destination",
   "description":"Turn",
   "startDate":null,
   "endDate":null,
   "status":"active",
   "destinationType":"PUSH",
   "createTime":1281997484000,
   "updateTime":1300752888000,
   "crUID":224,
   "upUID":308,
   "domainRestrictions":"ALL_DOMAINS",
   "tagType":0,
   "serializationEnabled":false,
   "urlFormatString":null,
   "secureUrlFormatString":null,
   "delimiter":null,
   "mappings":null
}
```

## Retornar todos os destinos {#return-all-destinations}

A `GET` que retorna todos os destinos para o parceiro especificado.

<!-- r_get_all_destinations.xml -->

### Solicitação

`GET https://api.demdex.com/v1/destinations`

>[!NOTE]
>
>* *(Opcional)* Passar em `containsSegment=<sid>` para retornar uma matriz de todos os destinos mapeados para o segmento especificado. Por exemplo, sua query pode ser semelhante a esta: `GET .../destinations/?containsSegment=4321`.
>
>* Não retorna o objeto de destino completo. Obtenha o destino por ordem de dados se precisar de um objeto totalmente preenchido.


### Parâmetros de consulta opcionais

Você pode usar esses parâmetros opcionais com métodos de API que retornam *all* propriedades de um objeto. Defina essas opções na string de solicitação ao transmitir essa consulta para o [!DNL API]. Consulte [Parâmetros opcionais](../../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th>
   <th colname="col2" class="entry"> Descrição </th>
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"><code> page</code> </td>
   <td colname="col2"> Retorna resultados por número de página. A numeração começa em 0. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td>
   <td colname="col2"> Define o número de resultados de resposta retornados pela solicitação (10 é o padrão). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td>
   <td colname="col2">Classifica e retorna resultados de acordo com os valores especificados <span class="keyword"> JSON</span> propriedade. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> Classifica e retorna resultados em ordem decrescente. Crescente é o padrão. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">Retorna resultados com base na cadeia de caracteres especificada que você deseja usar como parâmetro de pesquisa. Por exemplo, digamos que você queira encontrar resultados para todos os modelos que têm a palavra "Teste" em qualquer um dos campos de valor para esse item. Seu exemplo de solicitação pode ser semelhante a: <p><code> GET https://api.demdex.com/v1/models/?search=Test</code>. </p> <p>Você pode pesquisar qualquer valor retornado por um método "get all". </p> </td>
  </tr>
 </tbody>
</table>

### Resposta

```
[
   {
      "destinationId":364,
      "pid":1099,
      "name":"Test",
      "description":"",
      "status":"active",
      "destinationType":"PUSH",
      "createTime":1291345192000,
      "updateTime":1291347561000,
      "crUID":262,
      "upUID":262,
      "domainRestrictions":"all_domains"
   },
   {
      "destinationId":369,
      "pid":1099,
      "name":"sample destination",
      "status":"active",
      "destinationType":"PUSH",
      "createTime":1292631706000,
      "updateTime":1292631706000,
      "crUID":262,
      "upUID":262,
      "domainRestrictions":"all_domains"
   }
]
```

## Retornar um mapeamento de destino com a ID de mapeamento {#return-dest-mapping-id}

A `GET` que retorna um mapeamento de destino individual com base na variável `mappingId`.

<!-- r_get_destination_trait_data_order.xml -->

### Solicitação

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`*`<destinationMappingId>`*

### Resposta

```
{
"mappingId": 14593,
"traitType": "SEGMENT",
"traitValue": 0,
"destinationId": 314,
"elementName": "sample",
"elementDescription": "Migration Pixel",
"elementStatus": "active",
"createTime": 1281997484000,
"updateTime": 1300752888000,
"crUID": 224,
"upUID": 308,
"sid": 80920,
"startDate": "2010-11-15",
"endDate": null,
"priority": null,
"url": "https://www.adobe.com/send?%ALIAS%",
"secureUrl": "https://www.adobe.com/send?%ALIAS%",
"tagCode": null,
"secureTagCode": null,
"traitAlias": null
}
```

## Mapeamentos de destino de retorno {#return-dest-mappings}

A `GET` método que retorna os mapeamentos para um destino.

<!-- r_get_destination_mappings.xml -->

>[!NOTE]
>
>O mapeamento retornado é específico para o tipo e a configuração de destino.

### Solicitação

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings`

>[!NOTE]
>
>Suporta parâmetros de paginação.

### Resposta

```
{
   "total":354,
   "page":0,
   "pageSize":2,
   "list":[
      {
         "destinationMappingId":14395,
         "traitType":"SEGMENT",
         "traitValue":0,
         "destinationId":314,
         "elementName":"sample pixel",
         "elementDescription":"Migration Pixel",
         "elementStatus":"active",
         "createTime":1281997484000,
         "updateTime":1300752888000,
         "crUID":224,
         "upUID":308,
         "sid":80920,
         "startDate":"2010-11-15",
         "endDate":null,
         "priority":null,
         "url":"https://www.adobe.com/send?%ALIAS%",
         "secureUrl":"https://www.adobe.com/send?%ALIAS%",
         "tagCode":null,
         "secureTagCode":null,
         "traitAlias":null
      }
      {
         "destinationMappingId":15934,
         "traitType":"SEGMENT",
         "traitValue":0,
         "destinationId":314,
         "elementName":"sample pixel",
         "elementDescription":"Migration Pixel",
         "elementStatus":"active",
         "createTime":1281997484000,
         "updateTime":1300752888000,
         "crUID":242,
         "upUID":803,
         "sid":90820,
         "startDate":"2010-11-15",
         "endDate":null,
         "priority":null,
         "url":"https://www.adobe.com/send?%ALIAS%",
         "secureUrl":"https://www.adobe.com/send?%ALIAS%",
         "tagCode":null,
         "secureTagCode":null,
         "traitAlias":null
      }
   ]
{
```

## Retornar todas as plataformas de destino disponíveis {#return-dest-platforms}

A `GET` que retorna todas as plataformas de dispositivo disponíveis para destinos.

<!-- r_get_dest_platforms.xml -->

### Solicitação

`GET /destinations/configurations/available-platforms/`

### Resposta

```
[
BROWSER, ANDROID, iOS, ALL
]
```

## Retornar Histórico de Trabalhos de Destino S2S e S2S em Massa {#return-job-history}

A `GET` método que retorna a saída [!UICONTROL Server-to-Server] ( [!UICONTROL S2S]) e em massa [!UICONTROL S2S] informações do histórico do trabalho de destino.

<!-- r_get_job_history.xml -->

### Solicitação

`GET https://api.demdex.com/v1/destinations/655/history/outbound?startDate=1000000000&endDate=1403034473000`

Parâmetros de consulta obrigatórios: `startDate` = *&lt;`epochtime`>* e `endDate` = *&lt;`epochtime`>*.

### Resposta

```
[
{
      "pushID":34090,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337292466000,
      "endTime":1337292466000,
      "dataFileName":"ftp_655_269_iter_1337229891903.sync",
      "success":true
   },
   {
      "pushID":34104,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337346397000,
      "endTime":1337346397000,
      "dataFileName":"ftp_655_269_iter_1337285714581.sync",
      "success":true
   },
   {
      "pushID":34124,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337396811000,
      "endTime":1337396812000,
      "dataFileName":"ftp_655_269_iter_1337338243600.sync",
      "success":true
   }
]
```
