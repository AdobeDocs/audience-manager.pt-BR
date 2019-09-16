---
description: A otimização de público-alvo para anunciantes pode ajudá-lo a identificar possíveis oportunidades de desempenho para segmentos do Audience Manager em suas campanhas de mídia paga. Esses relatórios combinam dados de desempenho de campanha em nível de log com métricas de segmento do Audience Manager para informar otimizações centradas em segmentos e uma combinação de canais eficaz.
seo-description: A otimização de público-alvo para anunciantes pode ajudá-lo a identificar possíveis oportunidades de desempenho para segmentos do Audience Manager em suas campanhas de mídia paga. Esses relatórios combinam dados de desempenho de campanha em nível de log com métricas de segmento do Audience Manager para informar otimizações centradas em segmentos e uma combinação de canais eficaz.
seo-title: Otimização de público-alvo para anunciantes
solution: Audience Manager
title: Otimização de público-alvo para anunciantes
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Optimization for Advertisers{#audience-optimization-for-advertisers}

A otimização de público-alvo para anunciantes pode ajudá-lo a identificar possíveis oportunidades de desempenho para segmentos do Audience Manager em suas campanhas de mídia paga. Esses relatórios combinam dados de desempenho de campanha em nível de log com métricas de segmento do Audience Manager para informar otimizações centradas em segmentos e uma combinação de canais eficaz.

## Métodos de ingestão de dados {#data-ingestion-methods}

É possível enviar dados para uso [!DNL Audience Manager] nesses relatórios por um destes métodos. Às vezes, os clientes enviam dados por ambos os métodos. Isso ajuda a garantir que seus relatórios contenham as informações mais completas e precisas sobre um visitante. Para usar os [!UICONTROL Audience Optimization] relatórios, suas chamadas de evento devem incluir *todos* os parâmetros listados na documentação [Visão geral e Mapeamentos para arquivos](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) de metadados. Você pode enviar dados pelos seguintes métodos listados abaixo.

* Chamadas de pixel: Para passar os parâmetros de metadados necessários para [!DNL Audience Manager] ver [Captura de dados de cliques da campanha por meio de chamadas](../../../integration/media-data-integration/click-data-pixels.md) de pixels e [Captura de dados de impressão da campanha por meio de chamadas](../../../integration/media-data-integration/impression-data-pixels.md)de pixels.

* Arquivos de dados: Se você quiser usar esses relatórios para analisar seus próprios dados ou dados de uma fonte não integrada, é necessário criar e carregar arquivos de dados e metadados [!DNL Audience Manager]para esses dados. Para obter mais informações, consulte Arquivos [de dados para relatórios](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) de otimização de público-alvo e Arquivos [de dados e metadados para relatórios](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)de otimização de público-alvo.

## RBAC (Role-Based Access Controls) {#rbac}

O tipo de relatórios que você pode exibir depende do [!UICONTROL RBAC] grupo ao qual você está atribuído. Consulte [Administração](../../../features/administration/administration-overview.md) e [Criar um grupo](../../../features/administration/administration-overview.md#create-group) para obter mais informações.

[!UICONTROL RBAC] grupos devem ter algumas fontes de dados configuradas para exibir os [!UICONTROL Audience Optimization] relatórios. Seu [!DNL Audience Manager] consultor irá configurar essas fontes de dados para você. Quanto mais fontes de dados em cada grupo de [!UICONTROL RBAC] usuários, mais dados esses membros do grupo terão acesso. No mínimo, seu consultor irá configurar pelo menos uma dessas fontes de dados:

* Fonte de dados do anunciante
* Fonte de dados da marca
* Fonte de dados da plataforma

Os usuários que pertencem a mais de um grupo de [!UICONTROL RBAC] usuários podem alternar entre a exibição de cada grupo. Os dados exibidos serão atualizados para respeitar o grupo selecionado. Se sua empresa não usar [!UICONTROL RBAC], todos os usuários terão privilégios de administrador e acesso a todas as fontes de dados (grupos de conversão).

## Grupos de conversão {#conversion-groups}

Nos [!UICONTROL Audience Optimization] relatórios, **[!UICONTROL Conversion Groups]** são sinônimos de fontes de dados que contêm pelo menos uma característica de conversão. As fontes de dados que não contêm pelo menos uma característica de conversão não aparecem nos [!UICONTROL Audience Optimization] relatórios. Você pode exibir as características de conversão para grupos de conversão no relatório Características [de conversão](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) reportadas.
