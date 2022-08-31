---
description: Perguntas frequentes sobre o recurso Audience Lab.
seo-description: Frequently asked questions about the Audience Lab feature.
seo-title: Audience Lab FAQ
solution: Audience Manager
title: Perguntas frequentes sobre o Audience Lab
uuid: b1daf99d-af60-4f65-987d-794a6d45d566
feature: Audience Lab
exl-id: 25bdabb5-2ba8-45d2-81ca-05c0590d7d96
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 94%

---

# Perguntas frequentes sobre o Audience Lab{#audience-lab-faq}

Perguntas frequentes sobre o recurso Audience Lab.

<br> 

**Os segmentos de teste criados nos grupos de teste têm IDs de segmento diferentes? Como mapear as IDs para destinos diferentes?**

Sim, os segmentos de teste têm IDs de segmento diferentes. Para destinos com o [!UICONTROL Auto-fill Destination Mapping] ou segmentos enviados para o [!DNL Google], o [!UICONTROL Audience Lab] tratará os valores de mapeamento da mesma forma que os destinos normalmente.

<br> 

**A mesma característica de conversão pode ser associada a vários grupos de teste?**

Sim, isso é permitido. Pense no caso de um teste usando um segmento macho associado à conversão X e um teste usando um segmento fêmea associado à conversão X. Não importa se os dois testes estão conduzindo conversões, já que estão testando dois públicos diferentes.

<br> 

**Digamos que um grupo de teste esteja usando um perfil autenticado para a divisão do segmento de teste. O perfil autenticado está vinculado a 4 [UUIDs do Audience Manager](../reference/ids-in-aam.md). Quando o visitante exibe uma característica de conversão de uma das quatro UUIDs, o [!UICONTROL Audience Lab] conta como uma ou quatro conversões?**

Nesse caso, o [!UICONTROL Audience Lab] só conta uma conversão.

<br> 

**E se o visitante do caso acima exibir primeiro a característica de conversão de uma das quatro UUIDs vinculados ao seu perfil autenticado e também exibir a característica de conversão de duas outras UUIDs vinculadas ao perfil autenticado? Esse caso conta como uma ou três conversões?**

Nesse caso, o [!UICONTROL Audience Lab] conta três conversões, uma para cada dispositivo que exibiu a característica de autenticação.

<br> 

**Um usuário pode ter acesso [!UICONTROL Segment: Read-Only], mas também ter acesso à criação de segmentos de teste do [!UICONTROL Audience Lab]?**

Consulte [Criar grupo de teste de segmento](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) para obter informações sobre como usar o [!UICONTROL Audience Lab] com privilégios [!UICONTROL RBAC].

**Posso usar [!UICONTROL Audience Lab] em conjunto com a [!UICONTROL Profile Link Device Graph] e Gráficos de dispositivos externos (Gráfico de dispositivos Tapad, Gráfico de dispositivos Liveramp)?**

Por enquanto, o [!UICONTROL Audience Lab] só pode dividir populações de segmentos pelos dispositivos conectados a um dispositivo qualificado ao usar o [!UICONTROL Profile Link Device Graph]. Estamos trabalhando para adicionar suporte ao [!UICONTROL Audience Lab] para os outros gráficos de dispositivos e informaremos quando isso for possível.
