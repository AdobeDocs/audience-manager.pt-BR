---
description: Descreve segmentos, suas partes constituintes e a criação de regras com o Construtor de segmentos.
seo-description: Descreve segmentos, suas partes constituintes e a criação de regras com o Construtor de segmentos.
seo-title: Finalidade, composição e regras dos segmentos
solution: Audience Manager
title: Finalidade, composição e regras dos segmentos
uuid: 886 d 4 abe-b 1 b 6-4983-b 4 fb-b 552 d 54 d 51 ba
translation-type: tm+mt
source-git-commit: c229bf71da5b07277811219cbf2794c3ca7bc89d

---


# Segments: Purpose, Composition, and Rules {#segments-purpose-composition-and-rules}

Describes segments, their constituent parts, and rule creation with [!UICONTROL Segment Builder].

## Finalidade dos segmentos

A *`segment`* (or an *`audience`*) is a set of users who share common attributes. No Audience Manager, você cria segmentos com regras do servidor. Essas regras permitem que você construa grupos de público-alvo com base nos atributos do visitante do site, como:

* Comportamento;
* Demografia (idade, gênero, renda etc.);
* Outras características que você pode definir na interface do usuário.

## Composição do segmento

Um segmento do Audience Manager é uma regra do lado do servidor que consiste em grupos individuais ou grupos de características. As características são compostos de elementos de dados chamados pares de chave-valor. Juntamente com as regras definidas no nível do segmento, esses pares de valores chave contêm os critérios que qualificam os visitantes para características de características e segmentos.

## Considerações sobre o mapeamento de segmentos do Adobe Analytics

Ao mapear segmentos do Adobe Analytics ou conjuntos de relatórios para a organização da Experience Cloud, o Audience Manager cria automaticamente novos segmentos correspondentes, correspondentes e somente leitura. Não é possível editar nem alterar o local de armazenamento desses segmentos no Audience Manager. No entanto, qualquer alteração realizada nos segmentos do Adobe Analytics mapeados ou nos conjuntos de relatórios reflete no Audience Manager.

>[!TIP]
>
>Audience Manager segments are different from [!DNL Adobe Analytics] segments. Read [Understanding Segments in Analytics and Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) for an in-depth description of the differences.

## Criar segmentos baseados em regras com o construtor de segmentos

Diferentemente de pixels tradicionais que são acionados em resposta a condições simples de sim/não, o Construtor de segmentos permite criar requisitos complexos de segmento. Like traits, segments evaluate data using [!DNL Boolean] expressions ([!DNL AND], [!DNL OR], [!DNL NOT]), comparison operators (greater than, less than, equal to, etc.), and recency/frequency criteria. Esses recursos ajudam a criar segmentos de público-alvo específicos relevantes para suas necessidades de negócios.

## Benefícios

Os segmentos melhoram em processos de criação/segmentação de público-alvo padrão com base em pixels, pois permitem:

* Crie segmentos relevantes e úteis com características primeiro e de terceiros.
* Crie regras de segmentação sofisticadas e complexas com operadores booleanos, expressões comparativas e critérios de recenticidade/frequência.
* Enviar dados de segmento para um parceiro de destino.
* Monitore o desempenho com os relatórios do Audience Manager.

>[!MORE_ LIKE_ THIS]
>
>* [Sinais, características e segmentos](../../reference/signal-trait-segment.md)

