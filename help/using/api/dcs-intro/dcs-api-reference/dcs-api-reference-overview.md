---
description: Informações, descrições e definições conceituais para código, métodos e processos da API DCS.
seo-description: Informações, descrições e definições conceituais para código, métodos e processos da API DCS no Adobe Audience Manager (AAM).
seo-title: Visão geral de referência da API DCS no Adobe Audience Manager (AAM)
title: Visão geral de referência da DCS API
feature: DCS
exl-id: 84d20041-0b98-4ba5-ba97-29c35f088ad9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 13%

---

# Visão geral de referência da DCS API

Informações, descrições e definições conceituais para código, métodos e processos [!DNL DCS API].

* [Métodos da DCS API](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   Envie dados para o [!DNL DCS API] usando os métodos GET ou POST.

* [Códigos de erros, mensagens e exemplos de DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   Códigos de erro e mensagens geradas pelos Servidores de coleta de dados (DCS) listados em ordem numérica por ID de código.

* [Monitoramento de ID e Incluir na lista de bloqueios](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

   O DCS monitora as IDs recebidas e adiciona aquelas que estão sendo enviadas em uma taxa excepcionalmente alta durante um curto período para uma lista de bloqueios.

* [IDs da região do DCS, locais e nomes de host](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   O nome de host do servidor DCS regional é necessário para fazer chamadas para o DCS. Isso ocorre porque o DCS armazena informações em data centers geograficamente próximos aos visitantes do site. Suas consultas funcionarão se você enviá-las para o DCS errado, mas essas chamadas são ineficientes e podem atrasar a resposta. Para fazer uma solicitação de DCS, corresponda a ID da região ao nome de host regional correspondente e forme a consulta com o nome de host apropriado.

* [Formatação de pares de valores-chave em chamadas DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   Ao fazer uma chamada, o DCS aceita dados de valor chave em formato padrão ou serializado. Consulte esta seção para obter informações sobre como formatar dados de valores-chave padrão e serializados.

* [Condições de raça e tratamento de erros](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   Descreve como evitar condições de corrida e tratamento de erros do DCS.

* [Atributos compatíveis com chamadas de DCS API](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   Lista e descreve a sintaxe e os atributos suportados (ou pares de valores chave) que podem ser passados para os Servidores de coleta de dados (DCS). Essas informações podem ajudar a formatar as solicitações DCS e compreender os parâmetros retornados por esse sistema.
