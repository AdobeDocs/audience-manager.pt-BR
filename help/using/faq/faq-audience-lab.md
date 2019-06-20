---
description: Perguntas frequentes sobre o recurso do Audience Lab.
seo-description: Perguntas frequentes sobre o recurso do Audience Lab.
seo-title: Perguntas frequentes do Audience Lab
solution: Audience Manager
title: Perguntas frequentes do Audience Lab
topic: API DIL
uuid: b 1 daf 99 d-af 60-4 f 65-987 d -794 a 6 d 45 d 566
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab FAQ{#audience-lab-faq}

Perguntas frequentes sobre o recurso do Audience Lab.

<!-- 

audience-lab-faq.xml

 -->

<br> 

**Os segmentos de teste criados nos grupos de teste têm IDs de segmento diferentes? How do I map the IDs to different destinations?**

Sim, os segmentos de teste têm IDs de segmento diferentes. For destinations with [!UICONTROL Auto-fill Destination Mapping] or segments sent to [!DNL Google], [!UICONTROL Audience Lab] will handle the mapping values just like the destinations normally would.

<br> 

**A mesma característica de conversão pode ser associada a vários grupos de teste?**

Sim, isso é permitido. Pense em um caso de um teste usando um segmento masculino associado à conversão X e um teste usando um segmento feminino associado à conversão X. Não importa que ambos os testes estejam promovendo conversões, pois estão testando dois públicos diferentes.

<br> 

**Vamos supor que um grupo de teste esteja usando um perfil autenticado para a divisão do segmento de teste. The authenticated profile is linked to 4[Audience Manager UUIDs](../reference/ids-in-aam.md). When the visitor exhibits a conversion trait from one of the four UUIDs, does[!UICONTROL Audience Lab]count this as one or four conversions?**

In this case, [!UICONTROL Audience Lab] only counts one conversion.

<br> 

**O que acontece se o visitante do caso acima exibir a característica de conversão de um dos quatro uuids vinculados ao seu perfil autenticado e também exibir a característica de conversão de dois outros uuids vinculados ao perfil autenticado? Does this case count as one or three conversions?**

In this case, [!UICONTROL Audience Lab] counts three conversions, one for each device that has exhibited the authentication trait.

<br> 

**Um usuário pode[!UICONTROL Segment: Read-Only]ter acesso e[!UICONTROL Audience Lab]também testar o acesso à criação de segmentos?**

See [Create Segment Test Group](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) for information on how to use [!UICONTROL Audience Lab] with [!UICONTROL RBAC] privileges.

**Posso usar[!UICONTROL Audience Lab]em conjunto com[!UICONTROL Profile Link Device Graph]os Gráficos de dispositivo externos ([Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html), Gráfico de dispositivo de TV, Gráfico de dispositivo Liveramp)?**

For now, [!UICONTROL Audience Lab] can only split out segment populations by the devices connected to a qualifying device, when using the [!UICONTROL Profile Link Device Graph]. We are working on adding support in [!UICONTROL Audience Lab] for the other device graphs and will let you know when we do so.
