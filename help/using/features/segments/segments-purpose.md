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
source-wordcount: '303'
ht-degree: 1%

---

# Segmentos: finalidade, composição e regras {#segments-purpose-composition-and-rules}

Descreve [!UICONTROL segments], suas partes constituintes e a criação da regra com [!UICONTROL Segment Builder].

## Finalidade de [!UICONTROL Segments]

Um *`segment`* (ou *`audience`*) é um conjunto de usuários que compartilham atributos comuns. No Audience Manager, você cria [!UICONTROL segments] com regras do lado do servidor. Essas regras permitem criar grupos de públicos-alvo com base nos atributos do visitante do site, como:

* Comportamento;
* Demografia (idade, sexo, renda etc.);
* Outras características que você pode definir na interface do usuário do.

## Composição de [!UICONTROL Segment]

Um Audience Manager [!UICONTROL segment] é uma regra do lado do servidor que consiste em características individuais ou grupos de características. As características são compostas por elementos de dados chamados de pares de valores chave. Juntamente com as regras definidas no nível [!UICONTROL segment], esses pares de valores chave contêm os critérios que qualificam visitantes para características e associação [!UICONTROL segment].

## Considerações sobre o mapeamento de [!UICONTROL Adobe Analytics] [!UICONTROL Segment]

Ao mapear o Adobe Analytics [!UICONTROL segments] ou conjuntos de relatórios para sua organização da Experience Cloud, o Audience Manager cria automaticamente [!UICONTROL segments] e características novas, correspondentes e somente leitura. Não é possível editar ou alterar o local de armazenamento destes [!UICONTROL segments] no Audience Manager. No entanto, qualquer alteração que você executar no Adobe Analytics [!UICONTROL segments] ou conjuntos de relatórios mapeados será refletida no Audience Manager.

>[!TIP]
>
>Audience Manager [!UICONTROL segments] são diferentes de [!DNL Adobe Analytics] [!UICONTROL segments]. Leia [Entendendo os segmentos no Analytics e no Audience Manager](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) para obter uma descrição detalhada sobre as diferenças.

## Criar [!UICONTROL Segments] com base em Regras com [!UICONTROL Segment Builder]

Ao contrário dos pixels tradicionais que são acionados em resposta a condições simples de sim/não, o [!UICONTROL Segment Builder] permite criar requisitos complexos de [!UICONTROL segment]. Como [!UICONTROL traits], [!UICONTROL segments] avalia dados usando [!DNL Boolean] expressões ([!DNL AND], [!DNL OR], [!DNL NOT]), operadores de comparação (maior que, menor que, igual a, etc.) e critérios de recenticidade/frequência. Esses recursos ajudam a criar um público-alvo [!UICONTROL segments] focado, relevante para as necessidades da sua empresa.

## Benefícios

[!UICONTROL Segments] melhore os processos padrão de criação/segmentação de público com base em pixels, pois eles permitem:

* Criar [!UICONTROL segments] relevante e útil com características próprias e de terceiros.
* Crie regras de segmentação sofisticadas e complexas com operadores booleanos, expressões de comparação e critérios de recenticidade/frequência.
* Enviar dados do [!UICONTROL segment] para um parceiro de destino.
* Monitore o desempenho com relatórios do Audience Manager.

>[!MORELIKETHIS]
>
>* [Sinais, características e segmentos](../../reference/signal-trait-segment.md)
