---
description: Métodos que permitem trabalhar programaticamente com recursos de destino.
seo-description: Métodos que permitem trabalhar programaticamente com recursos de destino.
seo-title: Métodos da API de destino
solution: Audience Manager
title: Métodos da API de destino
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Métodos da API de destino {#destination-api-methods}

Métodos que permitem trabalhar programaticamente com recursos de destino.

<!-- c_destinations_api.xml -->

No Audience Manager, o destino é qualquer outro sistema (servidor de anúncios, rede de anúncios, troca, cookie próprio, etc.) [!DNL DSP] com os quais você deseja compartilhar dados.

## Tipos de Destino: URL e cookie {#destination-types}

Lista as variáveis usadas pelo `destinationType` parâmetro. Especifique `push` ou `ADS` para trabalhar com um [!UICONTROL URL] ou [!UICONTROL cookie destination]. Não é possível criar [!UICONTROL server-to-server destinations] com os [!DNL API] métodos de destino disponíveis.

<!-- r_destination_types.xml -->

| Tipo de destino da API | Tipo de Destino da IU |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORE_LIKE_THIS]
>
>* [Como escolher um tipo de destino](../../../features/destinations/destinations.md)

