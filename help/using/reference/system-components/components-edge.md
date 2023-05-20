---
description: O Audience Manager usa topologias de computação de borda distribuídas para atender às demandas colocadas em nossos sistemas por fontes externas.
seo-description: Audience Manager uses distributed, edge-computing topologies to meet the demands placed on our systems by external sources.
seo-title: Understanding the Edge Data Center
solution: Audience Manager
title: Compreensão do Edge Data Center
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: System Components
exl-id: 28958b49-3075-4601-9271-ef2913721a66
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 4%

---

# Compreensão do Edge Data Center{#understanding-the-edge-data-center}

O Audience Manager usa topologias de computação de borda distribuídas para atender às demandas colocadas em nossos sistemas por fontes externas.

## Noções básicas do Edge Data Center {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

A computação de borda oferece melhor desempenho em resposta a demanda difusa em toda a Internet, porque a &quot;borda&quot; em si é um limite global. Isso significa [!DNL Audience Manager] coloca o processamento dinamicamente mais próximo das origens de demanda e retorna os dados pelo caminho mais curto possível. A computação de borda ajuda a manter o desempenho do site, o que, por sua vez, preserva a experiência do usuário em seu site. O data center de borda é um gateway essencial para entrada e saída de dados [!DNL Audience Manager].

A variável [!DNL Audience Manager] o data center de borda inclui:

* **Servidores principais:** Estes são os principais [!DNL Audience Manager] sistemas. Eles atualizam e fornecem dados para os servidores de borda do.

* **Servidores de borda:** Normalmente, são servidores de aplicativos e/ou da Web. Eles se sentam na fronteira entre [!DNL Audience Manager] e a Internet. Servidores de borda, como o [!DNL DCS] sistemas Akamai, geralmente lidam com dados e solicitações que entram e saem do [!DNL Audience Manager].

* **Balanceadores de carga:** Gerencie as demandas de computação/processamento desiguais inerentes aos aplicativos da Internet. Esses balanceadores impedem que clusters de servidores sejam sobrecarregados enquanto outros permanecem ociosos.

O diagrama a seguir ilustra o ambiente de data center de borda do Audience Manager.

![](assets/edge_data_center.png)

## Distribuição geográfica e balanceamento de carga {#geo-dist-balance}

Consulte a [!DNL DCS] seção em [Componentes da coleção de dados](../../reference/system-components/components-data-collection.md).
