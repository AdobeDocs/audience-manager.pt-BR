---
description: Este mapa contém os principais sistemas de Audience Manager. Ele representa visualmente como os dados fluem para, fora e entre componentes do Audience Manager.
seo-description: Este mapa contém os principais sistemas de Audience Manager. Ele representa visualmente como os dados fluem para, fora e entre componentes do Audience Manager.
seo-title: Mapa de fluxo de dados da arquitetura da plataforma
solution: Audience Manager
title: Mapa de fluxo de dados da arquitetura da plataforma
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: 'Componentes do sistema '
exl-id: 6543df7d-aac5-4181-87a8-bc47edd2e951
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 3%

---

# Arquitetura da plataforma: mapa de fluxo de dados{#platform-architecture-data-flow-map}

Este mapa contém os principais sistemas de Audience Manager. Ele representa visualmente como os dados fluem para, fora e entre componentes do Audience Manager.

## Como ler este mapa {#compmap}

<!-- 

c_compmap.xml

 -->

No mapa, a caixa cinza contém sistemas [!DNL Audience Manager]. Alguns componentes são completamente internos e outros permanecem no limite entre [!DNL Audience Manager] e o mundo externo. Como cliente [!DNL Audience Manager], os componentes internos geralmente são transparentes ou inacessíveis. No entanto, às vezes você pode se envolver com esses sistemas por meio da interface do usuário ou de integrações de dados. Os sistemas na borda da caixa coletam e enviam dados entre [!DNL Audience Manager] e o mundo externo.

As cores definem o tipo de dados que flui de e para [!DNL Audience Manager]. Verde são dados de clientes, azul são dados de clientes (pessoas visitando seu site) e laranja são dados usados para relatórios.

Para obter descrições e resumos do sistema, consulte as seções de dados [action](../../reference/system-components/components-data-action.md), [collection](../../reference/system-components/components-data-collection.md), [processing](../../reference/system-components/components-data-processing.md) e [tag management](../../reference/system-components/components-tag-management.md).

![](assets/flowmap.png)
