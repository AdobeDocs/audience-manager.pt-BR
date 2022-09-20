---
description: Retorna dados sobre o número de usuários únicos compartilhados entre todas as suas características originais e de terceiros.
seo-description: Returns data on the number of unique users shared among all your first and third-party traits.
seo-title: Trait-to-Trait Overlap Report
solution: Audience Manager
title: Relatório de sobreposição de característica por característica
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
feature: Overlap Reports
exl-id: cbc933bb-f2af-4ad0-8eb9-cbec1ee952e0
source-git-commit: 6cc1351c3a84d4d2219f33ef6175f182b9641377
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 7%

---

# Relatório de sobreposição de característica por característica{#trait-to-trait-overlap-report}

Retorna dados sobre o número de usuários únicos compartilhados entre todas as suas características originais e de terceiros.

>[!NOTE]
>
>Os relatórios de sobreposição em Audience Manager seguem os princípios do RBAC. Você só pode ver características de fontes de dados às quais tem acesso com base no [Grupo de usuários RBAC](/help/using/features/administration/administration-overview.md) a que você pertence.

<!-- 

c_overlap_reports.xml

 -->

## Visão geral

O [!UICONTROL Trait-to-Trait Overlap] retorna dados sobre a % de usuários únicos compartilhados entre todas as suas características e características de terceiros. Como ferramenta de otimização, este relatório ajuda a:

* Crie segmentos com sobreposição alta ou baixa, dependendo de suas necessidades. Características com alta sobreposição fornecem um público-alvo direcionado, mas menos visitantes únicos. Características com baixa sobreposição podem ser úteis para alcançar um conjunto de visitantes único e maior.
* Validar dados de características de terceiros: A forte sobreposição entre características semelhantes originais e de terceiros sugere que a característica do seu parceiro de dados é precisa e confiável. Por outro lado, a baixa sobreposição pode indicar que uma característica de terceiros pode não conter realmente as mesmas informações que sua própria característica primária semelhante.
* Encontre uma sobreposição inesperada entre características e use essas informações para criar segmentos inovadores.

## Relatório de exemplo

A ilustração a seguir fornece uma visão geral de alto nível dos elementos na [!UICONTROL Trait-to-Trait Overlap] relatório.

>[!NOTE]
>
>O [!UICONTROL Trait-to-Trait Overlap] relatório retorna um campo vazio quando compara a mesma característica a si mesmo.

>[!NOTE]
>
>As características da pasta não estão disponíveis para comparação nos relatórios de sobreposição de característica por característica. Ao criar um segmento utilizando uma característica de pasta específica, é possível realizar análises através do [relatório de sobreposição de segmento por característica](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md).

![](assets/trait-to-trait-overlap.png)

## Detalhar em pontos de dados individuais

Selecione um ponto individual para exibir os detalhes dos dados em uma janela pop-up. As ações de clique atualizam automaticamente os dados exibidos no relatório.

## Campos de Pop de Dados de Sobreposição de Característica por Característica Definidos {#field-definitions}

Descreve as métricas exibidas na janela pop-up quando você clica em um ponto de dados individual.

<!-- 

r_t2t_data_pop.xml

 -->

O pop-up para o [!UICONTROL Trait-to-Trait Overlap] contém as métricas abaixo. Observe que a métrica de únicos na tabela representa a *usuários em tempo real*.

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> % de sobreposição</span></b> </td> 
   <td colname="col2"> Mostra a % de sobreposição exclusiva entre características comparadas (únicos de sobreposição/únicos de característica). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Tipo de fonte de dados</span></b> </td> 
   <td colname="col2">Define o tipo de fonte de dados à qual uma característica pertence. Pode ser: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Primários (sua própria característica). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Terceiros (de um parceiro/fornecedor de dados externo). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID de característica sobreposta</span></b> </td> 
   <td colname="col2"> ID numérica exclusiva para a característica de sobreposição. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sobreposição do nome da característica</span></b> </td> 
   <td colname="col2"> Nome da característica sobreposta. </td> 
  </tr>
    <tr> 
   <td colname="col1"><b><span class="wintitle"> ID de característica 2</span></b> </td> 
   <td colname="col2"> ID numérica exclusiva para a característica na fonte de dados base. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nome da característica 2</span></b> </td> 
   <td colname="col2"> Nome da característica na fonte de dados base. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sobreposição de Uniques</span></b> </td> 
   <td colname="col2"> <p>Para obter a % de sobreposição, o Audience Manager usa a seguinte fórmula:</p> <p>Sobreposição de únicos / (Únicos de característica base + Únicos de característica sobreposta - Únicos sobrepostos)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sobreposição de características únicas</span></b> </td> 
   <td colname="col2"> O número de visitantes únicos da característica sobreposta. </td> 
  </tr> 
    <tr> 
   <td colname="col1"><b><span class="wintitle"> Únicos de características básicas</span></b> </td> 
   <td colname="col2"> O número de visitantes únicos da característica básica. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtrar resultados do relatório com os controles deslizantes de dados](../../reporting/dynamic-reports/data-sliders.md)
>* [Formas, cores e tamanhos usados em relatórios dinâmicos](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Explicação dos ícones e ferramentas do relatório](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Relatórios de sobreposição: Atualizar agendamento e tamanho mínimo do segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Amostragem de dados e taxas de erro em alguns relatórios do Audience Manager...](../../reporting/report-sampling.md)
>* [Arquivos CSV para relatórios de sobreposição](../../reporting/dynamic-reports/overlap-csv-files.md)

