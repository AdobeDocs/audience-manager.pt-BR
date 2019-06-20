---
description: Retorna dados sobre quantos usuários únicos são compartilhados entre seus segmentos.
seo-description: Retorna dados sobre quantos usuários únicos são compartilhados entre seus segmentos.
seo-title: Relatório de sobreposição de segmento por segmento
solution: Audience Manager
title: Relatório de sobreposição de segmento por segmento
uuid: 0339 eb 6 c -6355-44 a 3-9 c 46-f 159485449 d 1
translation-type: tm+mt
source-git-commit: 339d5550b22949862415d2abc812217e5479c993

---


# Relatório de sobreposição de segmento por segmento{#segment-to-segment-overlap-report}

Retorna dados sobre quantos usuários únicos são compartilhados entre seus segmentos.

>[!NOTE]
>
>Os relatórios de Sobreposição no Audience Manager seguem os princípios RBAC. You can only see segments from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

<!-- 

c_segment_segment_overlap.xml

 -->

## Visão geral

The [!UICONTROL Segment-to-Segment Overlap] report can help you:

* Identifique segmentos com sobreposição alta ou baixa, dependendo de suas necessidades. As características com alta sobreposição proporcionam um público-alvo direcionado, mas menos visitantes únicos. As características com baixa sobreposição podem ser úteis para atingir um conjunto de visitantes maior e único.
* Encontre sobreposição inesperada e use essas informações para criar segmentos novos e de alto desempenho.

## Relatório de exemplo

The following illustration provides a high-level overview of the [!UICONTROL Segment-to-Segment Overlap] report.

>[!NOTE]
>
>The [!UICONTROL Segment-to-Segment Overlap] report returns an empty field when it compares the same segment to itself.

![](assets/segment-to-segment-overlap.png)

## Detalhar em pontos de dados individuais

Selecione um ponto individual para exibir detalhes de dados em uma janela pop-up. Suas ações de cliques atualizam automaticamente os dados exibidos no relatório.

## Segment-to-Segment Overlap Data Pop Fields Defined {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

The popup for the [!UICONTROL Segment-to-Segment Overlap] report contains the metrics below. Note that the uniques metric in the table represents your *real-time users*.

| Métrica | Descrição |
|---|---|
| **[!UICONTROL Segment ID1]** | ID numérica exclusiva para o segmento que aparece nos resultados do relatório. Aparece como a ID da linha do segmento. |
| **[!UICONTROL Segment ID2]** | ID numérica exclusiva para o segmento selecionado ao executar o relatório. Aparece como a ID da coluna do segmento. |
| **[!UICONTROL Segment Name1]** | Nome do segmento que aparece na linha de resultados do relatório. |
| **[!UICONTROL Segment Name2]** | Nome do segmento selecionado ao executar o relatório. Aparece na coluna de resultados do relatório. |
| **[!UICONTROL Overlap %]** | Para obter a sobreposição %, o Audience Manager usa a seguinte fórmula: Sobreposições de únicos/(Únicos de segmento base + Sobreposição de segmentos sobrepostos - Sobreposição Únicos) |
| **[!UICONTROL Overlap Uniques]** | O número de visitantes únicos compartilhados entre os segmentos comparados. |
| **[!UICONTROL Segment Uniques1]** | O número de visitantes únicos no segmento 1. |
| **[!UICONTROL Segment Uniques2]** | O número de visitantes únicos no segmento 2. |

>[!MORE_ LIKE_ THIS]
>
>* [Filtrar resultados do relatório com os controles deslizantes de dados](../../reporting/dynamic-reports/data-sliders.md)
>* [Formas, cores e tamanhos usados em relatórios interativos](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Ícones de relatório e ferramentas explicadas](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Relatórios de sobreposição: Atualização do agendamento e tamanho mínimo do segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Amostragem de dados e taxas de erro nos relatórios do Audience Manager selecionados…](../../reporting/report-sampling.md)
>* [Arquivos CSV para relatórios de sobreposição](../../reporting/dynamic-reports/overlap-csv-files.md)