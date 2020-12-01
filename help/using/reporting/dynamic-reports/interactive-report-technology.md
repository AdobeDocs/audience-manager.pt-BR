---
description: Descreve o software subjacente que alimenta os relatórios interativos e o agendamento da atualização de dados.
seo-description: Descreve o software subjacente que alimenta os relatórios interativos e o agendamento da atualização de dados.
seo-title: Tecnologia de relatórios
solution: Audience Manager
title: Tecnologia de relatórios
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
feature: overlap reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 3%

---


# Tecnologia de relatórios{#report-technology}

Descreve o software subjacente que alimenta os relatórios interativos e o agendamento da atualização de dados.

<!-- 

c_report_technology.xml

 -->

## Relatórios interativos usam a tecnologia Tableau

[!DNL Audience Manager] usa o  [](https://www.tableausoftware.com/) Tableausoftware para exibir dados nos relatórios interativos. Com [!DNL Tableau], os relatórios [!UICONTROL Delivery and Overlap] usam dicas visuais e símbolos que ajudam a:

* Encontre características de alto e baixo desempenho.
* Características especiais e segmentos com sobreposição de visitante único baixa e alta.
* Use dados de sobreposição para criar segmentos direcionados.
* Expanda o alcance identificando características relacionadas com baixa sobreposição.

## Agendamento de atualização de dados

Os dados do relatório são atualizados semanalmente a cada domingo. A atualização processa dados de sábado (o dia anterior) de volta ao domingo anterior.

## Formas, cores e tamanhos usados em relatórios interativos {#shapes-colors-sizes}

A maioria dos relatórios interativos exibe resultados usando formas de tamanhos e cores diferentes. Esse formato de exibição foi projetado para ajudá-lo a entender os dados visualmente, sem precisar percorrer linhas e colunas de números.

<!-- 

r_legend.xml

 -->

### Legenda do relatório

A tabela a seguir define as formas, os tamanhos e as cores usadas nos relatórios dinâmicos.

<table id="table_EC180A96E3784FC6B81FCFB546C4A3FA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento de dados </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Formas</b> </td> 
   <td colname="col2"> 
    <ul id="ul_076773ABD0BB4CE6834ACFA8B3D6AC2E"> 
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">Círculos indicam suas próprias características originais. </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">Quadrados indicam características de terceiros. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Cores</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">Os tons vermelhos indicam <i>low</i> sobreposição. </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">Os tons verdes indicam <i>high</i> sobreposição. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Tamanho</b> </td> 
   <td colname="col2"> O tamanho aumenta ou diminui em proporção direta ao alcance (o número ou a % de cliques ou usuários únicos em uma característica ou segmento). </td> 
  </tr> 
 </tbody> 
</table>

## Documentação do Tableau {#tableau-documentation}

Para saber mais sobre os controles do Tableau que você pode ver em nossos relatórios interativos, consulte a documentação oficial do [Tableau Server no Linux 2018.2](https://help.tableau.com/v2018.2/server-linux/en-us/get_started_server.htm)