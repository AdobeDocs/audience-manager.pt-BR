---
description: A dessegmentação descreve processos que desqualificam e removem perfis de dispositivos dos segmentos. Sua capacidade de remover um perfil de dispositivo de um segmento depende da opção de dispositivo usada para criar uma Regra de mesclagem de perfil.
seo-description: A dessegmentação descreve processos que desqualificam e removem perfis de dispositivos dos segmentos. Sua capacidade de remover um perfil de dispositivo de um segmento depende da opção de dispositivo usada para criar uma Regra de mesclagem de perfil.
seo-title: Regras de mesclagem de perfil e processos de dessegmentação de dispositivo
solution: Audience Manager
title: Regras de mesclagem de perfil e processos de dessegmentação de dispositivo
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# Regras de mesclagem de perfil e processos de dessegmentação de dispositivo {#profile-merge-rules-and-device-un-segmentation-processes}

A dessegmentação descreve processos que desqualificam e removem perfis de dispositivos dos segmentos. Sua capacidade de remover um perfil de dispositivo de um segmento depende da opção de dispositivo usada para criar um [!UICONTROL Profile Merge Rule].

## Opções de dispositivo disponíveis {#device-options}

Como lembrete, os [!UICONTROL Device Options] estão disponíveis na [!UICONTROL Profile Merge Rules Setup] seção quando você cria ou edita um [!UICONTROL Profile Merge Rule].

## Opção de perfil do dispositivo atual e cancelamento da segmentação do dispositivo {#current-device-profile-options}

**[!UICONTROL Device Profile]** é a opção de perfil de dispositivo padrão para um [!UICONTROL Profile Merge Rule]. [!DNL Audience Manager] pode remover um perfil de dispositivo de um segmento quando você [!UICONTROL Profile Merge Rule] usa a **[!UICONTROL Device Profile]** opção. Nestas condições, a dessegmentação acontece quando:

* O perfil do dispositivo está inativo por 120 dias. Um processo semanal de limpeza de dados remove perfis de dispositivos inativos de seus segmentos.
* O dispositivo não se qualifica mais para um segmento porque as atualizações ou alterações no perfil do dispositivo o desqualificam. Isso acontece quando os critérios de qualificação de segmento são alterados, ou você aplica um operador a uma regra de segmento, ou especifica condições de [!DNL AND NOT] recenticidade e frequência [](../segments/recency-and-frequency.md) que usam as configurações menores que/iguais. Os casos de uso são descritos na documentação Supressão [interdispositivo](instant-cross-device-suppression.md) instantânea.

![somente dispositivo](assets/device-only.png)

## Nenhuma opção de dispositivo e cancelamento de segmentação de dispositivo {#no-device-option}

[!DNL Audience Manager] pode remover uma ID entre dispositivos de um segmento quando você [!UICONTROL Profile Merge Rule] usa a opção **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** . Nessas condições, a dessegmentação ocorre quando a ID entre dispositivos não se qualifica mais para um segmento porque as atualizações ou alterações no perfil entre dispositivos a desqualificam. Isso acontece quando os critérios de qualificação de segmento são alterados, ou você aplica um operador a uma regra de segmento, ou especifica condições de [!UICONTROL AND NOT] recenticidade e frequência [](../segments/recency-and-frequency.md) que usam as configurações menores que/iguais. Os casos de uso são descritos na documentação Supressão [interdispositivo](instant-cross-device-suppression.md) instantânea.

![](../assets/current-no-device.png)

## Opções de gráfico de dispositivo e cancelamento da segmentação de dispositivo {#device-graph-options-unsegmentation}

[!DNL Audience Manager] pode remover vários perfis de dispositivo de um segmento quando você [!UICONTROL Profile Merge Rule] usa uma opção de gráfico de dispositivo. A dessegmentação ocorre quando o perfil mesclado do dispositivo a partir do gráfico do dispositivo não se qualifica mais para o segmento porque as atualizações ou alterações nesse perfil mesclado o desqualificam do segmento. Isso acontece quando os critérios de qualificação de segmento são alterados, ou você aplica um operador a uma regra de segmento, ou especifica condições de [!UICONTROL AND NOT] recenticidade e frequência [](../segments/recency-and-frequency.md) que usam as configurações menores que/iguais. Os casos de uso são descritos na documentação Supressão [interdispositivo](instant-cross-device-suppression.md) instantânea.

>[!NOTE]
>
>**Limite de 100 dispositivos para avaliação e desqualificação**de segmentos.
>O Audience Manager mescla até 100 dispositivos ao avaliar segmentos com uma Regra de mesclagem de perfil que usa um gráfico de dispositivo. O Audience Manager avalia o dispositivo atual e até 99 dispositivos vinculados ao dispositivo atual por um perfil [](../../reference/visitor-authentication-states.md) autenticado (ID entre dispositivos). Se o sinal de cancelamento de segmento for emitido, o dispositivo atual e os dispositivos adicionais serão removidos do segmento no destino.

![](assets/last-device-graph.png)

>[!MORE_LIKE_THIS]
>
>* [Perguntas frequentes sobre Regras de mesclagem de perfil e Gráfico de dispositivos](../../faq/faq-profile-merge.md)
>* [Supressão instantânea entre dispositivos](instant-cross-device-suppression.md)

