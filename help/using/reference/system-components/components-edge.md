---
description: O Audience Manager usa topologias de computação de borda distribuídas para atender às demandas colocadas em nossos sistemas por fontes externas.
seo-description: Audience Manager uses distributed, edge-computing topologies to meet the demands placed on our systems by external sources.
seo-title: Understanding the Edge Data Center
solution: Audience Manager
title: Noções básicas sobre o data center da Edge
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: System Components
exl-id: 28958b49-3075-4601-9271-ef2913721a66
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# Noções básicas sobre o data center da Edge{#understanding-the-edge-data-center}

O Audience Manager usa topologias de computação de borda distribuídas para atender às demandas colocadas em nossos sistemas por fontes externas.

## Noções básicas do data center da Edge {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

A computação Edge oferece melhor desempenho em resposta a demanda difusa em toda a Internet porque a &quot;borda&quot; em si é um limite global. Isso significa que o [!DNL Audience Manager] coloca dinamicamente o processamento mais próximo das fontes de demanda e retorna os dados pelo caminho mais curto possível. A computação Edge ajuda a manter o desempenho do site, o que, por sua vez, preserva a experiência do usuário no seu site. O data center de borda é um gateway chave para mover dados de e para [!DNL Audience Manager].

O data center de borda [!DNL Audience Manager] inclui:

* **Servidores principais:** Estes são os [!DNL Audience Manager] sistemas principais. Eles atualizam e fornecem dados para os servidores de borda do.

* **Servidores Edge:** Normalmente, são servidores de aplicativos e/ou Web. Eles ficam no limite entre o [!DNL Audience Manager] e a Internet. Os servidores do Edge, como o [!DNL DCS] ou os sistemas Akamai, geralmente lidam com dados e solicitações que entram e saem do [!DNL Audience Manager].

* **Balanceadores de carga:** gerencie as demandas de computação/processamento irregulares inerentes aos aplicativos da Internet. Esses balanceadores impedem que clusters de servidores sejam sobrecarregados enquanto outros permanecem ociosos.

O diagrama a seguir ilustra o ambiente de data center de borda do Audience Manager.

![](assets/edge_data_center.png)

## Distribuição geográfica e balanceamento de carga {#geo-dist-balance}

Consulte a seção [!DNL DCS] em [Componentes da Coleção de Dados](../../reference/system-components/components-data-collection.md).
