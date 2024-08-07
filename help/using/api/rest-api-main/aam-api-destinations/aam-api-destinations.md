---
description: Métodos que permitem trabalhar programaticamente com recursos de destino.
seo-description: Methods that let you work programmatically with destination features.
seo-title: Destination API Methods
solution: Audience Manager
title: Métodos da API de destino
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
exl-id: 38dea854-2b7b-417e-9d56-919b65807628
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 0%

---

# Métodos da API de destino {#destination-api-methods}

Métodos que permitem trabalhar programaticamente com recursos de destino.

<!-- c_destinations_api.xml -->

No Audience Manager, um destino é qualquer outro sistema (servidor de anúncios, [!DNL DSP], rede de anúncios, exchange, seu próprio cookie próprio, etc.) com o qual você deseja compartilhar dados.

## Tipos de destino: URL e cookie {#destination-types}

Lista as variáveis usadas pelo parâmetro `destinationType`. Especifique `push` ou `ADS` para trabalhar com um [!UICONTROL URL] ou [!UICONTROL cookie destination]. Você não pode criar [!UICONTROL server-to-server destinations] com os métodos de destino [!DNL API] disponíveis.

<!-- r_destination_types.xml -->

| Tipo de destino de API | Tipo de destino da interface do usuário |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [Como escolher um tipo de destino](../../../features/destinations/destinations.md)
