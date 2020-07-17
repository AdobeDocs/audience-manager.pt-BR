---
description: O nome do host do servidor DCS regional é necessário para fazer chamadas para o DCS. Isso ocorre porque o DCS armazena informações em data centers geograficamente próximos aos visitantes do site. Seus query funcionarão se você os enviar para o DCS errado, mas essas chamadas são ineficientes e podem atrasar a resposta. Para fazer uma solicitação DCS, corresponda a ID da região ao nome do host regional correspondente e forme o query com o nome do host apropriado.
seo-description: O nome do host do servidor DCS regional é necessário para fazer chamadas para o DCS. Isso ocorre porque o DCS armazena informações em data centers geograficamente próximos aos visitantes do site. Seus query funcionarão se você os enviar para o DCS errado, mas essas chamadas são ineficientes e podem atrasar a resposta. Para fazer uma solicitação DCS, corresponda a ID da região ao nome do host regional correspondente e forme o query com o nome do host apropriado.
seo-title: IDs da região do DCS, locais e nomes de host
solution: Audience Manager
title: IDs da região do DCS, locais e nomes de host
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 9%

---


# IDs da região do DCS, locais e nomes de host {#dcs-region-ids-locations-and-host-names}

O nome do host do [!DNL DCS] servidor regional é necessário para fazer chamadas para o [!DNL DCS]. Isso ocorre porque o [!DNL DCS] armazena informações em data centers geograficamente próximos aos visitantes do site. Seus query funcionarão se você enviá-los para o erro [!DNL DCS], mas essas chamadas são ineficientes e podem atrasar a resposta. Para fazer uma [!DNL DCS] solicitação, corresponda a ID da região ao nome do host regional correspondente e forme o query com o nome do host apropriado.

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID da região do DCS (dcs_region) </th> 
   <th colname="col2" class="entry"> Região (e local) </th> 
   <th colname="col3" class="entry"> Nome do host </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID3 </p> </td> 
   <td colname="col2"> <p>Sudeste Asiático (Cingapura) </p> </td> 
   <td colname="col3"> <p> <code> apse.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID4 </p> </td> 
   <td colname="col2"> <p>América do Sul (São Paulo, Brasil) </p> </td> 
   <td colname="col3"> <p> <code> sae.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID6 </p> </td> 
   <td colname="col2"> <p>Europa (Dublin, Irlanda) </p> </td> 
   <td colname="col3"> <p> <code> irl1.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID7 </p> </td> 
   <td colname="col2"> <p>Leste dos EUA (Virgínia, EUA) </p> </td> 
   <td colname="col3"> <p> <code> use.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID8 </p> </td> 
   <td colname="col2"> <p>Pacífico Sul/Oceânia (Sidney, Austrália) </p> </td> 
   <td colname="col3"> <p> <code> apse2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID9 </p> </td> 
   <td colname="col2"> <p>Oeste dos EUA (Oregon, EUA) </p> </td> 
   <td colname="col3"> <p> <code> usw2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID11 </p> </td> 
   <td colname="col2"> <p>Ásia (Tóquio, Japão) </p> </td> 
   <td colname="col3"> <p> <code> tyo3.demdex.net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID12 </p> </td> 
   <td colname="col2"> <p>Índia </p> </td> 
   <td colname="col3"> <p> <code> ind1.demdex.net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Você também pode usar [!DNL API] métodos para obter uma lista das [!DNL DCS] regiões disponíveis. See [DCS Region API Methods](../../../api/rest-api-main/aam-api-dcs-regions.md).