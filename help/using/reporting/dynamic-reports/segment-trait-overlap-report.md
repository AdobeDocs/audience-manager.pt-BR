---
description: Retorna dados sobre o número de usuários únicos compartilhados entre uma característica específica e um segmento inteiro.
seo-description: Retorna dados sobre o número de usuários únicos compartilhados entre uma característica específica e um segmento inteiro.
seo-title: Relatório de sobreposição de segmento por característica
solution: Audience Manager
title: Relatório de sobreposição de segmento por característica
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
feature: Overlap Reports
exl-id: 7ce3dd2d-ab22-46f8-90bf-a32222df2e76
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 5%

---

# Relatório de sobreposição de segmento por característica{#segment-to-trait-overlap-report}

Retorna dados sobre o número de usuários únicos compartilhados entre uma característica específica e um segmento inteiro.

>[!NOTE]
>
>Os relatórios de sobreposição em Audience Manager seguem os princípios do RBAC. Você só pode ver segmentos e características de fontes de dados às quais você tem acesso com base no [Grupo de usuários RBAC](/help/using/features/administration/administration-overview.md) ao qual você pertence.

<!-- 

c_segment_trait_overlap.xml

 -->

## Visão geral

Como ferramenta de otimização, os relatórios [!UICONTROL Segment to Trait Overlap] ajudam a criar segmentos altamente focados ou a expandir o alcance do segmento. Por exemplo, você pode criar segmentos focados e características com alta sobreposição para atingir um público-alvo específico. No entanto, muitas sobreposições podem significar menos usuários únicos (menos alcance). Executar esse relatório para ajudar a expandir o alcance removendo características com muita sobreposição de segmentos e substituindo-as por características que têm menos sobreposição.

### Relatório de exemplo

A ilustração a seguir fornece uma visão geral de alto nível do relatório [!UICONTROL Segment-to-Trait Overlap].

![](assets/segment-to-trait-overlap.png)

### Detalhar em pontos de dados individuais

Selecione um ponto individual para exibir os detalhes dos dados em uma janela pop-up. As ações de clique atualizam automaticamente os dados exibidos no relatório.

## Comparação de segmentos com características {#comparing-segments-to-traits}

Descreve como você pode comparar segmentos e características para obter informações significativas a partir dos resultados.

<!-- 

c_compare_s2t.xml

 -->

### Comparação de características e únicos de segmentos: Um exemplo

À primeira vista, pode parecer ilógico comparar segmentos a características e tentar tirar conclusões dos resultados. Afinal, segmentos e características são diferentes, então como os dados derivados de itens diferentes podem ter significado? No entanto, nesse caso, não estamos comparando características e segmentos, mas o número de visitantes únicos compartilhados entre eles. A contagem de visitantes únicos compartilhados fornece o valor comum que torna possível uma comparação de características de um segmento.

O diagrama a seguir ilustra a relação entre uma característica e o segmento ao qual ela pertence. Nesse caso, temos uma característica com 10 visitantes e um segmento com 1.000 visitantes. Eles compartilham três visitantes únicos em comum.

![](assets/s2t.png)

A contagem de visitantes únicos é o valor comum e constante compartilhado entre essas diferentes classes de objetos. Como resultado, você pode determinar a relação de visitante único entre eles da seguinte maneira:

* A característica compartilha 30% de seus visitantes únicos com o segmento (3/10 = 0,30).
* O segmento compartilha 0,3% de seus visitantes únicos com a característica (3/1. 000 = 0,003)

### Localizar valor no segmento para comparações de características

Observar a sobreposição entre características e segmentos pode ajudar a estimar o conjunto de visitantes disponíveis (previsão) ou encontrar segmentos ineficientes com sobreposição excessiva.

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
   <td colname="col2"> <p>Para determinar o conjunto de visitantes disponível, some a diferença entre o total de características (menos sobreposição) e o total do segmento (menos sobreposição). </p> <p>Essa combinação de características de segmento pode alcançar até 1004 novos usuários. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Encontrar segmentos ineficientes</b> </td> 
   <td colname="col2"> <p>Se uma característica faz parte de um grupo <span class="wintitle"> AND</span> em uma definição de segmento, os visitantes únicos que têm essa característica já estão no segmento e não estão disponíveis para adição ao segmento. Você pode usar esse relatório para encontrar características relevantes com baixa sobreposição e adicioná-las à definição do segmento, aumentando assim o alcance desse público-alvo. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Como entender os filtros de dados no relatório de sobreposição de segmento por característica {#data-filters-s2t-report}

Descreve como funcionam os % de controles deslizantes de sobreposição de característica e segmento exclusivo.

<!-- 

r_s2t_sliders.xml

 -->

O relatório [!UICONTROL Segment-to-Trait overlap] permite usar dois controles deslizantes para filtrar dados pela % de sobreposição por característica ou segmento.

* **[!UICONTROL Filter Trait Uniques %:]** Filtra os dados pela % de visitantes únicos compartilhados entre a característica e o segmento.
* **[!UICONTROL Filter Segment Uniques Overlap %:]** Filtra os dados pela % de visitantes únicos compartilhados entre o segmento e a característica.

### Exemplo

O diagrama a seguir ilustra a diferença entre as características únicas % e as % únicas do segmento. Nesse caso, a característica e o segmento compartilham três visitantes únicos. Como proporções:

* A característica compartilha 30% de seus visitantes únicos com o segmento (3/10 = 0,30).
* O segmento compartilha 0,3% de seus visitantes únicos com a característica (3/1. 000 = 0,003)

![](assets/s2t.png)

## Campos de Pop de Dados de Segmento para Característica Definidos {#fields-defined}

Descreve as métricas exibidas na janela pop-up quando você clica em um ponto de dados individual.

<!-- 

r_s2t_data_pop.xml

 -->

O pop-up do relatório [!UICONTROL Segment-to-Trait Overlap] contém as métricas abaixo. Observe que a métrica de únicos na tabela representa seus *usuários em tempo real*.

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
   <td colname="col1"><b><span class="wintitle"> Fonte de dados da característica  </span></b> </td> 
   <td colname="col2"> Nome do proprietário da característica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Tipo de fonte de dados</span></b> </td> 
   <td colname="col2">Define o tipo de provedor ao qual uma característica pertence. Pode ser: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Primários (sua própria característica). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Terceiros (de um parceiro/fornecedor de dados externo). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID da característica</span></b> </td> 
   <td colname="col2"> ID numérica exclusiva para a característica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nome da característica</span></b> </td> 
   <td colname="col2"> Nome da característica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> % de sobreposição de características únicas</span></b> </td> 
   <td colname="col2"> % de visitantes únicos que uma característica compartilha com o segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> % de sobreposição de segmentos únicos</span></b> </td> 
   <td colname="col2"> % de visitantes únicos que um segmento compartilha com uma característica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sobreposição de Uniques</span></b> </td> 
   <td colname="col2"> Número de visitantes únicos compartilhados entre o segmento e a característica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Segmento único</span></b> </td> 
   <td colname="col2"> Número de visitantes únicos no segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Características únicas</span></b> </td> 
   <td colname="col2"> Número de visitantes únicos na característica. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtrar resultados do relatório com os controles deslizantes de dados](../../reporting/dynamic-reports/data-sliders.md)
>* [Formas, cores e tamanhos usados em relatórios interativos](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Explicação dos ícones e ferramentas do relatório](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Relatórios de sobreposição: Atualizar agendamento e tamanho mínimo do segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Amostragem de dados e taxas de erro em alguns relatórios do Audience Manager...](../../reporting/report-sampling.md)
>* [Arquivos CSV para relatórios de sobreposição](../../reporting/dynamic-reports/overlap-csv-files.md)

