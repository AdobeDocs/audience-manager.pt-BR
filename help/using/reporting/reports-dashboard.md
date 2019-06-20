---
description: Use o Painel para exibir informações sobre as contagens de visitantes únicos dos parceiros detalhadas por tipos de características e segmentos por um período especificado.
seo-description: Use o Painel para exibir informações sobre as contagens de visitantes únicos dos parceiros detalhadas por tipos de características e segmentos por um período especificado.
seo-title: Painel de relatórios
solution: Audience Manager
title: Painel de relatórios
uuid: 350 eee 2 d -72 f 7-42 a 7-916 b -60 f 9 a 362 c 5 cf
translation-type: tm+mt
source-git-commit: ad4721cd2ff1f4b2b7cb814cbafdef1f59138a26

---


# Reports Dashboard {#reports-dashboard}

Use o Painel para exibir informações sobre as contagens de visitantes únicos detalhadas por tipos de características e segmentos, por um período especificado.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] usa [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) para estender permissões de grupo do usuário para o [!UICONTROL Dashboard]. Os usuários podem ver apenas informações no painel que têm permissão para visualizar. [!UICONTROL RBAC] permite controlar quais equipes internas de dados de relatório podem exibir.

Por exemplo, uma agência que gerencia diferentes contas de anunciante pode configurar permissões de grupo do usuário para que uma equipe que gerencia a conta do anunciante A não possa ver os dados de relatório do anunciante B. Esse painel pode ser usado para solucionar problemas de entrega de dados.

Por exemplo, se você notar um declínio ou pico, no total de usuários únicos com o detalhamento do tipo de usuário exclusivo (baseado em regras vs. on-line com base em regras), você tem um ponto de partida melhor para rastrear um possível problema de entrega de dados. If you notice a dip in total unique users and in on-boarded unique users, you can go to the [!UICONTROL On-boarding Status] report to see if there was an issue with an inbound file.

**Para acessar o Painel:**

1. In the top navigation menu, click **[!UICONTROL Dashboard]**.
2. *Opcional* Selecione o intervalo de tempo desejado na última data do relatório na lista suspensa (7 dias, 14 dias (o padrão), 30 dias ou 60 dias).

   Depending on the period selected, the delta change in the [!UICONTROL Largest Traits] &gt; [!UICONTROL Most Changed Traits] and [!UICONTROL Largest Segments] &gt; [!UICONTROL Most Changed Segments] panels displays the change in unique visitors in the audience over the period ending today vs. the prior period of the same length. Por exemplo, se você selecionar 7 dias, o delta compara os visitantes únicos nos últimos sete dias terminando hoje em relação aos visitantes únicos dos sete dias terminando em sete dias atrás.

   >[!NOTE]
   >
   >You can investigate a delta change that seems out of the ordinary by running a [!UICONTROL Trend] report. For example, if you see an unusually large delta change during the last seven days, you could run a [!UICONTROL Trend] report for the last 14 days (2 x 7) to better understand the numbers.

   Dependendo das permissões do usuário conectado, os seguintes painéis são exibidos:

   * [Únicos do parceiro](../reporting/reports-dashboard.md#partner-uniques)
   * [Características maiores/mais alteradas](../reporting/reports-dashboard.md#largest-traits)
   * [Segmentos maiores/Segmentos mais alterados](../reporting/reports-dashboard.md#most-changed-segments)

3. *Clique opcional* **[!UICONTROL Normalize]** acima de qualquer gráfico para mostrar todos os dados na mesma escala. Você também pode passar o mouse sobre qualquer ponto de dados para ver mais informações.

## Partner Uniques {#partner-uniques}

Permission Required to View: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

Esse painel exibe o número de visitantes únicos durante o período especificado. As linhas individuais codificadas por cores representam o número total de visitantes únicos e o número de visitantes únicos capturados por meio de características algorítmicas, baseadas em regras e integrados.

>[!NOTE]
>
>O número total de visitantes únicos representa os visitantes capturados por meio de características baseadas em regras ou em termos internos. No entanto, o número total de visitantes únicos não é igual à soma dos visitantes únicos capturados por meio das características baseadas em regras e integrados. O mesmo usuário exclusivo pode ser representado em um desses dois tipos de características.

## Largest Traits/Most Changed Traits {#largest-traits}

Permission Required to View: [!UICONTROL View Traits].

![](assets/largest_traits.png)

Esse painel exibe o número de visitantes únicos capturados por diversos traços.

Use the **[!UICONTROL Show]** drop-down list to display information about different types of traits: [!UICONTROL All Traits], [!UICONTROL Algorithmic], [!UICONTROL Onboarded], or [!UICONTROL Rule-Based].

Esse painel contém as seguintes guias:

<table id="table_DA48BDEB4E0143BEA4EB85AC26FF6AE3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tabulação </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Maiores características</span> </p> </td> 
   <td colname="col2"> <p>Exibe informações sobre o número de visitantes únicos classificados por número (mais alto para o menor) e também lista a alteração delta de visitantes únicos durante o período especificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Características mais alteradas</span> </p> </td> 
   <td colname="col2"> <p>Exibe informações sobre o número de visitantes únicos classificados pela alteração delta. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Largest Segments/Most Changed Segments {#most-changed-segments}

Permission Required to View: [!UICONTROL View Segments].

![](assets/largest_segments.png)

Este painel exibe o número de visitantes únicos capturados por vários segmentos em tempo real.

Esse painel contém as seguintes guias:

<table id="table_8E22E0579FA74C5A86CC40B40B2548BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tabulação </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segmentos maiores</span> </p> </td> 
   <td colname="col2"> <p>Exibe informações sobre o número de visitantes únicos e a alteração delta de visitantes únicos durante o período especificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segmentos mais alterados</span> </p> </td> 
   <td colname="col2"> <p>Exibe informações sobre o número de visitantes únicos classificados pela alteração delta. </p> </td> 
  </tr> 
 </tbody> 
</table>

