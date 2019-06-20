---
description: Recomendações e casos de uso para prospecção, redefinição de metas e personalização de usuários desconhecidos com um gráfico de dispositivo externo. Um gráfico de dispositivo externo é definido como um gráfico de dispositivos separado do Audience Manager. Isso inclui o Device Co-op da Adobe Experience Cloud e outras integrações que a Adobe possui com empresas determinísticos determinísticos ou determinionais de dispositivos.
seo-description: Recomendações e casos de uso para prospecção, redefinição de metas e personalização de usuários desconhecidos com um gráfico de dispositivo externo. Um gráfico de dispositivo externo é definido como um gráfico de dispositivos separado do Audience Manager. Isso inclui o Device Co-op da Adobe Experience Cloud e outras integrações que a Adobe possui com empresas determinísticos determinísticos ou determinionais de dispositivos.
seo-title: Casos de uso do gráfico do dispositivo externo
solution: Audience Manager
title: Casos de uso do gráfico do dispositivo externo
uuid: f 4 bc 822 d -39 d 2-4680-90 ed -7 ee 2 ead 6 db 6 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Casos de uso do gráfico do dispositivo externo {#external-device-graph-use-cases}

Recomendações e casos de uso para prospecção, redefinição de metas e personalização de usuários desconhecidos com um gráfico de dispositivo externo. Um gráfico de dispositivo externo é definido como um gráfico de dispositivos separado do Audience Manager. This includes the [!DNL Adobe Experience Cloud Device Co-op] and other integrations Adobe has with third-party deterministic or probabilistic device graph companies.

## Recomendações {#recommendations}

Consider the [!DNL Experience Cloud Device Co-op] and third-party device graph options for campaigns that:

* Tenha um nível baixo de autenticação em suas propriedades digitais. Use the [Profile Link device graph option](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) if you have a large number of authenticated users.
* Direcione públicos grandes. The [!DNL Experience Cloud Device Co-op] and third-party device graphs contain authenticated and un-authenticated data.
* Segmentação de visitantes autenticados e/ou não autenticados no nível individual e doméstico.

![](assets/merge-rule-triangle1.png)

## Prospecting/Branding Use Case {#prospecting-branding-use-cases}

Uma campanha de marca foi projetada para atingir o maior número de pessoas possível. Ela coloca alguns limites na qualificação de segmentos. Contudo, essas campanhas podem desperdiçar orçamento e impressões ao direcionar constantemente as pessoas que veem seu conteúdo várias vezes e não convertem. A [!UICONTROL Profile Merge] rule that uses the [!DNL Device Co-op] or third-party option can help you create an efficient branding campaign. Por exemplo, você pode adicionar esses usuários desconhecidos a um segmento &quot;não mercado&quot; depois de visualizá-los em vários dispositivos para o cap de frequência definido.

<table id="table_00F6EED172574E80A38CADA8A92A23B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso de uso </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Condições</b> </p> </td> 
   <td colname="col2">Esse caso de uso pressupõe estas condições: <p> 
     <ul id="ul_F5CA7EE525774F7EBA5FBB5F94E4EDC8"> 
      <li id="li_81AE304924724146A24FAB5B6533AD8E">Você deseja fornecer um máximo de 10 impressões para um usuário anônimo para uma campanha de anúncio específica. </li> 
      <li id="li_E371F989735245B0B82433DE240D56D0">Um usuário tem vários dispositivos e pode ou não ter sido autenticado no site. </li> 
      <li id="li_9231ABE15CA249E6B79D8BF0E511FD33">Um usuário anônimo vê o anúncio um total de 10 vezes ao navegar em um estado não autenticado em seu dispositivo atual e até 3 dispositivos vinculados por um gráfico de dispositivo externo. </li> 
      <li id="li_8C276C07019C49EFA3A0D0D54CF73C31">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify anonymous users after they have seen 10 impressions. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_8E988B1005324526BC6DC6637BBACCFB"> 
      <li id="li_C9DD546754914BACB8F4C92C7D4ED70E">Une a atividade anônima e não autenticada coletada do dispositivo atual e dos 3 dispositivos vinculados pelo gráfico de dispositivo externo (as impressões de anúncio de cada dispositivo). </li> 
      <li id="li_FB55CB9116074525BA30FF062D1136AE">Avalia o usuário não autenticado para a qualificação de segmento com base em uma combinação de atividades anônimas em todos os 3 dispositivos vinculados pelo gráfico de dispositivo externo e pelo dispositivo atual. </li> 
      <li id="li_B28EB32F718145A7ABBDAC0AF75E2AFC">Envia o segmento para qualquer destino em tempo real para uso como um segmento de exclusão no dispositivo atual e em todos os 3 dispositivos vinculados pelo gráfico de dispositivo externo. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Retargeting or Site Personalization Use Case {#retargeting-use-case}

Essas estratégias foram projetadas para trazer um usuário não autenticado ou desconhecido de volta para o site ou personalizar sua experiência de navegação enquanto estiverem no site.

<table id="table_0EE2052AA3E744B3B76036FC06B5A453"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso de uso </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Condições</b> </p> </td> 
   <td colname="col2">Esse caso de uso pressupõe estas condições: <p> 
     <ul id="ul_FD0B869B4AF3453FAEC9BA3A45ABF039"> 
      <li id="li_8E30BAED42E94AB3B81FCB1C7464E5FC">Você deseja fornecer uma experiência personalizada e/ou fora do site a um usuário anônimo com base em sua atividade no site, enquanto em um estado não autenticado. </li> 
      <li id="li_3DBE53BA94324F1BA1C52A37AD4E426C">Um usuário tem vários dispositivos e pode ou não ter sido autenticado no site. </li> 
      <li id="li_F867AFBDC1A54CD6A68AB0EC196E27C9">Um usuário exibe várias páginas do site ao navegar em um estado não autenticado em seu dispositivo atual e em até 3 dispositivos vinculados por um gráfico de dispositivo externo. </li> 
      <li id="li_7E35D77949CE4E69BD51655AA4C40BEE">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify users after they have viewed multiple pages on your site while browsing in an unauthenticated state. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="wintitle"> Audience Manager</span>: </p> <p> 
     <ul id="ul_301339426B0643B295DC5B17E1939CFB"> 
      <li id="li_7E8BC3B179804F4A929497DE81E76911">Une a atividade anônima e não autenticada coletada dos dispositivos atuais e dos 3 dispositivos vinculados pelo gráfico de dispositivo externo (as várias exibições de página de cada dispositivo). </li> 
      <li id="li_803EFD58AA124A5BBC8279C4DC695544">Avalia o usuário não autenticado para a qualificação de segmento com base em uma combinação de atividades anônimas em todos os 3 dispositivos vinculados pelo gráfico de dispositivo externo e pelo dispositivo atual. </li> 
      <li id="li_98D749268CC5456CBC9CF3BF5EB91BA8">Envia o segmento para qualquer destino em tempo real para fornecer uma experiência personalizada no site e/ou fora do site, no dispositivo atual e em todos os 3 dispositivos vinculados pelo gráfico de dispositivos externos. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

## Profile Merge Rule Options for External Device Graph Use Cases {#profile-merge}

As opções de regra de mesclagem para esses casos de uso seriam parecidas com as opções disponíveis mostradas abaixo. [!UICONTROL Authenticated Profile] As opções são desativadas porque essas configurações só estão disponíveis quando você seleciona **[!UICONTROL Current Authenticated Profile]** ou **[!UICONTROL Last Authenticated Profile]**. Your [!UICONTROL Device Options] will vary depending on the type of device graph setting that you want to use or that is available to you.

![](assets/merge-rules-external.png)

For more information about how these device graph processes work, download our PDF, [Audience Manager and External Device Graphs](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf).

>[!MORE_ LIKE_ THIS]
>
>* [Casos de uso do gráfico de dispositivo de vinculação de perfil](../../features/profile-merge-rules/profile-link-use-case.md)
>* [Casos de uso geral para regras de mesclagem de perfil](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [Perguntas frequentes sobre regras de mesclagem de perfil](../../faq/faq-profile-merge.md)

