---
description: Crie segmentos de teste mutuamente exclusivos em Grupos de teste de segmento para comparar e medir a eficácia de diferentes destinos. Você pode separar um grupo de controle e dividir seu segmento em porcentagens de um todo, a fim de testar a eficácia.
seo-description: Create mutually exclusive test segments in Segment Test Groups to compare and measure effectiveness of different destinations. You can set aside a control group and divide your segment into percentages of a whole, in order to test efficacy.
seo-title: Audience Lab
solution: Audience Manager
title: Audience Lab
uuid: aaee820c-1e78-4fd4-bd8f-2629085d78e9
feature: Audience Lab
exl-id: b7fbeb03-52aa-4489-8fcb-45bc2d26621d
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 2%

---

# [!UICONTROL Audience Lab] {#audience-lab}

Crie segmentos de teste mutuamente exclusivos em [!UICONTROL Segment Test Groups] para comparar e medir a eficácia de destinos diferentes. Você pode separar um grupo de controle e dividir seu segmento em porcentagens de um todo, a fim de testar a eficácia.

## Visão geral {#audience-lab-overview}

[!UICONTROL Audience Lab] usa [Link de Perfil](../../features/profile-merge-rules/merge-rules-overview.md) para habilitar testes entre dispositivos. Isso ajuda a garantir que um usuário se qualifique para o mesmo segmento de teste e receba o mesmo tratamento em todos os dispositivos. Os segmentos de teste em grupos de teste herdarão a [Regra de mesclagem de perfis](../../features/profile-merge-rules/merge-rules-dashboard.md) que o segmento base atribuiu a ele.

O modo de exibição padrão [!UICONTROL Audience Lab] exibe um cartão para cada um dos grupos de teste. Clique em um cartão para acessar a exibição **[!UICONTROL Test Group]**. Essa exibição inclui as seguintes informações:

* **[Testar informações do grupo](../../features/audience-lab/audience-lab-information-view.md)**
* **[Relatórios do grupo de teste](../../features/audience-lab/audience-lab-reporting-view.md)**

Você pode criar **até 10 grupos de teste**, cada um com **até 15 segmentos de teste**.

![](assets/test-groups-view.PNG)

## Pesquisar e filtrar grupos de teste {#search-and-filter}

Depois de começar a criar vários grupos de teste com vários segmentos de teste, pode ser mais fácil usar a caixa de pesquisa para encontrar um grupo de teste específico. Você pode procurar um grupo de teste por:

* O nome do grupo de teste;
* O nome de qualquer um dos segmentos de teste no seu grupo de teste;
* A descrição do grupo de teste.

![](assets/search_and_filter_audience_lab.png)

Você também pode filtrar seus grupos de teste por status. Todos os status disponíveis estão descritos na seção [Status](../../features/audience-lab/audience-lab.md#status) abaixo.

## [!UICONTROL Status] {#status}

O status de um grupo de teste pode ser ativo, programado, pausado, rascunho ou concluído. Mais informações sobre cada uma delas na tabela abaixo:

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
   <td colname="col2"> <p>Um grupo de teste <i>ativo</i> significa que os dados estão sendo enviados para destinos. Pressione o cartão <b><span class="uicontrol"> Pausar Teste </span></b> no <b><span class="uicontrol"> Grupo de Teste </span></b> para suspender o envio de dados para destinos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Agendado </span></b> </p> </td> 
   <td colname="col2"> <p>Um grupo de teste <i>programado</i> ainda não está ativo, mas não pode ser mais editado. Ele se tornará ativo na data de início selecionada no assistente <b>Criar grupos de teste</b>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pausado </span></b> </p> </td> 
   <td colname="col2"> <p>Um grupo de teste <i>paused</i> não envia dados para destinos no momento. Pressione <b><span class="uicontrol"> Tornar ativo </span></b> no cartão <b><span class="uicontrol"> Grupo de teste </span></b> para retomar o envio de características. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Rascunho </span></b> </p> </td> 
   <td colname="col2"> <p>Um grupo de teste de <i>rascunho</i> ainda não está ativo e ainda pode ser editado. Ele ainda não envia dados para os destinos mapeados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Concluído </span></b> </p> </td> 
   <td colname="col2"> <p>Um grupo de teste <i>concluído</i> atingiu a data de término selecionada no assistente <b><span class="uicontrol"> Criar Grupos de Teste </span></b> e parou de enviar dados de relatório. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Actions] {#actions}

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
   <td colname="col2"> <p>Disponível <b>somente</b> para grupos de teste de rascunho. Permite retomar o assistente <b><span class="uicontrol"> para Criar Novo Grupo de Teste </span></b>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pausar </span></b> </p> </td>
   <td colname="col2"> <p>Disponível para grupos de teste ativos. Permite pausar o envio dos segmentos de teste para destinos. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tornar Ativo </span></b> </p> </td>
   <td colname="col2"> <p>Disponível para grupos de teste pausados. Permite que você continue enviando os segmentos de teste para destinos. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Visualização </span></b> </p> </td>
   <td colname="col2"> <p>Disponível para grupos de teste concluídos. Permite exibir as informações de relatório geradas pelo teste. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Duplicado </span></b> </p> </td>
   <td colname="col2"> <p>Permite criar um novo grupo de teste com a mesma configuração do grupo que você está duplicando. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Excluir </span></b> </p> </td>
   <td colname="col2"> <p>Permite excluir um grupo de teste. Os segmentos de teste serão desmapeados dos destinos, o segmento da linha de base e as características de conversão associadas ao grupo de teste serão totalmente editáveis. Um alerta solicitará que você baixe o arquivo CSV ao excluir um grupo de teste para salvar os relatórios, se desejar. </p> </td>
  </tr>
 </tbody>
</table>
