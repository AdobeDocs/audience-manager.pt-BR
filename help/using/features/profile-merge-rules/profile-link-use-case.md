---
description: Recomendações e casos de uso para redirecionamento de segmento e qualificação de segmento personalizado com o gráfico de dispositivos do Link de perfil.
seo-description: Recommendations and use cases for segment retargeting and personalized segment qualification with the Profile Link device graph.
seo-title: Profile Link Device Graph Use Cases
solution: Audience Manager
title: Casos de uso do gráfico de dispositivos de link de perfis
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge
exl-id: 8712d02f-c431-4116-8807-41f9e2dda44c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 4%

---

# Casos de uso do gráfico de dispositivos de link de perfis {#profile-link-device-graph-use-cases}

Recomendações e casos de uso para redirecionamento de segmento e qualificação de segmento personalizado com o [!UICONTROL Profile Link Device Graph].

## Recomendações   {#recommendations}

Considere o gráfico de dispositivos [!UICONTROL Profile Link] para campanhas que:

* Ter um alto nível de autenticação em suas propriedades digitais. Use uma [opção de gráfico de dispositivo externo](merge-rule-definitions.md#device-options) se você tiver uma pequena quantidade de usuários autenticados.
* Exigir o direcionamento preciso de públicos conhecidos. O [!UICONTROL Profile Link Device Graph] é compilado usando dados autenticados próprios.
* Direcione públicos-alvo conhecidos em seus estados autenticado e não autenticado em tempo real.

![](assets/merge-rule-triangle2.png)

## Direcionamento entre dispositivos {#cross-device-personalization}

Digamos que John seja proprietário de três dispositivos que ele usa regularmente para procurar por ofertas de pacotes de viagem: seu laptop ([!DNL Device 1]), seu smartphone ([!DNL Device 2]) e seu tablet ([!DNL Device 3]). No entanto, John usa seus dispositivos para procurar por diferentes itens das ofertas de pacotes:

* Ele usa seu laptop para procurar voos;
* Ele usa seu smartphone para procurar hotéis;
* Ele usa seu tablet para procurar visitas guiadas.

Mesmo que John não seja autenticado em todos os três dispositivos mencionados acima, usando a regra **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]**, um provedor de pacotes de feriados pode associar esses dispositivos ao perfil autenticado de John, assumindo que ele foi a última pessoa a autenticar em todos os três dispositivos.

![último-gráfico-de-dispositivo](assets/last-device-graph.png)

Como o Audience Manager qualifica cada perfil de dispositivo que participou da mesclagem de perfis para um segmento, todos os três perfis de dispositivo são segmentados. O [!UICONTROL Profile Link Device Graph] permite que o Audience Manager analise o comportamento nos três dispositivos e qualifique cada dispositivo para um segmento para o qual nenhum perfil de dispositivo se qualifica por conta própria.

Este [!UICONTROL Profile Merge Rule] permite que os profissionais de marketing forneçam uma experiência consistente para todos os dispositivos de propriedade de uma pessoa, com base na atividade do usuário, em vez da atividade individual do dispositivo.

![personalização entre dispositivos](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [Casos de uso do gráfico do dispositivo externo](external-graph-use-cases.md)
>* [Casos de uso gerais para regras de mesclagem de perfis](merge-rule-targeting-options.md)
>* [Perguntas frequentes sobre Regras de Mesclagem de Perfis](../../faq/faq-profile-merge.md)
