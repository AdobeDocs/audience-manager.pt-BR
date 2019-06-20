---
description: Informações, descrições e definições conceituais para código, métodos e processos da API DCS.
seo-description: Informações, descrições e definições conceituais para código, métodos e processos da API DCS no Adobe Audience Manager (AAM).
seo-title: Visão geral de referência de API DCS no Adobe Audience Manager (AAM)
title: Visão geral da referência da API DCS
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# Visão geral da referência da API DCS

Informações, descrições e definições conceituais para código, métodos e processos da API DCS.

* [Métodos de API DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   Envie dados para a API DCS usando métodos GET ou POST.

* [Códigos de erros, mensagens e exemplos de DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   Códigos e mensagens de erro gerados pelos servidores de coleta de dados (DCS) listados em ordem numérica por ID de código.

* [Monitoramento de ID e lista negra](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-blacklisting.md)

   O DCS monitora as IDs que recebe e lista negra aquelas que estão sendo enviadas em uma taxa excepcionalmente alta durante um curto período.

* [IDs de região DCS, locais e nomes de host](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   O nome do host do servidor DCS regional é necessário para fazer chamadas para o DCS. Isso ocorre porque o DCS armazena informações em centros de dados que estão geograficamente próximos dos visitantes do site. Suas consultas funcionarão se você as envia para o DCS errado, mas essas chamadas são ineficientes e podem atrasar a resposta. Para fazer uma solicitação DCS, corresponda à ID da região correspondente ao nome de host regional correspondente e crie a sua consulta com o nome de host apropriado.

* [Formatação de pares de valores chave em chamadas DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   Ao fazer uma chamada, o DCS aceita dados de valor chave no formato padrão ou serializado. Analise esta seção para obter informações sobre como formatar dados padrão e serializados de valor-chave.

* [Condições de raça e manipulação de erros](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   Descreve como evitar condições de raça e manipulação de erros do DCS.

* [Atributos compatíveis para chamadas de API DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   Lista e descreve a sintaxe e os atributos suportados (ou pares de valores chave) que você pode passar para os Servidores de coleta de dados (DCS). Essas informações podem ajudar você a formatar suas solicitações do DCS e compreender os parâmetros retornados por este sistema.
