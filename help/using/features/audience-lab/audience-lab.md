---
description: Crie segmentos de teste mutuamente exclusivos nos Grupos de teste de segmento para comparar e medir a eficácia de destinos diferentes. Você pode definir um grupo de controle e dividir seu segmento em porcentagens de um todo para testar a eficácia.
seo-description: Crie segmentos de teste mutuamente exclusivos nos Grupos de teste de segmento para comparar e medir a eficácia de destinos diferentes. Você pode definir um grupo de controle e dividir seu segmento em porcentagens de um todo para testar a eficácia.
seo-title: Laboratório de público-alvo
solution: Audience Manager
title: Laboratório de público-alvo
topic: API DIL
uuid: aaee 820 c -1 e 78-4 fd 4-bd 8 f -2629085 d 78 e 9
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab {#audience-lab}

Create mutually exclusive test segments in [!UICONTROL Segment Test Groups] to compare and measure effectiveness of different destinations. Você pode definir um grupo de controle e dividir seu segmento em porcentagens de um todo para testar a eficácia.

## Visão geral {#audience-lab-overview}

[!UICONTROL Audience Lab] usa [o Link de perfil](../../features/profile-merge-rules/merge-rules-overview.md) para testes entre dispositivos. Isso ajuda a garantir que um usuário seja qualificado para o mesmo segmento de teste e recebe o mesmo tratamento em todos os dispositivos. The test segments in test groups will inherit the [Profile Merge Rule](../../features/profile-merge-rules/merge-rules-dashboard.md) the base segment has assigned to it.

The [!UICONTROL Audience Lab] default view displays a card for each of the test groups. Click a card to access the **[!UICONTROL Test Group]** view. Esta exibição inclui as seguintes informações:

* **[Informações do grupo de teste](../../features/audience-lab/audience-lab-information-view.md)**
* **[Relatórios de grupo de teste](../../features/audience-lab/audience-lab-reporting-view.md)**

You are able to create **up to 10 test groups**, each one with **up to 15 test segments**.

![](assets/test-groups-view.PNG)

## Search and Filter Test Groups {#search-and-filter}

Depois de começar a criar vários grupos de teste com vários segmentos de teste, pode ser mais fácil usar a caixa de pesquisa para encontrar um grupo de teste específico. Você pode pesquisar por um grupo de teste:

* O nome do grupo de teste;
* O nome de qualquer um dos segmentos de teste no grupo de teste;
* A descrição do grupo de teste.

![](assets/search_and_filter_audience_lab.png)

Você também pode filtrar os grupos de teste por status. All available statuses are described in the [Status](../../features/audience-lab/audience-lab.md#status) section below.

## Status {#status}

O status de um grupo de teste pode ser ativo, programado, pausado, rascunho ou concluído. Mais informações sobre cada uma na tabela abaixo:

<table id="table_7A0388BA02E045AC971C06A22DAC2C63"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Status </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Ativo </span></b> </p> </td> 
   <td colname="col2"> <p>An <i>active</i> test group means that data is currently being sent to destinations. Press <b><span class="uicontrol"> Pause Test </span></b> in the <b><span class="uicontrol"> Test Group </span></b> card to suspend sending data to destinations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Programado </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>scheduled</i> test group is not yet active but cannot be edited anymore. It will become active at the start date you selected in the <b>Create Test Groups</b> wizard. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pausado </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>paused</i> test group does not currently send data to destinations. Press <b><span class="uicontrol"> Make Active </span></b> in the <b><span class="uicontrol"> Test Group </span></b> card to resume sending traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Rascunho </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>draft</i> test group is not yet active and can still be edited. Ainda não envia dados para os destinos mapeados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Concluído </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>completed</i> test group has reached the end date you selected in the <b><span class="uicontrol"> Create Test Groups </span></b> wizard and has stopped sending reporting data. </p> </td>
  </tr>
 </tbody>
</table>

## Ações {#actions}

<table id="table_481A411E2D2F4FE891595D00E775CF60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ações </th> 
   <th colname="col2" class="entry"> Descrição </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Editar </span></b> </p> </td>
   <td colname="col2"> <p>Available <b>only</b> for draft test groups. Allows you to resume the <b><span class="uicontrol"> Create New Test Group </span></b> wizard. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pausar </span></b> </p> </td>
   <td colname="col2"> <p>Disponível para grupos de teste ativos. Permite pausar o envio dos segmentos de teste aos destinos. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tornar ativo </span></b> </p> </td>
   <td colname="col2"> <p>Disponível para grupos de teste pausados. Permite retomar o envio dos segmentos de teste aos destinos. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Exibir </span></b> </p> </td>
   <td colname="col2"> <p>Disponível para grupos de teste concluídos. Permite exibir as informações de relatório geradas pelo teste. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Duplicar </span></b> </p> </td>
   <td colname="col2"> <p>Permite criar um novo grupo de teste com a mesma configuração que aquela que você está duplicando. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Excluir </span></b> </p> </td>
   <td colname="col2"> <p>Permite excluir um grupo de teste. Os segmentos de teste serão desmapeados a partir dos destinos, o segmento da linha de base e as características de conversão associadas ao grupo de teste são totalmente editáveis. Um alerta solicitará que você faça download do arquivo CSV quando excluir um grupo de teste para salvar o relatório, se desejar. </p> </td>
  </tr>
 </tbody>
</table>