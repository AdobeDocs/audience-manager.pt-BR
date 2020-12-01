---
description: Este mapa contém os principais sistemas Audience Manager. Ele representa visualmente como os dados fluem para, fora e entre os componentes do Audience Manager.
seo-description: Este mapa contém os principais sistemas Audience Manager. Ele representa visualmente como os dados fluem para, fora e entre os componentes do Audience Manager.
seo-title: Mapa de fluxo de dados da arquitetura de plataforma
solution: Audience Manager
title: Mapa de fluxo de dados da arquitetura de plataforma
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 2%

---


# Arquitetura da plataforma: mapa de fluxo de dados{#platform-architecture-data-flow-map}

Este mapa contém os principais sistemas Audience Manager. Ele representa visualmente como os dados fluem para, fora e entre os componentes do Audience Manager.

## Como ler este mapa {#compmap}

<!-- 

c_compmap.xml

 -->

No mapa, a caixa cinza contém [!DNL Audience Manager] sistemas. Alguns componentes são completamente internos e outros ficam no limite entre [!DNL Audience Manager] e o mundo externo. Como um cliente [!DNL Audience Manager], os componentes internos geralmente são transparentes ou inacessíveis. No entanto, às vezes você pode se envolver com esses sistemas por meio da interface do usuário ou das integrações de dados. Os sistemas na borda da caixa coletam e enviam dados entre [!DNL Audience Manager] e o mundo externo.

As cores definem o tipo de dados que flui de e para [!DNL Audience Manager]. Verde são os dados do cliente, azul são os dados do cliente (as pessoas visitam seu site) e laranja são os dados usados para o relatórios.

Para obter descrições e resumos do sistema, consulte as seções [action](../../reference/system-components/components-data-action.md), [collection](../../reference/system-components/components-data-collection.md), [processing](../../reference/system-components/components-data-processing.md) e [gerenciamento de tags](../../reference/system-components/components-tag-management.md).

![](assets/flowmap.png)

