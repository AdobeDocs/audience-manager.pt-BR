---
description: Um método de GET que retorna o destino para o targetId especificado.
seo-description: Um método de GET que retorna o destino para o targetId especificado.
seo-title: Retornar um destino por ID de destino
solution: Audience Manager
title: Retornar um destino por ID de destino
uuid: abce7426-55a5-4045-93a7-0487652a7189
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 9%

---


# Retornar um destino por ID de destino {#return-a-destination-by-destination-id}

Um método `GET` que retorna o destino para o `destinationId` especificado.

<!-- r_get_all_destinations_order_id.xml -->

## Solicitação

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*

>[!NOTE]
>
>Para preencher o campo `mappings` passe em `includeMappings=true` no URL.

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

Um método `GET` que retorna todos os destinos para o parceiro especificado.

<!-- r_get_all_destinations.xml -->

### Solicitação

`GET https://api.demdex.com/v1/destinations`

>[!NOTE]
>
>* *(Opcional)* Transmita  `containsSegment=<sid>` para retornar uma matriz de todos os destinos mapeados para o segmento especificado. Por exemplo, seu query pode ter uma aparência semelhante a esta: `GET .../destinations/?containsSegment=4321`.
   >
   >
* Não retorna o objeto de destino completo. Obtenha o destino por ordem de dados se precisar de um objeto totalmente preenchido.


### Parâmetros de Query opcionais

Você pode usar esses parâmetros opcionais com métodos de API que retornam *todas* as propriedades de um objeto. Defina essas opções na string de solicitação ao passar esse query para [!DNL API]. Consulte [Parâmetros Opcionais](../../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

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
   <td colname="col2"> Retorna os resultados por número de página. Numerando start em 0. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td>
   <td colname="col2"> Define o número de resultados de resposta retornados pela solicitação (10 é padrão). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td>
   <td colname="col2">Classifica e retorna os resultados de acordo com a propriedade <span class="keyword"> JSON</span> especificada. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> Classifica e retorna os resultados em ordem decrescente. Crescente é padrão. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">Retorna os resultados com base na string especificada que você deseja usar como parâmetro de pesquisa. Por exemplo, digamos que você queira encontrar resultados para todos os modelos que têm a palavra "Teste" em qualquer um dos campos de valor desse item. Sua solicitação de amostra pode ser semelhante a: <p><code> GET https://api.demdex.com/v1/models/?search=Test</code>. </p> <p>Você pode pesquisar qualquer valor retornado por um método "obter tudo". </p> </td>
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

Um método `GET` que retorna um mapeamento de destino individual com base em `mappingId`.

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

Um método `GET` que retorna os mapeamentos de um destino.

<!-- r_get_destination_mappings.xml -->

>[!NOTE]
>
>O mapeamento retornado é específico para o tipo de destino e a configuração.

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

## Devolver Todas as Plataformas de Destino Disponíveis {#return-dest-platforms}

Um método `GET` que retorna todas as plataformas de dispositivos disponíveis para destinos.

<!-- r_get_dest_platforms.xml -->

### Solicitação

`GET /destinations/configurations/available-platforms/`

### Resposta

```
[
BROWSER, ANDROID, iOS, ALL
]
```

## Devolver S2S e o Histórico de Tarefas de Destino S2S em Massa {#return-job-history}

Um método `GET` que retorna [!UICONTROL Server-to-Server] ( [!UICONTROL S2S]) e [!UICONTROL S2S] informações em massa do histórico de tarefas de destino.

<!-- r_get_job_history.xml -->

### Solicitação

`GET https://api.demdex.com/v1/destinations/655/history/outbound?startDate=1000000000&endDate=1403034473000`

Parâmetros de query necessários: `startDate` = *&lt;`epochtime`>* e `endDate` = *&lt;`epochtime`>*.

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
