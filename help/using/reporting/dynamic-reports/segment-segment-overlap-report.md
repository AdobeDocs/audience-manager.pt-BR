---
description: Retorna dados sobre quantos usuários únicos são compartilhados entre seus segmentos.
seo-description: Retorna dados sobre quantos usuários únicos são compartilhados entre seus segmentos.
seo-title: Relatório de sobreposição de segmento por segmento
solution: Audience Manager
title: Relatório de sobreposição de segmento por segmento
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
translation-type: tm+mt
source-git-commit: 339d5550b22949862415d2abc812217e5479c993

---


# Relatório de sobreposição de segmento por segmento{#segment-to-segment-overlap-report}

Retorna dados sobre quantos usuários únicos são compartilhados entre seus segmentos.

>[!NOTE]
>
>Os relatórios de sobreposição no Audience Manager seguem os princípios do RBAC. Você só pode ver segmentos de fontes de dados às quais você tem acesso com base no Grupo [de usuários](/help/using/features/administration/administration-overview.md) RBAC ao qual você pertence.

<!-- 

c_segment_segment_overlap.xml

 -->

## Visão geral

O [!UICONTROL Segment-to-Segment Overlap] relatório pode ajudá-lo a:

* Identifique segmentos com sobreposição alta ou baixa, dependendo de suas necessidades. Características com alta sobreposição oferecem um público-alvo direcionado, mas menos visitantes únicos. Características com baixa sobreposição podem ser úteis para alcançar um conjunto de visitantes maior e único.
* Encontre sobreposições inesperadas e use essas informações para criar novos segmentos de alto desempenho.

## Relatório de exemplo

A ilustração a seguir fornece uma visão geral de alto nível do [!UICONTROL Segment-to-Segment Overlap] relatório.

>[!NOTE]
>
>O [!UICONTROL Segment-to-Segment Overlap] relatório retorna um campo vazio quando compara o mesmo segmento a si mesmo.

![](assets/segment-to-segment-overlap.png)

## Detalhar pontos de dados individuais

Selecione um ponto individual para exibir detalhes de dados em uma janela pop-up. As ações de clique atualizam automaticamente os dados exibidos no relatório.

## Campos de Pop de Dados de Sobreposição de Segmento a Segmento Definidos {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

O pop-up do [!UICONTROL Segment-to-Segment Overlap] relatório contém as métricas abaixo. Observe que a métrica de únicos na tabela representa seus usuários *em tempo* real.

| Métrica | Descrição |
|---|---|
| **[!UICONTROL Segment ID1]** | ID numérica exclusiva do segmento que aparece nos resultados do relatório. Aparece como a ID da linha para o segmento. |
| **[!UICONTROL Segment ID2]** | ID numérica exclusiva do segmento selecionado ao executar o relatório. Aparece como a ID da coluna do segmento. |
| **[!UICONTROL Segment Name1]** | Nome do segmento que aparece na linha de resultados do relatório. |
| **[!UICONTROL Segment Name2]** | Nome do segmento selecionado ao executar o relatório. Aparece na coluna de resultados do relatório. |
| **[!UICONTROL Overlap %]** | Para obter a % de sobreposição, o Audience Manager usa a seguinte fórmula:Únicos sobrepostos / (Únicos do segmento base + Únicos do segmento sobrepostos - Únicos sobrepostos) |
| **[!UICONTROL Overlap Uniques]** | O número de visitantes únicos compartilhados entre segmentos comparados. |
| **[!UICONTROL Segment Uniques1]** | O número de visitantes únicos no segmento 1. |
| **[!UICONTROL Segment Uniques2]** | O número de visitantes únicos no segmento 2. |

>[!MORE_LIKE_THIS]
>
>* [Filtrar resultados do relatório com os controles deslizantes de dados](../../reporting/dynamic-reports/data-sliders.md)
>* [Formas, cores e tamanhos usados em relatórios interativos](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Explicação dos ícones e ferramentas do relatório](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Relatórios de sobreposição: Atualizar agendamento e tamanho mínimo do segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Amostragem de dados e taxas de erro nos relatórios selecionados do Audience Manager...](../../reporting/report-sampling.md)
>* [Arquivos CSV para relatórios de sobreposição](../../reporting/dynamic-reports/overlap-csv-files.md)