---
description: Informações conceituais, descrições e definições para código, métodos e processos da API DCS.
seo-description: Conceptual information, descriptions, and definitions for DCS API code, methods, and processes in Adobe Audience Manager (AAM).
seo-title: DCS API Reference Overview in Adobe Audience Manager (AAM)
title: Visão geral de referência da DCS API
feature: DCS
exl-id: 84d20041-0b98-4ba5-ba97-29c35f088ad9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 0%

---

# Visão geral de referência da DCS API

Informações conceituais, descrições e definições para [!DNL DCS API] código, métodos e processos.

* [Métodos da DCS API](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

  Enviar dados para [!DNL DCS API] usando os métodos GET ou POST.

* [Códigos de erros, mensagens e exemplos de DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

  Códigos de erro e mensagens geradas pelos Data Collection Servers (DCS) listados em ordem numérica pela ID de código.

* [Monitoramento e Incluir na lista de bloqueios de ID](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

  O DCS monitora as IDs que recebe e adiciona as que estão sendo enviadas em uma taxa excepcionalmente alta durante um curto período de tempo a uma lista de bloqueios.

* [IDs da região do DCS, locais e nomes de host](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

  O nome de host do servidor DCS regional é necessário para fazer chamadas para o DCS. Isso ocorre porque o DCS armazena informações em data centers geograficamente próximos aos visitantes do site. Suas consultas funcionarão se você enviá-las para o DCS errado, mas essas chamadas são ineficientes e podem atrasar a resposta. Para fazer uma solicitação de DCS, associe a ID da região ao nome de host regional correspondente e forme sua query com o nome de host apropriado.

* [Formatação de pares de valores-chave em chamadas DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

  Ao fazer uma chamada, o DCS aceita dados de valores-chave em formato padrão ou serializado. Consulte esta seção para obter informações sobre como formatar dados de valor-chave padrão e serializados.

* [Condições de raça e tratamento de erros](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

  Descreve como evitar condições de corrida e tratamento de erros DCS.

* [Atributos compatíveis com chamadas de DCS API](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

  Lista e descreve a sintaxe e os atributos compatíveis (ou pares de valores chave) que você pode transmitir para os Servidores de coleta de dados (DCS). Essas informações podem ajudar você a formatar as solicitações do DCS e entender os parâmetros retornados por esse sistema.
