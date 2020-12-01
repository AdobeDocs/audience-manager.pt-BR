---
description: A página de resumo do segmento exibe detalhes como nome, características no segmento, regras, dados de desempenho e informações de mapeamento de destino.
seo-description: A página de resumo do segmento exibe detalhes como nome, características no segmento, regras, dados de desempenho e informações de mapeamento de destino.
seo-title: Página Detalhes do Segmento
solution: Audience Manager
title: Página Detalhes do Segmento
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: identity type breakdown, identity breakdown, audience identity reporting, cross-device, cross-device ID, device ID
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---


# Página Detalhes do Segmento {#segment-summary-view}

A página de detalhes de um segmento individual fornece uma visão geral dos detalhes do segmento, como o nome do segmento, a ID, as métricas de desempenho, as regras que definem o segmento e os mapeamentos de destino. Para visualização desses detalhes, vá até **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** e clique no nome do segmento com o qual deseja trabalhar.

## Ferramentas de gerenciamento de segmentos {#segment-management-tools}

A parte superior da página de detalhes do segmento hospeda as ferramentas que você pode usar para gerenciar seus segmentos:

1. **[!UICONTROL Add New]**: Use essa opção para ativar  [!UICONTROL Segment Builder] e criar novos segmentos.
2. **[!UICONTROL Edit]**: Use essa opção para alterar a configuração do segmento atual.
3. **[!UICONTROL Duplicate]**: Use essa opção para criar uma cópia do segmento atual.
4. **[!UICONTROL Delete]**: Use essa opção para remover o segmento atual da sua conta do Audience Manager.
5. **[!UICONTROL Marketplace Recommendations]**: Use essa opção para localizar segmentos semelhantes àqueles que você está visualizando, de feeds de  [!UICONTROL Audience Marketplace] dados aos quais você não está inscrito. Consulte [Audience Marketplace para Data Buyers](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) para saber como navegar no Marketplace e encontrar segmentos semelhantes.

![informações básicas do segmento](assets/basic-segment-information.png)

## Informações do segmento {#basics}

Abaixo das ferramentas de gerenciamento de segmentos você pode encontrar as seguintes informações de segmento:

1. **[!UICONTROL Basic Information]:** Mostra os detalhes obrigatórios e opcionais especificados quando o segmento foi criado. Consulte [Construtor de segmentos](segment-builder.md) para obter uma visão geral detalhada do significado desses campos.
2. **[!UICONTROL Segment Graph]:** Exibe dados de desempenho graficamente e para intervalos fixos de 1, 7, 14, 30, 60 e 90 dias. Explicamos os números de população do segmento em um [artigo separado](../../features/segments/segment-builder-data.md).

   ![gráfico de segmentos](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]:** O relatório mostra o número de pessoas ou residências que se qualificam para um segmento contando o número de IDs de dispositivos cruzados e/ou IDs de gráficos de dispositivos externos que estão vinculados aos dispositivos qualificados para o segmento (mostrados pelo  [!UICONTROL Total Segment Population]). As IDs entre dispositivos e as IDs de gráfico de dispositivos externos mostradas neste relatório são usadas para unir perfis à regra de mesclagem de perfis que o segmento está usando. Este relatório é exibido somente se você selecionou uma fonte de dados entre dispositivos ou um Gráfico de dispositivos externos na regra de mesclagem de perfis que o segmento está usando.

   ![gráfico de segmentos](assets/segment-type.png)

   >[!NOTE]
   >
   >O Audience Manager só exibe o relatório [!UICONTROL Identity Type Breakdown] se você tiver IDs de vários dispositivos qualificados para o segmento.

   Assista ao vídeo abaixo para obter uma visão geral de [!UICONTROL Identity Type Breakdown].
   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

4. **[!UICONTROL Segment Rules]:características** Listas no segmento junto com as regras de qualificação.
5. **[!UICONTROL Destination Mappings]:** Lista mapeamentos de destino para o segmento.
6. **[!UICONTROL Management Tools]:** Controles que permitem criar, editar, clonar e excluir segmentos.