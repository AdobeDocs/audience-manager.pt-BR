---
description: Evite usar Regras de mesclagem de perfil com um Gráfico de dispositivos para segmentos que têm pouca ou nenhuma população de segmentos em tempo real.
seo-description: Evite usar Regras de mesclagem de perfil com um Gráfico de dispositivos para segmentos que têm pouca ou nenhuma população de segmentos em tempo real.
seo-title: Considerações importantes para regras de mesclagem de perfil com gráficos de dispositivo
title: Considerações importantes para regras de mesclagem de perfil com gráficos de dispositivo
uuid: 93cd8861-210d-4c52-9cb7-6f2dd7dc018a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Considerações importantes para regras de mesclagem de perfil com gráficos de dispositivo {#important-considerations-for-profile-merge-rules-with-device-graphs}

Evite usar [!UICONTROL Profile Merge Rules] com um [!UICONTROL Device Graph] para segmentos que têm pouca ou nenhuma população de segmentos em tempo real.

>[!IMPORTANT]
>
>Se o segmento [!UICONTROL Profile Merge Rule] estiver configurado incorretamente, a população de segmentos exportada para destinos em lote pode ser significativamente menor do que o esperado.

Segmentos que usam uma Regra de mesclagem de [perfil com um Gráfico](../../features/profile-merge-rules/merge-rule-targeting-options.md#device-graph-options) de dispositivos são avaliados somente em dispositivos vistos em tempo real nos Servidores [de borda do](../../reference/system-components/components-edge.md) Audience Manager após a criação do segmento.

Lembre-se de que um dispositivo [!UICONTROL Profile Merge Rule] com uma [!UICONTROL Device Graph] das opções de dispositivo a seguir está selecionado, conforme mostrado abaixo.

![](assets/pmr-considerations-1.png)

Os dispositivos que se qualificam para um segmento em tempo real são medidos pela população [em tempo real do](../../features/segments/segment-builder-data.md#segment-populations)segmento.

![](assets/pmr-considerations-2.png)

Uma população de segmentos em tempo real baixa significa que muito poucos dos dispositivos qualificados para o segmento estão sendo vistos em tempo real. Para obter o melhor desempenho, os segmentos com pouca ou nenhuma população em tempo real devem usar um [!UICONTROL Profile Merge Rule] conjunto para avaliar o *[!UICONTROL Current Device]*, como na imagem abaixo.

![](assets/pmr-considerations-3.png)

A configuração [!UICONTROL Profile Merge Rule] para avaliar o *[!UICONTROL Current Device]* garante que todos os dispositivos (não apenas os visualizados em tempo real) sejam avaliados para o segmento. Todos os dispositivos qualificados para o segmento são definidos pela população total do segmento, como mostrado abaixo.

![](assets/pmr-considerations-4.png)