---
description: Retorna dados sobre o número de usuários únicos compartilhados entre uma característica específica e um segmento inteiro.
seo-description: Retorna dados sobre o número de usuários únicos compartilhados entre uma característica específica e um segmento inteiro.
seo-title: Relatório de sobreposição de segmento por característica
solution: Audience Manager
title: Relatório de sobreposição de segmento por característica
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
feature: overlap reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 5%

---


# Relatório de sobreposição de segmento por característica{#segment-to-trait-overlap-report}

Retorna dados sobre o número de usuários únicos compartilhados entre uma característica específica e um segmento inteiro.

>[!NOTE]
>
>Os relatórios de sobreposição em Audience Manager seguem os princípios do RBAC. Você só pode ver segmentos e características de fontes de dados às quais você tem acesso com base no Grupo [de usuários](/help/using/features/administration/administration-overview.md) RBAC ao qual você pertence.

<!-- 

c_segment_trait_overlap.xml

 -->

## Visão geral

Como ferramenta de otimização, os [!UICONTROL Segment to Trait Overlap] relatórios ajudam a criar segmentos altamente focados ou a expandir o alcance dos segmentos. Por exemplo, é possível criar segmentos focados e características com alta sobreposição para atingir uma audiência específica. No entanto, muitas sobreposições podem significar menos usuários únicos (menos alcance). Executar este relatório para ajudar a expandir o alcance, removendo características com muita sobreposição de segmentos e substituindo-as por características que têm menos sobreposição.

### Relatório de exemplo

A ilustração a seguir fornece uma visão geral de alto nível do [!UICONTROL Segment-to-Trait Overlap] relatório.

![](assets/segment-to-trait-overlap.png)

### Detalhar pontos de dados individuais

Selecione um ponto individual para visualização de detalhes de dados em uma janela pop-up. As ações de clique atualizam automaticamente os dados exibidos no relatório.

## Comparação de segmentos a características {#comparing-segments-to-traits}

Descreve como você pode comparar segmentos e características para obter informações significativas a partir dos resultados.

<!-- 

c_compare_s2t.xml

 -->

### Comparando características e únicos de segmentos: Um exemplo

À primeira vista, pode parecer ilógico comparar segmentos a características e tentar tirar conclusões dos resultados. Afinal, segmentos e características são diferentes, então como os dados derivados de itens diferentes podem ter significado? Entretanto, neste caso, não estamos comparando características e segmentos, mas o número de visitantes únicos compartilhados entre eles. A contagem de visitantes exclusivos compartilhados fornece o valor comum que torna possível a comparação entre um segmento e uma característica.

O diagrama a seguir ilustra a relação entre uma característica e o segmento ao qual ela pertence. Neste caso, temos um traço com 10 visitantes e um segmento com 1.000 visitantes. Eles compartilham três visitantes únicos em comum.

![](assets/s2t.png)

A contagem exclusiva de visitantes é o valor comum e constante compartilhado entre essas diferentes classes de objetos. Como resultado, você pode determinar a relação de visitante exclusiva entre eles da seguinte forma:

* A característica compartilha 30% de seus visitantes únicos com o segmento (3/10 = 0,30).
* O segmento compartilha 0,3% de seus visitantes únicos com a característica (3/1. 000 = 0,003)

### Encontrar valor em comparação entre segmento e característica

Analisar a sobreposição entre características e segmentos pode ajudar a estimar o conjunto total de visitantes disponíveis (previsão) ou localizar segmentos ineficientes com sobreposição excessiva.

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
   <td colname="col2"> <p>Para determinar o pool de visitantes disponível, soma a diferença entre o total da característica (menos sobreposição) e o total do segmento (menos sobreposição). </p> <p>Essa combinação segmento-característica pode atingir até 1004 novos usuários. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Localizar segmentos ineficientes</b> </td> 
   <td colname="col2"> <p>Se uma característica faz parte de um grupo <span class="wintitle"> AND</span> em uma definição de segmento, os visitantes exclusivos que têm essa característica já estão no segmento e não estão disponíveis para adição ao segmento. Você pode usar esse relatório para encontrar características relevantes com baixa sobreposição e adicioná-las à definição do segmento, aumentando assim o alcance desse pool de audiências de segmentos. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Como entender os Filtros de dados no relatório de sobreposição entre segmentos e características {#data-filters-s2t-report}

Descreve como os controles deslizantes % de sobreposição exclusiva de características e segmentos funcionam.

<!-- 

r_s2t_sliders.xml

 -->

O [!UICONTROL Segment-to-Trait overlap] relatório permite que você use dois controles deslizantes para filtrar os dados pela % de sobreposição por característica ou segmento.

* **[!UICONTROL Filter Trait Uniques %:]** Dados de Filtros por % de visitantes únicos compartilhados entre a característica e o segmento.
* **[!UICONTROL Filter Segment Uniques Overlap %:]** Dados de Filtros por % de visitantes únicos compartilhados entre o segmento e a característica.

### Exemplo

O diagrama a seguir ilustra a diferença entre os únicos de característica % e os únicos de segmento %. Nesse caso, a característica e o segmento compartilham 3 visitantes únicos. Como proporções:

* A característica compartilha 30% de seus visitantes únicos com o segmento (3/10 = 0,30).
* O segmento compartilha 0,3% de seus visitantes únicos com a característica (3/1. 000 = 0,003)

![](assets/s2t.png)

## Campos de Pop de Dados Segmento para Caractere Definidos {#fields-defined}

Descreve as métricas exibidas na janela pop-up quando você clica em um ponto de dados individual.

<!-- 

r_s2t_data_pop.xml

 -->

O pop-up do [!UICONTROL Segment-to-Trait Overlap] relatório contém as métricas abaixo. Observe que a métrica de únicos na tabela representa seus usuários *em tempo* real.

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
   <td colname="col2"> ID numérica exclusiva do segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Fonte de Dados de Características </span></b> </td> 
   <td colname="col2"> Nome do proprietário da característica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Tipo de fonte de dados</span></b> </td> 
   <td colname="col2">Define o tipo de provedor ao qual uma característica pertence. Pode ser: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Primeiro partido (seu próprio traço). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Terceiros (de um parceiro/fornecedor externo de dados). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID da característica</span></b> </td> 
   <td colname="col2"> ID numérica exclusiva da característica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nome da característica</span></b> </td> 
   <td colname="col2"> Nome do traço. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> % de sobreposição de características únicas</span></b> </td> 
   <td colname="col2"> % de visitantes únicos que uma característica compartilha com o segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> % de sobreposição de segmentos únicos</span></b> </td> 
   <td colname="col2"> % de visitantes únicos compartilhados por um segmento com uma característica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sobreposição de únicos</span></b> </td> 
   <td colname="col2"> Número de visitantes únicos compartilhados entre o segmento e a característica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Únicos do segmento</span></b> </td> 
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