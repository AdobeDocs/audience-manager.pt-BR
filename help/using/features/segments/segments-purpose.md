---
description: Descreve os segmentos, suas partes constituintes e a criação de regras com o Construtor de segmentos.
seo-description: Describes segments, their constituent parts, and rule creation with Segment Builder.
seo-title: Segments  Purpose, Composition, and Rules
solution: Audience Manager
title: Finalidade, composição e regras dos segmentos
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
exl-id: 4e4da7a7-3267-4564-b1c5-663dcddf2b93
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 3%

---

# Segmentos: finalidade, composição e regras {#segments-purpose-composition-and-rules}

Descreve [!UICONTROL segments], suas partes constituintes e a criação de regras com [!UICONTROL Segment Builder].

## Finalidade de [!UICONTROL Segments]

A *`segment`* (ou um *`audience`*) é um conjunto de usuários que compartilham atributos comuns. No Audience Manager, você cria [!UICONTROL segments] com as regras do lado do servidor. Essas regras permitem criar grupos de públicos-alvo com base nos atributos do visitante do site, como:

* Comportamento;
* Demografia (idade, sexo, renda etc.);
* Outras características que você pode definir na interface do usuário do.

## [!UICONTROL Segment] Composição

Um Audience Manager [!UICONTROL segment] é uma regra do lado do servidor que consiste em características individuais ou grupos de características. As características são compostas por elementos de dados chamados de pares de valores chave. Juntamente com as regras definidas no [!UICONTROL segment] esses pares de valores chave contêm os critérios que qualificam visitantes para características e [!UICONTROL segment] associação.

## Considerações sobre [!UICONTROL Adobe Analytics] [!UICONTROL Segment] Mapeamento

Ao mapear o Adobe Analytics [!UICONTROL segments] ou conjuntos de relatórios para sua organização Experience Cloud, o Audience Manager cria automaticamente conjuntos novos, correspondentes e somente leitura [!UICONTROL segments] e características. Não é possível editar ou alterar o local de armazenamento desses [!UICONTROL segments] do Audience Manager. No entanto, qualquer alteração executada no Adobe Analytics mapeado [!UICONTROL segments] ou os conjuntos de relatórios refletem no Audience Manager.

>[!TIP]
>
>Audience Manager [!UICONTROL segments] são diferentes de [!DNL Adobe Analytics] [!UICONTROL segments]. Ler [Noções básicas sobre segmentos no Analytics e no Audience Manager](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) para obter uma descrição detalhada das diferenças.

## Criar baseado em regras [!UICONTROL Segments] Com [!UICONTROL Segment Builder]

Ao contrário dos pixels tradicionais que são acionados em resposta a condições simples de sim/não, [!UICONTROL Segment Builder] permite criar relatórios complexos [!UICONTROL segment] requisitos. Curtir [!UICONTROL traits], [!UICONTROL segments] avaliar dados usando [!DNL Boolean] expressões ([!DNL AND], [!DNL OR], [!DNL NOT]), operadores de comparação (maior que, menor que, igual a, etc.) e critérios de recenticidade/frequência. Esses recursos ajudam a criar um público-alvo focado [!UICONTROL segments] relevantes para suas necessidades comerciais.

## Benefícios

[!UICONTROL Segments] melhore os processos padrão de criação/segmentação de público com base em pixels, pois eles permitem:

* Criar relevante, útil [!UICONTROL segments] com características próprias e de terceiros.
* Crie regras de segmentação sofisticadas e complexas com operadores booleanos, expressões de comparação e critérios de recenticidade/frequência.
* Enviar [!UICONTROL segment] para um parceiro de destino.
* Monitore o desempenho com relatórios de Audience Manager.

>[!MORELIKETHIS]
>
>* [Sinais, características e segmentos](../../reference/signal-trait-segment.md)

