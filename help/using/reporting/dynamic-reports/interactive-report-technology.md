---
description: Descreve o software subjacente que alimenta os relatórios interativos e o agendamento de atualização de dados.
seo-description: Descreve o software subjacente que alimenta os relatórios interativos e o agendamento de atualização de dados.
seo-title: Tecnologia de relatório
solution: Audience Manager
title: Tecnologia de relatório
uuid: 5 f 3 d 815 b-e 1 e 6-42 f 2-b 848-ac 035 a 5 aa 77 d
translation-type: tm+mt
source-git-commit: b5a962381780f1a1627e39b59e3ca86fd51763b5

---


# Report Technology{#report-technology}

Descreve o software subjacente que alimenta os relatórios interativos e o agendamento de atualização de dados.

<!-- 

c_report_technology.xml

 -->

## Relatórios interativos Use tecnologia Tableau

[!DNL Audience Manager] usa [o software Tableau](https://www.tableausoftware.com/) para exibir dados nos relatórios interativos. With [!DNL Tableau], the [!UICONTROL Delivery and Overlap] reports use visual cues and symbols that help you:

* Encontre características de desempenho alto e baixo.
* Características especiais e segmentos com sobreposição de visitante único baixo e alto.
* Use dados de sobreposição para criar segmentos direcionados.
* Amplie o alcance identificando características relacionadas com baixa sobreposição.

## Programação de atualização de dados

Os dados do relatório são atualizados semanalmente a cada domingo. A atualização processa dados de sábado (o dia antes) de volta para o domingo anterior.

## Shapes, Colors, and Sizes Used in Interactive Reports {#shapes-colors-sizes}

A maioria dos relatórios interativos exibe resultados usando formas de tamanhos e cores diferentes. Esse formato de exibição foi projetado para ajudá-lo a tornar os dados visualmente, sem precisar percorrer linhas e colunas de números.

<!-- 

r_legend.xml

 -->

### Legenda do relatório

A tabela a seguir define as formas, tamanhos e cores usadas nos relatórios dinâmicos.

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
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">Os círculos indicam seus próprios traços próprios. </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">Os quadrados indicam características de terceiros. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Cores</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">Red shades indicate <i>low</i> overlap. </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">Green shades indicate <i>high</i> overlap. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Tamanho</b> </td> 
   <td colname="col2"> O tamanho aumenta ou diminui em proporção direta para alcance (o número ou a porcentagem de cliques ou usuários únicos em uma característica ou segmento). </td> 
  </tr> 
 </tbody> 
</table>

## Report Icons and Tools Explained {#icons-tools-explained}

Descreve como pesquisar e usar as várias ferramentas de ícone usadas nos relatórios dinâmicos.

<!-- 

r_icons.xml

 -->

### Ícones e ferramentas de dados

Os ícones a seguir estão disponíveis na parte inferior de cada janela de relatório dinâmico. A ilustração a seguir fornece mais informações sobre essas ferramentas.

![](assets/tools_icons90.png)

### Exportar dados

Essas ferramentas permitem exportar dados do relatório em 4 formatos diferentes.

| Opção Exportar | Exportar dados |
|---|---|
| **[!UICONTROL Image]** | Como um arquivo de imagem (. png). Útil quando você deseja baixar e compartilhar dados do relatório em seu formato original e gráfico. |
| **[!UICONTROL PDF]** | Como um arquivo PDF. |
| **[!UICONTROL Data]** | Em uma nova janela do navegador como dados numéricos em colunas e linhas. |
| **[!UICONTROL Crosstab]** | Como um arquivo. csv. |

### Reverter alterações

Selecione essa ferramenta para desfazer quaisquer alterações de clique interativas que você tenha executado no relatório.

### Atualizações automáticas

The [!UICONTROL Delivery-Performance] and [!UICONTROL Trait-to-Trait Overlap] reports are dynamic reports that respond and change based on user click actions.

For example, say you want to select several advertisers in the [!UICONTROL Overlap] report. Quando ativadas, as atualizações automáticas começarão a retornar dados assim que você selecionar uma caixa de seleção. Esse comportamento dinâmico pode interromper seu fluxo de trabalho porque é necessário aguardar até que o relatório conclua o processamento antes de selecionar outro anunciante. Use essa ferramenta para desativar o recurso (e novamente), conforme necessário.

### Atualizar dados

Clique no ícone de atualização para executar um relatório ou recarregar seu conjunto de dados. Quando as atualizações automáticas estiverem desativadas, clique em atualizar para executar ou atualizar o relatório.

### Ferramenta de pesquisa

A pesquisa é representada por um ícone de lupa genérico (não mostrado). O campo de pesquisa fica oculto até que você clique nos rótulos de seleção no lado esquerdo da tela. A tabela abaixo descreve a localização da ferramenta de pesquisa para cada relatório.

| Relatório | Para encontrar a pesquisa, passe o mouse sobre o |
|---|---|
| [!UICONTROL Delivery and Performance] relatório | O rótulo «Nome do anunciante». |
| [!UICONTROL Overlap] relatórios | O rótulo «Nome da SID». |
