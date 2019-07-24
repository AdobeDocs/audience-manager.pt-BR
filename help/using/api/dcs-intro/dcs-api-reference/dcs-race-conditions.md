---
description: Descreve como evitar condições de raça e manipulação de erros do DCS.
seo-description: Descreve como evitar condições de raça e manipulação de erros do DCS.
seo-title: Condições de raça e manipulação de erros
solution: Audience Manager
title: Condições de raça e manipulação de erros
uuid: b 0 aac 960-6732-4 e 96-87 a 5-40 ba 2755 e 02 d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Race Conditions and Error Handling {#race-conditions-and-error-handling}

Describes how to prevent race conditions and [!UICONTROL DCS] error handling.

## Preventing Race Conditions {#prevent-race-conditions}

A race condition can occur if you send multiple calls simultaneously (or in rapid succession) to the [!UICONTROL DCS] before it finishes responding to the initial queries and writing data to the user’s cookie. Uma condição de raça é indesejada, pois pode corromper ou substituir incorretamente os dados do cookie. Como prática recomendada, considere os seguintes métodos para ajudar a evitar esse problema:

* Don't make simultaneous calls, or calls in rapid succession, to the [!UICONTROL DCS] from the same user.
* Aguarde cada resposta para retornar antes de fazer chamadas subsequentes.

## Error Handling {#error-handling}

O tratamento de erros é limitado para consultas inválidas ou incorretas. An invalid request returns an `HTTP 200 OK` response and no data. Also, the [!UICONTROL DCS] stops processing a request, discards trait data, and returns an `HTTP 200 OK` response when a user:

* Recusa o rastreamento no Audience Manager ou no nível do parceiro.
* Vem de uma região geográfica inválida/não selecionada.
* Desativa os cookies do navegador (todos ou de terceiros).

See also, [DCS Error Codes, Messages, and Examples](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).