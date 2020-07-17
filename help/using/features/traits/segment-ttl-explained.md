---
description: Como o intervalo de tempo de vida real (TTL) afeta a associação ao segmento.
seo-description: Como o intervalo de tempo de vida real (TTL) afeta a associação ao segmento.
seo-title: Explicação do tempo de vida do segmento e da característica
solution: Audience Manager
title: Explicação do tempo de segmento ao vivo
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 3%

---


# Explicação do tempo de vida útil do segmento e da característica {#segment-time-to-live-explained}

Como o intervalo de características [!UICONTROL time-to-live] ([!DNL TTL]) afeta a associação de segmentos.

<!-- segment-ttl-explained.xml -->

## Tempo de vida

[!DNL TTL] define quanto tempo um visitante do site permanece em um segmento após o último evento de qualificação de característica. [!DNL TTL]O é definido nas características e não em segmentos. Visitors fall out of a segment if they do not qualify for a trait before the end of the [!DNL TTL] interval. O padrão [!DNL TTL] para novas características é 120 dias. Quando definido como 0 dias, a característica nunca expira. [Defina o valor](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) TTL ao criar ou editar uma característica na [!UICONTROL Advanced Options] seção da interface de criação de característica.

### Explicação do TTL de 1 dia

Ao definir [!DNL TTL] como 1 dia, o temporizador TTL start no dia seguinte após a realização do traço, sem contar as horas restantes no dia de realização do traço.

Audience Manager calcula a [!DNL TTL] expiração de características com 1 dia [!DNL TTL] com base na seguinte fórmula:

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **Exemplo 1**: Um traço realizado às 13:00 [!DNL UTC], com um dia [!DNL TTL]. [!DNL TTL] expirará 24 + 24 - 1 = 47 horas depois.
* **Exemplo 2**: Um traço realizado às 23:00 [!DNL UTC], com um dia [!DNL TTL]. [!DNL TTL] expirará 24 + 24 - 23 = 25 horas depois.

## [!DNL TTL] e Desistência de um segmento

Um usuário sai de um segmento se não estiver qualificado para nenhuma de suas características dentro do [!DNL TTL] intervalo. Por exemplo, se você tiver um segmento de 1 característica com 30 dias [!DNL TTL], o usuário sairá desse segmento se ele não se qualificar para a característica novamente nos próximos 30 dias.

![](assets/ttl-explained.png)

## [!DNL TTL] e renovação de segmentos

O usuário [!DNL TTL] é redefinido e permanece em um segmento, se estiver qualificado para a característica desse segmento dentro do [!DNL TTL] período. Além disso, como a maioria dos segmentos contém várias características com seus próprios [!DNL TTL] intervalos, um usuário pode permanecer em um segmento e redefinir o [!DNL TTL] intervalo, contanto que continue se qualificando para quaisquer características associadas ao segmento.

Por exemplo, digamos que você tenha o Segmento 1 composto pela Caractere A (30 dias [!DNL TTL]) e pela Caractere B (15 dias [!DNL TTL]). Considerando que um visitante se qualifica para cada característica apenas uma vez, a ilustração abaixo descreve o processo de [!DNL TTL] renovação e a duração total do segmento.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] Os TTLs são independentes das configurações TTL de terceiros

Lembre-se, o [!DNL TTL] conjunto no seu [!DNL Audience Manager] pixel opera independentemente do [!DNL TTL] conjunto em outros pixels usados por terceiros ([!DNL DSP]s, redes de anúncios etc.).

>[!MORELIKETHIS]
>
>* [Definir um intervalo de expiração de característica](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

