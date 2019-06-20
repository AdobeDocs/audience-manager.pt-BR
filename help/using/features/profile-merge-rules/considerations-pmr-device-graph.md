---
description: Evite usar Regras de mesclagem de perfil com um Gráfico de dispositivo para segmentos que têm pouca a população de segmentos em tempo real.
seo-description: Evite usar Regras de mesclagem de perfil com um Gráfico de dispositivo para segmentos que têm pouca a população de segmentos em tempo real.
seo-title: Considerações importantes para Regras de mesclagem de perfil com gráficos de dispositivo
title: Considerações importantes para Regras de mesclagem de perfil com gráficos de dispositivo
uuid: 93 cd 8861-210 d -4 c 52-9 cb 7-6 f 2 dd 7 dc 018 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Important Considerations for Profile Merge Rules with Device Graphs {#important-considerations-for-profile-merge-rules-with-device-graphs}

Avoid using [!UICONTROL Profile Merge Rules] with a [!UICONTROL Device Graph] for segments which have little to no real-time segment population.

>[!IMPORTANT]
>
>If the [!UICONTROL Profile Merge Rule] is configured incorrectly, the segment population exported to batch destinations may be significantly lower than expected.

Segments using a [Profile Merge Rule with a Device Graph](../../features/profile-merge-rules/merge-rule-targeting-options.md#device-graph-options) are only evaluated against devices seen in real-time on [Audience Manager’s Edge Servers](../../reference/system-components/components-edge.md) after the segment has been created.

Remember, a [!UICONTROL Profile Merge Rule] with a [!UICONTROL Device Graph] has one of the following device options selected, as shown below.

![](assets/pmr-considerations-1.png)

Devices that qualify for a segment in real-time are measured by the [segment’s real-time population](../../features/segments/segment-builder-data.md#segment-populations).

![](assets/pmr-considerations-2.png)

Uma população de segmento em tempo real baixa significa que alguns dos dispositivos qualificados para o segmento são vistos em tempo real. For best performance, segments with little to no real-time population should use a [!UICONTROL Profile Merge Rule] set to evaluate the *[!UICONTROL Current Device]*, like in the image below.

![](assets/pmr-considerations-3.png)

Setting the [!UICONTROL Profile Merge Rule] to evaluate the *[!UICONTROL Current Device]* ensures that all devices (not just those seen in real-time) are evaluated for the segment. Todos os dispositivos qualificados para o segmento são definidos pela população do segmento total, como mostrado abaixo.

![](assets/pmr-considerations-4.png)