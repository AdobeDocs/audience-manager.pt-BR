---
description: Retorna dados sobre quantos usuários únicos são compartilhados entre seus segmentos.
seo-description: Retorna dados sobre quantos usuários únicos são compartilhados entre seus segmentos.
seo-title: Relatório de sobreposição de segmento por segmento
solution: Audience Manager
title: Relatório de sobreposição de segmento por segmento
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
feature: Relatórios de sobreposição
exl-id: 43a8ea20-3197-4623-a03a-bfe40e5049cd
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 11%

---

# Relatório de sobreposição de segmento por segmento{#segment-to-segment-overlap-report}

Retorna dados sobre quantos usuários únicos são compartilhados entre seus segmentos.

>[!NOTE]
>
>Os relatórios de sobreposição em Audience Manager seguem os princípios do RBAC. Você só pode ver segmentos a partir de fontes de dados às quais você tem acesso com base no [Grupo de usuários RBAC](/help/using/features/administration/administration-overview.md) ao qual você pertence.

<!-- 

c_segment_segment_overlap.xml

 -->

## Visão geral

O relatório [!UICONTROL Segment-to-Segment Overlap] pode ajudá-lo a:

* Identifique segmentos com sobreposição alta ou baixa, dependendo de suas necessidades. Características com alta sobreposição fornecem um público-alvo direcionado, mas menos visitantes únicos. Características com baixa sobreposição podem ser úteis para alcançar um conjunto de visitantes único e maior.
* Encontre sobreposições inesperadas e use essas informações para criar segmentos novos e de alto desempenho.

## Relatório de exemplo

A ilustração a seguir fornece uma visão geral de alto nível do relatório [!UICONTROL Segment-to-Segment Overlap].

>[!NOTE]
>
>O relatório [!UICONTROL Segment-to-Segment Overlap] retorna um campo vazio quando compara o mesmo segmento a ele mesmo.

![](assets/segment-to-segment-overlap.png)

## Detalhar em pontos de dados individuais

Selecione um ponto individual para exibir os detalhes dos dados em uma janela pop-up. As ações de clique atualizam automaticamente os dados exibidos no relatório.

## Campos de Pop de Dados de Sobreposição de Segmento por Segmento Definidos {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

O pop-up do relatório [!UICONTROL Segment-to-Segment Overlap] contém as métricas abaixo. Observe que a métrica de únicos na tabela representa seus *usuários em tempo real*.

| Métrica | Descrição |
|---|---|
| **[!UICONTROL Base Segment ID]** | ID numérica exclusiva para o segmento exibido nos resultados do relatório. Aparece como a ID da linha para o segmento. |
| **[!UICONTROL Base Segment Name]** | Nome do segmento que aparece na linha de resultados do relatório. |
| **[!UICONTROL Overlapping Segment ID]** | ID numérica exclusiva para o segmento selecionado durante a execução do relatório. Aparece como a ID da coluna do segmento. |
| **[!UICONTROL Overlapping Segment Name]** | Nome do segmento selecionado ao executar o relatório. Aparece na coluna de resultados do relatório. |
| **[!UICONTROL Base Segment Uniques]** | O número de visitantes únicos em seu segmento base. |
| **[!UICONTROL Base Segment Uniques]** | O número de visitantes únicos em seu segmento sobreposto. |
| **[!UICONTROL Overlapping Uniques]** | O número de visitantes únicos compartilhados entre segmentos comparados. |
| **[!UICONTROL Overlap %]** | Para obter a % de sobreposição, o Audience Manager usa a seguinte fórmula: Sobreposição de únicos / (Únicos de segmento base + Únicos de segmento sobreposto - Únicos sobrepostos) |



>[!MORELIKETHIS]
>
>* [Filtrar resultados do relatório com os controles deslizantes de dados](../../reporting/dynamic-reports/data-sliders.md)
>* [Formas, cores e tamanhos usados em relatórios interativos](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Explicação dos ícones e ferramentas do relatório](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Relatórios de sobreposição: Atualizar agendamento e tamanho mínimo do segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Amostragem de dados e taxas de erro em alguns relatórios do Audience Manager...](../../reporting/report-sampling.md)
>* [Arquivos CSV para relatórios de sobreposição](../../reporting/dynamic-reports/overlap-csv-files.md)

