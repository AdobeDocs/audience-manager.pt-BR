---
description: Audience Optimization para anunciantes pode ajudá-lo a identificar possíveis oportunidades de desempenho para segmentos de Audience Manager em suas campanhas de mídia paga. Esses relatórios combinam dados de desempenho de campanha de nível de log com métricas de segmento de Audience Manager para informar otimizações centradas no segmento e uma combinação eficiente de canais.
seo-description: Audience Optimization para anunciantes pode ajudá-lo a identificar possíveis oportunidades de desempenho para segmentos de Audience Manager em suas campanhas de mídia paga. Esses relatórios combinam dados de desempenho de campanha de nível de log com métricas de segmento de Audience Manager para informar otimizações centradas no segmento e uma combinação eficiente de canais.
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

[!UICONTROL Audience Optimization] para anunciantes, você pode ajudá-lo a identificar possíveis oportunidades de desempenho para segmentos de Audience Manager em suas campanhas de mídia paga. Esses relatórios combinam dados de desempenho de campanha de nível de log com métricas Audience Manager [!UICONTROL segment] para informar otimizações centradas no segmento e uma combinação eficiente de canais.

## Métodos de ingestão de dados {#data-ingestion-methods}

Você pode enviar dados para [!DNL Audience Manager] para uso nesses relatórios por um destes métodos. Às vezes, os clientes enviam dados por ambos os métodos. Isso ajuda a garantir que seus relatórios contenham as informações mais completas e precisas sobre um visitante. Para usar os relatórios [!UICONTROL Audience Optimization], suas chamadas de evento devem incluir *all* dos parâmetros listados na documentação [Visão geral e mapeamentos para arquivos de metadados](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md). Você pode enviar dados pelos seguintes métodos listados abaixo.

* Chamadas de pixel: Para passar os parâmetros de metadados necessários para [!DNL Audience Manager] consulte [Captura de dados de cliques de Campanha via chamadas de pixel](../../../integration/media-data-integration/click-data-pixels.md) e [Captura de dados de impressão de Campanha via chamadas de pixels](../../../integration/media-data-integration/impression-data-pixels.md).

* Arquivos de dados: Se você quiser usar esses relatórios para analisar seus próprios dados ou dados de uma fonte que não esteja integrada com [!DNL Audience Manager], será necessário criar e carregar arquivos de dados e metadados para esses dados. Para obter mais informações, consulte [Arquivos de Dados para Relatórios Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) e [Arquivos de Dados e Metadados para Relatórios Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## [!UICONTROL Role-Based Access Controls] (RBAC)  {#rbac}

O tipo de relatórios que você pode visualização depende do grupo [!UICONTROL RBAC] ao qual você está atribuído. Consulte [Administração](../../../features/administration/administration-overview.md) e [Criar um Grupo](../../../features/administration/administration-overview.md#create-group) para obter mais informações.

[!UICONTROL RBAC] grupos devem ter algumas fontes de dados configuradas para visualização dos  [!UICONTROL Audience Optimization] relatórios. Seu consultor [!DNL Audience Manager] irá configurar esses [!UICONTROL data sources] para você. Quanto mais [!UICONTROL data sources] em cada [!UICONTROL RBAC] grupo de usuários, mais dados esses membros do grupo terão acesso. No mínimo, seu consultor irá configurar pelo menos um destes [!UICONTROL data sources]:

* Anunciante [!UICONTROL data source ]
* Marca [!UICONTROL data source]
* Plataforma [!UICONTROL data source]

Os usuários que pertencem a mais de um [!UICONTROL RBAC] grupo de usuários podem alternar entre a visualização de cada grupo. Os dados exibidos serão atualizados para respeitar o grupo selecionado. Se sua empresa não usar [!UICONTROL RBAC], todos os usuários terão privilégios de administrador e acesso a todos os [!UICONTROL data sources] (grupos de conversão).

## Grupos de conversão {#conversion-groups}

Nos relatórios [!UICONTROL Audience Optimization], **[!UICONTROL Conversion Groups]** são sinônimos de [!UICONTROL data sources] que contêm pelo menos uma característica de conversão. [!UICONTROL Data sources] que não contêm pelo menos uma característica de conversão não aparecem nos  [!UICONTROL Audience Optimization] relatórios. Você pode visualização as características de conversão para grupos de conversão no relatório [Características de conversão reportadas](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md).
