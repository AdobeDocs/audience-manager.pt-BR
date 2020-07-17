---
description: A Audience Manager usa topologias distribuídas e de tecnologia de ponta para atender às demandas colocadas em nossos sistemas por fontes externas.
seo-description: A Audience Manager usa topologias distribuídas e de tecnologia de ponta para atender às demandas colocadas em nossos sistemas por fontes externas.
seo-title: Compreensão do Edge Data Center
solution: Audience Manager
title: Compreensão do Edge Data Center
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---


# Compreensão do Edge Data Center{#understanding-the-edge-data-center}

A Audience Manager usa topologias distribuídas e de tecnologia de ponta para atender às demandas colocadas em nossos sistemas por fontes externas.

## Noções básicas do Edge Data Center {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

A computação de borda oferece desempenho aprimorado em resposta a demandas difusas de toda a Internet, pois a &quot;borda&quot; em si é um limite global. Isso significa que coloca o processamento [!DNL Audience Manager] dinamicamente mais próximo das fontes de demanda e retorna os dados pelo caminho mais curto possível. A computação de borda ajuda a manter o desempenho do site, o que, por sua vez, preserva a experiência do usuário em seu site. O centro de dados de borda é um gateway chave para mover os dados para dentro e para fora [!DNL Audience Manager].

O centro de dados de [!DNL Audience Manager] borda inclui:

* **Servidores principais:** Estes são os [!DNL Audience Manager] sistemas principais. Eles atualizam e fornecem dados para os servidores de borda.

* **Servidores Edge:** Normalmente, são servidores de aplicativos e/ou da Web. Eles ficam na fronteira entre [!DNL Audience Manager] a Internet. Os servidores de borda, como os sistemas [!DNL DCS] ou Akamai, geralmente lidam com dados e solicitações que entram e saem [!DNL Audience Manager].

* **Balanceadores de Carga:** Gerencie demandas desiguais de computação/processamento inerentes aos aplicativos da Internet. Esses balanceadores impedem que clusters de servidores sejam sobrecarregados enquanto outros permanecem ociosos.

O diagrama a seguir ilustra o ambiente do centro de dados da borda do Audience Manager.

![](assets/edge_data_center.png)

## Distribuição geográfica e balanceamento de carga {#geo-dist-balance}

Consulte a [!DNL DCS] seção em Componentes [de coleta de](../../reference/system-components/components-data-collection.md)dados.
