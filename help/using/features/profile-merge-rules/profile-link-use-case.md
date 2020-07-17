---
description: Recomendações e casos de uso para redefinição de metas de segmentos e qualificação de segmentos personalizados com o gráfico de dispositivo Link de Perfil.
seo-description: Recomendações e casos de uso para redefinição de metas de segmentos e qualificação de segmentos personalizados com o gráfico de dispositivo Link de Perfil.
seo-title: Casos de uso do gráfico de dispositivo de link de perfis
solution: Audience Manager
title: Casos de uso do gráfico de dispositivo de link de perfis
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 9%

---


# Casos de uso do gráfico de dispositivo de link de perfis {#profile-link-device-graph-use-cases}

Recomendações e casos de uso para o redirecionamento de segmentos e qualificação de segmentos personalizados com o [!UICONTROL Profile Link Device Graph].

## Recomendações {#recommendations}

Considere o gráfico do [!UICONTROL Profile Link] dispositivo para campanhas que:

* Tenha um alto nível de autenticação em suas propriedades digitais. Use uma opção [de gráfico de dispositivo](merge-rule-definitions.md#device-options) externo se você tiver uma pequena quantidade de usuários autenticados.
* Exigir direcionamento preciso de audiências conhecidas. O [!UICONTROL Profile Link Device Graph] é criado usando dados autenticados originais.
* Público alvo audiências conhecidas em seus estados autenticados e não autenticados em tempo real.

![](assets/merge-rule-triangle2.png)

## Definição de metas entre dispositivos {#cross-device-personalization}

Vamos dizer que John é dono de três dispositivos que ele usa regularmente para procurar por acordos de pacotes de férias: seu laptop ([!DNL Device 1]), seu smartphone ([!DNL Device 2]) e seu tablet ([!DNL Device 3]). No entanto, John usa seus dispositivos para procurar itens diferentes das ofertas de pacotes:

* Ele usa seu laptop para procurar voos.
* Ele usa seu smartphone para procurar hotéis.
* Ele usa seu tablet para procurar tours guiados.

Mesmo se o John não for autenticado em todos os três dispositivos mencionados acima, usando a regra **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]** , um provedor de pacotes de feriados poderá associar esses dispositivos ao perfil autenticado do John, assumindo que ele foi a última pessoa a autenticar em todos os três dispositivos.

![último dispositivo-gráfico](assets/last-device-graph.png)

Como o Audience Manager qualifica cada perfil de dispositivo que participou da mesclagem de perfil para um segmento, todos os três perfis de dispositivo são segmentados. O [!UICONTROL Profile Link Device Graph] permite que a Audience Manager examine o comportamento em todos os três dispositivos e qualifice cada dispositivo para um segmento que nenhum perfil de dispositivo se qualifica sozinho.

Isso [!UICONTROL Profile Merge Rule] permite que os profissionais de marketing ofereçam uma experiência consistente a todos os dispositivos pertencentes a uma pessoa, com base na atividade do usuário em vez da atividade individual do dispositivo.

![personalização entre dispositivos](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [Casos de uso do gráfico do dispositivo externo](external-graph-use-cases.md)
>* [Casos de uso gerais para regras de mesclagem de perfis](merge-rule-targeting-options.md)
>* [Perguntas frequentes sobre as regras de mesclagem de Perfis](../../faq/faq-profile-merge.md)

