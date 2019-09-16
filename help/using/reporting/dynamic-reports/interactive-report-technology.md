---
description: Descreve o software subjacente que alimenta os relatórios interativos e o agendamento da atualização de dados.
seo-description: Descreve o software subjacente que alimenta os relatórios interativos e o agendamento da atualização de dados.
seo-title: Tecnologia de relatórios
solution: Audience Manager
title: Tecnologia de relatórios
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
translation-type: tm+mt
source-git-commit: b5a962381780f1a1627e39b59e3ca86fd51763b5

---


# Tecnologia de relatórios{#report-technology}

Descreve o software subjacente que alimenta os relatórios interativos e o agendamento da atualização de dados.

<!-- 

c_report_technology.xml

 -->

## Relatórios interativos usam a tecnologia Tableau

[!DNL Audience Manager] usa o software [Tableau](https://www.tableausoftware.com/) para exibir dados nos relatórios interativos. Com [!DNL Tableau], os [!UICONTROL Delivery and Overlap] relatórios usam dicas visuais e símbolos que ajudam a:

* Encontre características de alto e baixo desempenho.
* Características especiais e segmentos com sobreposição de visitantes únicos baixa e alta.
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
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">Os tons vermelhos indicam <i>baixa</i> sobreposição. </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">Os tons verdes indicam <i>alta</i> sobreposição. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Tamanho</b> </td> 
   <td colname="col2"> O tamanho aumenta ou diminui em proporção direta ao alcance (o número ou a % de cliques ou usuários únicos em uma característica ou segmento). </td> 
  </tr> 
 </tbody> 
</table>

## Explicação dos ícones e ferramentas do relatório {#icons-tools-explained}

Descreve como pesquisar e usar as várias ferramentas de ícone usadas nos relatórios dinâmicos.

<!-- 

r_icons.xml

 -->

### Ícones e ferramentas de dados

As seguintes ferramentas de ícones estão disponíveis na parte inferior de cada janela de relatório dinâmico. A ilustração a seguir fornece mais informações sobre essas ferramentas.

![](assets/tools_icons90.png)

### Exportar dados

Essas ferramentas permitem exportar dados do relatório em 4 formatos diferentes.

| Opção de exportação | Exportar dados |
|---|---|
| **[!UICONTROL Image]** | Como um arquivo de imagem (.png). Útil quando você deseja baixar e compartilhar dados do relatório em seu formato gráfico original. |
| **[!UICONTROL PDF]** | Como um arquivo PDF. |
| **[!UICONTROL Data]** | Em uma nova janela do navegador como dados numéricos em colunas e linhas. |
| **[!UICONTROL Crosstab]** | Como um arquivo .csv. |

### Reverter alterações

Selecione essa ferramenta para desfazer qualquer alteração de clique interativo que você tenha feito no relatório.

### Atualizações automáticas

Os relatórios [!UICONTROL Delivery-Performance] e [!UICONTROL Trait-to-Trait Overlap] são relatórios dinâmicos que respondem e mudam com base em ações de cliques do usuário.

Por exemplo, digamos que você deseja selecionar vários anunciantes no [!UICONTROL Overlap] relatório. Quando ativada, as atualizações automáticas começarão a retornar dados assim que você marcar uma caixa de seleção. Esse comportamento dinâmico pode interromper o fluxo de trabalho, pois é necessário aguardar até que o relatório conclua o processamento antes de selecionar outro anunciante. Use essa ferramenta para desativar esse recurso (e ligar novamente), conforme necessário.

### Atualizar dados

Clique no ícone de atualização para executar um relatório ou recarregar seu conjunto de dados. Quando as atualizações automáticas estiverem desativadas, clique em atualizar para executar ou atualizar o relatório.

### Ferramenta de pesquisa

A pesquisa é representada por um ícone de lupa genérico (não exibido). O campo de pesquisa fica oculto até que você clique nos rótulos de seleção no lado esquerdo da tela. A tabela abaixo descreve o local da ferramenta de pesquisa para cada relatório.

| Relatório | Para localizar a pesquisa, passe o mouse sobre |
|---|---|
| [!UICONTROL Delivery and Performance] relatório | O rótulo "Nome do anunciante". |
| [!UICONTROL Overlap] relatórios | O rótulo "SID Name". |
