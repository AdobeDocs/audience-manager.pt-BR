---
description: Informações conceituais, descrições e definições para código, métodos e processos da API DCS.
seo-description: Informações conceituais, descrições e definições para código, métodos e processos da API DCS no Adobe Audience Manager (AAM).
seo-title: Visão geral de referência da API DCS no Adobe Audience Manager (AAM)
title: Visão geral de referência da DCS API
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 13%

---


# Visão geral de referência da DCS API

Informações conceituais, descrições e definições para [!DNL DCS API] código, métodos e processos.

* [Métodos da DCS API](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   Envie dados para o [!DNL DCS API] usando os métodos GET ou POST.

* [Códigos de erros, mensagens e exemplos de DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   Códigos de erro e mensagens geradas pelos servidores de coleta de dados (DCS) listados em ordem numérica por ID de código.

* [Monitoramento e Incluir na lista de bloqueios de ID](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

   O DCS monitora as IDs que recebe e adiciona aquelas que estão sendo enviadas a uma taxa excepcionalmente alta durante um curto período de tempo para uma lista de bloqueios.

* [IDs da região do DCS, locais e nomes de host](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   O nome do host do servidor DCS regional é necessário para fazer chamadas para o DCS. Isso ocorre porque o DCS armazena informações em data centers geograficamente próximos aos visitantes do site. Seus query funcionarão se você os enviar para o DCS errado, mas essas chamadas são ineficientes e podem atrasar a resposta. Para fazer uma solicitação DCS, corresponda a ID da região ao nome do host regional correspondente e forme o query com o nome do host apropriado.

* [Formatação de pares de valores-chave em chamadas DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   Ao fazer uma chamada, o DCS aceita dados de valor chave em formato padrão ou serializado. Consulte esta seção para obter informações sobre como formatar dados de valores chave padrão e serializados.

* [Condições de raça e tratamento de erros](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   Descreve como evitar condições de raça e tratamento de erros do DCS.

* [Atributos compatíveis com chamadas de DCS API](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   Listas e descreve a sintaxe e os atributos suportados (ou pares de valores chave) que podem ser transmitidos para os Servidores de Coleta de Dados (DCS). Essas informações podem ajudar a formatar as solicitações do DCS e entender os parâmetros retornados por este sistema.
