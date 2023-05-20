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
source-wordcount: '354'
ht-degree: 3%

---

# Explicação do tempo de vida útil do segmento e da característica {#segment-time-to-live-explained}

Como característica [!UICONTROL time-to-live] ([!DNL TTL]) afeta a associação do segmento.

<!-- segment-ttl-explained.xml -->

## Tempo de vida

[!DNL TTL] define quanto tempo um visitante do site permanece em um segmento após o último evento de qualificação de característica. [!DNL TTL]O é definido nas características e não em segmentos. Os visitantes saem de um segmento se não se qualificarem para uma característica antes do fim do [!DNL TTL] intervalo. O padrão [!DNL TTL] para novas características é de 120 dias. Quando definida para 0 dias, a característica nunca expira. [Definir o valor TTL](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) ao criar ou editar uma característica na variável [!UICONTROL Advanced Options] seção da interface de criação de características.

### TTL de 1 dia explicado

Ao definir a variável [!DNL TTL] até 1 dia, o cronômetro TTL começa no dia seguinte após a realização da característica, sem contar as horas restantes no dia de realização da característica.

Audience Manager calcula [!DNL TTL] expiração de características com 1 dia [!DNL TTL] com base na seguinte fórmula:

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **Exemplo 1**: uma característica realizada às 1:00 [!DNL UTC], com 1 dia [!DNL TTL]. [!DNL TTL] expirará 24 + 24 - 1 = 47 horas depois.
* **Exemplo 2**: uma característica realizada às 23:00 [!DNL UTC], com 1 dia [!DNL TTL]. [!DNL TTL] expirará 24 + 24 - 23 = 25 horas depois.

## [!DNL TTL] e remoção de um segmento

Um usuário sai de um segmento se não se qualificar para nenhuma de suas características na [!DNL TTL] intervalo. Por exemplo, se você tiver um segmento com uma característica única com 30 dias [!DNL TTL], o usuário abandonará esse segmento se não se qualificar para a característica novamente nos próximos 30 dias.

![](assets/ttl-explained.png)

## [!DNL TTL] e Renovação de segmento

A variável [!DNL TTL] O é redefinido e o usuário permanece em um segmento, se ele se qualificar para a característica desse segmento dentro do [!DNL TTL] período. Além disso, como a maioria dos segmentos contém várias características com as suas próprias [!DNL TTL] intervalos, um usuário pode permanecer em um segmento e redefinir a variável [!DNL TTL] intervalo, desde que continuem se qualificando para quaisquer características associadas ao segmento.

Por exemplo, digamos que você tenha o Segmento 1 composto da Característica A (30 dias [!DNL TTL]) e Característica B (15 dias [!DNL TTL]). Supondo que um visitante se qualifique para cada característica apenas uma vez, a ilustração abaixo descreve a [!DNL TTL] processo de renovação e duração total no segmento.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] Os TTLs são independentes das configurações de TTL de terceiros

Lembre-se, o [!DNL TTL] definir no seu [!DNL Audience Manager] pixel opera independentemente do [!DNL TTL] definido em outros pixels usados por terceiros ([!DNL DSP]s, redes de anúncios etc.).

>[!MORELIKETHIS]
>
>* [Definir um intervalo de expiração de característica](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

