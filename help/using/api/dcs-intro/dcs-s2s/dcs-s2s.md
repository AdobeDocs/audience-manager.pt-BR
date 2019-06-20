---
description: As apis do servidor para servidor (S 2 S) fornecem códigos e métodos que permitem enviar e receber dados do usuário do DCS e trabalhar com essas informações em seus próprios sistemas ou aplicativos.
seo-description: As apis do servidor para servidor (S 2 S) fornecem códigos e métodos que permitem enviar e receber dados do usuário do DCS e trabalhar com essas informações em seus próprios sistemas ou aplicativos.
seo-title: Apis DCS para transferências de dados do servidor a servidor
solution: Audience Manager
title: Apis DCS para transferências de dados do servidor a servidor
uuid: 8 c 369166-c 8 a 7-46 b 0-9c 13-4 c 027 f 5 b 1 df 9
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# DCS APIs for Server-to-Server Data Transfers{#dcs-apis-for-server-to-server-data-transfers}

Server-to-server ([!UICONTROL S2S]) [!DNL API]s provide code and methods that let you send and receive [!UICONTROL DCS] user data and work with this information in your own systems or applications.

## Common Use Cases {#common-use-cases}

[!UICONTROL Server-to-server] as transferências podem ajudar a personalizar páginas de aterrissagem ou outras interações com base nos interesses do visitante. Alguns casos de uso comuns incluem:

* Personalização no site: Personalize a experiência de um visitante em seu site adicionando dinamicamente conteúdo relevante e chamando a ação com base nos segmentos aos quais eles pertencem.
* Improve customer service: Import [!DNL Audience Manager] segments into a [!DNL CRM] or other system through a server-to-server data transfer. Esses dados podem fornecer serviços de chamada ou operadores de bate-papo online com informações relevantes e personalizadas sobre um cliente.

## Requirements: User IDs and Regional Server Names {#requirements}

The [!UICONTROL DCS API] requires user IDs and region IDs to validate and make data requests.

* A ID de usuário é necessária porque é necessário associar dados a um visitante específico.
* A ID da região é necessária para vincular chamadas de volta a um nome de servidor e porque os dados do usuário são armazenados em centros de dados que estão geograficamente mais próximos dos visitantes do site.

## Introdução {#getting-started}

Atualmente, este guia aborda como:

* Get the user and region IDs from the [!UICONTROL DCS] files you may already receive as an [!DNL Audience Manager] customer.

* Get the user and region IDs if you use the [!DNL Visitor ID Service].
* Make calls to the [!UICONTROL DCS] after you have the user and region ID.

Adicionaremos novos métodos à medida que estiverem disponíveis. Consulte as seções a seguir para começar.

* [Obter IDs de usuário e regiões de uma resposta DCS](dcs-aam-ids.md)
* [Obter IDs de usuário e regiões pela Experience Cloud ID…](dcs-mcid-ids.md)
* [Efetuar chamadas de API do servidor para servidor DCS](dcs-s2s-calls.md)

>[!MORE_ LIKE_ THIS]
>
>* [Referência de API DCS](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

