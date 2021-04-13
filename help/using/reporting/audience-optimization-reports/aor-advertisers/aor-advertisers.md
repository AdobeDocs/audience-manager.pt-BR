---
description: O Audience Optimization para anunciantes pode ajudá-lo a identificar oportunidades potenciais de desempenho para segmentos de Audience Manager em suas campanhas de mídia paga. Esses relatórios combinam dados de desempenho de campanha no nível do registro com métricas de Audience Manager para informar otimizações centradas em segmentos e uma combinação de canais eficaz.
seo-description: O Audience Optimization para anunciantes pode ajudá-lo a identificar oportunidades potenciais de desempenho para segmentos de Audience Manager em suas campanhas de mídia paga. Esses relatórios combinam dados de desempenho de campanha no nível do registro com métricas de Audience Manager para informar otimizações centradas em segmentos e uma combinação de canais eficaz.
seo-title: Otimização de público-alvo para anunciantes
solution: Audience Manager
title: Otimização de público-alvo para anunciantes
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: Relatórios de otimização de público-alvo
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 3%

---

# [!UICONTROL Audience Optimization] para anunciantes{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] O para anunciantes pode ajudá-lo a identificar oportunidades potenciais de desempenho para segmentos de Audience Manager em suas campanhas de mídia paga. Esses relatórios combinam dados de desempenho de campanha no nível do log com métricas Audience Manager para informar otimizações centradas em segmentos e uma combinação de canais eficaz.[!UICONTROL segment]

## Métodos de assimilação de dados {#data-ingestion-methods}

Você pode enviar dados para [!DNL Audience Manager] para uso nesses relatórios por um desses métodos. Às vezes, os clientes enviam dados pelos dois métodos. Isso ajuda a garantir que seus relatórios contenham as informações mais completas e precisas sobre um visitante. Para usar os relatórios [!UICONTROL Audience Optimization], suas chamadas de evento devem incluir *todos* dos parâmetros listados na documentação [Visão geral e mapeamentos para arquivos de metadados](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md). Você pode enviar dados por meio dos seguintes métodos listados abaixo.

* Chamadas de pixel: Para transmitir os parâmetros de metadados necessários para [!DNL Audience Manager] consulte [Capturando dados de cliques de campanha via Pixel Calls](../../../integration/media-data-integration/click-data-pixels.md) e [Capturando dados de impressão de campanha via Pixel Calls](../../../integration/media-data-integration/impression-data-pixels.md).

* Arquivos de dados: Se quiser usar esses relatórios para analisar seus próprios dados ou dados de uma fonte não integrada a [!DNL Audience Manager], será necessário criar e carregar dados e arquivos de metadados para esses dados. Para obter mais informações, consulte [Arquivos de dados para relatórios do Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) e [Arquivos de dados e metadados para relatórios do Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## [!UICONTROL Role-Based Access Controls] (RBAC)  {#rbac}

O tipo de relatórios que você pode visualizar depende do grupo [!UICONTROL RBAC] ao qual você está atribuído. Consulte [Administração](../../../features/administration/administration-overview.md) e [Criar um grupo](../../../features/administration/administration-overview.md#create-group) para obter mais informações.

[!UICONTROL RBAC] Os grupos devem ter algumas fontes de dados configuradas para visualizar os  [!UICONTROL Audience Optimization] relatórios. Seu consultor [!DNL Audience Manager] irá configurar esses [!UICONTROL data sources] para você. Quanto mais [!UICONTROL data sources] em cada [!UICONTROL RBAC] grupo de usuários, mais dados esses membros do grupo terão acesso. No mínimo, seu consultor definirá pelo menos um desses [!UICONTROL data sources]:

* Anunciante [!UICONTROL data source ]
* Marca [!UICONTROL data source]
* Plataforma [!UICONTROL data source]

Os usuários que pertencem a mais de um grupo de usuários [!UICONTROL RBAC] podem alternar entre a exibição de cada grupo. Os dados exibidos serão atualizados para respeitar o grupo selecionado. Se sua empresa não usar [!UICONTROL RBAC], todos os usuários terão privilégios de administrador e acesso a todos os [!UICONTROL data sources] (grupos de conversão).

## Grupos de conversão {#conversion-groups}

Nos relatórios [!UICONTROL Audience Optimization], **[!UICONTROL Conversion Groups]** são sinônimos de [!UICONTROL data sources] que contêm pelo menos uma característica de conversão. [!UICONTROL Data sources] que não contêm pelo menos uma característica de conversão não aparecem nos  [!UICONTROL Audience Optimization] relatórios. Você pode exibir as características de conversão para grupos de conversão no relatório [Características de conversão relatadas](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md).
