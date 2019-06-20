---
description: O Audience Manager usa topologias distribuídas e de computação para atender às demandas de nossos sistemas por fontes externas.
seo-description: O Audience Manager usa topologias distribuídas e de computação para atender às demandas de nossos sistemas por fontes externas.
seo-title: Como entender o Centro de dados da borda
solution: Audience Manager
title: Como entender o Centro de dados da borda
uuid: 4177 e 666-99 f 4-453 d -94 dd -058 c 6182 c 8 d 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Understanding the Edge Data Center{#understanding-the-edge-data-center}

O Audience Manager usa topologias distribuídas e de computação para atender às demandas de nossos sistemas por fontes externas.

## Edge Data Center Basics {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

A computação de borda fornece desempenho aprimorado em resposta a difusos, sob demanda à Internet, pois a própria «borda» é um limite global. This means [!DNL Audience Manager] dynamically places processing closest to the sources of demand and returns data by the shortest possible path. O cálculo de borda ajuda a manter o desempenho do site, que, por sua vez, preserva a experiência do usuário em seu site. The edge data center is a key gateway for moving data in and out of [!DNL Audience Manager].

The [!DNL Audience Manager] edge data center includes:

* **Principais servidores:** Esses são os [!DNL Audience Manager] sistemas principais. Eles atualizam e fornecem dados aos servidores de borda.

* **Servidores Edge:** Normalmente, são servidores de aplicativos e/ou Web. They sit at the boundary between [!DNL Audience Manager] and the Internet. Edge servers, such as the [!UICONTROL DCS] or Akamai systems, typically handle data and requests flowing into and out of [!DNL Audience Manager].

* **Balanceadores de carga:** Gerencie pedidos de computação/processamento desigual inerentes aos aplicativos da Internet. Esses balanceadores impedem que clusters de servidores sejam sobrecarregados enquanto outros permanecem ociosos.

O diagrama a seguir ilustra o ambiente center da borda do Audience Manager.

![](assets/edge_data_center.png)

## Geographic Distribution and Load Balancing {#geo-dist-balance}

See the [!UICONTROL DCS] section in [Data Collection Components](../../reference/system-components/components-data-collection.md).
