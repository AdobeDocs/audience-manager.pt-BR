---
description: Retorna dados sobre quantos usuários únicos são compartilhados entre seus segmentos.
seo-description: Returns data on how many unique users are shared between your segments.
seo-title: Segment-to-Segment Overlap Report
solution: Audience Manager
title: Relatório de sobreposição de segmento por segmento
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
feature: Overlap Reports
exl-id: 43a8ea20-3197-4623-a03a-bfe40e5049cd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 6%

---

# Relatório de sobreposição de segmento por segmento{#segment-to-segment-overlap-report}

Retorna dados sobre quantos usuários únicos são compartilhados entre seus segmentos.

>[!NOTE]
>
>Os relatórios de sobreposição no Audience Manager seguem os princípios do RBAC. Você só pode ver segmentos de fontes de dados às quais você tem acesso com base no [Grupo de Usuários RBAC](/help/using/features/administration/administration-overview.md) ao qual você pertence.

<!-- 

c_segment_segment_overlap.xml

 -->

## Visão geral

O relatório [!UICONTROL Segment-to-Segment Overlap] pode ajudá-lo a:

* Identifique segmentos com sobreposição alta ou baixa, dependendo das suas necessidades. As características com alta sobreposição fornecem um público-alvo direcionado, mas com menos visitantes únicos. Características com baixa sobreposição podem ser úteis para atingir um conjunto maior e exclusivo de visitantes.
* Encontre sobreposições inesperadas e use essas informações para criar segmentos novos e de alto desempenho.

## Exemplo de relatório

A ilustração a seguir fornece uma visão geral de alto nível do relatório [!UICONTROL Segment-to-Segment Overlap].

>[!NOTE]
>
>O relatório [!UICONTROL Segment-to-Segment Overlap] retorna um campo vazio quando compara o mesmo segmento a si mesmo.

![](assets/segment-to-segment-overlap.png)

## Analisar Pontos de Dados Individuais

Selecione um ponto individual para ver os detalhes dos dados em uma janela pop-up. Suas ações de clique atualizam automaticamente os dados exibidos no relatório.

## Campos Pop De Dados De Sobreposição De Segmento Por Segmento Definidos {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

O pop-up para o relatório [!UICONTROL Segment-to-Segment Overlap] contém as métricas abaixo. Observe que a métrica única na tabela representa seus *usuários em tempo real*.

| Métrica | Descrição |
|---|---|
| **[!UICONTROL Base Segment ID]** | ID numérica exclusiva do segmento que aparece nos resultados do relatório. Aparece como a ID da linha para o segmento. |
| **[!UICONTROL Base Segment Name]** | Nome do segmento que aparece na linha de resultados do relatório. |
| **[!UICONTROL Overlapping Segment ID]** | ID numérica exclusiva para o segmento selecionado ao executar o relatório. Aparece como a ID da coluna para o segmento. |
| **[!UICONTROL Overlapping Segment Name]** | Nome do segmento selecionado ao executar o relatório. Aparece na coluna de resultados do relatório. |
| **[!UICONTROL Base Segment Uniques]** | O número de visitantes únicos em seu segmento base. |
| **[!UICONTROL Base Segment Uniques]** | O número de visitantes únicos no segmento sobreposto. |
| **[!UICONTROL Overlapping Uniques]** | O número de visitantes únicos compartilhados entre segmentos comparados. |
| **[!UICONTROL Overlap %]** | Para obter a % de sobreposição, o Audience Manager usa a seguinte fórmula: Uniques de sobreposição / (Únicos do segmento base + Únicos do segmento de sobreposição - Únicos de sobreposição) |



>[!MORELIKETHIS]
>
>* [Filtrar resultados do relatório com os controles deslizantes de dados](../../reporting/dynamic-reports/data-sliders.md)
>* [Formas, Cores e Tamanhos Usados em Relatórios Interativos](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Explicação dos Ícones e Ferramentas do Relatório](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Relatórios de sobreposição: Atualizar agendamento e tamanho mínimo do segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Amostragem de Dados e Taxas de Erro em Relatórios Selecionados do Audience Manager...](../../reporting/report-sampling.md)
>* [Arquivos CSV para relatórios de sobreposição](../../reporting/dynamic-reports/overlap-csv-files.md)
