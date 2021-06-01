---
description: Como o intervalo TTL (trait time-to-live) afeta a associação de segmentos.
seo-description: Como o intervalo TTL (trait time-to-live) afeta a associação de segmentos.
seo-title: Explicação do tempo de vida útil do segmento e da característica
solution: Audience Manager
title: Explicação do tempo de vida do segmento
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: 'Características '
exl-id: 2f019071-f829-4336-b2cf-26ec1f18fc91
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 3%

---

# Explicação do tempo de vida útil do segmento e da característica {#segment-time-to-live-explained}

Como o intervalo de características [!UICONTROL time-to-live] ([!DNL TTL]) afeta a associação de segmentos.

<!-- segment-ttl-explained.xml -->

## Tempo de vida

[!DNL TTL] define quanto tempo um visitante do site permanece em um segmento após o último evento de qualificação de característica. [!DNL TTL]O é definido nas características e não em segmentos. Os visitantes saem de um segmento se não se qualificarem para uma característica antes do final do intervalo [!DNL TTL]. O padrão [!DNL TTL] para novas características é de 120 dias. Quando definido como 0 dias, a característica nunca expira. [Defina o ](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) valor TTL ao criar ou editar uma característica na  [!UICONTROL Advanced Options] seção da interface de criação de características.

### Explicação do TTL de 1 dia

Ao definir [!DNL TTL] para 1 dia, o cronômetro TTL começa no dia seguinte após a realização da característica, sem contar as horas restantes no dia de realização da característica.

Audience Manager calcula [!DNL TTL] a expiração para características com 1 dia [!DNL TTL] com base na seguinte fórmula:

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **Exemplo 1**: Uma característica realizada às 1:00  [!DNL UTC], com um dia  [!DNL TTL]. [!DNL TTL] expirará 24 + 24 - 1 = 47 horas depois.
* **Exemplo 2**: Uma característica realizada às 23:00  [!DNL UTC], com um dia  [!DNL TTL]. [!DNL TTL] expirará 24 + 24 - 23 = 25 horas depois.

## [!DNL TTL] e Descartar de um segmento

Um usuário sai de um segmento se não estiver qualificado para nenhuma de suas características dentro do intervalo [!DNL TTL]. Por exemplo, se você tiver um segmento de 1 característica com um período de 30 dias [!DNL TTL], o usuário sairá desse segmento se não se qualificar para a característica novamente nos próximos 30 dias.

![](assets/ttl-explained.png)

## [!DNL TTL] e Renovação de segmentos

O [!DNL TTL] é redefinido e o usuário permanece em um segmento, se estiver qualificado para a característica desse segmento dentro do período [!DNL TTL]. Além disso, como a maioria dos segmentos contém várias características com seus próprios intervalos [!DNL TTL], um usuário pode permanecer em um segmento e redefinir o intervalo [!DNL TTL], desde que continue se qualificando para quaisquer características associadas ao segmento.

Por exemplo, digamos que você tenha o Segmento 1 composto pela Característica A (30 dias [!DNL TTL]) e pela Característica B (15 dias [!DNL TTL]). Supondo que um visitante se qualifique para cada característica apenas uma vez, a ilustração abaixo descreve o processo de renovação [!DNL TTL] e a duração total no segmento.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] Os TTLs são independentes das configurações de TTL de terceiros

Lembre-se, o [!DNL TTL] definido no pixel [!DNL Audience Manager] opera independentemente do [!DNL TTL] definido em outros pixels usados por terceiros ([!DNL DSP]s, redes de anúncios etc.).

>[!MORELIKETHIS]
>
>* [Definir um intervalo de expiração de característica](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

