---
description: Os clientes do serviço de ID devem consultar esta seção para obter informações sobre como ler o cookie do visitante para as IDs necessárias para fazer chamadas de DCS API.
seo-description: ID service customers should refer to this section for information on how to read the visitor cookie for the IDs required to make DCS API calls.
seo-title: Get User IDs and Regions Through the Adobe Experience Platform Identity Service
solution: Audience Manager
title: Obter IDs de usuário e regiões por meio do Adobe Experience Platform Identity Service
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
exl-id: 0b855237-ac14-4c0e-b831-221b9218840f
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 6%

---

# Obter IDs de usuário e regiões por meio do Adobe Experience Platform Identity Service {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

Os clientes do serviço de ID devem consultar esta seção para obter informações sobre como ler o cookie do visitante para as IDs necessárias para fazer [!DNL DCS] Chamadas de API.

## Obter a ID de usuário do cookie do serviço de ID {#get-user-ids-from-service-cookie}

A variável [Serviço de identidade da Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html) O atribui IDs de visitante e região aos usuários que chegam ao site. Essas IDs identificam os usuários em todas as soluções da [!DNL Experience Cloud] e eles são necessários se você quiser fazer [!DNL DCS] chamadas.

* A variável [!UICONTROL user ID] O é necessário para identificar e associar dados a um visitante específico.
* A variável [!UICONTROL region ID] é necessário porque está vinculado a um nome de servidor regional, ao qual você precisa enviar dados para o [!DNL DCS]. A variável [!DNL DCS] O armazena informações em data centers geograficamente mais próximos dos visitantes do site. Consulte [IDs da região do DCS, locais e nomes de host](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

Os clientes do serviço de ID podem extrair essas informações do cookie do serviço de ID ou chamando uma função. A tabela abaixo descreve as tarefas ou etapas que você precisa concluir para começar.

Código no *itálico* representa um espaço reservado para variável.

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tarefa </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. Verifique o seu <span class="keyword"> Experience Cloud</span> status</b> </p> </td> 
   <td colname="col2"> <p>Você precisa de um <span class="keyword"> Experience Cloud</span> conta para usar o serviço de ID. Se você tiver uma <span class="keyword"> Experience Cloud</span> conta, ótimo! </p> <p> Se você não fizer parte do <span class="keyword"> Experience Cloud</span>, em seguida, inscreva-se. Adoraríamos tê-lo e sempre há espaço para mais. Para obter instruções sobre como configurar uma conta, consulte <a href="https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html" format="https" scope="external"> Ativação de suas soluções para os serviços principais</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Configurar o <span class="keyword"> Serviço de ID</span></b> </p> </td> 
   <td colname="col2"> <p>A variável <span class="keyword"> Serviço de ID</span> O consiste no código JavaScript que é colocado em cada página que você deseja usar para a coleta de dados do. Consulte o serviço de ID <a href="https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html" format="https" scope="external"> guias de implementação</a> para obter mais informações. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Leia o <span class="keyword"> Serviço de ID</span> cookie</b> </p> </td> 
   <td colname="col2"> <p>A variável <span class="keyword"> Serviço de ID</span> O armazena a ID do usuário e da região no cookie AMCV. O nome completo do cookie é <code>AMCV_<i>###</i>@AdobeOrg</code>. A variável <code><i>###</i></code> Os elementos do são espaços reservados para a ID da organização. Consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies e a ID do Experience Cloud</a> para obter detalhes. </p> <p>Analise o cookie AMCV para esses pares de valores chave: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>: esse par de valores chave contém a variável <span class="keyword"> Experience Cloud</span> ID de usuário. </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>: esse par de valores chave contém a ID da região (às vezes chamada de <span class="term"> dica de localização</span>) que está associado a um nome de servidor regional. </li> 
     </ul> </p> <p>Você pode fazer chamadas para a variável <span class="wintitle"> DCS</span> depois de ter as IDs de usuário e região. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Recuperar o <span class="keyword"> ID do Experience Cloud</span> com getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(Opcional)</i> Esta função retorna a variável <span class="keyword"> Experience Cloud</span> ID de visitante. Ele foi projetado para soluções personalizadas e casos de uso específicos. Consulte <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Trabalhar com getMarketingCloudVisitorID</a> abaixo e o <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> documentação do serviço de ID relacionado</a>. </p> <p>Não é necessário usar se você obter as IDs de usuário e de local do cookie do serviço de ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trabalhar com `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Outra maneira de obter a ID de visitante é com o `getMarketingCloudVisitorID` função. Quando invocada, essa função consulta o [!DNL ID service] e retorna uma ID. `getMarketingCloudVisitorID` aceita o opcional `callback` como mostrado:

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Uso e finalidade do retorno de chamada {#callback-usage}

`callback` é opcional. Essa função funciona sem ela, mas retorna uma ID somente quando um visitante tem uma [!DNL Experience Cloud] cookie no navegador. Se o cookie do visitante estiver ausente ou um visitante não tiver uma ID, a função retornará um cookie vazio `()` objeto. Isso pode acontecer mesmo depois que a página é carregada e o visitante recebe uma nova ID. Para evitar isso, `callback` força essa função para verificar uma ID de visitante depois que a página é carregada. Sem `callback`, a função de ID de visitante não retornará uma ID mesmo se ela for gravada no navegador do visitante posteriormente.

## Próximas etapas {#next-steps}

Depois de ter a ID do usuário e da região, você pode começar a enviar e receber [!DNL DCS] dados. Consulte [Como fazer chamadas de DCS API](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
