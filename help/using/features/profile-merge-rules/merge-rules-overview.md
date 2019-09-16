---
description: Com as Regras de mesclagem de perfil, você obtém controle sobre os conjuntos de dados usados para segmentação e pode direcionar uma pessoa com precisão em vários dispositivos.
seo-description: Com as Regras de mesclagem de perfil, você obtém controle sobre os conjuntos de dados usados para segmentação e pode direcionar uma pessoa com precisão em vários dispositivos.
seo-title: Visão geral das regras de mesclagem de perfil
solution: Audience Manager
title: Visão geral das regras de mesclagem de perfil
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# Visão geral das regras de mesclagem de perfil {#profile-merge-rules-overview}

Com [!UICONTROL Profile Merge Rules] você obtém controle sobre os conjuntos de dados usados para segmentação e pode direcionar uma pessoa com precisão em vários dispositivos.

## Coleta e direcionamento de dados com perfis anônimos e autenticados {#data-collection-targeting}

Normalmente, a segmentação e a segmentação do público-alvo dependem dos dados coletados de todos os usuários em um dispositivo. A coleta e a segmentação de dados com base em dados no nível do dispositivo apresenta algumas desvantagens. Por exemplo, não é possível distinguir entre vários usuários que compartilham um dispositivo ou direcionam precisamente usuários em vários dispositivos. A coleta de dados centralizada no dispositivo não é mais suficiente para campanhas de marketing digital ou direcionamento entre dispositivos.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] fundamentalmente altera a forma como [!DNL Audience Manager] coleta dados e segmentos de usuários para definição de metas. Ele permite que você trabalhe com dois tipos distintos de perfis, um perfil de dispositivo e um perfil autenticado.

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
   <td colname="col2"> <p>Um perfil de dispositivo está vinculado a uma ID de um determinado dispositivo, como uma ID de cookie ou uma ID de dispositivo móvel. O serviço inclui: </p> <p>
     <ul id="ul_0420875DE65E44FFAC76E0DD205CFEC4"> 
      <li id="li_044AD85C644A41FB8EF48164BAC0CE34">Características baseadas em regras realizadas quando um usuário não é autenticado. </li> 
      <li id="li_984D9790A6984139AFCFC2DFE4DF1BFC">Características integradas vinculadas a uma ID de dispositivo, como dados de terceiros baseados em cookies. </li>
     </ul> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> Perfil autenticado </td> 
   <td colname="col2"> <p>O perfil autenticado é vinculado a uma ID de usuário transmitida quando uma pessoa faz logon no site. O serviço inclui </p>
    <ul id="ul_18319CAA875148DBAE095134D42637B3"> 
     <li id="li_E24BD33E049849E5A594B0750F530475">Características baseadas em regras coletadas em dispositivos quando um usuário é autenticado. </li>
     <li id="li_531AC9E0EC9D45108457FEC8E8D4E66C">Características integradas em um arquivo offline vinculado à mesma ID de usuário. </li>
    </ul> </td>
  </tr>
 </tbody>
</table>

Esses perfis diferentes controlam os dados que você pode usar para segmentação. Por exemplo, com um perfil autenticado, você pode criar segmentos precisos com base em dados de vários dispositivos para uma única pessoa. Isso significa que você pode oferecer uma experiência consistente com a marca aos clientes em vários dispositivos. Além disso, a autenticação entre dispositivos permite [!DNL Audience Manager] mapear as diferentes plataformas que uma pessoa usa para suas atividades online. Isso se chama [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Benefícios {#advantages}

Com [!UICONTROL Profile Merge Rules] você pode:

* Direcione usuários com base em perfis autenticados, perfis anônimos ou combinações de ambos.
* Direcione um cliente específico em seus dispositivos.
* Crie um gráfico de dispositivos com base em dados determinísticos.
* Ajuste os dados em seus segmentos com base em diferentes perfis.
* Obtenha informações adicionais sobre o seu público-alvo.

## Introdução {#getting-started}

Consulte as seções a seguir e as [Perguntas frequentes](../../faq/faq-profile-merge.md) para obter mais informações sobre [!UICONTROL Profile Merge Rules].

* [Introdução às regras de mesclagem de perfil](/help/using/features/profile-merge-rules/merge-rules-start.md)
* [Painel Regras de mesclagem de perfil](/help/using/features/profile-merge-rules/merge-rules-dashboard.md)
* [Definição das opções de regra de mesclagem de perfil](/help/using/features/profile-merge-rules/merge-rule-definitions.md)
* [Casos de uso gerais para regras de mesclagem de perfil](/help/using/features/profile-merge-rules/merge-rule-targeting-options.md)
* [Casos de uso do gráfico de dispositivo de link de perfil](/help/using/features/profile-merge-rules/profile-link-use-case.md)
* [Casos de uso do gráfico do dispositivo externo](/help/using/features/profile-merge-rules/external-graph-use-cases.md)
* [Métricas de relatório para regras de mesclagem de perfil](/help/using/features/profile-merge-rules/profile-link-metrics.md)
* [Regras de mesclagem de perfil e processos de dessegmentação de dispositivo](/help/using/features/profile-merge-rules/merge-rule-unsegment.md)
* [Supressão instantânea entre dispositivos](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md)
* [Considerações importantes para regras de mesclagem de perfil com gráficos de dispositivo](/help/using/features/profile-merge-rules/considerations-pmr-device-graph.md)
