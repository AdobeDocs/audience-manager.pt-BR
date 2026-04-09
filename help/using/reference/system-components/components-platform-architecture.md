---
description: Este mapa contém os principais sistemas Audience Manager. Ele representa visualmente como os dados fluem para, fora de e entre componentes do Audience Manager.
seo-description: This map contains the major Audience Manager systems. It visually represents how data flows into, out of, and among Audience Manager components.
seo-title: Platform Architecture  Data Flow Map
solution: Audience Manager
title: Mapa de fluxo de dados da arquitetura de plataforma
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: System Components
exl-id: 6543df7d-aac5-4181-87a8-bc47edd2e951
TQID: https://experienceleague.adobe.com/AuYZKnavjMq-XyilPWgEeWASzFB3K5HuAqx-wsE-H9k
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 170
ht-degree: 0%

---

# Arquitetura da plataforma: mapa de fluxo de dados{#platform-architecture-data-flow-map}

Este mapa contém os principais sistemas Audience Manager. Ele representa visualmente como os dados fluem para, fora de e entre componentes do Audience Manager.

## Como ler este mapa {#compmap}

<!-- 

c_compmap.xml

 -->

No mapa, a caixa cinza contém [!DNL Audience Manager] sistemas. Alguns componentes são completamente internos e outros ficam no limite entre [!DNL Audience Manager] e o mundo exterior. Como cliente do [!DNL Audience Manager], os componentes internos geralmente são transparentes ou inacessíveis. No entanto, às vezes você pode se envolver com esses sistemas por meio da interface do usuário ou de integrações de dados. Os sistemas na borda da caixa coletam e enviam dados entre [!DNL Audience Manager] e o mundo exterior.

As cores definem o tipo de dados que fluem para dentro e para fora de [!DNL Audience Manager]. Verde são os dados do cliente, azul são os dados do cliente (pessoas que visitam o site) e laranja são os dados usados para os relatórios.

Para obter descrições e resumos do sistema, consulte as seções [ação](../../reference/system-components/components-data-action.md), [coleção](../../reference/system-components/components-data-collection.md), [processamento](../../reference/system-components/components-data-processing.md) e [gerenciamento de tags](../../reference/system-components/components-tag-management.md) de dados.

![](assets/flowmap.png)
