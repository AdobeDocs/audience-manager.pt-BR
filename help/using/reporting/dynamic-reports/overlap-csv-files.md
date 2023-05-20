---
description: É possível requisitar um arquivo .csv para um Relatório de sobreposição quando ele alcança o limite de 1 milhão. Um relatório pode ter atingido esse limite ao receber a mensagem "Ocorreu um erro inesperado". Entre em contato com o Atendimento ao cliente para solicitar um arquivo .csv compactado, que pode ser importado e usado no seu próprio sistema de banco de dados. Os arquivos estão disponíveis para relatórios de sobreposição de segmento por segmento, segmento por característica e característica por característica.
seo-description: You can request a .csv file for an Overlap Report when that report reaches its 1-million record limit. A report may have reached this limit when you see an "Unexpected error has occurred" message. Contact Customer Care to request a compressed .csv file, which you can import and work with in your own database system. Files are available for segment-to-segment, segment-to-trait, and trait-to-trait overlap reports.
seo-title: CSV Files for Overlap Reports
solution: Audience Manager
title: Arquivos CSV para relatórios de sobreposição
uuid: 047e440e-00c5-4d06-a809-51d776326cd6
feature: Overlap Reports
exl-id: 759c39cb-64ec-47dd-a3a4-027408aa6b5e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '906'
ht-degree: 7%

---

# Arquivos CSV para relatórios de sobreposição{#csv-files-for-overlap-reports}

É possível requisitar um arquivo .csv para um Relatório de sobreposição quando ele alcança o limite de 1 milhão. Um relatório pode ter atingido esse limite ao receber a mensagem &quot;Ocorreu um erro inesperado&quot;. Entre em contato com o Atendimento ao cliente para solicitar um arquivo .csv compactado, que pode ser importado e usado no seu próprio sistema de banco de dados. Os arquivos estão disponíveis para relatórios de sobreposição de segmento por segmento, segmento por característica e característica por característica.

## Metadados do nome do arquivo {#file-name-metadata}

A tabela a seguir lista e descreve as convenções de nomenclatura de arquivo e as extensões de arquivo usadas em um arquivo .csv sobreposto. Nos exemplos, *itálico* indica um espaço reservado para variável.

<table id="table_C99FCABA365B4AB99620F27D4414E623"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento de metadados </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Arquivo Extensão </p> </td> 
   <td colname="col2"> <p>Os arquivos de relatório de sobreposição são compactados por gzip e têm um <code> .gz</code> extensão de arquivo. É necessário adicionar o <code> .csv</code> ao arquivo após a descompactação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome do arquivo </p> </td> 
   <td colname="col2"> <p>Sintaxe do nome do arquivo: </p> <p> 
     <ul id="ul_D69D320A1AE94361B75D2AB47F90C4D1"> 
      <li id="li_FFB104975D104050AB67FEEC903C6E2E">Arquivos de segmento por segmento: <code>S2S_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_7DEC51D693FB4377840D652AF40386EF">Arquivos de segmento para característica: <code>S2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_CCB35A2BCB714E518AB279D453740623">Arquivos de característica por característica: <code>T2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intervalo de datas </p> </td> 
   <td colname="col2"> <p>O intervalo de datas de um relatório é uma ID de 5 dígitos que inclui: </p> <p> 
     <ul id="ul_7B334CDFD7DA42AC8F383BE0F8F77FB9"> 
      <li id="li_0045DED532E747C08824DCC98A9174B3"> <code> 70000</code> para um relatório de 7 dias. </li> 
      <li id="li_3A22775F78E648BF8AC32A9E1AF1F5DE"> <code> 30000</code> para um relatório de 30 dias. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vários arquivos </p> </td> 
   <td colname="col2"> <p>Incrementamos o último dígito no nome do arquivo se um relatório contiver vários arquivos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exemplos </p> </td> 
   <td colname="col2"> <p>Exemplos de nome de arquivo para um único relatório: </p> <p> 
     <ul id="ul_EED13F73F37D48868236F8945E19C88F"> 
      <li id="li_55DD677F9BA7460AA4AAD27AFD08A5AE">Arquivo único, de 7 dias: <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_487F8B76B7F24DCEB890C2D8186728F7">Arquivo único, de 30 dias: <code> S2S_overlap_12345_2017_01_14_30000.gz</code> </li> 
     </ul> </p> <p>Exemplos de nome de arquivo para um relatório com vários arquivos: </p> <p> 
     <ul id="ul_D307EECBB3524962AB8C8332BF699D29"> 
      <li id="li_9FA3B5539E5A4F95899075866D96DEA0"> <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_D8776BD8BAD842C29119B7765F258384"> <code> S2S_overlap_12345_2017_01_14_70001.gz</code> </li> 
      <li id="li_E97AC7696E954A9DAE3DA4E51B5C1B0E"> <code> S2S_overlap_12345_2017_01_14_70002.gz</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Conteúdo do arquivo {#file-contents}

No arquivo, os dados da cadeia de caracteres são colocados entre aspas duplas. Consulte os dados simulados abaixo. Este foi truncado por questões de brevidade e para caber na tela.

```js
//File header
"segment_id1","segment_name1","segment_id2","segment_name3,"range_id",...
//File body
"123456","segmentA","654321","segmentB","30","yyyy-mm-dd","98765",...
```

## Registros do relatório de segmento por segmento {#segment-segment-records}

Um arquivo de dados para o [Relatório de sobreposição de segmento por segmento](segment-segment-overlap-report.md) contém os seguintes registros.

<table id="table_1BDC7019DF2543069D7AE229C5E2454E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rótulo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> segment_id1</code> </p> </td> 
   <td colname="col2"> <p>A ID do segmento que você está comparando ao segmento da linha de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name1</code> </p> </td> 
   <td colname="col2"> <p>O nome do segmento que você está comparando aos segmentos da linha de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_id2</code> </p> </td> 
   <td colname="col2"> <p>A ID do segmento da linha de base. O segmento da linha de base é o segmento que você deseja comparar com outros segmentos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name2</code> </p> </td> 
   <td colname="col2"> <p>O nome do segmento de linha de base que você está comparando com outros segmentos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Você pode obter relatórios para intervalos de retrospectiva de 7 e 30 dias. A variável <code> rangeid</code> corresponde aos intervalos de tempo mostrados abaixo. </p> <p> 
     <ul id="ul_129D6CB0EB6F48F28440D22DA257D1A4"> 
      <li id="li_5FC34516A437459F854C81B1CE353B89"> <code> 7</code>: 7 dias </li> 
      <li id="li_2CECC5039DAF4796BCCF27DACC3754A3"> <code> 30</code>: 30 dias </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>A data de processamento de um relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques1</code> </p> </td> 
   <td colname="col2"> <p>O número de usuários únicos no segmento que você está comparando ao segmento da linha de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques2</code> </p> </td> 
   <td colname="col2"> <p>O número de usuários únicos no segmento da linha de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>Uma contagem total da sobreposição de usuários únicos entre o segmento da linha de base e os outros segmentos selecionados para comparação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>A % de sobreposição de usuários únicos entre o segmento da linha de base e os outros segmentos selecionados para comparação. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Registros do relatório de segmento por característica {#segment-trait-records}

Um arquivo de dados para o [Relatório de sobreposição de segmento por característica](segment-trait-overlap-report.md) contém os seguintes registros.

<table id="table_45270B5D01014AD99921B320D3A32DB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rótulo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> trait_id</code> </p> </td> 
   <td colname="col2"> <p>ID da característica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_name</code> </p> </td> 
   <td colname="col2"> <p>Nome da característica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>A ID do provedor de dados. As IDs incluem: </p> <p> 
     <ul id="ul_B40EF144552B4BD3A1C2AE2BAFFC5A68"> 
      <li id="li_8E3B524C615F4047A5A06AF2EDF9C758"> <code> 1st Party</code> </li> 
      <li id="li_F0979659028F4E2D989F1F3D1014FD3A"> <code> 3rd Party</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>Nome do provedor de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Você pode obter relatórios para intervalos de retrospectiva de 7 e 30 dias. A variável <code> rangeid</code> corresponde aos intervalos de tempo mostrados abaixo. </p> <p> 
     <ul id="ul_4B07DFF4A226428A930E22B5FF73E1D0"> 
      <li id="li_4BD0F8AE64C74D7BBE2298F19E2F5328"> <code> 7</code>: 7 dias </li> 
      <li id="li_7C0C0D2CD9144C4CAF00EDEA90929104"> <code> 30</code>: 30 dias </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>A data de processamento de um relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques</code> </p> </td> 
   <td colname="col2"> <p>O número de usuários únicos no segmento selecionado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>O número de usuários únicos em uma característica. No relatório da interface do usuário, esse número aparece na janela pop-up quando você passa o mouse sobre uma característica nos resultados do mapa de calor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>O número de usuários únicos compartilhados entre as características e os segmentos selecionados. No relatório da interface do usuário, esse número aparece na janela pop-up quando você passa o mouse sobre uma característica nos resultados do mapa de calor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% de usuários únicos que sobrepõem a característica e o segmento. No relatório da interface do usuário, esse número aparece na janela pop-up quando você passa o mouse sobre uma característica nos resultados do mapa de calor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% de usuários únicos que sobrepõem o segmento e a característica. No relatório da interface do usuário, esse número aparece na janela pop-up quando você passa o mouse sobre uma característica nos resultados do mapa de calor. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Registros do relatório de característica por característica {#trait-trait-records}

Um arquivo de dados para o [Relatório de sobreposição de característica por característica](trait-trait-overlap-report.md) contém os seguintes registros.

<table id="table_603216E6AFE4439A87C91DDFF2989F53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rótulo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_id</code> </p> </td> 
   <td colname="col2"> <p>A ID da característica que você está comparando à característica da linha de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_name</code> </p> </td> 
   <td colname="col2"> <p>O nome da característica que você está comparando à característica da linha de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_id</code> </p> </td> 
   <td colname="col2"> <p>A ID da característica da linha de base. A característica da linha de base é a característica que você deseja comparar com outras características. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_name</code> </p> </td> 
   <td colname="col2"> <p>O nome da característica da linha de base que você está comparando com outras características. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>A ID do provedor de dados. As IDs incluem: </p> <p> 
     <ul id="ul_FB6FCAF484BE404B8987B54078F5E858"> 
      <li id="li_5E473205AB494D199FBDF22CAA4A1C57"> <code> 1st Party</code> </li> 
      <li id="li_C9A5F455FB6D458F9DDB56EDBF5A6304"> <code> 3rd Party</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>Nome do provedor de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Você pode obter relatórios para intervalos de retrospectiva de 7 e 30 dias. A variável <code> rangeid</code> corresponde aos intervalos de tempo mostrados abaixo. </p> <p> 
     <ul id="ul_BC2C41B90F864522B075EFDED33537EC"> 
      <li id="li_929639F70A1A4039BA19332562B71845"> <code> 7</code>: 7 dias </li> 
      <li id="li_1C489A4B755D4444AD5FAAF0B492F412"> <code> 30</code>: 30 dias </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>A data de processamento de um relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>O número de usuários únicos compartilhados entre as características selecionadas. No relatório da interface do usuário, esse número aparece na janela pop-up quando você passa o mouse sobre uma característica nos resultados do mapa de calor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>O número de usuários únicos em uma característica básica. No relatório da interface do usuário, esse número aparece na janela pop-up quando você passa o mouse sobre uma característica nos resultados do mapa de calor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>O número de usuários únicos compartilhados entre as características selecionadas. No relatório da interface do usuário, esse número aparece na janela pop-up quando você passa o mouse sobre uma característica nos resultados do mapa de calor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% de usuários únicos que se sobrepõem entre as características selecionadas. No relatório da interface do usuário, esse número aparece na janela pop-up quando você passa o mouse sobre uma característica nos resultados do mapa de calor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% de usuários únicos que se sobrepõem entre as características selecionadas. No relatório da interface do usuário, esse número aparece na janela pop-up quando você passa o mouse sobre uma característica nos resultados do mapa de calor. </p> </td> 
  </tr> 
 </tbody> 
</table>
