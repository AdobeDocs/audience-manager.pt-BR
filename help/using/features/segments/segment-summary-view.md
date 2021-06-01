---
description: A página de resumo de segmento exibe detalhes como nome, características no segmento, regras, dados de desempenho e informações de mapeamento de destino.
seo-description: A página de resumo de segmento exibe detalhes como nome, características no segmento, regras, dados de desempenho e informações de mapeamento de destino.
seo-title: Página Detalhes do segmento
solution: Audience Manager
title: Página Detalhes do segmento
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: detalhamento de tipo de identidade, detalhamento de identidade, relatório de identidade de público-alvo, entre dispositivos, ID entre dispositivos, ID de dispositivo
feature: 'Segmentos '
exl-id: d33c8146-fd98-47fc-aa3d-96f002538df4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---

# Página Detalhes do Segmento {#segment-summary-view}

A página de detalhes de um segmento individual fornece uma visão geral dos detalhes do segmento, como o nome do segmento, a ID, as métricas de desempenho, as regras que definem o segmento e os mapeamentos de destino. Para exibir esses detalhes, vá para **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** e clique no nome do segmento com o qual deseja trabalhar.

## Ferramentas de gerenciamento de segmento {#segment-management-tools}

A parte superior da página de detalhes do segmento hospeda as ferramentas que você pode usar para gerenciar seus segmentos:

1. **[!UICONTROL Add New]**: Use essa opção para ativar  [!UICONTROL Segment Builder] e criar novos segmentos.
2. **[!UICONTROL Edit]**: Use essa opção para alterar a configuração do segmento atual.
3. **[!UICONTROL Duplicate]**: Use essa opção para criar uma cópia do segmento atual.
4. **[!UICONTROL Delete]**: Use esta opção para remover o segmento atual de sua conta do Audience Manager.
5. **[!UICONTROL Marketplace Recommendations]**: Use essa opção para encontrar segmentos semelhantes àqueles que você está visualizando, de feeds de  [!UICONTROL Audience Marketplace] dados aos quais você não está inscrito. Consulte [Audience Marketplace for Data Buyers](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) para saber como navegar no Marketplace e encontrar segmentos semelhantes.

![informações básicas do segmento](assets/basic-segment-information.png)

## Informações do segmento {#basics}

Abaixo das ferramentas de gerenciamento de segmentos você pode encontrar as seguintes informações do segmento:

1. **[!UICONTROL Basic Information]:** mostra os detalhes obrigatórios e opcionais especificados quando o segmento foi criado. Consulte [Construtor de segmentos](segment-builder.md) para obter uma visão geral detalhada do significado desses campos.
2. **[!UICONTROL Segment Graph]:** exibe dados de desempenho graficamente e para intervalos fixos de 1, 7, 14, 30, 60 e 90 dias. Explicamos os números da população do segmento em um [artigo separado](../../features/segments/segment-builder-data.md).

   ![gráfico de segmentos](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]:** o relatório mostra o número de pessoas ou residências qualificadas para um segmento pela contagem do número de IDs entre dispositivos e/ou de IDs de gráfico de dispositivo externo vinculadas aos dispositivos qualificados para o segmento (mostradas pelo  [!UICONTROL Total Segment Population]). As IDs entre dispositivos e as IDs de gráfico do dispositivo externo mostradas nesse relatório são usadas para unir perfis à regra de mesclagem de perfis que o segmento está usando. Este relatório é exibido somente se você selecionou uma fonte de dados entre dispositivos ou um Gráfico de dispositivos externos na regra de mesclagem de perfis que o segmento está usando.

   ![gráfico de segmentos](assets/segment-type.png)

   >[!NOTE]
   >
   >O Audience Manager exibe somente o relatório [!UICONTROL Identity Type Breakdown] se você tiver IDs de vários dispositivos qualificadas para o segmento.

   Assista ao vídeo abaixo para obter uma visão geral de [!UICONTROL Identity Type Breakdown].
   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

4. **[!UICONTROL Segment Rules]:** lista as características no segmento junto com as regras de qualificação.
5. **[!UICONTROL Destination Mappings]:** lista mapeamentos de destino para o segmento.
6. **[!UICONTROL Management Tools]:** controles que permitem criar, editar, clonar e excluir segmentos.
