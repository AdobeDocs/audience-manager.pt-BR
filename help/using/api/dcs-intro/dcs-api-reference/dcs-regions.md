---
description: O nome de host do servidor DCS regional é necessário para fazer chamadas para o DCS. Isso ocorre porque o DCS armazena informações em data centers geograficamente próximos aos visitantes do site. Suas consultas funcionarão se você enviá-las para o DCS errado, mas essas chamadas são ineficientes e podem atrasar a resposta. Para fazer uma solicitação de DCS, associe a ID da região ao nome de host regional correspondente e forme sua query com o nome de host apropriado.
seo-description: The regional DCS server host name is required to make calls to the DCS. This is because the DCS stores information in data centers that are geographically close to site visitors. Your queries will work if you send them to the wrong DCS, but these calls are inefficient and can delay the response. To make a DCS request, match the region ID to its corresponding regional host name and form your query with the proper host name.
seo-title: DCS Region IDs, Locations, and Host Names
solution: Audience Manager
title: IDs da região do DCS, locais e nomes de host
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
feature: DCS
exl-id: 9b12946c-89f1-4f6f-adb9-961e15a0b816
TQID: https://experienceleague.adobe.com/1oK9TLEwbGO-6r9Hempmz8Al6AIYVFkdpKB-ya2UBWw
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2: id: d8f681b8-67cc-42dc-85c5-a0977528a942
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 234
ht-degree: 0%

---

# IDs da região do DCS, locais e nomes de host {#dcs-region-ids-locations-and-host-names}

O nome de host do servidor regional [!DNL DCS] é necessário para fazer chamadas para o [!DNL DCS]. Isso ocorre porque o [!DNL DCS] armazena informações em data centers geograficamente próximos aos visitantes do site. Suas consultas funcionarão se você enviá-las para o [!DNL DCS] errado, mas essas chamadas são ineficientes e podem atrasar a resposta. Para fazer uma solicitação [!DNL DCS], associe a ID da região ao nome de host regional correspondente e forme sua query com o nome de host apropriado.

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID da região do DCS (dcs_region) </th> 
   <th colname="col2" class="entry"> Região (e Local) </th> 
   <th colname="col3" class="entry"> Nome do host </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID 3 </p> </td> 
   <td colname="col2"> <p>Sudeste Asiático (Cingapura) </p> </td> 
   <td colname="col3"> <p> <code> apse.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 4 </p> </td> 
   <td colname="col2"> <p>América do Sul (São Paulo, Brasil) </p> </td> 
   <td colname="col3"> <p> <code> sae.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 6 </p> </td> 
   <td colname="col2"> <p>Europa (Dublin, Irlanda) </p> </td> 
   <td colname="col3"> <p> <code> irl1.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 7 </p> </td> 
   <td colname="col2"> <p>Leste dos EUA (Virgínia, EUA) </p> </td> 
   <td colname="col3"> <p> <code> use.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 8 </p> </td> 
   <td colname="col2"> <p>Pacífico Sul/Oceania (Sydney, Austrália) </p> </td> 
   <td colname="col3"> <p> <code> apse2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 9 </p> </td> 
   <td colname="col2"> <p>Oeste dos EUA (Oregon, EUA) </p> </td> 
   <td colname="col3"> <p> <code> usw2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 11 </p> </td> 
   <td colname="col2"> <p>Ásia (Tóquio, Japão) </p> </td> 
   <td colname="col3"> <p> <code> tyo3.demdex.net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID 12 </p> </td> 
   <td colname="col2"> <p>Índia </p> </td> 
   <td colname="col3"> <p> <code> ind1.demdex.net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Você também pode usar métodos [!DNL API] para obter uma lista das regiões [!DNL DCS] disponíveis. Consulte [Métodos de API da região DCS](../../../api/rest-api-main/aam-api-dcs-regions.md).
