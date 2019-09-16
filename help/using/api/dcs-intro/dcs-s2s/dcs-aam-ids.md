---
description: Esta seção descreve como analisar uma resposta DCS para recuperar as IDs de visitante e região necessárias para fazer chamadas em tempo real para o DCS.
seo-description: Esta seção descreve como analisar uma resposta DCS para recuperar as IDs de visitante e região necessárias para fazer chamadas em tempo real para o DCS.
seo-title: Obter IDs de usuário e regiões de uma resposta DCS
solution: Audience Manager
title: Obter IDs de usuário e regiões de uma resposta DCS
uuid: 08036045-3b26-4d40-8e94-7d0884048683
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Get User IDs and Regions From a DCS Response {#get-user-ids-and-regions-from-a-dcs-response}

Esta seção descreve como analisar uma [!UICONTROL DCS] resposta para recuperar as IDs de visitante e região necessárias para fazer chamadas em tempo real para o [!UICONTROL DCS].

## IDs de usuário e região {#user-region-ids}

Uma [!UICONTROL DCS] resposta contém dados sobre os visitantes do site. Você precisa da ID de visitante e de região antes de poder fazer chamadas de servidor para servidor para o [!UICONTROL DCS].

* A ID do usuário é necessária para identificar e associar dados a um visitante específico.
* A ID da região é necessária porque está vinculada a um nome de servidor regional, que você precisa enviar dados para o [!UICONTROL DCS]. O [!UICONTROL DCS] armazena informações em data centers geograficamente mais próximos dos visitantes do site. Consulte [IDs da região do DCS, locais e nomes de host](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

Esses parâmetros estão descritos abaixo. O código em *itálico* representa um espaço reservado variável.

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
   <td colname="col1"> <p><code>"uuid": ID <i>do usuário</i></code></span> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p> <code> "uuid":"123456789"</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>"dcs_region":ID da<i>região</i></code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p> <code> "dcs_region":9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Resposta de exemplo {#sample-response}

Essa resposta simples mostra a região `UUID` e a região `ID`. Observe que esses são dados de amostra apenas. Seus arquivos de registro podem ser mais longos e complexos.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Próximas etapas {#next-steps}

Depois de ter a ID de usuário e o nome do servidor regional, você pode começar a enviar e receber [!UICONTROL DCS] dados. Consulte [Efetuar chamadas](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)de API DCS.
