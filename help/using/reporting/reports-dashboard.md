---
description: Use o Painel para exibir informações sobre as contagens de visitantes únicos de seus parceiros detalhadas por tipos de características e segmentos para um intervalo de tempo especificado.
seo-description: Use the Dashboard to view information about your partners' unique visitor counts broken down by trait types and segments for a specified time frame.
seo-title: Reports Dashboard
solution: Audience Manager
title: Painel de relatórios
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
feature: Reporting Reference
exl-id: 1ca0280a-d67b-46f7-9c58-effc5be4e38f
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 0%

---

# Painel de relatórios {#reports-dashboard}

Use o Painel para exibir informações sobre a contagem de visitantes únicos detalhadas por tipos de características e segmentos, para um intervalo de tempo especificado.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] usa [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) para estender permissões de grupo de usuários para [!UICONTROL Dashboard]. Os usuários podem ver somente as informações no painel que têm permissões para visualizar. A funcionalidade [!UICONTROL RBAC] permite controlar quais dados de relatório as equipes internas podem exibir.

Por exemplo, uma agência que gerencia diferentes contas de anunciante pode configurar permissões de grupo de usuários para que uma equipe que gerencia a conta do Anunciante A não possa ver os dados de relatório do Anunciante B. Esse painel pode ser usado para solucionar problemas de entrega de dados.

Por exemplo, se você notar uma queda, ou pico, no total de usuários únicos com o detalhamento do tipo de usuário único (com base em regras versus integrado), você tem um ponto de partida melhor para rastrear um possível problema de entrega de dados. Se você observar uma queda no total de usuários únicos e nos usuários únicos integrados, poderá ir para o relatório [!UICONTROL On-boarding Status] para ver se houve um problema com um arquivo de entrada.

**Para acessar o Painel:**

1. No menu de navegação superior, clique em **[!UICONTROL Dashboard]**.
2. *Opcional* Selecione o intervalo de tempo desejado a partir da última data do relatório na lista suspensa (7 dias, 14 dias (o padrão), 30 dias ou 60 dias).

   Dependendo do período selecionado, a alteração delta nos painéis [!UICONTROL Largest Traits] > [!UICONTROL Most Changed Traits] e [!UICONTROL Largest Segments] > [!UICONTROL Most Changed Segments] exibe a alteração em visitantes únicos no público-alvo durante o período que termina hoje em comparação com o período anterior com a mesma duração. Por exemplo, se você selecionar 7 dias, o delta compara os visitantes únicos nos sete dias anteriores que terminam hoje com os visitantes únicos nos sete dias que terminam há sete dias.

   >[!NOTE]
   >
   >Você pode investigar uma alteração delta que parece fora do comum executando um relatório [!UICONTROL Trend]. Por exemplo, se você vir uma alteração delta excepcionalmente grande durante os últimos sete dias, poderá executar um relatório [!UICONTROL Trend] para os últimos 14 dias (2 x 7) para entender melhor os números.

   Dependendo das permissões do usuário conectado, os seguintes painéis serão exibidos:

   * [Parceiros únicos](../reporting/reports-dashboard.md#partner-uniques)
   * [Características Maiores/Características Mais Alteradas](../reporting/reports-dashboard.md#largest-traits)
   * [Maiores segmentos/Mais segmentos alterados](../reporting/reports-dashboard.md#most-changed-segments)

3. *Opcional* Clique em **[!UICONTROL Normalize]** acima de qualquer gráfico para mostrar todos os dados na mesma escala. Você também pode passar o mouse sobre qualquer ponto de dados para ver mais informações.

## Parceiro único {#partner-uniques}

Permissão necessária para visualizar: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

Esse painel exibe o número de visitantes únicos durante o período especificado. As linhas individuais codificadas por cores representam o número total de visitantes únicos e o número de visitantes únicos capturados usando características algorítmicas, baseadas em regras e integradas.

>[!NOTE]
>
>O número total de visitantes únicos representa os visitantes capturados por meio de características com base em regras ou integradas. No entanto, o número total de visitantes únicos não é igual à soma de visitantes únicos capturados usando as características integradas e com base em regras. O mesmo usuário único pode ser representado em qualquer um desses dois tipos de características.

## Características principais/Características mais alteradas {#largest-traits}

Permissão necessária para visualizar: [!UICONTROL View Traits].

![](assets/largest_traits.png)

Esse painel exibe o número de visitantes únicos capturados por várias características.

Use a lista suspensa **[!UICONTROL Show]** para exibir informações sobre diferentes tipos de características: [!UICONTROL All Traits], [!UICONTROL Algorithmic], [!UICONTROL Onboarded] ou [!UICONTROL Rule-Based].

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
   <td colname="col1"> <p><span class="wintitle"> Maiores Características</span> </p> </td> 
   <td colname="col2"> <p>Exibe informações sobre o número de visitantes únicos classificados por número (do mais alto ao mais baixo) e também lista a alteração delta de visitantes únicos durante o intervalo de tempo especificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Características mais alteradas</span> </p> </td> 
   <td colname="col2"> <p>Exibe informações sobre o número de visitantes únicos classificados pela alteração do delta. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Maiores segmentos/Mais segmentos alterados {#most-changed-segments}

Permissão necessária para visualizar: [!UICONTROL View Segments].

![](assets/largest_segments.png)

Esse painel exibe o número de visitantes únicos capturados por vários segmentos em tempo real.

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
   <td colname="col1"> <p><span class="wintitle"> Maiores Segmentos</span> </p> </td> 
   <td colname="col2"> <p>Exibe informações sobre o número de visitantes únicos e a alteração delta de visitantes únicos durante o intervalo de tempo especificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segmentos mais alterados</span> </p> </td> 
   <td colname="col2"> <p>Exibe informações sobre o número de visitantes únicos classificados pela alteração do delta. </p> </td> 
  </tr> 
 </tbody> 
</table>
