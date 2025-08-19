---
description: Usado para informar ao DIL que ele é carregado após o carregamento da janela.
seo-description: Used to let DIL know that it is loaded after the window loads.
seo-title: isAddedPostWindowLoad
solution: Audience Manager
title: isAddedPostWindowLoad
uuid: 8cdeab00-6ce4-4f07-bb63-41425369a5b7
feature: DIL Implementation
exl-id: 955fe0f2-2a64-491f-9098-e5aabcc697db
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 2%

---


# isAddedPostWindowLoad{#isaddedpostwindowload}

>[!WARNING]
>
>A partir de julho de 2023, a Adobe descontinuou o desenvolvimento do [!DNL Data Integration Library (DIL)] e da extensão [!DNL DIL].
>
>Os clientes existentes podem continuar usando a implementação [!DNL DIL]. Entretanto, a Adobe não desenvolverá [!DNL DIL] além deste ponto. Os clientes são incentivados a avaliar o [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) para sua estratégia de coleta de dados de longo prazo.
>
>Os clientes que desejam implementar novas integrações de coleta de dados após julho de 2023 devem usar o [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en).

Usado para informar ao DIL que ele é carregado após o carregamento da janela.

**Assinatura da Função:** `isAddedPostWindowLoad: function()`

<!--
r_dil_added_post_window_load.xml
-->

## Código de exemplo

```
DIL.isAddedPostWindowLoad();
```
