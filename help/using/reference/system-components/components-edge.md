---
description: O Audience Manager usa topologias de computação de borda distribuídas para atender às demandas colocadas em nossos sistemas por fontes externas.
seo-description: O Audience Manager usa topologias de computação de borda distribuídas para atender às demandas colocadas em nossos sistemas por fontes externas.
seo-title: Como entender o Edge Data Center
solution: Audience Manager
title: Como entender o Edge Data Center
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Como entender o Edge Data Center{#understanding-the-edge-data-center}

O Audience Manager usa topologias de computação de borda distribuídas para atender às demandas colocadas em nossos sistemas por fontes externas.

## Noções básicas do Edge Data Center {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

A computação de borda oferece desempenho aprimorado em resposta a demandas difusas de toda a Internet, pois a "borda" em si é um limite global. Isso significa que coloca o processamento [!DNL Audience Manager] dinamicamente mais próximo das fontes de demanda e retorna os dados pelo caminho mais curto possível. A computação de borda ajuda a manter o desempenho do site, o que, por sua vez, preserva a experiência do usuário em seu site. O centro de dados de borda é um gateway chave para mover os dados para dentro e para fora [!DNL Audience Manager].

O centro de dados de [!DNL Audience Manager] borda inclui:

* **** Servidores principais: Estes são os [!DNL Audience Manager] sistemas principais. Eles atualizam e fornecem dados para os servidores de borda.

* **** Servidores Edge: Normalmente, são servidores de aplicativos e/ou da Web. Eles ficam na fronteira entre [!DNL Audience Manager] a Internet. Os servidores de borda, como os sistemas [!UICONTROL DCS] ou Akamai, geralmente lidam com dados e solicitações que entram e saem [!DNL Audience Manager].

* **** Balanceadores de Carga: Gerencie demandas desiguais de computação/processamento inerentes aos aplicativos da Internet. Esses balanceadores impedem que clusters de servidores sejam sobrecarregados enquanto outros permanecem ociosos.

O diagrama a seguir ilustra o ambiente do centro de dados de borda do Audience Manager.

![](assets/edge_data_center.png)

## Distribuição geográfica e balanceamento de carga {#geo-dist-balance}

Consulte a [!UICONTROL DCS] seção em Componentes [de coleta de](../../reference/system-components/components-data-collection.md)dados.
