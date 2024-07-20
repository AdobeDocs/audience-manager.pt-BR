---
description: Descreve como evitar condições de corrida e tratamento de erros DCS.
seo-description: Describes how to prevent race conditions and DCS error handling.
seo-title: Race Conditions and Error Handling
solution: Audience Manager
title: Condições de raça e tratamento de erros
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
exl-id: bfb0b684-6b15-434d-b5ec-5f8741c0c691
source-git-commit: 25d785097228ae66d20cf2b35c8ef63fd64936c6
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 0%

---

# Condições de raça, limite de taxa e tratamento de erros {#race-conditions-and-error-handling}

Descreve como evitar condições de corrida e [!DNL DCS] manipulação de erros.

## Prevenção de condições de raça {#prevent-race-conditions}

Uma condição de corrida pode ocorrer se você enviar várias chamadas simultaneamente (ou em rápida sucessão) para o [!DNL DCS] antes que ele termine de responder às consultas iniciais e gravar dados no cookie do usuário. Uma condição de corrida não é desejável porque pode corromper ou substituir incorretamente os dados do cookie. Como prática recomendada, considere os seguintes métodos para ajudar a evitar esse problema:

* Não faça chamadas simultâneas, ou chamadas em rápida sucessão, para o [!DNL DCS] do mesmo usuário.
* Aguarde até que cada resposta retorne antes de fazer chamadas subsequentes.

## Limitação de taxa {#rate-limiting}

O Adobe pode introduzir uma limitação de taxa se detectar chamadas excessivas de DCS API que possam ter um impacto negativo na disponibilidade do serviço.

Se a limitação de taxa estiver habilitada, você poderá receber um código de status de resposta HTTP `429 Too Many Requests` em suas chamadas DCS. Ao receber essa resposta HTTP, tente novamente as chamadas de API mais tarde.

## Tratamento de erros {#error-handling}

O tratamento de erros é limitado a consultas inválidas ou mal formadas. Uma solicitação inválida retorna uma resposta `HTTP 200 OK` e nenhum dado. Além disso, o [!DNL DCS] para de processar uma solicitação, descarta dados de características e retorna uma resposta de `HTTP 200 OK` quando um usuário:

* Recusa o rastreamento no nível de Audience Manager ou parceiro.
* É proveniente de uma região geográfica inválida/não selecionada.
* Desativa os cookies do navegador (todos ou de terceiros).

Consulte também [Códigos de erro, mensagens e exemplos de DCS](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).
