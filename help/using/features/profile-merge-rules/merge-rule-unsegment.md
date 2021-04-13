---
description: O cancelamento de segmentos descreve processos que desqualificam e removem perfis de dispositivos dos segmentos. Sua capacidade de remover um perfil de dispositivo de um segmento depende da opção de dispositivo usada para criar uma Regra de mesclagem de perfis.
seo-description: O cancelamento de segmentos descreve processos que desqualificam e removem perfis de dispositivos dos segmentos. Sua capacidade de remover um perfil de dispositivo de um segmento depende da opção de dispositivo usada para criar uma Regra de mesclagem de perfis.
seo-title: Regras de mesclagem de perfis e processos de dessegmentação de dispositivos
solution: Audience Manager
title: Regras de mesclagem de perfis e processos de dessegmentação de dispositivos
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: Mesclar perfis
exl-id: ff3da607-5c25-45b2-ac27-071c22d518a0
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 6%

---

# Regras de mesclagem de perfis e processos de dessegmentação de dispositivos {#profile-merge-rules-and-device-un-segmentation-processes}

O cancelamento de segmentos descreve processos que desqualificam e removem perfis de dispositivos dos segmentos. Sua capacidade de remover um perfil de dispositivo de um segmento depende da opção de dispositivo usada para criar um [!UICONTROL Profile Merge Rule].

## Opções de dispositivo disponíveis {#device-options}

Como lembrete, [!UICONTROL Device Options] estão disponíveis na seção [!UICONTROL Profile Merge Rules Setup] ao criar ou editar um [!UICONTROL Profile Merge Rule].

## Opção de Perfil de Dispositivo Atual e Cancelamento de Segmentação de Dispositivo {#current-device-profile-options}

**[!UICONTROL Device Profile]** é a opção de perfil de dispositivo padrão para um  [!UICONTROL Profile Merge Rule]. [!DNL Audience Manager] Você pode remover um perfil de dispositivo de um segmento, quando  [!UICONTROL Profile Merge Rule] usar a  **[!UICONTROL Device Profile]** opção . Nessas condições, a cancelamento de segmentação ocorre quando:

* O perfil do dispositivo ficou inativo por 120 dias. Um processo semanal de limpeza de dados remove perfis de dispositivos inativos de seus segmentos.
* O dispositivo não se qualifica mais para um segmento porque as atualizações ou alterações no perfil do dispositivo o desqualificam. Isso acontece quando os critérios de qualificação de segmento mudam, ou você aplica um operador [!DNL AND NOT] a uma regra de segmento, ou especifica [recenticidade e frequência](../segments/recency-and-frequency.md) condições que usam as configurações menor que/igual a. Os casos de uso são descritos na documentação de [Supressão instantânea entre dispositivos](instant-cross-device-suppression.md).

![somente dispositivo](assets/device-only.png)

## Nenhuma opção de dispositivo e cancelamento de segmentos de dispositivo {#no-device-option}

[!DNL Audience Manager] Você pode remover uma ID entre dispositivos de um segmento quando  [!UICONTROL Profile Merge Rule] usar a  **[!UICONTROL Current Authenticated Profiles]** opção  **[!UICONTROL No Device Profile]** +. Nessas condições, a cancelamento de segmentação acontece quando a ID entre dispositivos não se qualifica mais para um segmento porque as atualizações ou alterações no perfil entre dispositivos a desqualificam. Isso acontece quando os critérios de qualificação de segmento mudam, ou você aplica um operador [!UICONTROL AND NOT] a uma regra de segmento, ou especifica [recenticidade e frequência](../segments/recency-and-frequency.md) condições que usam as configurações menor que/igual a. Os casos de uso são descritos na documentação de [Supressão instantânea entre dispositivos](instant-cross-device-suppression.md).

![](assets/current-no-device.png)

## Opções de gráfico de dispositivo e cancelamento de segmentação de dispositivo {#device-graph-options-unsegmentation}

[!DNL Audience Manager] Você pode remover vários perfis de dispositivo de um segmento, quando  [!UICONTROL Profile Merge Rule] usar uma opção de gráfico de dispositivos. A cancelamento de segmentos acontece quando o perfil mesclado do dispositivo no gráfico de dispositivos não se qualifica mais para o segmento, pois as atualizações ou alterações nesse perfil mesclado o desqualificam do segmento. Isso acontece quando os critérios de qualificação de segmento mudam, ou você aplica um operador [!UICONTROL AND NOT] a uma regra de segmento, ou especifica [recenticidade e frequência](../segments/recency-and-frequency.md) condições que usam as configurações menor que/igual a. Os casos de uso são descritos na documentação de [Supressão instantânea entre dispositivos](instant-cross-device-suppression.md).

>[!NOTE]
>
>**Limite de 100 dispositivos para avaliação e inibição** de segmentos.
>O Audience Manager mescla até 100 dispositivos ao avaliar segmentos com uma Regra de mesclagem de perfis que usa um gráfico de dispositivos. O Audience Manager avalia o dispositivo atual e até 99 dispositivos vinculados ao dispositivo atual por um [perfil autenticado](../../reference/visitor-authentication-states.md) (ID entre dispositivos). Se o sinal de cancelamento de segmento for emitido, o dispositivo atual e os dispositivos adicionais serão removidos do segmento no destino.

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [Perguntas frequentes sobre regras de mesclagem de perfis e gráfico de dispositivos](../../faq/faq-profile-merge.md)
>* [Supressão instantânea entre dispositivos](instant-cross-device-suppression.md)

