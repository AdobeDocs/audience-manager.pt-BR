---
description: Os clientes do serviço de ID devem consultar esta seção para obter informações sobre como ler o cookie do visitante para as IDs necessárias para fazer chamadas de API DCS.
seo-description: Os clientes do serviço de ID devem consultar esta seção para obter informações sobre como ler o cookie do visitante para as IDs necessárias para fazer chamadas de API DCS.
seo-title: Obter IDs de usuário e regiões por meio do Adobe Experience Platform Identity Service
solution: Audience Manager
title: Obter IDs de usuário e regiões por meio do Adobe Experience Platform Identity Service
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 9%

---


# Obter IDs de usuário e regiões por meio do Adobe Experience Platform Identity Service {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

Os clientes do serviço de ID devem consultar esta seção para obter informações sobre como ler o cookie do visitante para as IDs necessárias para fazer chamadas de [!DNL DCS] API.

## Obter a ID do usuário do cookie do serviço de ID {#get-user-ids-from-service-cookie}

O Serviço [de identidade do](https://docs.adobe.com/content/help/en/id-service/using/home.html) Adobe Experience Platform atribui IDs de visitante e região a usuários que acessam seu site. Essas IDs identificam os usuários em todas as soluções no [!DNL Experience Cloud] e são necessárias se você deseja fazer [!DNL DCS] chamadas.

* O [!UICONTROL user ID] é necessário para identificar e associar dados a um determinado visitante.
* O [!UICONTROL region ID] é obrigatório porque está vinculado a um nome de servidor regional, que você precisa enviar dados para o [!DNL DCS]. O [!DNL DCS] armazena informações em data centers geograficamente mais próximos dos visitantes do site. Consulte [IDs da região do DCS, locais e nomes de host](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

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
   <td colname="col1"> <p> <b>1. Verifique o status do seu <span class="keyword"> Experience Cloud</span></b> </p> </td> 
   <td colname="col2"> <p>Você precisa de uma conta <span class="keyword"> Experience Cloud</span> para usar o serviço de ID. Se você tem uma conta <span class="keyword"> Experience Cloud</span> , ótimo! </p> <p> Se você não faz parte do <span class="keyword"> Experience Cloud</span>, então inscreva-se. Adoraríamos tê-lo e sempre há espaço para mais. Para obter instruções sobre como configurar uma conta, consulte <a href="https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html" format="https" scope="external"> Ativando suas soluções para os principais serviços</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Set up the <span class="keyword"> ID service</span></b> </p> </td> 
   <td colname="col2"> <p>O serviço <span class="keyword"> de</span> ID consiste no código JavaScript que é colocado em cada página que você deseja usar para a coleta de dados. Consulte os guias <a href="https://docs.adobe.com/content/help/en/id-service/using/implementation/implementation-guides.html" format="https" scope="external"></a> de implementação do serviço de ID para obter mais informações. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Ler o cookie do serviço <span class="keyword"></span> de ID</b> </p> </td> 
   <td colname="col2"> <p>O serviço <span class="keyword"> de</span> ID armazena a ID de usuário e região no cookie AMCV. O nome completo do cookie é <code>AMCV_<i>###</i>@AdobeOrg</code>. Os <code><i>###</i></code> elementos são espaços reservados para a ID da organização. See <a href="https://docs.adobe.com/content/help/pt-BR/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a> for details. </p> <p>Analise o cookie AMCV para estes pares de valores chave: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>: Esse par de valores chave contém a ID de usuário do <span class="keyword"> Experience Cloud</span> . </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>: Esse par de valor chave contém a ID da região (às vezes chamada de dica <span class="term"> de</span>localização) associada ao nome de um servidor regional. </li> 
     </ul> </p> <p>Você pode fazer chamadas para o <span class="wintitle"> DCS</span> depois de ter as IDs de usuário e região. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Recuperar a <span class="keyword"> ID</span> do Experience Cloud com getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(Opcional)</i> Essa função retorna a ID do visitante <span class="keyword"> Experience Cloud</span> . Ele foi projetado para soluções personalizadas e casos de uso específicos. Consulte <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Trabalhar com getMarketingCloudVisitorID</a> abaixo e a documentação <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> do serviço de ID</a>relacionado. </p> <p>Não é necessário usar isso se você obter as IDs de usuário e local do cookie do serviço de ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trabalhar com `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Outra maneira de obter a ID do visitante é com a `getMarketingCloudVisitorID` função. Quando invocada, essa função query o e retorna uma ID. [!DNL ID service] `getMarketingCloudVisitorID` aceita o `callback` argumento opcional como mostrado:

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Uso e finalidade do retorno de chamada {#callback-usage}

`callback` é opcional. Essa função funciona sem ela, mas retorna uma ID somente quando um visitante tem um [!DNL Experience Cloud] cookie em seu navegador. Se o cookie do visitante estiver ausente ou um visitante não tiver uma ID, a função retornará um `()` objeto vazio. Isso pode ocorrer mesmo depois que a página é carregada e o visitante recebe uma nova ID. Para evitar isso, `callback` força essa função a verificar uma ID de visitante depois que a página é carregada. Sem `callback`, a função de ID do visitante não retornará uma ID, mesmo se ela for gravada no navegador do visitante posteriormente.

## Próximas etapas {#next-steps}

Depois de ter a ID de usuário e região, você pode start enviando e recebendo [!DNL DCS] dados. Consulte [Efetuar chamadas](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)de API do DCS.