---
description: Descreve como evitar condições de raça e tratamento de erros do DCS.
seo-description: Descreve como evitar condições de raça e tratamento de erros do DCS.
seo-title: Condições de raça e tratamento de erros
solution: Audience Manager
title: Condições de raça e tratamento de erros
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 7%

---


# Condições de raça e tratamento de erros {#race-conditions-and-error-handling}

Descreve como evitar condições de raça e tratamento de erros [!DNL DCS].

## Impedindo Condições de Raça {#prevent-race-conditions}

Uma condição de corrida pode ocorrer se você enviar várias chamadas simultaneamente (ou em rápida sucessão) para o [!DNL DCS] antes que ele termine de responder aos query iniciais e gravar dados no cookie do usuário. Uma condição de raça é indesejável porque pode corromper ou substituir incorretamente os dados do cookie. Como prática recomendada, considere os seguintes métodos para ajudar a evitar esse problema:

* Não faça chamadas simultâneas, ou chamadas em rápida sucessão, para [!DNL DCS] do mesmo usuário.
* Aguarde que cada resposta volte antes de realizar chamadas subsequentes.

## Tratamento de Erros {#error-handling}

O tratamento de erros é limitado para query inválidos ou mal formados. Uma solicitação inválida retorna uma resposta `HTTP 200 OK` e nenhum dado. Além disso, o [!DNL DCS] para de processar uma solicitação, descarta dados de características e retorna uma resposta `HTTP 200 OK` quando um usuário:

* Opt out de rastreamento no nível de Audience Manager ou parceiro.
* Vem de uma região geográfica inválida/não selecionada.
* Desativa os cookies do navegador (todos ou de terceiros).

Consulte também [Códigos de erro, mensagens e exemplos do DCS](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).