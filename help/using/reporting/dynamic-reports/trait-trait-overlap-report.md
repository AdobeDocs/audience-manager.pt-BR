---
description: Retorna dados sobre o número de usuários únicos compartilhados entre todas as suas características originais e de terceiros.
seo-description: Retorna dados sobre o número de usuários únicos compartilhados entre todas as suas características originais e de terceiros.
seo-title: Relatório de sobreposição de característica por característica
solution: Audience Manager
title: Relatório de sobreposição de característica por característica
uuid: 7 fb 3 fc 9 e -0 e 0 b -492 a -9 c 3 a -04356 afb 19 c 7
translation-type: tm+mt
source-git-commit: 4dc8aad623198cbc24c5c76ac3818d7ee00e9a5e

---


# Relatório de sobreposição de característica por característica{#trait-to-trait-overlap-report}

Retorna dados sobre o número de usuários únicos compartilhados entre todas as suas características originais e de terceiros.

>[!NOTE]
>
>Os relatórios de Sobreposição no Audience Manager seguem os princípios RBAC. You can only see traits from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

<!-- 

c_overlap_reports.xml

 -->

## Visão geral

The [!UICONTROL Trait-to-Trait Overlap] report returns data on the % of unique users shared between all your own traits and your third-party traits. Como ferramenta de otimização, este relatório ajuda você a:

* Crie segmentos com sobreposição alta ou baixa, dependendo de suas necessidades. As características com alta sobreposição proporcionam um público-alvo direcionado, mas menos visitantes únicos. As características com baixa sobreposição podem ser úteis para atingir um conjunto de visitantes maior e único.
* Validar dados de características de terceiros: A sobreposição forte entre características semelhantes e de terceiros similares sugere que a característica do seu parceiro de dados seja precisa e confiável. Por outro lado, a baixa sobreposição pode indicar que uma característica de terceiros pode não conter realmente as mesmas informações que o seu próprio caractere primário semelhante.
* Encontre sobreposição inesperada entre as características e use essas informações para criar segmentos inovadores.

## Relatório de exemplo

The following illustration provides a high-level overview of elements in the [!UICONTROL Trait-to-Trait Overlap] report.

>[!NOTE]
>
>The [!UICONTROL Trait-to-Trait Overlap] report returns an empty field when it compares the same trait to itself.

![](assets/trait-to-trait-overlap.png)

## Detalhar em pontos de dados individuais

Selecione um ponto individual para exibir detalhes de dados em uma janela pop-up. Suas ações de cliques atualizam automaticamente os dados exibidos no relatório.

## Trait-to-Trait Overlap Data Pop Fields Defined {#field-definitions}

Descreve as métricas exibidas na janela pop-up quando você clica em um ponto de dados individual.

<!-- 

r_t2t_data_pop.xml

 -->

The popup for the [!UICONTROL Trait-to-Trait Overlap] report contains the metrics below. Note that the uniques metric in the table represents your *real-time users*.

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nome do provedor de dados</span></b> </td> 
   <td colname="col2"> Nome do proprietário da característica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Tipo de provedor de dados</span></b> </td> 
   <td colname="col2">Define o tipo de provedor ao qual uma característica pertence. Pode ser: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Próprio (sua própria característica). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Terceiros (de um parceiro/fornecedor de dados externos). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID de característica</span></b> </td> 
   <td colname="col2"> ID numérica exclusiva para essa característica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nome da característica</span></b> </td> 
   <td colname="col2"> Nome da característica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sobreposição %</span></b> </td> 
   <td colname="col2"> Mostra o % da sobreposição exclusiva entre as características comparadas (sobreposições exclusivas/únicos de características). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sobreposições de sobreposição</span></b> </td> 
   <td colname="col2"> <p>Para obter a sobreposição %, o Audience Manager usa a seguinte fórmula:</p> <p>Sobreposições de únicos/(Únicos de segmento base + Sobreposição de segmentos sobrepostos - Sobreposição Únicos)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Únicos de característica</span></b> </td> 
   <td colname="col2"> O número de visitantes únicos na característica. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Filtrar resultados do relatório com os controles deslizantes de dados](../../reporting/dynamic-reports/data-sliders.md)
>* [Formas, cores e tamanhos usados em relatórios dinâmicos](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Ícones de relatório e ferramentas explicadas](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Relatórios de sobreposição: Atualização do agendamento e tamanho mínimo do segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Amostragem de dados e taxas de erro nos relatórios do Audience Manager selecionados…](../../reporting/report-sampling.md)
>* [Arquivos CSV para relatórios de sobreposição](../../reporting/dynamic-reports/overlap-csv-files.md)