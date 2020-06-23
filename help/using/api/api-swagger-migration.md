---
description: Aqui na Audience Manager, somos engenheiros, desenvolvedores, e codificamos ninjas como você. E, como você, queremos trabalhar com documentação de API confiável e precisa. Como resultado, estamos reescrevendo nosso conteúdo de API no Swagger e movendo-o para um novo local. Essas alterações foram projetadas para ajudar a melhorar sua experiência com o código da API do Audience Manager.
seo-description: Aqui na Audience Manager, somos engenheiros, desenvolvedores, e codificamos ninjas como você. E, como você, queremos trabalhar com documentação de API confiável e precisa. Como resultado, estamos reescrevendo nosso conteúdo de API no Swagger e movendo-o para um novo local. Essas alterações foram projetadas para ajudar a melhorar sua experiência com o código da API do Audience Manager.
seo-title: Migração de código da API Audience Manager
solution: Audience Manager
title: Migração de código da API Audience Manager
uuid: 93cc28c4-4b91-4c79-93d5-ece9bb4cc9d5
translation-type: tm+mt
source-git-commit: 0869e016d7f80710cb194449c48675b82fdfa865
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 2%

---


# Audience Manager API Code Migration {#audience-manager-api-code-migration}

Aqui na Audience Manager, somos engenheiros, desenvolvedores, e codificamos ninjas como você. E, como vocês, queremos trabalhar com [!DNL API] documentação confiável e precisa. Como resultado, estamos reescrevendo nosso [!DNL API] conteúdo [!DNL Swagger] e movendo-o para um novo local. Essas alterações foram projetadas para ajudar a melhorar sua experiência com o código de Audience Manager [!DNL API] .

## Mover para cima {#code-migration-details}

<!-- api-swagger-migration.xml -->

O site de Documentos [da API do](https://bank.demdex.com/portal/swagger/index.html) Adobe Audience Manager é o novo lar para nosso [!DNL API] conteúdo revisado. Tentaremos reescrever e mover alguns conjuntos de [!DNL API] métodos a cada versão. Isso significa que você precisará verificar o novo local e a documentação da API [](../api/rest-api-main/rest-api-main.md) REST para encontrar todos os métodos disponíveis. Eventualmente, todo o público [!DNL API]estará no [!DNL Audience Manager] site de [!DNL API] documentos. A tabela a seguir lista os [!DNL API]s revisados e migrados.

<!--

<table id="table_CD3C244CB02C48C898745FB982EC828C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API Type </th> 
   <th colname="col2" class="entry"> API Methods </th> 
  </tr> 
 </thead>
 <tbody>
 <tr> 
   <td colname="col1"> <p> <b>Algorithmic Models</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Algorithmic_Models_API" format="https" scope="external"> Algorithmic Models</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audience Marketplace</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_4CFB3FAAC0B04E5AADD80E7D7FAF2722"> 
      <li id="li_50EE5F6B2278480E9FEA04AD51664F9D"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_API" format="https" scope="external"> Data Feeds</a> </li> 
      <li id="li_5D372E3819014AB78C12048A9A2DC89F"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Request_API/" format="https" scope="external"> Data Feed Request</a> </li> 
      <li id="li_0582688D08C346C68B81D86A5C46E053"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Finance_API" format="https" scope="external"> Data Feed Finance</a> </li> 
      <li id="li_C1C1CB42D6A74803B4672F6EE2D2D08C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Plans_API" format="https" scope="external"> Data Feed Plans</a> </li> 
      <li id="li_D8F9D791D0824287B9D0B0585E3106AB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Subscription_API" format="https" scope="external"> Data Feed Subscriptions</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Data Source</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Source_API" format="https" scope="external"> Data Sources</a> </p> </td> 
  </tr> 
   <td colname="col1"> <p> <b>Derived Signals</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Derived_Signals_API" format="https" scope="external"> Derived Signals</a> </p> </td> 
  </tr>   
  <tr> 
   <td colname="col1"> <p> <b>Folders</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_FD05673B372141F3B0EF2C79A338F744"> 
      <li id="li_5D16FCAF6F0E411694A1CFBE9571BDAC"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Folder_API" format="https" scope="external"> Segment Folders</a> </li> 
      <li id="li_5DC088C0F8CA4FC193248366C8400030"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Trait_Folder_API" scope="external" format="https"> Trait Folders</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Reporting</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Reporting_API" format="https" scope="external"> Reporting</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segments</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_098B0655653D4846B70349A35A055C19"> 
      <li id="li_41A3003BF41147969BC88D4F12A5C1BB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segments_API" format="https" scope="external"> Segments</a> </li> 
      <li id="li_22A858D377634D88AE58BE2CE924169C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_API/" format="https" scope="external"> Segment Test Groups</a> </li> 
      <li id="li_2B505A1B43CF4B29A0336106C321E7FD"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_Draft_API/" format="https" scope="external"> Segment Test Group Draft API</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Traits</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Traits_API" format="https" scope="external"> Traits</a> </p> </td> 
  </tr>
 </tbody>
</table>

-->


| Tipo de API | Métodos da API |
---------|----------
| **[!UICONTROL Algorithmic Models**] | [Modelos algorítmicos](https://bank.demdex.com/portal/swagger/index.html#/Algorithmic_Models_API) |
| **[!UICONTROL Audience Marketplace]** | <ul><li>[Feeds de dados](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Buyer%20API/get_available_data_feeds_)</li><li>[Solicitação de feed de dados](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Buyer%20API/post_available_data_feeds__dataSourceId__requests)</li><li>[Financiamento de feed de dados](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Finance%20API/get_data_feeds_billing_report)</li><li>[Planos de feed de dados](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Seller%20API/get_data_feeds__dataSourceId__plans_)</li><li>[Subscrições do feed de dados](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Seller%20API/get_data_feeds__dataSourceId__subscriptions)</li></ul> |
| **[!UICONTROL Data Sources]** | [Fontes de dados](https://bank.demdex.com/portal/swagger/index.html#/Data_Source_API) |
| **[!UICONTROL Folders]** | <ul><li>[Pastas de segmentos](https://bank.demdex.com/portal/swagger/index.html#/Segment_Folder_API)</li><li>[Pastas de características](https://bank.demdex.com/portal/swagger/index.html#/Trait%20Folder%20API)</li></ul> |
| **[!UICONTROL Reporting]** | [Relatórios](https://bank.demdex.com/portal/swagger/index.html#/Reporting%20API) |
| **[!UICONTROL Segments]** | <ul><li>[Segmentos](https://bank.demdex.com/portal/swagger/index.html#/Segments%20API)</li><li>[Grupos de teste de segmento](https://bank.demdex.com/portal/swagger/index.html#/Segment%20Test%20Group%20API)</li><li>[API de rascunho do grupo de teste de segmento](https://bank.demdex.com/portal/swagger/index.html#/Segment%20Test%20Group%20API/post_segment_test_groups_drafts)</li></ul> |
| **[!UICONTROL Traits]** | [Características](https://bank.demdex.com/portal/swagger/index.html#/Traits%20API) |