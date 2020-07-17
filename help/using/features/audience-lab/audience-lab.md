---
description: Crie segmentos de teste mutuamente exclusivos em Grupos de teste de segmento para comparar e medir a eficácia de destinos diferentes. Pode separar um grupo de controle e dividir o seu segmento em percentagens de um todo, a fim de testar a eficácia.
seo-description: Crie segmentos de teste mutuamente exclusivos em Grupos de teste de segmento para comparar e medir a eficácia de destinos diferentes. Pode separar um grupo de controle e dividir o seu segmento em percentagens de um todo, a fim de testar a eficácia.
seo-title: 'Audience Lab '
solution: Audience Manager
title: 'Audience Lab '
topic: DIL API
uuid: aaee820c-1e78-4fd4-bd8f-2629085d78e9
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 4%

---


# [!UICONTROL Audience Lab] {#audience-lab}

Crie segmentos de teste mutuamente exclusivos [!UICONTROL Segment Test Groups] para comparar e medir a eficácia de diferentes destinos. Pode separar um grupo de controle e dividir o seu segmento em percentagens de um todo, a fim de testar a eficácia.

## Visão geral {#audience-lab-overview}

[!UICONTROL Audience Lab] usa o Link [do](../../features/profile-merge-rules/merge-rules-overview.md) Perfil para acionar o teste entre dispositivos. Isso ajuda a garantir que o usuário se qualifice para o mesmo segmento de teste e receba o mesmo tratamento em todos os dispositivos. Os segmentos de teste em grupos de teste herdarão a Regra [de mesclagem de](../../features/profile-merge-rules/merge-rules-dashboard.md) Perfis atribuída pelo segmento base.

A visualização [!UICONTROL Audience Lab] padrão exibe um cartão para cada um dos grupos de teste. Clique em um cartão para acessar a **[!UICONTROL Test Group]** visualização. Esta visualização inclui as seguintes informações:

* **[Testar informações do grupo](../../features/audience-lab/audience-lab-information-view.md)**
* **[Relatórios do grupo de teste](../../features/audience-lab/audience-lab-reporting-view.md)**

Você pode criar **até 10 grupos** de teste, cada um com **até 15 segmentos** de teste.

![](assets/test-groups-view.PNG)

## Pesquisar e filtrar grupos de teste {#search-and-filter}

Depois que você start a criação de vários grupos de teste com vários segmentos de teste, pode ser mais fácil usar a caixa de pesquisa para localizar um grupo de teste específico. Você pode pesquisar por um grupo de teste:

* O nome do grupo de ensaio;
* O nome de qualquer um dos segmentos de teste no grupo de teste;
* A descrição do grupo de teste.

![](assets/search_and_filter_audience_lab.png)

Você também pode filtrar seus grupos de teste por status. Todos os status disponíveis estão descritos na seção [Status](../../features/audience-lab/audience-lab.md#status) abaixo.

## [!UICONTROL Status] {#status}

O status de um grupo de teste pode estar ativo, programado, pausado, rascunho ou concluído. Mais informações sobre cada uma delas na tabela abaixo:

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
   <td colname="col2"> <p>Um grupo de teste <i>ativo</i> significa que os dados estão sendo enviados para destinos no momento. Pressione <b><span class="uicontrol"> Pause Test (Pausar teste) </span></b> no cartão <b><span class="uicontrol"> </span></b> Test Group (Grupo de teste) para suspender o envio de dados para destinos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Programado </span></b> </p> </td> 
   <td colname="col2"> <p>Um grupo de teste <i>agendado</i> ainda não está ativo, mas não pode mais ser editado. Ele ficará ativo na data de start selecionada no assistente <b>Criar grupos</b> de teste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pausado </span></b> </p> </td> 
   <td colname="col2"> <p>Um grupo de teste <i>pausado</i> não envia dados para destinos no momento. Pressione <b><span class="uicontrol"> Tornar ativo </span></b> no cartão <b><span class="uicontrol"> do Grupo de teste </span></b> para retomar o envio das características. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Rascunho </span></b> </p> </td> 
   <td colname="col2"> <p>Um grupo de teste de <i>rascunho</i> ainda não está ativo e ainda pode ser editado. Ainda não envia dados para os destinos mapeados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Concluído </span></b> </p> </td> 
   <td colname="col2"> <p>Um grupo de teste <i>concluído</i> atingiu a data de término selecionada no assistente <b><span class="uicontrol"> Criar grupos de teste </span></b> e parou de enviar dados do relatórios. </p> </td>
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
   <td colname="col2"> <p>Disponível <b>somente</b> para grupos de teste de rascunho. Permite retomar o assistente <b><span class="uicontrol"> Criar novo grupo de teste </span></b> . </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pausar </span></b> </p> </td>
   <td colname="col2"> <p>Disponível para grupos de teste ativos. Permite que você pare de enviar os segmentos de teste para destinos. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tornar ativo </span></b> </p> </td>
   <td colname="col2"> <p>Disponível para grupos de teste pausados. Permite retomar o envio dos segmentos de teste para destinos. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Exibir </span></b> </p> </td>
   <td colname="col2"> <p>Disponível para grupos de teste concluídos. Permite que você visualização as informações do relatórios que o teste gerou. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Duplicar </span></b> </p> </td>
   <td colname="col2"> <p>Permite criar um novo grupo de teste com a mesma configuração do grupo que você está duplicando. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Excluir </span></b> </p> </td>
   <td colname="col2"> <p>Permite que você exclua um grupo de teste. Os segmentos de teste não serão mapeados dos destinos, o segmento de linha de base e as características de conversão associadas ao grupo de teste serão totalmente editáveis. Um alerta solicitará o download do arquivo CSV quando você excluir um grupo de teste para salvar o relatórios, se desejar. </p> </td>
  </tr>
 </tbody>
</table>