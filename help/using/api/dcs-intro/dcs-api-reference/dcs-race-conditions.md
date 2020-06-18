---
description: Descreve como evitar condições de raça e tratamento de erros do DCS.
seo-description: Descreve como evitar condições de raça e tratamento de erros do DCS.
seo-title: Condições de raça e tratamento de erros
solution: Audience Manager
title: Condições de raça e tratamento de erros
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---


# Condições de raça e tratamento de erros {#race-conditions-and-error-handling}

Descreve como evitar condições de raça e tratamento de [!DNL DCS] erros.

## Evitar Condições de Raça {#prevent-race-conditions}

Uma condição de corrida pode ocorrer se você enviar várias chamadas simultaneamente (ou em rápida sucessão) para o usuário antes que ele conclua de responder aos query iniciais e gravar dados no cookie do usuário. [!DNL DCS] Uma condição de raça é indesejável porque pode corromper ou substituir incorretamente os dados do cookie. Como prática recomendada, considere os seguintes métodos para ajudar a evitar esse problema:

* Não faça chamadas simultâneas, ou chamadas em rápida sucessão, para o usuário [!DNL DCS] do mesmo usuário.
* Aguarde que cada resposta retorne antes de realizar chamadas subsequentes.

## Tratamento de erros {#error-handling}

O tratamento de erros é limitado para query inválidos ou mal formados. Uma solicitação inválida retorna uma `HTTP 200 OK` resposta e nenhum dado. Além disso, o usuário [!DNL DCS] para de processar uma solicitação, descarta dados de características e retorna uma `HTTP 200 OK` resposta quando:

* Opt out de rastreamento no nível de Audience Manager ou parceiro.
* Vem de uma região geográfica inválida/não selecionada.
* Desativa os cookies do navegador (todos ou de terceiros).

See also, [DCS Error Codes, Messages, and Examples](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).