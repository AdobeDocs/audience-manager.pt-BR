---
description: As APIs de servidor para servidor (S2S) fornecem código e métodos que permitem que você envie e receba dados de usuário do DCS e trabalhe com essas informações em seus próprios sistemas ou aplicativos.
seo-description: As APIs de servidor para servidor (S2S) fornecem código e métodos que permitem que você envie e receba dados de usuário do DCS e trabalhe com essas informações em seus próprios sistemas ou aplicativos.
seo-title: DCS APIs para transferências de dados de servidor para servidor
solution: Audience Manager
title: DCS APIs para transferências de dados de servidor para servidor
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 11%

---


# DCS APIs para transferências de dados de servidor para servidor{#dcs-apis-for-server-to-server-data-transfers}

Os servidores para servidor ([!UICONTROL S2S]) [!DNL API]fornecem código e métodos que permitem que você envie e receba dados [!DNL DCS] do usuário e trabalhe com essas informações em seus próprios sistemas ou aplicativos.

## Casos de uso comuns {#common-use-cases}

[!UICONTROL Server-to-server] as transferências podem ajudá-lo a personalizar landings page ou outras interações com base em interesses de visitantes. Alguns casos de uso comuns incluem:

* Personalização no site: Personalize a experiência de um visitante no site adicionando dinamicamente o conteúdo relevante e as chamadas para ação com base nos segmentos aos quais pertencem.
* Melhorar o serviço ao cliente: Importe [!DNL Audience Manager] segmentos para um [!DNL CRM] ou outro sistema por meio de uma transferência de dados de servidor para servidor. Esses dados podem fornecer ao serviço de chamada ou aos operadores de bate-papo on-line informações relevantes e personalizadas sobre um cliente.

## Requisitos: IDs de usuário e nomes de servidor regionais {#requirements}

O [!UICONTROL DCS API] requer IDs de usuário e IDs de região para validar e fazer solicitações de dados.

* A ID do usuário é obrigatória porque você precisa associar dados a um visitante específico.
* A ID da região é necessária para vincular chamadas novamente a um nome de servidor e porque os dados do usuário são armazenados em data centers geograficamente mais próximos dos visitantes do site.

## Introdução {#getting-started}

Atualmente, este guia aborda como:

* Obtenha as IDs de usuário e região dos [!DNL DCS] arquivos que você já pode receber como [!DNL Audience Manager] cliente.

* Obtenha as IDs de usuário e região se você usar o [!DNL Visitor ID Service].
* Faça chamadas para o [!DNL DCS] depois de ter a ID de usuário e região.

Adicionaremos novos métodos à medida que eles forem sendo disponibilizados. Consulte as seções a seguir para começar.

* [Obter IDs de usuário e regiões de uma resposta do DCS](dcs-aam-ids.md)
* [Obter IDs de usuário e regiões por meio da ID de Experience Cloud...](dcs-mcid-ids.md)
* [Como fazer chamadas de DCS API de servidor para servidor](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [Referência da DCS API ](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

