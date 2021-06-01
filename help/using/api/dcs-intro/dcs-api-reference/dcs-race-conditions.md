---
description: Descreve como evitar condições de corrida e tratamento de erros do DCS.
seo-description: Descreve como evitar condições de corrida e tratamento de erros do DCS.
seo-title: Condições de raça e tratamento de erros
solution: Audience Manager
title: Condições de raça e tratamento de erros
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
exl-id: bfb0b684-6b15-434d-b5ec-5f8741c0c691
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 7%

---

# Condições de raça e tratamento de erros {#race-conditions-and-error-handling}

Descreve como evitar condições de corrida e tratamento de erros [!DNL DCS].

## Evitando Condições de Raça {#prevent-race-conditions}

Uma condição de corrida pode ocorrer se você enviar várias chamadas simultaneamente (ou em rápida sucessão) para o [!DNL DCS] antes de terminar de responder às consultas iniciais e gravar dados no cookie do usuário. Uma condição de corrida é indesejável porque pode corromper ou substituir incorretamente os dados do cookie. Como prática recomendada, considere os seguintes métodos para ajudar a evitar esse problema:

* Não faça chamadas simultâneas ou chamadas em rápida sucessão para o [!DNL DCS] do mesmo usuário.
* Aguarde cada resposta retornar antes de fazer chamadas subsequentes.

## Tratamento de erros {#error-handling}

O tratamento de erros é limitado para consultas inválidas ou mal formadas. Uma solicitação inválida retorna uma resposta `HTTP 200 OK` e nenhum dado. Além disso, o [!DNL DCS] para de processar uma solicitação, descarta dados de características e retorna uma resposta `HTTP 200 OK` quando um usuário:

* Recusa o rastreamento no nível de Audience Manager ou parceiro.
* É proveniente de uma região geográfica inválida/não selecionada.
* Desativa os cookies do navegador (todos ou de terceiros).

Consulte também [Códigos de erros, mensagens e exemplos de DCS](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).
