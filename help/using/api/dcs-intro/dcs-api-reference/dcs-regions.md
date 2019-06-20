---
description: O nome do host do servidor DCS regional é necessário para fazer chamadas para o DCS. Isso ocorre porque o DCS armazena informações em centros de dados que estão geograficamente próximos dos visitantes do site. Suas consultas funcionarão se você as envia para o DCS errado, mas essas chamadas são ineficientes e podem atrasar a resposta. Para fazer uma solicitação DCS, corresponda à ID da região correspondente ao nome de host regional correspondente e crie a sua consulta com o nome de host apropriado.
seo-description: O nome do host do servidor DCS regional é necessário para fazer chamadas para o DCS. Isso ocorre porque o DCS armazena informações em centros de dados que estão geograficamente próximos dos visitantes do site. Suas consultas funcionarão se você as envia para o DCS errado, mas essas chamadas são ineficientes e podem atrasar a resposta. Para fazer uma solicitação DCS, corresponda à ID da região correspondente ao nome de host regional correspondente e crie a sua consulta com o nome de host apropriado.
seo-title: IDs de região DCS, locais e nomes de host
solution: Audience Manager
title: IDs de região DCS, locais e nomes de host
uuid: ad 150 ffe -4583-472 b-ac 8 b-fb 900 a 7966 e 4
translation-type: tm+mt
source-git-commit: 51a326d0ac02175e0e1452e0a00b4a3a415d88ff

---


# DCS Region IDs, Locations, and Host Names {#dcs-region-ids-locations-and-host-names}

The regional [!UICONTROL DCS] server host name is required to make calls to the [!UICONTROL DCS]. This is because the [!UICONTROL DCS] stores information in data centers that are geographically close to site visitors. Your queries will work if you send them to the wrong [!UICONTROL DCS], but these calls are inefficient and can delay the response. To make a [!UICONTROL DCS] request, match the region ID to its corresponding regional host name and form your query with the proper host name.

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> DCS Region ID (dcs_ region) </th> 
   <th colname="col2" class="entry"> Região (e Local) </th> 
   <th colname="col3" class="entry"> Nome do host </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID3 </p> </td> 
   <td colname="col2"> <p>Sudeste Asiático (Singapura) </p> </td> 
   <td colname="col3"> <p> <code> apse. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID4 </p> </td> 
   <td colname="col2"> <p>América do Sul (São Paulo, Brasil) </p> </td> 
   <td colname="col3"> <p> <code> sae. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID6 </p> </td> 
   <td colname="col2"> <p>Europa (Dublin, Irlanda) </p> </td> 
   <td colname="col3"> <p> <code> irl 1. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID7 </p> </td> 
   <td colname="col2"> <p>Leste dos EUA (Virgínia, EUA) </p> </td> 
   <td colname="col3"> <p> <code> use. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID8 </p> </td> 
   <td colname="col2"> <p>Pacífico do Sul/Oceania (Sydney, Austrália) </p> </td> 
   <td colname="col3"> <p> <code> apse 2. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID9 </p> </td> 
   <td colname="col2"> <p>US West (Oregon, EUA) </p> </td> 
   <td colname="col3"> <p> <code> usw 2. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID11 </p> </td> 
   <td colname="col2"> <p>Ásia (Tóquio, Japão) </p> </td> 
   <td colname="col3"> <p> <code> tyo 3. demdex. net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID12 </p> </td> 
   <td colname="col2"> <p>Índia </p> </td> 
   <td colname="col3"> <p> <code> ind 1. demdex. net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

You can also use [!DNL API] methods to get a list of the available [!UICONTROL DCS] regions. See [DCS Region API Methods](../../../api/rest-api-main/aam-api-dcs-regions.md).