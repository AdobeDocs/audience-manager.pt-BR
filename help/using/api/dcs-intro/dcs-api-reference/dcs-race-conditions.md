---
description: Descreve como evitar condições de raça e tratamento de erros do DCS.
seo-description: Descreve como evitar condições de raça e tratamento de erros do DCS.
seo-title: Condições de raça e tratamento de erros
solution: Audience Manager
title: Condições de raça e tratamento de erros
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Condições de raça e tratamento de erros {#race-conditions-and-error-handling}

Descreve como evitar condições de raça e tratamento de [!UICONTROL DCS] erros.

## Prevenção de condições de raça {#prevent-race-conditions}

Uma condição de corrida pode ocorrer se você enviar várias chamadas simultaneamente (ou em rápida sucessão) para o usuário antes de terminar de responder às consultas iniciais e gravar dados no cookie do usuário. [!UICONTROL DCS] Uma condição de raça é indesejável porque pode corromper ou substituir incorretamente os dados do cookie. Como prática recomendada, considere os seguintes métodos para ajudar a evitar esse problema:

* Não faça chamadas simultâneas, ou chamadas em rápida sucessão, para o usuário [!UICONTROL DCS] do mesmo usuário.
* Aguarde que cada resposta volte antes de realizar chamadas subsequentes.

## Tratamento de erros {#error-handling}

A manipulação de erros é limitada para consultas inválidas ou mal formadas. Uma solicitação inválida retorna uma `HTTP 200 OK` resposta e nenhum dado. Além disso, o usuário [!UICONTROL DCS] para de processar uma solicitação, descarta dados de características e retorna uma `HTTP 200 OK` resposta quando:

* Opta por não ser rastreado no Audience Manager ou no nível do parceiro.
* Vem de uma região geográfica inválida/não selecionada.
* Desativa os cookies do navegador (todos ou de terceiros).

See also, [DCS Error Codes, Messages, and Examples](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).