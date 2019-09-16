---
description: Como o intervalo de tempo de vida real (TTL) afeta a associação ao segmento.
seo-description: Como o intervalo de tempo de vida real (TTL) afeta a associação ao segmento.
seo-title: Explicação do tempo de vida do segmento e da característica
solution: Audience Manager
title: Explicação do tempo de segmento ao vivo
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
translation-type: tm+mt
source-git-commit: 7e9aada98fe9c18c6fc484255b3c9ff33dc59324

---


# Explicação do tempo de vida do segmento e da característica {#segment-time-to-live-explained}

Como o intervalo de características [!UICONTROL time-to-live] ([!DNL TTL]) afeta a associação de segmentos.

<!-- segment-ttl-explained.xml -->

## Tempo de vida

[!DNL TTL] define quanto tempo um visitante do site permanece em um segmento após o último evento de qualificação de característica. [!DNL TTL] é definida em características e não em segmentos. Os visitantes saem de um segmento se não visualizarem uma característica qualificada antes do final do [!DNL TTL] intervalo. O padrão [!DNL TTL] para novas características é 120 dias. Quando definido como 0 dias, a característica nunca expira. [Defina o valor](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) TTL ao criar ou editar uma característica na [!UICONTROL Advanced Options] seção da interface de criação de característica.

## [!DNL TTL] e Desistência de um segmento

Um usuário cai de um segmento se não vir nenhuma de suas características dentro do [!DNL TTL] intervalo. Por exemplo, se você tiver um segmento de 1 característica com 30 dias [!DNL TTL], o usuário sairá desse segmento se ele não vir a característica novamente dentro de 30 dias.

![](assets/ttl_1.png)

## [!DNL TTL] e renovação de segmentos

O usuário [!DNL TTL] é redefinido e permanece em um segmento, se ele vir a característica desse segmento dentro do [!DNL TTL] período. Além disso, como a maioria dos segmentos contém várias características com seus próprios [!DNL TTL] períodos, um usuário pode permanecer em um segmento (e redefinir o [!DNL TTL] intervalo), contanto que continue vendo quaisquer características associadas a um segmento. Por exemplo, digamos que você tenha o Segmento 1 composto pela Caractere A (30 dias [!DNL TTL]) e pela Caractere B (15 dias [!DNL TTL]). Supondo que o usuário visualize cada característica apenas uma vez, a ilustração abaixo descreve o processo de [!DNL TTL] renovação e a duração total do segmento.

![](assets/ttl_2.png)

## [!DNL Audience Manager] Os TTLs são independentes das configurações TTL de terceiros

Lembre-se, o [!DNL TTL] conjunto no seu [!DNL Audience Manager] pixel opera independentemente do [!DNL TTL] conjunto em outros pixels usados por terceiros ([!DNL DSP]s, redes de anúncios etc.).

>[!MORE_LIKE_THIS]
>
>* [Definir um intervalo de expiração de característica](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

