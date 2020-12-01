---
description: A dessegmentação descreve processos que desqualificam e removem perfis de dispositivos de segmentos. Sua capacidade de remover um perfil de dispositivo de um segmento depende da opção de dispositivo usada para criar uma Regra de mesclagem de Perfis.
seo-description: A dessegmentação descreve processos que desqualificam e removem perfis de dispositivos de segmentos. Sua capacidade de remover um perfil de dispositivo de um segmento depende da opção de dispositivo usada para criar uma Regra de mesclagem de Perfis.
seo-title: Regras de mesclagem de perfis e processos de dessegmentação de dispositivos
solution: Audience Manager
title: Regras de mesclagem de perfis e processos de dessegmentação de dispositivos
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 6%

---


# Regras de mesclagem de perfis e processos de dessegmentação de dispositivos {#profile-merge-rules-and-device-un-segmentation-processes}

A dessegmentação descreve processos que desqualificam e removem perfis de dispositivos de segmentos. Sua capacidade de remover um perfil de dispositivo de um segmento depende da opção de dispositivo usada para criar um [!UICONTROL Profile Merge Rule].

## Opções de dispositivo disponíveis {#device-options}

Como lembrete, [!UICONTROL Device Options] estão disponíveis na seção [!UICONTROL Profile Merge Rules Setup] quando você cria ou edita um [!UICONTROL Profile Merge Rule].

## Opção de Perfil de dispositivo atual e cancelamento de segmentação de dispositivo {#current-device-profile-options}

**[!UICONTROL Device Profile]** é a opção padrão de perfil do dispositivo para um  [!UICONTROL Profile Merge Rule]. [!DNL Audience Manager] pode remover um perfil de dispositivo de um segmento quando você  [!UICONTROL Profile Merge Rule] usa a  **[!UICONTROL Device Profile]** opção. Nestas condições, a dessegmentação acontece quando:

* O perfil do dispositivo está inativo por 120 dias. Um processo semanal de limpeza de dados remove perfis de dispositivos inativos de seus segmentos.
* O dispositivo não se qualifica mais para um segmento porque as atualizações ou alterações no perfil do dispositivo o desqualificam. Isso acontece quando os critérios de qualificação de segmentos são alterados, ou você aplica um operador [!DNL AND NOT] a uma regra de segmento, ou especifica [a recenticidade e frequência](../segments/recency-and-frequency.md) condições que usam as configurações menores que/iguais a. Os casos de uso são descritos na documentação [Supressão interdispositivo instantânea](instant-cross-device-suppression.md).

![somente dispositivo](assets/device-only.png)

## Nenhuma opção de dispositivo e cancelamento de segmentação de dispositivo {#no-device-option}

[!DNL Audience Manager] pode remover uma ID entre dispositivos de um segmento quando você  [!UICONTROL Profile Merge Rule] usa a  **[!UICONTROL Current Authenticated Profiles]** opção  **[!UICONTROL No Device Profile]** +. Nessas condições, a dessegmentação ocorre quando a ID entre dispositivos não se qualifica mais para um segmento porque as atualizações ou alterações no perfil entre dispositivos a desqualificam. Isso acontece quando os critérios de qualificação de segmentos são alterados, ou você aplica um operador [!UICONTROL AND NOT] a uma regra de segmento, ou especifica [a recenticidade e frequência](../segments/recency-and-frequency.md) condições que usam as configurações menores que/iguais a. Os casos de uso são descritos na documentação [Supressão interdispositivo instantânea](instant-cross-device-suppression.md).

![](assets/current-no-device.png)

## Opções de gráfico de dispositivo e cancelamento de segmentação de dispositivo {#device-graph-options-unsegmentation}

[!DNL Audience Manager] pode remover vários perfis de dispositivo de um segmento quando você  [!UICONTROL Profile Merge Rule] usa uma opção de gráfico de dispositivo. A dessegmentação acontece quando o perfil unido do dispositivo a partir do gráfico do dispositivo não se qualifica mais para o segmento porque as atualizações ou alterações nesse perfil mesclado o desqualificam do segmento. Isso acontece quando os critérios de qualificação de segmentos são alterados, ou você aplica um operador [!UICONTROL AND NOT] a uma regra de segmento, ou especifica [a recenticidade e frequência](../segments/recency-and-frequency.md) condições que usam as configurações menores que/iguais a. Os casos de uso são descritos na documentação [Supressão interdispositivo instantânea](instant-cross-device-suppression.md).

>[!NOTE]
>
>**Limite de 100 dispositivos para avaliação e desqualificação** de segmentos.
>Audience Manager une até 100 dispositivos ao avaliar segmentos com uma Regra de mesclagem de Perfil que usa um gráfico de dispositivo. O Audience Manager avalia o dispositivo atual e até 99 dispositivos vinculados ao dispositivo atual por um [perfil autenticado](../../reference/visitor-authentication-states.md) (ID entre dispositivos). Se o sinal de cancelamento de segmento for emitido, o dispositivo atual e os dispositivos adicionais serão removidos do segmento no destino.

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [Perguntas frequentes sobre regras de mesclagem de perfis e gráfico de dispositivos](../../faq/faq-profile-merge.md)
>* [Supressão instantânea entre dispositivos](instant-cross-device-suppression.md)

