---
description: A Otimização da Audiência para anunciantes pode ajudá-lo a identificar possíveis oportunidades de desempenho para segmentos de Audience Manager nas campanhas de mídia paga. Esses relatórios combinam dados de desempenho de campanha de nível de log com métricas de segmento de Audience Manager para informar otimizações centradas no segmento e uma combinação eficiente de canais.
seo-description: A Otimização da Audiência para anunciantes pode ajudá-lo a identificar possíveis oportunidades de desempenho para segmentos de Audience Manager nas campanhas de mídia paga. Esses relatórios combinam dados de desempenho de campanha de nível de log com métricas de segmento de Audience Manager para informar otimizações centradas no segmento e uma combinação eficiente de canais.
seo-title: Otimização de público-alvo para anunciantes
solution: Audience Manager
title: Otimização de público-alvo para anunciantes
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 2%

---


# [!UICONTROL Audience Optimization] para anunciantes{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] para anunciantes, você pode ajudá-lo a identificar possíveis oportunidades de desempenho para segmentos de Audience Manager em suas campanhas de mídia paga. Esses relatórios combinam dados de desempenho de campanha de nível de log com métricas de Audience Manager [!UICONTROL segment] para informar otimizações centradas no segmento e uma combinação eficiente de canais.

## Métodos de ingestão de dados {#data-ingestion-methods}

É possível enviar dados para uso [!DNL Audience Manager] nesses relatórios por um destes métodos. Às vezes, os clientes enviam dados por ambos os métodos. Isso ajuda a garantir que seus relatórios contenham as informações mais completas e precisas sobre um visitante. Para usar os [!UICONTROL Audience Optimization] relatórios, suas chamadas de evento devem incluir *todos* os parâmetros listados na documentação [Visão geral e Mapeamentos para arquivos](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) de metadados. Você pode enviar dados pelos seguintes métodos listados abaixo.

* Chamadas de pixel: Para passar os parâmetros de metadados necessários para [!DNL Audience Manager] ver [Captura de dados de clique de Campanha por meio de chamadas](../../../integration/media-data-integration/click-data-pixels.md) de pixels e [Captura de dados de impressão de Campanha por meio de chamadas](../../../integration/media-data-integration/impression-data-pixels.md)de pixels.

* Arquivos de dados: Se você quiser usar esses relatórios para analisar seus próprios dados ou dados de uma fonte não integrada, é necessário criar e carregar arquivos de dados e metadados [!DNL Audience Manager]para esses dados. Para obter mais informações, consulte Arquivos [de dados para relatórios](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) de otimização de Audiência e Arquivos [de dados e metadados para relatórios](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)de otimização de Audiência.

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

O tipo de relatórios que você pode visualização depende do [!UICONTROL RBAC] grupo ao qual você está atribuído. Consulte [Administração](../../../features/administration/administration-overview.md) e [Criar um grupo](../../../features/administration/administration-overview.md#create-group) para obter mais informações.

[!UICONTROL RBAC] grupos devem ter algumas fontes de dados configuradas para visualização dos [!UICONTROL Audience Optimization] relatórios. Seu [!DNL Audience Manager] consultor irá configurá-los [!UICONTROL data sources] para você. Quanto mais [!UICONTROL data sources] em cada grupo de [!UICONTROL RBAC] usuários, mais dados esses membros do grupo terão acesso. No mínimo, seu consultor criará pelo menos um destes [!UICONTROL data sources]:

* Anunciante [!UICONTROL data source ]
* Marca [!UICONTROL data source]
* Plataforma [!UICONTROL data source]

Os usuários que pertencem a mais de um grupo de [!UICONTROL RBAC] usuários podem alternar entre a visualização de cada grupo. Os dados exibidos serão atualizados para respeitar o grupo selecionado. Se sua empresa não usar [!UICONTROL RBAC], todos os usuários terão privilégios de administrador e acesso a todos os usuários [!UICONTROL data sources] (grupos de conversão).

## Grupos de conversão {#conversion-groups}

Nos [!UICONTROL Audience Optimization] relatórios, **[!UICONTROL Conversion Groups]** são sinônimos de [!UICONTROL data sources] que contêm pelo menos uma característica de conversão. [!UICONTROL Data sources] que não contêm pelo menos uma característica de conversão não aparecem nos [!UICONTROL Audience Optimization] relatórios. Você pode visualização as características de conversão para grupos de conversão no relatório Características [de conversão](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) reportadas.
