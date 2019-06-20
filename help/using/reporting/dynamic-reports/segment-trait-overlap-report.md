---
description: Retorna dados sobre o número de usuários únicos compartilhados entre um característica específico e um segmento inteiro.
seo-description: Retorna dados sobre o número de usuários únicos compartilhados entre um característica específico e um segmento inteiro.
seo-title: Relatório de sobreposição de segmento por característica
solution: Audience Manager
title: Relatório de sobreposição de segmento por característica
uuid: a 6 b 3 dd 21-332 e -449 f-aa 01-2 beb 47 f 1794 e
translation-type: tm+mt
source-git-commit: 8f2ec880cbbe2f516ebc240a712337dc09c4e7f7

---


# Relatório de sobreposição de segmento por característica{#segment-to-trait-overlap-report}

Retorna dados sobre o número de usuários únicos compartilhados entre um característica específico e um segmento inteiro.

>[!NOTE]
>
>Os relatórios de Sobreposição no Audience Manager seguem os princípios RBAC. You can only see segments and traits from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

<!-- 

c_segment_trait_overlap.xml

 -->

## Visão geral

As an optimization tool, the [!UICONTROL Segment to Trait Overlap] reports helps you build highly focused segments or expand segment reach. Por exemplo, você pode criar segmentos e características focadas com alta sobreposição para atingir um público-alvo específico. No entanto, muita sobreposição pode significar menos usuários únicos (menos alcance). Executar este relatório para ajudar a expandir o alcance, removendo características com muita sobreposição de segmento e substituindo-as por características com menos sobreposição.

### Relatório de exemplo

The following illustration provides a high-level overview of the [!UICONTROL Segment-to-Trait Overlap] report.

![](assets/segment-to-trait-overlap.png)

### Detalhar em pontos de dados individuais

Selecione um ponto individual para exibir detalhes de dados em uma janela pop-up. Suas ações de cliques atualizam automaticamente os dados exibidos no relatório.

## Comparing Segments to Traits {#comparing-segments-to-traits}

Descreve como você pode comparar segmentos e características para obter informações significativas dos resultados.

<!-- 

c_compare_s2t.xml

 -->

### Comparação de características de características e segmentos: Um exemplo

Na primeira vista, pode parecer ilógico comparar segmentos com características e tentar desenhar conclusões dos resultados. Depois de todos, os segmentos e características são diferentes, portanto, como os dados derivados de itens diferentes têm significado? No entanto, nesse caso, não estamos comparando características e segmentos, mas o número de visitantes únicos compartilhados entre eles. A contagem de visitantes únicos compartilhados fornece o valor comum que torna um segmento a comparação característica possível.

O diagrama a seguir ilustra a relação entre uma característica e o segmento ao qual pertence. Nesse caso, temos uma característica com 10 visitantes e um segmento com 1,00visitors visitantes. Eles compartilham 3 visitantes únicos em comum.

![](assets/s2t.png)

A contagem de visitantes únicos é o valor comum e constante compartilhado entre essas classes diferentes de objetos. Como resultado, você pode determinar a relação de visitante único entre eles, da seguinte maneira:

* A característica compartilha 30% de seus visitantes únicos com o segmento (3/10 = 0.30).
* O segmento compartilha 0.3% de seus visitantes únicos com a característica (3/1,000 = 0.003)

### Localizar valor em segmento para comparações de características

Analisar a sobreposição entre características e segmentos pode ajudar a estimar o pool total de visitantes disponível (previsão) ou encontrar segmentos ineficientes com muita sobreposição.

<table id="table_5B211EF95216426299EB20253A5A9C1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso de uso </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Previsão</b> </td> 
   <td colname="col2"> <p>Para determinar o pool de visitantes disponível, soma a diferença entre o total de características (menos sobreposição) e o total do segmento (menos sobreposição). </p> <p>Essa combinação de segmento de segmento pode atingir até 1004 novos usuários. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Encontrar segmentos inconsistentes</b> </td> 
   <td colname="col2"> <p>If a trait is part of an <span class="wintitle"> AND</span> group in a segment definition, the unique visitors who have that trait are already in the segment and not available for adding to the segment. Você pode usar este relatório para encontrar características relevantes com baixa sobreposição e adicioná-las à definição do segmento, aumentando dessa forma o alcance do pool de público-alvo do segmento. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Understanding the Data Filters in the Segment-to-Trait Overlap Report {#data-filters-s2t-report}

Descreve como a característica e o segmento de sobreposição % sliders funcionam.

<!-- 

r_s2t_sliders.xml

 -->

The [!UICONTROL Segment-to-Trait overlap] report lets you use two sliders to filter data by the overlap % by trait or segment.

* **[!UICONTROL Filter Trait Uniques %:]** Os dados de filtros por % de visitantes únicos compartilhados entre a característica e o segmento.
* **[!UICONTROL Filter Segment Uniques Overlap %:]** Os dados de filtros por % de visitantes únicos compartilham entre o segmento e a característica.

### Exemplo

O diagrama a seguir ilustra a diferença entre os únicos de característica % e os únicos de segmento %. Nesse caso, a característica e o segmento compartilham 3 visitantes únicos. Como proporções:

* A característica compartilha 30% de seus visitantes únicos com o segmento (3/10 = 0.30).
* O segmento compartilha 0.3% de seus visitantes únicos com a característica (3/1,000 = 0.003)

![](assets/s2t.png)

## Segment-to-Trait Data Pop Fields Defined {#fields-defined}

Descreve as métricas exibidas na janela pop-up quando você clica em um ponto de dados individual.

<!-- 

r_s2t_data_pop.xml

 -->

The popup for the [!UICONTROL Segment-to-Trait Overlap] report contains the metrics below. Note that the uniques metric in the table represents your *real-time users*.

<table id="table_4AF72754276242FFB11543635B43AD90"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID do segmento</span></b> </td> 
   <td colname="col2"> ID numérica exclusiva para o segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nome do provedor de dados</span></b> </td> 
   <td colname="col2"> Nome do proprietário do segmento. </td> 
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
   <td colname="col1"><b><span class="wintitle"> SID</span></b> </td> 
   <td colname="col2"> ID numérica exclusiva para o segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nome da SID</span></b> </td> 
   <td colname="col2"> Nome do segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sobreposição de Únicos Únicos %</span></b> </td> 
   <td colname="col2"> % de visitantes únicos que uma característica compartilha com o segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sobreposição de Únicos de Segmento %</span></b> </td> 
   <td colname="col2"> % de visitantes únicos que um segmento compartilha com uma característica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sobreposições de sobreposição</span></b> </td> 
   <td colname="col2"> Número de visitantes únicos compartilhados entre o segmento e a característica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Únicos de segmento</span></b> </td> 
   <td colname="col2"> Número de visitantes únicos no segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Únicos de característica</span></b> </td> 
   <td colname="col2"> Número de visitantes únicos na característica. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Filtrar resultados do relatório com os controles deslizantes de dados](../../reporting/dynamic-reports/data-sliders.md)
>* [Formas, cores e tamanhos usados em relatórios interativos](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Ícones de relatório e ferramentas explicadas](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Relatórios de sobreposição: Atualização do agendamento e tamanho mínimo do segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Amostragem de dados e taxas de erro nos relatórios do Audience Manager selecionados…](../../reporting/report-sampling.md)
>* [Arquivos CSV para relatórios de sobreposição](../../reporting/dynamic-reports/overlap-csv-files.md)