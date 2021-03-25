---
description: As APIs de servidor para servidor (S2S) fornecem código e métodos que permitem enviar e receber dados do usuário do DCS e trabalhar com essas informações em seus próprios sistemas ou aplicativos.
seo-description: As APIs de servidor para servidor (S2S) fornecem código e métodos que permitem enviar e receber dados do usuário do DCS e trabalhar com essas informações em seus próprios sistemas ou aplicativos.
seo-title: DCS APIs para transferências de dados de servidor para servidor
solution: Audience Manager
title: DCS APIs para transferências de dados de servidor para servidor
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
translation-type: tm+mt
source-git-commit: e40233ace5cb74743db7d0f9f90707fa596a7e79
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 11%

---


# DCS APIs para transferências de dados de servidor para servidor{#dcs-apis-for-server-to-server-data-transfers}

Os [!UICONTROL S2S] [!DNL API]s fornecem código e métodos que permitem enviar e receber [!DNL DCS] dados do usuário e trabalhar com essas informações em seus próprios sistemas ou aplicativos.

## Casos de uso comuns {#common-use-cases}

[!UICONTROL Server-to-server] as transferências podem ajudar você a personalizar as páginas de aterrissagem ou outras interações com base nos interesses do visitante. Alguns casos de uso comuns incluem:

* Personalização no site: Personalize a experiência de um visitante em seu site adicionando dinamicamente conteúdo relevante e chamadas para ação com base nos segmentos aos quais ele pertence.
* Melhore o serviço ao cliente: Importe [!DNL Audience Manager] segmentos em um [!DNL CRM] ou outro sistema por meio de uma transferência de dados de servidor para servidor. Esses dados podem fornecer ao serviço de chamadas ou aos operadores de chat on-line informações relevantes e personalizadas sobre um cliente.

## Requisitos: IDs de usuário e nomes de servidor regionais {#requirements}

O [!UICONTROL DCS API] requer IDs de usuário e IDs de região para validar e fazer solicitações de dados.

* A ID de usuário é obrigatória porque é necessário associar os dados a um visitante específico.
* A ID de região é necessária para vincular chamadas a um nome de servidor e porque os dados do usuário são armazenados em data centers geograficamente mais próximos dos visitantes do site.

## Introdução {#getting-started}

Atualmente, este guia aborda como:

* Obtenha as IDs de usuário e região dos arquivos [!DNL DCS] que você já pode receber como cliente [!DNL Audience Manager].

* Obtenha as IDs de usuário e região se você usar o [!DNL Visitor ID Service].
* Faça chamadas para [!DNL DCS] depois de ter a ID do usuário e da região.

Adicionaremos novos métodos à medida que eles forem sendo disponibilizados. Consulte as seções a seguir para começar.

* [Obter IDs de usuário e regiões de uma resposta do DCS](dcs-aam-ids.md)
* [Obter IDs de usuário e regiões por meio da ID de Experience Cloud..](dcs-mcid-ids.md)
* [Como fazer chamadas de DCS API de servidor para servidor](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [Referência da DCS API ](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

