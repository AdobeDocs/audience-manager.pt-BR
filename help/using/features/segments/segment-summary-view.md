---
description: A página de resumo de segmento exibe detalhes como nome, características no segmento, regras, dados de desempenho e informações de mapeamento de destino.
seo-description: The segment summary page displays details such as name, traits in the segment, rules, performance data, and destination mapping information.
seo-title: Segment Details Page
solution: Audience Manager
title: Página Detalhes do Segmento
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: detalhamento por tipo de identidade, detalhamento de identidade, relatórios de identidade de público-alvo, entre dispositivos, ID entre dispositivos, ID de dispositivo
feature: Segments
exl-id: d33c8146-fd98-47fc-aa3d-96f002538df4
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 0%

---

# Página Detalhes do Segmento {#segment-summary-view}

A página de detalhes de um segmento individual fornece uma visão geral dos detalhes do segmento, como nome do segmento, ID, métricas de desempenho, regras que definem o segmento e mapeamentos de destino. Para exibir esses detalhes, vá para **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** e clique no nome do segmento com o qual deseja trabalhar.

## Ferramentas de gerenciamento de segmentos {#segment-management-tools}

A parte superior da página de detalhes do segmento hospeda as ferramentas que você pode usar para gerenciar seus segmentos:

1. **[!UICONTROL Add New]**: Use esta opção para ativar o [!UICONTROL Segment Builder] e criar novos segmentos.
2. **[!UICONTROL Edit]**: Use esta opção para alterar a configuração do segmento atual.
3. **[!UICONTROL Duplicate]**: use essa opção para criar uma cópia do segmento atual.
4. **[!UICONTROL Delete]**: Use esta opção para remover o segmento atual de sua conta do Audience Manager.
5. **[!UICONTROL Marketplace Recommendations]**: Use esta opção para localizar segmentos semelhantes ao que você está visualizando, a partir de [!UICONTROL Audience Marketplace] feeds de dados para os quais você não tem assinatura. Consulte [Audience Marketplace para Compradores de Dados](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) para saber como navegar no Marketplace e encontrar segmentos semelhantes.

![informações-básicas-de-segmento](assets/basic-segment-information.png)

## Informações do segmento {#basics}

Abaixo das ferramentas de gerenciamento de segmentos, você pode encontrar as seguintes informações de segmentos:

1. **[!UICONTROL Basic Information]:** Mostra os detalhes obrigatórios e opcionais especificados quando o segmento foi criado. Consulte [Construtor de segmentos](segment-builder.md) para obter uma visão geral detalhada do que significam esses campos.
1. **[!UICONTROL Segment Graph]:** Exibe dados de desempenho graficamente e para intervalos fixos de 1, 7, 14, 30, 60 e 90 dias. Explicamos os números da população de segmentos em um [artigo separado](../../features/segments/segment-builder-data.md).

   ![gráfico de segmentos](assets/segment-graph.png)

1. **[!UICONTROL Identity Type Breakdown]:** O relatório mostra o número de pessoas ou residências qualificadas para um segmento, contando o número de IDs entre dispositivos e/ou IDs de Gráficos de Dispositivos Externos vinculadas aos dispositivos qualificados para o segmento (mostrado pelo [!UICONTROL Total Segment Population]). As IDs entre dispositivos e as IDs do gráfico de dispositivos externos mostradas neste relatório são usadas para mesclar perfis com a regra de mesclagem de perfis que o segmento está usando. Esse relatório será exibido somente se você tiver selecionado uma fonte de dados entre dispositivos ou um Gráfico de dispositivos externos na regra de mesclagem de perfis que o segmento está usando.

   ![gráfico de segmentos](assets/segment-type.png)

   >[!NOTE]
   >
   >O Audience Manager só exibirá o relatório [!UICONTROL Identity Type Breakdown] se você tiver IDs entre dispositivos qualificadas para o segmento.

   Assista ao vídeo abaixo para obter uma visão geral do [!UICONTROL Identity Type Breakdown].

   >[!VIDEO](https://video.tv.adobe.com/v/32079?captions=por_br)

1. **[!UICONTROL Segment Rules]:** Lista as características no segmento junto com as regras de qualificação.
1. **[!UICONTROL Destination Mappings]:** Lista os mapeamentos de destino do segmento.
1. **[!UICONTROL Management Tools]:** Controles que permitem criar, editar, clonar e excluir segmentos.
