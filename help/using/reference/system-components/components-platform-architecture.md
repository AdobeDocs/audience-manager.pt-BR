---
description: Este mapa contém os principais sistemas do Audience Manager. Ele representa visualmente como os dados fluem para, fora e entre os componentes do Audience Manager.
seo-description: Este mapa contém os principais sistemas do Audience Manager. Ele representa visualmente como os dados fluem para, fora e entre os componentes do Audience Manager.
seo-title: Mapa de fluxo de dados da arquitetura de plataforma
solution: Audience Manager
title: Mapa de fluxo de dados da arquitetura de plataforma
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Arquitetura da plataforma: Mapa de fluxo de dados{#platform-architecture-data-flow-map}

Este mapa contém os principais sistemas do Audience Manager. Ele representa visualmente como os dados fluem para, fora e entre os componentes do Audience Manager.

## Como ler este mapa {#compmap}

<!-- 

c_compmap.xml

 -->

No mapa, a caixa cinza contém [!DNL Audience Manager] sistemas. Alguns componentes são completamente internos e outros ficam na fronteira entre [!DNL Audience Manager] o mundo exterior. Como [!DNL Audience Manager] cliente, os componentes internos geralmente são transparentes ou inacessíveis. No entanto, às vezes você pode se envolver com esses sistemas por meio da interface do usuário ou integrações de dados. Os sistemas na borda da caixa coletam e enviam dados entre [!DNL Audience Manager] e o mundo exterior.

As cores definem o tipo de dados que flui para dentro e para fora [!DNL Audience Manager]. Verde são os dados do cliente, azul são os dados do cliente (pessoas visitando seu site) e laranja são os dados usados para relatório.

Para obter descrições e resumos do sistema, consulte as seções [ação](../../reference/system-components/components-data-action.md)de dados, [coleta](../../reference/system-components/components-data-collection.md), [processamento](../../reference/system-components/components-data-processing.md)e gerenciamento [de](../../reference/system-components/components-tag-management.md) tags.

![](assets/flowmap.png)

