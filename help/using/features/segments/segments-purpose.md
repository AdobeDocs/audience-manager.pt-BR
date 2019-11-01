---
description: Descreve segmentos, suas partes constituintes e a criação de regras com o Construtor de segmentos.
seo-description: Descreve segmentos, suas partes constituintes e a criação de regras com o Construtor de segmentos.
seo-title: Finalidade, composição e regras dos segmentos
solution: Audience Manager
title: Finalidade, composição e regras dos segmentos
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Segmentos: Finalidade, composição e regras {#segments-purpose-composition-and-rules}

Descreve segmentos, suas partes constituintes e a criação de regras com [!UICONTROL Segment Builder].

## Finalidade dos segmentos

Um *`segment`* (ou um *`audience`*) é um conjunto de usuários que compartilham atributos comuns. No Audience Manager, você cria segmentos com regras do lado do servidor. Essas regras permitem que você crie grupos de público-alvo com base nos atributos de visitante do site, como:

* Comportamento;
* Demografia (idade, gênero, rendimento, etc.);
* Outras características que podem ser definidas na interface do usuário.

## Composição do segmento

Um segmento do Audience Manager é uma regra do lado do servidor que consiste em características individuais ou em grupos. As características são compostas de elementos de dados chamados pares de valores chave. Junto com as regras definidas no nível do segmento, esses pares de valores chave contêm os critérios que qualificam os visitantes para características e associação de segmentos.

## Considerações sobre o mapeamento de segmentos do Adobe Analytics

 Ao mapear segmentos do Adobe Analytics ou conjuntos de relatórios para a organização da Experience Cloud, o Audience Manager cria automaticamente segmentos e características novos, correspondentes e somente leitura. Não é possível editar ou alterar o local de armazenamento desses segmentos do Audience Manager. No entanto, qualquer alteração que você efetuar nos segmentos do Adobe Analytics ou conjuntos de relatórios mapeados será refletida no Audience Manager.

>[!TIP]
>
>Os segmentos do Audience Manager são diferentes dos [!DNL Adobe Analytics] segmentos. Leia [Como entender segmentos no Analytics e no Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) para obter uma descrição detalhada das diferenças.

## Criar segmentos baseados em regras com o Construtor de segmentos

Ao contrário dos pixels tradicionais que disparam em resposta a condições simples sim/não, o Construtor de segmentos permite que você crie requisitos complexos de segmento. Como características, os segmentos avaliam dados usando [!DNL Boolean] expressões ([!DNL AND], [!DNL OR], [!DNL NOT]), operadores de comparação (maior que, menor que, igual a, etc.) e critérios de recenticidade/frequência. Esses recursos ajudam a criar segmentos de público-alvo direcionados relevantes às suas necessidades comerciais.

## Benefícios

Os segmentos melhoram nos processos padrão de criação/segmentação do público-alvo com base em pixels, pois permitem:

* Crie segmentos relevantes e úteis com características próprias e de terceiros.
* Crie regras de segmentação sofisticadas e complexas com operadores booleanos, expressões de comparação e critérios de recenticidade/frequência.
* Enviar dados de segmento para um parceiro de destino.
* Monitore o desempenho com os relatórios do Audience Manager.

>[!MORELIKETHIS]
>
>* [Sinais, características e segmentos](../../reference/signal-trait-segment.md)

