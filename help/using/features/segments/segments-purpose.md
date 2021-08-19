---
description: Descreve segmentos, suas partes constituintes e a criação de regras com o Construtor de segmentos.
seo-description: Descreve segmentos, suas partes constituintes e a criação de regras com o Construtor de segmentos.
seo-title: Finalidade, composição e regras dos segmentos
solution: Audience Manager
title: Finalidade, composição e regras dos segmentos
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: 'Segmentos '
exl-id: 4e4da7a7-3267-4564-b1c5-663dcddf2b93
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 3%

---

# Segmentos: finalidade, composição e regras {#segments-purpose-composition-and-rules}

Descreve [!UICONTROL segments], suas partes constituintes e a criação de regras com [!UICONTROL Segment Builder].

## Finalidade de [!UICONTROL Segments]

Um *`segment`* (ou um *`audience`*) é um conjunto de usuários que compartilham atributos comuns. No Audience Manager, crie [!UICONTROL segments] com regras do lado do servidor. Essas regras permitem criar grupos de público-alvo com base nos atributos de visitante do site, como:

* Comportamento;
* Demografia (idade, gênero, renda etc.);
* Outras características que podem ser definidas na interface do usuário.

## [!UICONTROL Segment] Composição

Um Audience Manager [!UICONTROL segment] é uma regra do lado do servidor que consiste em características individuais ou em grupos de características. As características são compostas de elementos de dados chamados de pares de valores chave. Junto com as regras definidas no nível [!UICONTROL segment] , esses pares de valores chave contêm os critérios que qualificam visitantes para características e [!UICONTROL segment] associação.

## Considerações sobre o mapeamento [!UICONTROL Adobe Analytics] [!UICONTROL Segment]

Ao mapear Adobe Analytics [!UICONTROL segments] ou conjuntos de relatórios para sua organização do Experience Cloud, o Audience Manager automaticamente cria características e [!UICONTROL segments] novas, correspondentes e somente leitura. Não é possível editar ou alterar o local de armazenamento desses [!UICONTROL segments] do Audience Manager. No entanto, qualquer alteração realizada no Adobe Analytics [!UICONTROL segments] ou nos conjuntos de relatórios mapeados reflete no Audience Manager.

>[!TIP]
>
>Audience Manager [!UICONTROL segments] são diferentes de [!DNL Adobe Analytics] [!UICONTROL segments]. Leia [Entendendo os segmentos no Analytics e Audience Manager](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) para obter uma descrição detalhada das diferenças.

## Criar [!UICONTROL Segments] com base em regras com [!UICONTROL Segment Builder]

Ao contrário dos pixels tradicionais que são acionados em resposta a condições simples sim/não, [!UICONTROL Segment Builder] permite que você crie requisitos complexos [!UICONTROL segment]. Como [!UICONTROL traits], [!UICONTROL segments] avalia dados usando expressões [!DNL Boolean] ([!DNL AND], [!DNL OR], [!DNL NOT]), operadores de comparação (maior que, menor que, igual a etc.) e critérios de recenticidade/frequência. Esses recursos ajudam a criar um público-alvo focado [!UICONTROL segments] relevante para suas necessidades comerciais.

## Benefícios

[!UICONTROL Segments] melhore os processos padrão de criação/segmentação de público-alvo com base em pixels, pois eles permitem:

* Crie [!UICONTROL segments] relevantes e úteis com características originais e de terceiros.
* Crie regras de segmentação sofisticadas e complexas com operadores booleanos, expressões de comparação e critérios de recenticidade/frequência.
* Envie dados [!UICONTROL segment] para um parceiro de destino.
* Monitore o desempenho com os relatórios de Audience Manager.

>[!MORELIKETHIS]
>
>* [Sinais, características e segmentos](../../reference/signal-trait-segment.md)

