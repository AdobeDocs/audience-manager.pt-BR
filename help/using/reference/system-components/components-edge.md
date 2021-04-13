---
description: O Audience Manager usa topologias de computação de borda distribuídas para atender às demandas colocadas em nossos sistemas por fontes externas.
seo-description: O Audience Manager usa topologias de computação de borda distribuídas para atender às demandas colocadas em nossos sistemas por fontes externas.
seo-title: Compreensão do Edge Data Center
solution: Audience Manager
title: Compreensão do Edge Data Center
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: 'Componentes do sistema '
exl-id: 28958b49-3075-4601-9271-ef2913721a66
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 6%

---

# Compreensão do Edge Data Center{#understanding-the-edge-data-center}

O Audience Manager usa topologias de computação de borda distribuídas para atender às demandas colocadas em nossos sistemas por fontes externas.

## Noções básicas do Edge Data Center {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

A computação de borda oferece desempenho aprimorado em resposta a demandas difusas e de toda a Internet, pois a &quot;borda&quot; em si é um limite global. Isso significa que [!DNL Audience Manager] coloca dinamicamente o processamento mais próximo das fontes de demanda e retorna os dados pelo caminho mais curto possível. A computação de borda ajuda a manter o desempenho do site, o que, por sua vez, preserva a experiência do usuário em seu site. O data center de borda é um gateway principal para mover dados de e para [!DNL Audience Manager].

O data center de [!DNL Audience Manager] borda inclui:

* **Servidores principais:** esses são os principais  [!DNL Audience Manager] sistemas. Eles atualizam e fornecem dados para os servidores de borda.

* **Servidores de borda:** normalmente, esses são servidores de aplicativos e/ou da Web. Eles ficam no limite entre [!DNL Audience Manager] e a Internet. Os servidores de borda, como os sistemas [!DNL DCS] ou Akamai, geralmente lidam com dados e solicitações que entram e saem de [!DNL Audience Manager].

* **Balanceadores de carga:** gerencie demandas desiguais de computação/processamento inerentes aos aplicativos da Internet. Esses balanceadores impedem que os clusters de servidores sejam sobrecarregados enquanto outros permanecem inativos.

O diagrama a seguir ilustra o ambiente do data center de borda Audience Manager.

![](assets/edge_data_center.png)

## Distribuição geográfica e balanceamento de carga {#geo-dist-balance}

Consulte a seção [!DNL DCS] em [Componentes da coleta de dados](../../reference/system-components/components-data-collection.md).
