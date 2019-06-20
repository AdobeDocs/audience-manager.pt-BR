---
description: Aqui, no Audience Manager, nós engenheiros, desenvolvedores e código ninjas como você. E, como você, queremos trabalhar com a documentação confiável e precisa da API. Como resultado, regre o conteúdo da API no Swagger e movemos-o para um novo local. Essas alterações foram projetadas para ajudar a melhorar sua experiência com o código API do Audience Manager.
seo-description: Aqui, no Audience Manager, nós engenheiros, desenvolvedores e código ninjas como você. E, como você, queremos trabalhar com a documentação confiável e precisa da API. Como resultado, regre o conteúdo da API no Swagger e movemos-o para um novo local. Essas alterações foram projetadas para ajudar a melhorar sua experiência com o código API do Audience Manager.
seo-title: Migração de código API do Audience Manager
solution: Audience Manager
title: Migração de código API do Audience Manager
uuid: 93 cc 28 c 4-4 b 91-4 c 79-93 d 5-ece 9 bb 4 cc 9 d 5
translation-type: tm+mt
source-git-commit: d368699d0de9a43cb7cf2c1af64da941a811db71

---


# Audience Manager API Code Migration {#audience-manager-api-code-migration}

Aqui, no Audience Manager, nós engenheiros, desenvolvedores e código ninjas como você. And, like you, we want to work with reliable, accurate [!DNL API] documentation. As a result, we&#39;re re-writing our [!DNL API] content in [!DNL Swagger] and moving it to a new location. These changes are designed to help improve your experience with the Audience Manager [!DNL API] code.

## Movin&#39; On Up {#code-migration-details}

<!-- api-swagger-migration.xml -->

The [Adobe Audience Manager API Docs](https://bank.demdex.com/portal/swagger/index.html) site is the new home for our revised [!DNL API] content. We&#39;ll try to re-write and move a few sets of [!DNL API] methods with each release. This means you&#39;ll have to check in both the new location and the [REST API](../api/rest-api-main/rest-api-main.md) documentation to find all of the available methods. Eventually, all of the public [!DNL API]s will be on the [!DNL Audience Manager] [!DNL API] docs site. The following table lists the revised and migrated [!DNL API]s.

<table id="table_CD3C244CB02C48C898745FB982EC828C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de API </th> 
   <th colname="col2" class="entry"> Métodos de API </th> 
  </tr> 
 </thead>
 <tbody>
 <tr> 
   <td colname="col1"> <p> <b>Modelos algorítmicos</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Algorithmic_Models_API" format="https" scope="external"> Modelos algorítmicos</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audience Marketplace</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_4CFB3FAAC0B04E5AADD80E7D7FAF2722"> 
      <li id="li_50EE5F6B2278480E9FEA04AD51664F9D"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_API" format="https" scope="external"> Feeds de dados</a> </li> 
      <li id="li_5D372E3819014AB78C12048A9A2DC89F"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Request_API/" format="https" scope="external"> Solicitação do feed de dados</a> </li> 
      <li id="li_0582688D08C346C68B81D86A5C46E053"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Finance_API" format="https" scope="external"> Finanças do feed de dados</a> </li> 
      <li id="li_C1C1CB42D6A74803B4672F6EE2D2D08C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Plans_API" format="https" scope="external"> Planos de feed de dados</a> </li> 
      <li id="li_D8F9D791D0824287B9D0B0585E3106AB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Subscription_API" format="https" scope="external"> Assinaturas do feed de dados</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Fonte de dados</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Source_API" format="https" scope="external"> Fontes de dados</a> </p> </td> 
  </tr> 
   <td colname="col1"> <p> <b>Sinais derivados</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Derived_Signals_API" format="https" scope="external"> Sinais derivados</a> </p> </td> 
  </tr>   
  <tr> 
   <td colname="col1"> <p> <b>Pastas</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_FD05673B372141F3B0EF2C79A338F744"> 
      <li id="li_5D16FCAF6F0E411694A1CFBE9571BDAC"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Folder_API" format="https" scope="external"> Pastas de segmentos</a> </li> 
      <li id="li_5DC088C0F8CA4FC193248366C8400030"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Trait_Folder_API" scope="external" format="https"> Pastas de características</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Relatório</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Reporting_API" format="https" scope="external"> Relatório</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmentos</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_098B0655653D4846B70349A35A055C19"> 
      <li id="li_41A3003BF41147969BC88D4F12A5C1BB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segments_API" format="https" scope="external"> Segmentos</a> </li> 
      <li id="li_22A858D377634D88AE58BE2CE924169C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_API/" format="https" scope="external"> Grupos de teste de segmento</a> </li> 
      <li id="li_2B505A1B43CF4B29A0336106C321E7FD"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_Draft_API/" format="https" scope="external"> API de rascunho de grupo de teste de segmento</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Características</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Traits_API" format="https" scope="external"> Características</a> </p> </td> 
  </tr>
 </tbody>
</table>