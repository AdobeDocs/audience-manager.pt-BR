---
description: As APIs S2S (Server-to-server) fornecem código e métodos que permitem enviar e receber dados de usuários DCS e trabalhar com essas informações em seus próprios sistemas ou aplicativos.
seo-description: Server-to-server (S2S) APIs provide code and methods that let you send and receive DCS user data and work with this information in your own systems or applications.
seo-title: DCS APIs for Server-to-Server Data Transfers
solution: Audience Manager
title: DCS APIs para transferências de dados de servidor para servidor
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
exl-id: fd23d5e2-b74e-47ff-a4aa-3a4b2c7d39c5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---

# DCS APIs para transferências de dados de servidor para servidor{#dcs-apis-for-server-to-server-data-transfers}

Os [!DNL API]s servidor para servidor ([!UICONTROL S2S]) fornecem código e métodos que permitem enviar e receber dados de usuário do [!DNL DCS] e trabalhar com essas informações em seus próprios sistemas ou aplicativos.

## Casos de uso comuns {#common-use-cases}

As transferências do [!UICONTROL Server-to-server] podem ajudar você a personalizar páginas de aterrissagem ou outras interações com base nos interesses do visitante. Alguns casos de uso comuns incluem:

* Personalização no site: adapte a experiência de um visitante em seu site adicionando dinamicamente conteúdo relevante e chamadas para ação com base nos segmentos aos quais ele pertence.
* Melhorar o atendimento ao cliente: Importe [!DNL Audience Manager] segmentos para um [!DNL CRM] ou outro sistema por meio de uma transferência de dados de servidor para servidor. Esses dados podem fornecer serviço de chamadas ou operadores de chat online com informações relevantes e personalizadas sobre um cliente.

## Requisitos: IDs de usuário e nomes de servidores regionais {#requirements}

O [!UICONTROL DCS API] requer IDs de usuário e IDs de região para validar e fazer solicitações de dados.

* A ID de usuário é necessária porque você precisa associar dados a um visitante específico.
* A ID da região é necessária para vincular chamadas de volta a um nome de servidor e porque os dados do usuário são armazenados em data centers geograficamente mais próximos dos visitantes do site.

## Introdução {#getting-started}

Atualmente, este guia aborda como:

* Obtenha as IDs de usuário e região dos [!DNL DCS] arquivos que você já pode receber como cliente do [!DNL Audience Manager].

* Obtenha as IDs de usuário e região se você usar o [!DNL Visitor ID Service].
* Efetue chamadas para [!DNL DCS] após ter a ID do usuário e da região.

Adicionaremos novos métodos conforme eles estiverem disponíveis. Consulte as seções a seguir para começar.

* [Obter IDs de usuário e regiões de uma resposta do DCS](dcs-aam-ids.md)
* [Obter IDs de usuário e regiões por meio da ID de Experience Cloud...](dcs-mcid-ids.md)
* [Como fazer chamadas de DCS API de servidor para servidor](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [Referência da DCS API](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)
