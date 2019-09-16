---
description: Perguntas frequentes sobre o recurso Audience Lab.
seo-description: Perguntas frequentes sobre o recurso Audience Lab.
seo-title: Perguntas frequentes sobre o Audience Lab
solution: Audience Manager
title: Perguntas frequentes sobre o Audience Lab
topic: API DIL
uuid: b1daf99d-af60-4f65-987d-794a6d45d566
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Perguntas frequentes sobre o Audience Lab{#audience-lab-faq}

Perguntas frequentes sobre o recurso Audience Lab.

<!-- 

audience-lab-faq.xml

 -->

<br> 

**Os segmentos de teste criados nos grupos de teste têm IDs de segmento diferentes? Como mapear as IDs para destinos diferentes?**

Sim, os segmentos de teste têm IDs de segmento diferentes. Para destinos com [!UICONTROL Auto-fill Destination Mapping] ou segmentos enviados para [!DNL Google], [!UICONTROL Audience Lab] tratará os valores de mapeamento da mesma forma que os destinos normalmente.

<br> 

**A mesma característica de conversão pode ser associada a vários grupos de teste?**

Sim, isso é permitido. Pense no caso de um teste usando um segmento macho associado à conversão X e um teste usando um segmento fêmea associado à conversão X. Não importa se os dois testes estão conduzindo conversões, já que estão testando dois públicos diferentes.

<br> 

**Digamos que um grupo de teste esteja usando um perfil autenticado para a divisão do segmento de teste. O perfil autenticado está vinculado a 4 UUIDs do[Audience Manager](../reference/ids-in-aam.md). Quando o visitante exibe uma característica de conversão de uma das quatro UUIDs, isso[!UICONTROL Audience Lab]conta como uma ou quatro conversões?**

Nesse caso, [!UICONTROL Audience Lab] só conta uma conversão.

<br> 

**E se o visitante do caso acima exibir primeiro a característica de conversão de um dos quatro UUIDs vinculados ao perfil autenticado e também exibir a característica de conversão de dois outros UUIDs vinculados ao perfil autenticado? Esse caso conta como uma ou três conversões?**

Nesse caso, [!UICONTROL Audience Lab] conta três conversões, uma para cada dispositivo que exibiu a característica de autenticação.

<br> 

**Um usuário pode ter[!UICONTROL Segment: Read-Only]acesso, mas também[!UICONTROL Audience Lab]testar o acesso à criação de segmentos?**

Consulte [Criar grupo](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) de teste de segmento para obter informações sobre como usar [!UICONTROL Audience Lab] com [!UICONTROL RBAC] privilégios.

**É possível usar[!UICONTROL Audience Lab]em conjunto com os gráficos de dispositivo externo[!UICONTROL Profile Link Device Graph]e externo ([Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html), Tapad Device Graph, Liveramp Device Graph)?**

Por enquanto, [!UICONTROL Audience Lab] só é possível dividir as populações de segmentos pelos dispositivos conectados a um dispositivo qualificado, ao usar o [!UICONTROL Profile Link Device Graph]. Estamos trabalhando para adicionar suporte [!UICONTROL Audience Lab] para os outros gráficos de dispositivos e informaremos quando fizermos isso.
