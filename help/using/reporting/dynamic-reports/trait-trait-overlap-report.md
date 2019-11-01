---
description: Retorna dados sobre o número de usuários únicos compartilhados entre todas as suas características originais e de terceiros.
seo-description: Retorna dados sobre o número de usuários únicos compartilhados entre todas as suas características originais e de terceiros.
seo-title: Relatório de sobreposição de característica por característica
solution: Audience Manager
title: Relatório de sobreposição de característica por característica
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Relatório de sobreposição de característica por característica{#trait-to-trait-overlap-report}

Retorna dados sobre o número de usuários únicos compartilhados entre todas as suas características originais e de terceiros.

>[!NOTE]
>
>Os relatórios de sobreposição no Audience Manager seguem os princípios do RBAC. Você só pode ver características de fontes de dados às quais você tem acesso com base no Grupo [de usuários](/help/using/features/administration/administration-overview.md) RBAC ao qual você pertence.

<!-- 

c_overlap_reports.xml

 -->

## Visão geral

O [!UICONTROL Trait-to-Trait Overlap] relatório retorna dados sobre a % de usuários únicos compartilhados entre todas as suas características e as de terceiros. Como ferramenta de otimização, este relatório ajuda você a:

* Crie segmentos com sobreposição alta ou baixa, dependendo de suas necessidades. Características com alta sobreposição oferecem um público-alvo direcionado, mas menos visitantes únicos. Características com baixa sobreposição podem ser úteis para alcançar um conjunto de visitantes maior e único.
* Validar dados de características de terceiros: Uma forte sobreposição entre características semelhantes de terceiros e originais sugere que a característica do seu parceiro de dados é precisa e confiável. Por outro lado, a baixa sobreposição pode indicar que uma característica de terceiros pode não conter as mesmas informações que a sua própria característica primária, semelhante.
* Encontre sobreposições inesperadas entre características e use essas informações para criar segmentos inovadores.

## Relatório de exemplo

A ilustração a seguir fornece uma visão geral de alto nível dos elementos no [!UICONTROL Trait-to-Trait Overlap] relatório.

>[!NOTE]
>
>O [!UICONTROL Trait-to-Trait Overlap] relatório retorna um campo vazio quando compara o mesmo traço a si mesmo.

![](assets/trait-to-trait-overlap.png)

## Detalhar pontos de dados individuais

Selecione um ponto individual para exibir detalhes de dados em uma janela pop-up. As ações de clique atualizam automaticamente os dados exibidos no relatório.

## Campos de Pop-Pop de Dados de Sobreposição de Característica para Traço Definidos {#field-definitions}

Descreve as métricas exibidas na janela pop-up quando você clica em um ponto de dados individual.

<!-- 

r_t2t_data_pop.xml

 -->

O pop-up do [!UICONTROL Trait-to-Trait Overlap] relatório contém as métricas abaixo. Observe que a métrica de únicos na tabela representa seus usuários *em tempo* real.

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
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Primeiro partido (seu próprio traço). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Terceiros (de um parceiro/fornecedor externo de dados). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID da característica</span></b> </td> 
   <td colname="col2"> ID numérica exclusiva para essa característica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nome da característica</span></b> </td> 
   <td colname="col2"> Nome do traço. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> % de sobreposição</span></b> </td> 
   <td colname="col2"> Mostra a % de sobreposição exclusiva entre características comparadas (únicos de sobreposição/únicos de características). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sobreposição de únicos</span></b> </td> 
   <td colname="col2"> <p>Para obter a % de sobreposição, o Audience Manager usa a seguinte fórmula:</p> <p>Únicos sobrepostos / (Únicos do segmento base + Únicos do segmento sobrepostos - Únicos sobrepostos)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Características únicas</span></b> </td> 
   <td colname="col2"> O número de visitantes únicos na característica. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtrar resultados do relatório com os controles deslizantes de dados](../../reporting/dynamic-reports/data-sliders.md)
>* [Formas, cores e tamanhos usados em relatórios dinâmicos](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Explicação dos ícones e ferramentas do relatório](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Relatórios de sobreposição: Atualizar agendamento e tamanho mínimo do segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Amostragem de dados e taxas de erro nos relatórios selecionados do Audience Manager...](../../reporting/report-sampling.md)
>* [Arquivos CSV para relatórios de sobreposição](../../reporting/dynamic-reports/overlap-csv-files.md)