---
description: Descreve o software subjacente que alimenta os relatórios interativos e o agendamento de atualização de dados.
seo-description: Describes the underlying software that powers the interactive reports and the data update schedule.
seo-title: Report Technology
solution: Audience Manager
title: Tecnologia de relatório
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
feature: Overlap Reports
exl-id: 59d875d6-a630-4795-93a7-1d432860f0a1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 0%

---

# Tecnologia de relatório{#report-technology}

Descreve o software subjacente que alimenta os relatórios interativos e o agendamento de atualização de dados.

<!-- 

c_report_technology.xml

 -->

## Relatórios interativos usam a tecnologia Tableau

[!DNL Audience Manager] usa o software [Tableau](https://www.tableausoftware.com/) para exibir dados nos relatórios interativos. Com o [!DNL Tableau], os relatórios do [!UICONTROL Delivery and Overlap] usam dicas visuais e símbolos que ajudam a:

* Encontre características de alto e baixo desempenho.
* Características e segmentos pontuais com sobreposição baixa e alta de visitantes únicos.
* Use dados de sobreposição para criar segmentos direcionados.
* Expanda o alcance identificando características relacionadas com baixa sobreposição.

## Agendamento de atualização de dados

Os dados do relatório são atualizados semanalmente, todos os domingos. A atualização processa dados de sábado (o dia anterior) até o domingo anterior.

## Formas, Cores e Tamanhos Usados em Relatórios Interativos {#shapes-colors-sizes}

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
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">Os círculos indicam suas próprias características próprias. </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">Quadrados indicam características de terceiros. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Cores</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">Sombras vermelhas indicam sobreposição <i>baixa</i>. </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">Os tons verdes indicam uma sobreposição de <i>alta</i>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Tamanho</b> </td> 
   <td colname="col2"> O tamanho aumenta ou diminui na proporção direta para alcançar (o número ou % de cliques ou usuários únicos em uma característica ou segmento). </td> 
  </tr> 
 </tbody> 
</table>

## Documentação do Tableau {#tableau-documentation}

Para saber mais sobre os controles do Tableau que você pode ver em nossos relatórios interativos, consulte a documentação oficial do [Tableau Server no Linux 2018.2](https://help.tableau.com/v2018.2/server-linux/en-us/get_started_server.htm)
