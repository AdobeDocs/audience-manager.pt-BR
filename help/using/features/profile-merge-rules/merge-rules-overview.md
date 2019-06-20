---
description: Com Regras de mesclagem de perfil, você obtém controle sobre os conjuntos de dados usados para segmentação e pode direcionar uma pessoa precisamente em vários dispositivos.
seo-description: Com Regras de mesclagem de perfil, você obtém controle sobre os conjuntos de dados usados para segmentação e pode direcionar uma pessoa precisamente em vários dispositivos.
seo-title: Visão geral das regras de mesclagem de perfil
solution: Audience Manager
title: Visão geral das regras de mesclagem de perfil
uuid: 9 e 7988 cc -9145-432 b -540 a -54 fbd 8657 b 3 b
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# Profile Merge Rules Overview {#profile-merge-rules-overview}

With [!UICONTROL Profile Merge Rules] you get control over the data sets used for segmentation and can target a person accurately across multiple devices.

## Data collection and targeting with anonymous and authenticated profiles {#data-collection-targeting}

Normalmente, a segmentação e o direcionamento de público dependem dos dados coletados de todos os usuários em um dispositivo. A coleta de dados e a definição de metas com base nos dados do nível do dispositivo apresentam algumas desvantagens. Por exemplo, não é possível distinguir entre vários usuários que compartilham um dispositivo ou direcionam com precisão os usuários em vários dispositivos. A coleta de dados centralizada por dispositivos não é mais suficiente para campanhas de marketing digital ou segmentação entre dispositivos.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] altera fundamentalmente o modo [!DNL Audience Manager] como coleta dados e segmentos para segmentação. Permite trabalhar com dois tipos distintos de perfis, um perfil de dispositivo e um perfil autenticado.

<table id="table_CE98C0E32A964B27804736A896233869"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de perfil </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dispositivo perfil </td> 
   <td colname="col2"> <p>Um perfil de dispositivo está vinculado a uma ID para um determinado dispositivo, como uma ID de cookie ou ID de dispositivo móvel. O serviço inclui: </p> <p>
     <ul id="ul_0420875DE65E44FFAC76E0DD205CFEC4"> 
      <li id="li_044AD85C644A41FB8EF48164BAC0CE34">As características baseadas em regras percebem quando um usuário não é autenticado. </li> 
      <li id="li_984D9790A6984139AFCFC2DFE4DF1BFC">Características integradas vinculadas a uma ID do dispositivo, como dados baseados em cookies, dados de terceiros. </li>
     </ul> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> Perfil autenticado </td> 
   <td colname="col2"> <p>O perfil autenticado é vinculado a uma ID de usuário passada quando uma pessoa faz logon em seu site. O serviço inclui </p>
    <ul id="ul_18319CAA875148DBAE095134D42637B3"> 
     <li id="li_E24BD33E049849E5A594B0750F530475">Características baseadas em regras coletadas em dispositivos quando um usuário é autenticado. </li>
     <li id="li_531AC9E0EC9D45108457FEC8E8D4E66C">Características incorporadas em um arquivo offline vinculado à mesma ID de usuário. </li>
    </ul> </td>
  </tr>
 </tbody>
</table>

Esses diferentes perfis controlam os dados que podem ser usados para segmentação. Por exemplo, com um perfil autenticado, você pode criar segmentos precisos com base em dados de vários dispositivos para uma única pessoa. Isso significa que você pode fornecer uma experiência de marca consistente para clientes em vários dispositivos. Additionally, cross-device authentication allows [!DNL Audience Manager] to map the different platforms a person uses for their online activities. This is called the [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Benefícios {#advantages}

With [!UICONTROL Profile Merge Rules] you can:

* Direcione usuários com base em perfis autenticados, perfis anônimos ou combinações de ambos.
* Direcione um cliente específico em seus dispositivos.
* Crie um gráfico de dispositivos com base em dados determinísticos.
* Ajuste os dados em seus segmentos com base em diferentes perfis.
* Obtenha mais insight sobre seu público-alvo.

## Introdução {#getting-started}

See the following sections and the [FAQ](../../faq/faq-profile-merge.md) for more information about [!UICONTROL Profile Merge Rules].

* [Introdução às regras de mesclagem de perfil](/help/using/features/profile-merge-rules/merge-rules-start.md)
* [Painel de regras de mesclagem de perfil](/help/using/features/profile-merge-rules/merge-rules-dashboard.md)
* [Opções de regra de mesclagem de perfil definidas](/help/using/features/profile-merge-rules/merge-rule-definitions.md)
* [Casos de uso geral para regras de mesclagem de perfil](/help/using/features/profile-merge-rules/merge-rule-targeting-options.md)
* [Casos de uso do gráfico de dispositivo de vinculação de perfil](/help/using/features/profile-merge-rules/profile-link-use-case.md)
* [Casos de uso do gráfico do dispositivo externo](/help/using/features/profile-merge-rules/external-graph-use-cases.md)
* [Métricas de relatório para Regras de mesclagem de perfil](/help/using/features/profile-merge-rules/profile-link-metrics.md)
* [Regras de mesclagem de perfil e processos de dessegmentação do dispositivo](/help/using/features/profile-merge-rules/merge-rule-unsegment.md)
* [Supressão instantânea entre dispositivos](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md)
* [Considerações importantes para Regras de mesclagem de perfil com gráficos de dispositivo](/help/using/features/profile-merge-rules/considerations-pmr-device-graph.md)
