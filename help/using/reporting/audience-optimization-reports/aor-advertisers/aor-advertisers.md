---
description: O Audience Optimization para anunciantes pode ajudar você a identificar oportunidades potenciais de desempenho para segmentos do Audience Manager em suas campanhas de mídia paga. Esses relatórios combinam dados de desempenho da campanha no nível do registro com métricas de segmento do Audience Manager para informar otimizações centradas em segmentos e uma combinação eficaz de canais.
seo-description: Audience Optimization for Advertisers can help you identify potential performance opportunities for Audience Manager segments across your paid media campaigns. These reports combine log-level campaign performance data with Audience Manager segment metrics to inform segment-centric optimizations and an effective channel mix.
seo-title: Audience Optimization for Advertisers
solution: Audience Manager
title: Audience Optimization para anunciantes
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: Audience Optimization Reports
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
TQID: https://experienceleague.adobe.com/U9Rg-4rwjGdqYsjGDlctn0PBuxAlDjwIBtorAnGtqHU
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2:
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 406
ht-degree: 0%

---

# [!UICONTROL Audience Optimization] para anunciantes{#audience-optimization-for-advertisers}

O [!UICONTROL Audience Optimization] for Advertisers pode ajudar você a identificar oportunidades potenciais de desempenho para segmentos do Audience Manager em suas campanhas de mídia paga. Esses relatórios combinam dados de desempenho da campanha no nível do log com métricas do Audience Manager [!UICONTROL segment] para informar otimizações centradas em segmentos e uma combinação eficaz de canais.

## Métodos de assimilação de dados {#data-ingestion-methods}

Você pode enviar dados a [!DNL Audience Manager] para uso nesses relatórios por qualquer um desses métodos. Às vezes, os clientes enviam dados por ambos os métodos. Isso ajuda a garantir que seus relatórios contenham as informações mais abrangentes e precisas sobre um visitante. Para usar os relatórios [!UICONTROL Audience Optimization], suas chamadas de evento devem incluir *todos* os parâmetros listados na documentação [Visão geral e mapeamentos para arquivos de metadados](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md). Você pode enviar dados por meio dos métodos a seguir listados abaixo.

* Chamadas de pixel: Para transmitir os parâmetros de metadados necessários para [!DNL Audience Manager], consulte [Capturando Dados de Cliques da Campanha por meio de Chamadas de Pixel](../../../integration/media-data-integration/click-data-pixels.md) e [Capturando Dados de Impressão da Campanha por Meio de Chamadas de Pixel](../../../integration/media-data-integration/impression-data-pixels.md).

* Arquivos de dados: se você quiser usar esses relatórios para analisar seus próprios dados ou dados de uma fonte que não esteja integrada com o [!DNL Audience Manager], será necessário criar e carregar dados e arquivos de metadados para esses dados. Para obter mais informações, consulte [Arquivos de Dados para Relatórios do Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) e [Arquivos de Dados e Metadados para Relatórios do Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

O tipo de relatório que você pode exibir depende do grupo [!UICONTROL RBAC] ao qual você está atribuído. Consulte [Administração](../../../features/administration/administration-overview.md) e [Criar um Grupo](../../../features/administration/administration-overview.md#create-group) para obter mais informações.

[!UICONTROL RBAC] grupos devem ter algumas fontes de dados configuradas para exibir os relatórios [!UICONTROL Audience Optimization]. O consultor do [!DNL Audience Manager] irá configurar estes [!UICONTROL data sources] para você. Quanto mais [!UICONTROL data sources] em cada grupo de usuários [!UICONTROL RBAC], mais dados esses membros do grupo terão acesso. No mínimo, seu consultor configurará pelo menos um destes [!UICONTROL data sources]:

* Anunciante [!UICONTROL data source]
* Marca [!UICONTROL data source]
* Plataforma [!UICONTROL data source]

Os usuários que pertencem a mais de um grupo de usuários [!UICONTROL RBAC] podem alternar entre a exibição de cada grupo. Os dados exibidos serão atualizados para respeitar o grupo selecionado. Se a sua empresa não usar o [!UICONTROL RBAC], todos os usuários terão privilégios de administrador e acesso a todos os [!UICONTROL data sources] (grupos de conversão).

## Grupos de conversão {#conversion-groups}

Nos relatórios [!UICONTROL Audience Optimization], **[!UICONTROL Conversion Groups]** são sinônimos de [!UICONTROL data sources] que contêm pelo menos uma característica de conversão. [!UICONTROL Data sources] que não contêm pelo menos uma característica de conversão não aparecem nos relatórios [!UICONTROL Audience Optimization]. Você pode exibir as características de conversão para grupos de conversão no relatório [Características de conversão relatadas](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md).
