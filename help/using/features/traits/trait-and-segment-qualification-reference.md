---
description: A qualificação de característica, ou realização de característica, é tratada de forma diferente no Audience Manager, dependendo do tipo de característica. Consulte a tabela abaixo para obter informações detalhadas sobre a qualificação de características.
keywords: Qualificação de característica, Realização de característica, Realizações de característica única, UTR, Preenchimento de característica total, TTP
seo-description: Trait qualification, or trait realization, is treated differently in Audience Manager, depending on trait type. See the table below for detailed information on trait qualification.
seo-title: Trait Qualification Reference
solution: Audience Manager
title: Referência de qualificação de característica
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
exl-id: 223f5fc6-c939-4bc6-94a3-5d953abc601a
source-git-commit: c844ce5ed85e9071227df67b5b20e6ee674408be
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 0%

---

# Referência de qualificação de característica e segmento {#trait-qualification-reference}

A qualificação de característica, ou realização de característica, é tratada de forma diferente no Audience Manager, dependendo do tipo de característica. Consulte [Qualificação de característica por tipo de característica](#trait-type) para obter detalhes sobre a qualificação de tipo de característica.

Além disso, consulte [População de segmentos em tempo real e População total de segmentos](#real-time-segment) para obter detalhes sobre a qualificação de segmentos.



## Qualificação de característica por tipo de característica {#trait-type}

| Tipo de característica | Critérios de qualificação |
|---|---|
| Características com base em regras | A qualificação de características acontece em tempo real, à medida que os usuários se qualificam para uma característica em seu navegador. Seus usuários começarão a se qualificar para uma característica com base em regras aproximadamente 4 horas após você [criar a característica](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) na interface. As características baseadas em regras permitem que você use controles de [recenticidade e frequência](../segments/recency-and-frequency.md) para limite de frequência de anúncio e outros casos de uso. |
| Características integradas | A qualificação de característica ocorre depois que um arquivo de entrada é processado, ou seja, o arquivo de entrada é [importado para o Audience Manager](../../faq/faq-inbound-data-ingestion.md), e é quando ocorre a qualificação de característica. Aguarde aproximadamente 4 horas após a criação de uma característica integrada antes de fazer upload de um arquivo de entrada para processamento. Para características integradas, o número máximo de qualificações para um perfil de usuário é 1. |
| Características algorítmicas | Para características algorítmicas, o número máximo de qualificações para um perfil de usuário é 1. |
| Características de pasta | Uma característica de pasta soma as qualificações de característica das características que contém. Leia [Características de Pasta: Sobre](about-folder-traits.md) para obter mais informações. |
| Características do público-alvo ativo e características sincronizadas do Source de dados | Uma característica [!UICONTROL Active Audience] contém todos os dispositivos sob gerenciamento na sua conta Audience Manager. [!UICONTROL Data Source Synced Traits] rastreia todos os usuários associados a uma fonte de dados. Leia mais sobre [Características do público-alvo ativo e Características sincronizadas do Data Source](client-activity-synced-audience-traits.md). |

## Realizações de características únicas e preenchimento total de características {#unique-trait-realizations}

![realização de características exclusivas](assets/trait-graph.png)

Dependendo do tipo de resultados que você deseja que o gráfico mostre (filtrado por [!UICONTROL Device ID] ou [!UICONTROL Cross-Device ID]), as métricas têm significados diferentes:

Ao filtrar os resultados por [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] é o número de visitantes de dispositivos anônimos que adicionaram a característica aos seus perfis em diferentes intervalos de tempo.
* [!UICONTROL Total Trait Population] é o número de visitantes de dispositivos anônimos que possuem essa característica em seus perfis.

Ao filtrar os resultados por [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] é o número de visitantes autenticados que adicionaram a característica ao perfil, em diferentes intervalos de tempo.
* [!UICONTROL Total Trait Population] é o número de visitantes autenticados que possuem esta característica no perfil.

Pense nos números dessa maneira. Na imagem acima, da exibição [Detalhes da característica](../../features/traits/trait-details-page.md), 90.173 representa o número de dispositivos ativos, que visitaram suas propriedades ontem. O [!UICONTROL Total Trait Population] de 55.757 representa a quantidade de usuários qualificados atualmente para essa característica. O número [!UICONTROL Total Trait Population] é para mostrar a quantidade total de usuários que podem ser usados para segmentação/direcionamento. Normalmente, os usuários permanecerão parte de uma característica por 120 dias.

Como executamos dois trabalhos computacionais diferentes para calcular as duas populações, o [!UICONTROL Total Trait Population] sempre fica atrás do [!UICONTROL Unique Trait Realizations] por 24 horas. No gráfico acima, você pode ver por volta de 90.400 [!UICONTROL Unique Trait Realizations] e um [!UICONTROL Total Trait Population] de aproximadamente 90.300 de 5 de fevereiro. Os 90.400 perfis foram adicionados ao [!UICONTROL Total Trait Population] no dia seguinte.

Para direcionar ainda mais o ponto para casa, se você tivesse um pico de 10.000 visitantes agora, eles apareceriam no [!UICONTROL Unique Trait Realizations] de amanhã, mas só apareceriam 24 horas depois no [!UICONTROL Total Trait Population].

Qualquer alteração nas realizações de características reflete nas populações do segmento.

## População de segmentos em tempo real e População total de segmentos {#real-time-segment}

![realização de características exclusivas](assets/segment-graph.png)

O [!UICONTROL Real-time Segment Population] conta o número de dispositivos que se qualificaram para o segmento selecionado e atingiram suas propriedades, dentro do intervalo selecionado.

O [!UICONTROL Total Segment Population] conta o número de dispositivos que se qualificaram para o segmento selecionado dentro do intervalo de tempo selecionado. O relatório [!UICONTROL 1 Day] representa a contagem de população de segmentos mais atualizada.

Pense nos números dessa maneira. Na imagem acima, da exibição [Detalhes do segmento](../../features/segments/segment-summary-view.md), 9.993 representa o número de dispositivos ativos, que visitaram suas propriedades ontem e se qualificaram para o segmento. O [!UICONTROL Total Segment Population] de 699.532 representa o número total de dispositivos qualificados atualmente para esse segmento. O número [!UICONTROL Total Segment Population] é destinado a mostrar o número total de dispositivos que podem ser usados para segmentação/direcionamento.

Como executamos dois trabalhos computacionais diferentes para calcular as duas populações, o [!UICONTROL Total Segment Population] sempre fica atrás do [!UICONTROL Real-time Segment Population] por 24 horas. No gráfico acima, você pode ver um [!UICONTROL Real-time Segment Population] de 8.116 e um [!UICONTROL Total Segment Population] de 742.000 para 2 de fevereiro. Os 8.116 perfis foram adicionados ao [!UICONTROL Total Segment Population] no dia seguinte.

Para direcionar ainda mais o ponto para casa, se você tivesse um pico de 10.000 visitantes agora, eles apareceriam no [!UICONTROL Real-time Segment Population] de amanhã, mas só apareceriam 24 horas depois no [!UICONTROL Total Segment Population].

## Limite de qualificação de característica {#trait-qualification-limit}

Reforçamos um limite de 150.000 qualificações de características para cada perfil de usuário, seja um perfil autenticado ([DPUUID](../../reference/ids-in-aam.md)) ou uma ID de dispositivo ([UUID](../../reference/ids-in-aam.md)). Observe que, embora os DPUUIDs sejam exclusivos para uma instância específica do [!DNL Audience Manager], os UUIDs são compartilhados na plataforma [!DNL Audience Manager]. Para [!UICONTROL UUID]s, impomos uma política de integridade ao armazenar qualificações de características. Um algoritmo garante que um compartilhamento igual do perfil [!UICONTROL UUID] seja disponibilizado para cada instância de [!DNL Audience Manager].
