---
description: Os clientes do serviço de ID devem consultar esta seção para obter informações sobre como ler o cookie do visitante para as IDs necessárias para fazer chamadas de DCS API.
seo-description: Os clientes do serviço de ID devem consultar esta seção para obter informações sobre como ler o cookie do visitante para as IDs necessárias para fazer chamadas de DCS API.
seo-title: Obter IDs de usuário e regiões por meio do Adobe Experience Platform Identity Service
solution: Audience Manager
title: Obter IDs de usuário e regiões por meio do Adobe Experience Platform Identity Service
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
exl-id: 0b855237-ac14-4c0e-b831-221b9218840f
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 7%

---

# Obter IDs de usuário e regiões por meio do Adobe Experience Platform Identity Service {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

Os clientes do serviço de ID devem consultar esta seção para obter informações sobre como ler o cookie do visitante para as IDs necessárias para fazer chamadas de API [!DNL DCS].

## Obter a ID de usuário do cookie do serviço de ID {#get-user-ids-from-service-cookie}

O [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) atribui IDs de visitante e região a usuários que chegam ao seu site. Essas IDs identificam usuários em todas as soluções no [!DNL Experience Cloud] e são necessárias se você deseja fazer chamadas [!DNL DCS].

* O [!UICONTROL user ID] é necessário para identificar e associar dados a um visitante específico.
* O [!UICONTROL region ID] é necessário porque está vinculado a um nome de servidor regional, que você precisa enviar dados para o [!DNL DCS]. O [!DNL DCS] armazena informações em data centers que são geograficamente os mais próximos aos visitantes do site. Consulte [IDs da região do DCS, locais e nomes de host](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

Os clientes do serviço de ID podem extrair essas informações do cookie do serviço de ID ou chamando uma função. A tabela abaixo descreve as tarefas ou etapas que você precisa concluir para começar.

O código em *itálico* representa um espaço reservado de variável.

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tarefa </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. Verifique o status <span class="keyword"> Experience Cloud</span></b> </p> </td> 
   <td colname="col2"> <p>Você precisa de uma conta <span class="keyword"> Experience Cloud</span> para usar o serviço de ID. Se você tiver uma conta <span class="keyword"> Experience Cloud</span>, ótimo! </p> <p> Se você não fizer parte do <span class="keyword"> Experience Cloud</span>, inscreva-se. Adoraríamos ter você e sempre há espaço para mais. Para obter instruções sobre como configurar uma conta, consulte <a href="https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html" format="https" scope="external"> Ativando suas soluções para os serviços principais</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Configurar o <span class="keyword"> serviço de ID</span></b> </p> </td> 
   <td colname="col2"> <p>O <span class="keyword"> serviço de ID</span> consiste em um código JavaScript que é colocado em cada página que você deseja usar na coleta de dados. Consulte os guias de implementação <a href="https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html" format="https" scope="external"> do serviço de ID</a> para obter mais informações. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Leia o cookie <span class="keyword"> do serviço de ID</span></b> </p> </td> 
   <td colname="col2"> <p>O <span class="keyword"> serviço de ID</span> armazena a ID de usuário e de região no cookie AMCV. O nome completo do cookie é <code>AMCV_<i>###</i>@AdobeOrg</code>. Os elementos <code><i>###</i></code> são marcadores de posição da ID da organização. Consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies e o Experience Cloud ID</a> para obter detalhes. </p> <p>Analise o cookie AMCV para esses pares de valores chave: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>: Esse par de valores chave contém a  <span class="keyword"> Experience </span> Cloud ID. </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>: Esse par de valor-chave contém a ID de região (às vezes chamada de dica de  <span class="term"> localização</span>) que está associada a um nome de servidor regional. </li> 
     </ul> </p> <p>Você pode fazer chamadas para o <span class="wintitle"> DCS</span> depois de ter as IDs de usuário e região. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Recupere a <span class="keyword"> ID do Experience Cloud</span> com getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(Opcional)</i> Essa função retorna a ID de visitante da  <span class="keyword"> Experience </span> Cloud. Ele foi projetado para soluções personalizadas e casos de uso específicos. Consulte <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Trabalhar com getMarketingCloudVisitorID</a> abaixo e a <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> documentação do serviço de ID relacionado</a>. </p> <p>Não é necessário usar se você obter as IDs de usuário e de localização do cookie do serviço de ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trabalhar com `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Outra maneira de obter a ID de visitante é com a função `getMarketingCloudVisitorID` . Quando invocada, essa função consulta o [!DNL ID service] e retorna uma ID. `getMarketingCloudVisitorID` aceita o  `callback` argumento opcional como mostrado:

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Uso e finalidade do retorno de chamada {#callback-usage}

`callback` é opcional. Essa função funciona sem ela, mas retorna uma ID somente quando um visitante tem um cookie [!DNL Experience Cloud] em seu navegador. Se o cookie do visitante estiver ausente ou um visitante não tiver uma ID, a função retornará um objeto `()` vazio. Isso pode ocorrer mesmo depois que a página é carregada e o visitante recebe uma nova ID. Para evitar isso, `callback` força essa função a verificar uma ID de visitante depois que a página é carregada. Sem `callback`, a função de ID de visitante não retornará uma ID mesmo se ela for gravada no navegador do visitante posteriormente.

## Próximas etapas {#next-steps}

Depois de ter a ID do usuário e da região, você pode começar a enviar e receber dados [!DNL DCS]. Consulte [Efetuar chamadas de API DCS](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
