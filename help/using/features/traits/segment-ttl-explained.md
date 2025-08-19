---
description: Como o intervalo TTL (time-to-live) da característica afeta a associação do segmento.
seo-description: How trait time-to-live (TTL) interval affects segment membership.
seo-title: Segment and Trait Time to Live Explained
solution: Audience Manager
title: Explicação do tempo de vida do segmento
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: Traits
exl-id: 2f019071-f829-4336-b2cf-26ec1f18fc91
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# Explicação do tempo de vida útil do segmento e da característica {#segment-time-to-live-explained}

Como o intervalo [!UICONTROL time-to-live] ([!DNL TTL]) da característica afeta a associação do segmento.

<!-- segment-ttl-explained.xml -->

## Tempo de vida

[!DNL TTL] define quanto tempo um visitante do site permanece em um segmento após o último evento de qualificação de característica. [!DNL TTL] está definido nas características e não em segmentos. Os visitantes saem de um segmento se não se qualificarem para uma característica antes do final do intervalo [!DNL TTL]. O padrão [!DNL TTL] para novas características é 120 dias. Quando definida para 0 dias, a característica nunca expira. [Defina o valor TTL](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) ao criar ou editar uma característica na seção [!UICONTROL Advanced Options] da interface de criação de características.

### TTL de 1 dia explicado

Ao definir o [!DNL TTL] como 1 dia, o cronômetro TTL começa no dia seguinte após a realização da característica, sem contar as horas restantes no dia de realização da característica.

A Audience Manager calcula a expiração de [!DNL TTL] para características com 1 dia [!DNL TTL] com base na seguinte fórmula:

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **Exemplo 1**: uma característica realizada em 1:00 [!DNL UTC], com um 1 dia [!DNL TTL]. [!DNL TTL] expirará em 24 + 24 - 1 = 47 horas depois.
* **Exemplo 2**: uma característica realizada em 23:00 [!DNL UTC], com um dia 1 [!DNL TTL]. [!DNL TTL] expirará em 24 + 24 - 23 = 25 horas depois.

## [!DNL TTL] e Retirando de um Segmento

Um usuário sai de um segmento se não se qualificar para nenhuma de suas características no intervalo [!DNL TTL]. Por exemplo, se você tiver um segmento de uma característica com um [!DNL TTL] de 30 dias, o usuário abandonará esse segmento se não se qualificar para a característica novamente nos próximos 30 dias.

![](assets/ttl-explained.png)

## [!DNL TTL] e Renovação de segmento

O [!DNL TTL] é redefinido e o usuário permanece em um segmento, se ele se qualificar para a característica desse segmento dentro do período [!DNL TTL]. Além disso, como a maioria dos segmentos contém várias características com seus próprios intervalos [!DNL TTL], um usuário pode permanecer em um segmento e redefinir o intervalo [!DNL TTL], desde que continue se qualificando para quaisquer características associadas ao segmento.

Por exemplo, digamos que você tenha o Segmento 1 composto da Característica A (30 dias [!DNL TTL]) e da Característica B (15 dias [!DNL TTL]). Supondo que um visitante se qualifique para cada característica apenas uma vez, a ilustração abaixo descreve o processo de renovação [!DNL TTL] e a duração total no segmento.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTLs são independentes das configurações de TTL de terceiros

Lembre-se, o conjunto [!DNL TTL] no pixel [!DNL Audience Manager] opera independentemente do conjunto [!DNL TTL] em outros pixels usados por terceiros ([!DNL DSP]s, redes de anúncios etc.).

>[!MORELIKETHIS]
>
>* [Definir um intervalo de expiração de característica](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)
