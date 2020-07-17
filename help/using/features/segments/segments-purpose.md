---
description: Descreve segmentos, suas partes constituintes e a criação de regras com o Construtor de segmentos.
seo-description: Descreve segmentos, suas partes constituintes e a criação de regras com o Construtor de segmentos.
seo-title: Finalidade, composição e regras dos segmentos
solution: Audience Manager
title: Finalidade, composição e regras dos segmentos
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 6%

---


# Segmentos: finalidade, composição e regras {#segments-purpose-composition-and-rules}

Descreve [!UICONTROL segments]as partes constituintes e a criação de regras com [!UICONTROL Segment Builder].

## Finalidade da [!UICONTROL Segments]

A *`segment`* (or an *`audience`*) is a set of users who share common attributes. No Audience Manager, você cria [!UICONTROL segments] com regras do lado do servidor. Essas regras permitem que você crie grupos de audiências com base nos atributos de visitante do site, como:

* Comportamento;
* Demografia (idade, gênero, rendimento, etc.);
* Outras características que podem ser definidas na interface do usuário.

## [!UICONTROL Segment] Composição

Um Audience Manager [!UICONTROL segment] é uma regra do lado do servidor que consiste em indivíduos ou grupos de características. As características são compostas de elementos de dados chamados pares de valores chave. Junto com as regras definidas no [!UICONTROL segment] nível, esses pares de valores chave contêm os critérios que qualificam visitantes para características e [!UICONTROL segment] associação.

## Considerações sobre o [!UICONTROL Adobe Analytics] mapeamento [!UICONTROL Segment]

Ao mapear o Adobe Analytics [!UICONTROL segments] ou conjuntos de relatórios para a organização do Experience Cloud, o Audience Manager cria automaticamente características e características novas, correspondentes, somente leitura [!UICONTROL segments] . Não é possível editar ou alterar o local do armazenamento do Audience Manager [!UICONTROL segments] . No entanto, qualquer alteração que você efetuar no Adobe Analytics ou nos conjuntos de relatórios mapeados será refletida no Audience Manager. [!UICONTROL segments]

>[!TIP]
>
>Audience Manager [!UICONTROL segments] são diferentes de [!DNL Adobe Analytics][!UICONTROL segments]. Read [Understanding Segments in Analytics and Audience Manager](https://docs.adobe.com/content/help/pt-BR/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) for an in-depth description of the differences.

## Criar com base em regras [!UICONTROL Segments] com [!UICONTROL Segment Builder]

Ao contrário dos pixels tradicionais que disparam em resposta a condições simples de sim/não, [!UICONTROL Segment Builder] permite criar [!UICONTROL segment] requisitos complexos. Como [!UICONTROL traits], [!UICONTROL segments] avalie dados usando [!DNL Boolean] expressão ([!DNL AND], [!DNL OR], [!DNL NOT]), operadores de comparação (maior que, menor que, igual a, etc.) e critérios de recenticidade/frequência. Esses recursos ajudam a criar audiências focalizadas [!UICONTROL segments] relevantes às suas necessidades comerciais.

## Benefícios

[!UICONTROL Segments] melhore os processos padrão de criação/segmentação de audiências com base em pixels, pois eles permitem:

* Crie características relevantes e úteis [!UICONTROL segments] com características próprias e de terceiros.
* Crie regras de segmentação sofisticadas e complexas com operadores booleanos, expressões de comparação e critérios de recenticidade/frequência.
* Enviar [!UICONTROL segment] dados para um parceiro de destino.
* Monitore o desempenho com os relatórios de Audience Manager.

>[!MORELIKETHIS]
>
>* [Sinais, características e segmentos](../../reference/signal-trait-segment.md)

