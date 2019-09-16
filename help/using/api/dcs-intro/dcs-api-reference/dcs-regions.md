---
description: O nome do host do servidor DCS regional é necessário para fazer chamadas para o DCS. Isso ocorre porque o DCS armazena informações em data centers geograficamente próximos aos visitantes do site. Suas consultas funcionarão se você as enviar para o DCS errado, mas essas chamadas são ineficientes e podem atrasar a resposta. Para fazer uma solicitação DCS, corresponda a ID da região ao nome do host regional correspondente e forme a consulta com o nome do host apropriado.
seo-description: O nome do host do servidor DCS regional é necessário para fazer chamadas para o DCS. Isso ocorre porque o DCS armazena informações em data centers geograficamente próximos aos visitantes do site. Suas consultas funcionarão se você as enviar para o DCS errado, mas essas chamadas são ineficientes e podem atrasar a resposta. Para fazer uma solicitação DCS, corresponda a ID da região ao nome do host regional correspondente e forme a consulta com o nome do host apropriado.
seo-title: IDs de região DCS, locais e nomes de host
solution: Audience Manager
title: IDs de região DCS, locais e nomes de host
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
translation-type: tm+mt
source-git-commit: 51a326d0ac02175e0e1452e0a00b4a3a415d88ff

---


# DCS Region IDs, Locations, and Host Names {#dcs-region-ids-locations-and-host-names}

O nome do host do [!UICONTROL DCS] servidor regional é necessário para fazer chamadas para o [!UICONTROL DCS]. Isso ocorre porque o [!UICONTROL DCS] armazena informações em data centers geograficamente próximos aos visitantes do site. Suas consultas funcionarão se você enviá-las para o erro [!UICONTROL DCS], mas essas chamadas são ineficientes e podem atrasar a resposta. Para fazer uma [!UICONTROL DCS] solicitação, corresponda a ID da região ao nome do host regional correspondente e forme a consulta com o nome do host apropriado.

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID da região DCS (dcs_region) </th> 
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

Você também pode usar [!DNL API] métodos para obter uma lista das [!UICONTROL DCS] regiões disponíveis. Consulte Métodos [da API de região](../../../api/rest-api-main/aam-api-dcs-regions.md)DCS.