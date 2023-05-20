---
description: Use o Visualizador de perfil do visitante para exibir o estado atual de um perfil de usuário para o navegador atual, incluindo suas características e segmentos. Para cada característica, você pode visualizar seu SID, nome, detalhes sobre como as características do visitante foram realizadas (próprio ou de terceiros), a data de realização e a frequência de realizações. Para cada segmento, você pode exibir o SID, o nome e a data de associação do segmento. Você também pode exibir o perfil do visitante para outra ID de perfil de Audience Manager (UUID). O Visualizador de perfil do visitante é útil para fins de solução de problemas.
keywords: local;parâmetro de local
seo-description: Use the Visitor Profile Viewer to display the current state of a user profile for the current browser, including its traits and segments. For each trait, you can view its SID, name, details about how visitor traits were realized (first- or third-party), the realization date, and the frequency of realizations. For each segment, you can view its SID, name, and the segment membership date. You can also view the visitor profile for another Audience Manager profile ID (UUID). The Visitor Profile Viewer is helpful for troubleshooting purposes.
seo-title: Visitor Profile Viewer
solution: Audience Manager
title: Visualizador de perfil do visitante
uuid: 77ffe134-e08f-41de-8fc4-15494847b1d0
feature: Traits
exl-id: 6c1ee14c-6f78-4e45-9b88-24ace8400079
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 2%

---

# Visualizador de perfil do visitante {#visitor-profile-viewer}

Use o [!UICONTROL Visitor Profile Viewer] para exibir o estado atual de um perfil de usuário para o navegador atual, incluindo suas características e segmentos. Para cada característica, é possível visualizar sua [!UICONTROL SID], nome, detalhes sobre como as características do visitante foram realizadas (primárias ou de terceiros), a data de realização e a frequência de realizações. Para cada segmento, é possível visualizar suas [!UICONTROL SID], nome e a data de associação do segmento. Você também pode visualizar o perfil do visitante para outra ID de perfil do Audience Manager ([!UICONTROL UUID]). A variável [!UICONTROL Visitor Profile Viewer] O é útil para fins de solução de problemas.

>[!NOTE]
>
>* O acesso exige [!UICONTROL Administrator] permissões.
>* Há um atraso de 24 horas antes de as informações sobre segmentos realizados e características integradas serem exibidas na interface do usuário do.


<!-- 
Traits that are not part of a segment will not appear in the
<span class="wintitle"> Visitor Profile Viewer</span>.
-->

1. Clique em **[!UICONTROL Tools]** > **[!UICONTROL Visitor Profile Viewer]**.

1. *(Opcional)* Clique no nome da característica para exibi-la na caixa [!UICONTROL Trait Builder].

   Para obter mais informações, consulte [Características](../features/traits/trait-details-page.md).

1. *(Opcional)* Clique no nome do segmento para exibi-lo na [!UICONTROL Segment Builder].

   Para obter mais informações, consulte [Segmentos](../features/segments/segments-purpose.md).

1. *(Condicional)* No **[!UICONTROL UUID]** especifique outra ID de perfil de Audience Manager e clique em **[!UICONTROL Refresh]** para visualizar as características e os segmentos desse usuário.
