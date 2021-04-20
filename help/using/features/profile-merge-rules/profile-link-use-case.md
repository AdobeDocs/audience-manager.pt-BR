---
description: Recommendations e casos de uso para redirecionamento de segmentos e qualificação de segmento personalizada com o gráfico de dispositivos Link de perfil.
seo-description: Recommendations e casos de uso para redirecionamento de segmentos e qualificação de segmento personalizada com o gráfico de dispositivos Link de perfil.
seo-title: Casos de uso do gráfico de dispositivo de link de perfis
solution: Audience Manager
title: Casos de uso do gráfico de dispositivo de link de perfis
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge
exl-id: 8712d02f-c431-4116-8807-41f9e2dda44c
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 9%

---

# Casos de uso do gráfico de dispositivo de link de perfis {#profile-link-device-graph-use-cases}

Recommendations e casos de uso para redirecionamento de segmentos e qualificação de segmento personalizada com o [!UICONTROL Profile Link Device Graph].

## Recomendações {#recommendations}

Considere o gráfico do dispositivo [!UICONTROL Profile Link] para campanhas que:

* Ter um alto nível de autenticação em suas propriedades digitais. Use uma [opção de gráfico de dispositivo externo](merge-rule-definitions.md#device-options) se tiver uma pequena quantidade de usuários autenticados.
* Exigir direcionamento preciso de públicos-alvo conhecidos. O [!UICONTROL Profile Link Device Graph] é criado usando dados originais e autenticados.
* Direcione públicos conhecidos em seus estados autenticados e não autenticados em tempo real.

![](assets/merge-rule-triangle2.png)

## Direcionamento entre dispositivos {#cross-device-personalization}

Digamos que John seja proprietário de três dispositivos que ele usa regularmente para procurar por ofertas de pacotes de férias: Seu laptop ([!DNL Device 1]), seu smartphone ([!DNL Device 2]) e seu tablet ([!DNL Device 3]). No entanto, John usa seus dispositivos para procurar itens diferentes dos acordos de pacote:

* Ele usa seu laptop para procurar voos;
* Ele usa o seu smartphone para procurar hotéis;
* Ele usa seu tablet para procurar visitas guiadas.

Mesmo que John não seja autenticado em todos os três dispositivos mencionados acima, usando a regra **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]**, um provedor de pacotes de feriados pode associar esses dispositivos ao perfil autenticado de John, supondo que ele tenha sido a última pessoa a ser autenticada em todos os três dispositivos.

![gráfico do último dispositivo](assets/last-device-graph.png)

Como o Audience Manager qualifica cada perfil de dispositivo que participou da mesclagem de perfil para um segmento, todos os três perfis de dispositivo são segmentados. O [!UICONTROL Profile Link Device Graph] permite que o Audience Manager olhe o comportamento em todos os três dispositivos e qualifique cada dispositivo para um segmento que nenhum perfil de dispositivo individual qualifica por si mesmo.

Esse [!UICONTROL Profile Merge Rule] permite que os profissionais de marketing forneçam uma experiência consistente para todos os dispositivos de uma pessoa, com base na atividade do usuário em vez da atividade individual do dispositivo.

![personalização entre dispositivos](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [Casos de uso do gráfico do dispositivo externo](external-graph-use-cases.md)
>* [Casos de uso gerais para regras de mesclagem de perfis](merge-rule-targeting-options.md)
>* [Perguntas frequentes sobre as regras de mesclagem de perfis](../../faq/faq-profile-merge.md)

