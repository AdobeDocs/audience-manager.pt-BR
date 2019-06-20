---
description: Esta seção descreve como analisar uma resposta do DCS para recuperar as IDs de visitante e região necessárias para fazer chamadas em tempo real para o DCS.
seo-description: Esta seção descreve como analisar uma resposta do DCS para recuperar as IDs de visitante e região necessárias para fazer chamadas em tempo real para o DCS.
seo-title: Obter IDs de usuário e regiões de uma resposta DCS
solution: Audience Manager
title: Obter IDs de usuário e regiões de uma resposta DCS
uuid: 08036045-3 b 26-4 d 40-8 e 94-7 d 0884048683
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Get User IDs and Regions From a DCS Response {#get-user-ids-and-regions-from-a-dcs-response}

This section describes how to parse a [!UICONTROL DCS] response to retrieve the visitor and region IDs required to make real-time calls to the [!UICONTROL DCS].

## User and Region IDs {#user-region-ids}

[!UICONTROL DCS] Uma resposta contém dados sobre os visitantes do site. You need the visitor and region ID before you can make server-to-server calls to the [!UICONTROL DCS].

* A ID de usuário é necessária para identificar e associar dados a um visitante específico.
* The region ID is required because it is tied to a regional server name, which you need to send data to the [!UICONTROL DCS]. The [!UICONTROL DCS] stores information in data centers that are geographically closest to site visitors. Consulte [IDs da região do DCS, locais e nomes de host](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

Esses parâmetros estão descritos abaixo. Code in *italics* represents a variable placeholder.

<table id="table_822C02D5978348DCB7153001882D397C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Tipo de dados </th> 
   <th colname="col3" class="entry"> Exemplo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code>" uuid ": <i>ID de usuário</i></code></span> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p> <code> " uuid ": " 123456789 "</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>" dcs_ region ":<i>região da região</i></code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p> <code> " dcs_ region ": 9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Resposta de exemplo {#sample-response}

This simple response shows the `UUID` and region `ID`. Observação: isso é apenas dados de amostra. Seus arquivos de log podem ser maiores e mais complexos.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Próximas etapas {#next-steps}

Once you have the user ID and regional server name, you can start sending and receiving [!UICONTROL DCS] data. See [Making DCS API Calls](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
