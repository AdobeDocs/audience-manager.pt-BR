---
description: Com as Regras de mesclagem de Perfis, você obtém controle sobre os conjuntos de dados usados para segmentação e pode público alvo uma pessoa com precisão em vários dispositivos.
seo-description: Com as Regras de mesclagem de Perfis, você obtém controle sobre os conjuntos de dados usados para segmentação e pode público alvo uma pessoa com precisão em vários dispositivos.
seo-title: Visão geral das regras de mesclagem de Perfis
solution: Audience Manager
title: Visão geral das regras de mesclagem de Perfis
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 2%

---


# Visão geral das regras de mesclagem de Perfis {#profile-merge-rules-overview}

Com [!UICONTROL Profile Merge Rules] você pode controlar quais conjuntos de dados são usados para segmentação e público alvo os usuários com precisão em vários dispositivos.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## Coleta e segmentação de dados com perfis anônimos e autenticados {#data-collection-targeting}

Normalmente, a segmentação e a segmentação de audiências dependem dos dados coletados de todos os usuários em um dispositivo. A coleta e a segmentação de dados com base em dados no nível do dispositivo apresenta algumas desvantagens. Por exemplo, não é possível distinguir entre vários usuários que compartilham um dispositivo ou usuários públicos alvos com precisão em vários dispositivos. A coleta de dados centralizada no dispositivo não é mais suficiente para campanhas de marketing digital ou direcionamento entre dispositivos.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] fundamentalmente altera a forma como [!DNL Audience Manager] coleta dados e segmentos de usuários para definição de metas. Ele permite que você trabalhe com dois tipos distintos de perfis, um perfil de dispositivo e um perfil [](../../reference/visitor-authentication-states.md)autenticado.

<table id="table_CE98C0E32A964B27804736A896233869"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de Perfil </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dispositivo perfil </td> 
   <td colname="col2"> <p>Um perfil de dispositivo está vinculado a uma ID de um determinado dispositivo, como uma ID de cookie ou uma ID de dispositivo móvel. O serviço inclui: </p> <p>
     <ul id="ul_0420875DE65E44FFAC76E0DD205CFEC4"> 
      <li id="li_044AD85C644A41FB8EF48164BAC0CE34">Características baseadas em regras realizadas quando um usuário não é autenticado. </li> 
      <li id="li_984D9790A6984139AFCFC2DFE4DF1BFC">Características integradas vinculadas a uma ID de dispositivo, como dados de terceiros baseados em cookies. </li>
     </ul> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> perfil autenticado </td> 
   <td colname="col2"> <p>O perfil autenticado está vinculado a uma ID de usuário transmitida quando uma pessoa faz logon no site. O serviço inclui </p>
    <ul id="ul_18319CAA875148DBAE095134D42637B3"> 
     <li id="li_E24BD33E049849E5A594B0750F530475">Características baseadas em regras coletadas em dispositivos quando um usuário é autenticado. </li>
     <li id="li_531AC9E0EC9D45108457FEC8E8D4E66C">Características integradas em um arquivo offline vinculado à mesma ID de usuário. </li>
    </ul> </td>
  </tr>
 </tbody>
</table>

Esses perfis diferentes controlam os dados que você pode usar para segmentação. Por exemplo, com um perfil [](../../reference/visitor-authentication-states.md)autenticado, você pode criar segmentos precisos com base em dados de vários dispositivos para um único usuário. Isso significa que você pode oferecer uma experiência consistente com a marca aos clientes em vários dispositivos. [!DNL Audience Manager] Isso é feito armazenando o mapeamento dos diferentes dispositivos que uma pessoa usa para suas atividades online em seu perfil [](../../reference/visitor-authentication-states.md)autenticado. Esses mapeamentos são chamados de [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Benefícios {#advantages}

Com [!UICONTROL Profile Merge Rules] você pode:

* Usuários do Público alvo com base em perfis [](../../reference/visitor-authentication-states.md)autenticados, perfis anônimos ou combinações de ambos.
* Público alvo um cliente específico em seus dispositivos.
* Crie um gráfico de dispositivos com base em dados determinísticos.
* Ajuste os dados em seus segmentos com base em perfis diferentes.
* Obtenha informações adicionais sobre a sua audiência.
