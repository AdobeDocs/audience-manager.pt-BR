---
description: A qualificação de característica, ou realização de característica, é tratada de forma diferente no Audience Manager, dependendo do tipo de característica. Consulte a tabela abaixo para obter informações detalhadas sobre qualificação de características.
keywords: Qualificação de característica, Realização de característica, Realizações de característica única, UTR, Preenchimento de característica total, TTP
seo-description: A qualificação de característica, ou realização de característica, é tratada de forma diferente no Audience Manager, dependendo do tipo de característica. Consulte a tabela abaixo para obter informações detalhadas sobre qualificação de características.
seo-title: Referência de qualificação de característica
solution: Audience Manager
title: Referência de qualificação de característica
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: 'Características '
exl-id: 223f5fc6-c939-4bc6-94a3-5d953abc601a
source-git-commit: c844ce5ed85e9071227df67b5b20e6ee674408be
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 2%

---

# Referência de qualificação de características e segmentos {#trait-qualification-reference}

A qualificação de característica, ou realização de característica, é tratada de forma diferente no Audience Manager, dependendo do tipo de característica. Consulte [Qualificação de característica por tipo de característica](#trait-type) para obter detalhes sobre a qualificação de tipo de característica.

Além disso, consulte [População de segmentos em tempo real e População total de segmentos](#real-time-segment) para obter detalhes sobre a qualificação de segmentos.



## Qualificação de característica por tipo de característica {#trait-type}

| Tipo de característica | Critérios de qualificação |
|---|---|
| Características baseadas em regras | A qualificação de característica ocorre em tempo real, pois os usuários se qualificam para uma característica em seu navegador. Seus usuários começarão a se qualificar para uma característica baseada em regras aproximadamente 4 horas depois que você [criar a característica](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) na interface do usuário. As características com base em regras permitem usar os controles de [recenticidade e frequência](../segments/recency-and-frequency.md) para o limite de frequência do anúncio e outros casos de uso. |
| Características integradas | A qualificação de característica acontece depois que um arquivo de entrada é processado, ou seja, o arquivo de entrada é [importado para o Audience Manager](../../faq/faq-inbound-data-ingestion.md) e é quando a qualificação de característica acontece. Aguarde aproximadamente 4 horas após a criação de uma característica integrada antes de fazer upload de um arquivo de entrada para processamento. Para características integradas, o número máximo de qualificações para um perfil de usuário é 1. |
| Características algorítmicas | Para características algorítmicas, o número máximo de qualificações para um perfil de usuário é 1. |
| Características da pasta | Uma característica de pasta resume as qualificações de característica das características que ela contém. Leia [Características da pasta: Sobre](about-folder-traits.md) para obter mais informações. |
| Características do público-alvo ativo e características sincronizadas da fonte de dados | Uma característica [!UICONTROL Active Audience] contém todos os dispositivos sob gerenciamento na sua conta do Audience Manager. [!UICONTROL Data Source Synced Traits] rastrear todos os usuários associados a uma fonte de dados. Leia mais sobre [Características do público-alvo ativo e Características sincronizadas da fonte de dados](client-activity-synced-audience-traits.md). |

## Realizações de característica única e preenchimento de característica total {#unique-trait-realizations}

![realização de característica única](assets/trait-graph.png)

Dependendo do tipo de resultados que você deseja que o gráfico mostre (filtrado por [!UICONTROL Device ID] ou [!UICONTROL Cross-Device ID]), as métricas têm significados diferentes:

Ao filtrar os resultados por [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] é o número de visitantes anônimos de dispositivos que adicionaram a característica ao perfil dentro de diferentes intervalos de tempo.
* [!UICONTROL Total Trait Population] é o número de visitantes anônimos do seu dispositivo que têm essa característica no perfil.

Ao filtrar os resultados por [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] é o número de seus visitantes autenticados que adicionaram a característica ao perfil, dentro de diferentes intervalos de tempo.
* [!UICONTROL Total Trait Population] é o número de seus visitantes autenticados que têm essa característica em seu perfil.

Pense nos números desta forma. Na imagem acima, na visualização [Detalhes da característica](../../features/traits/trait-details-page.md), 90.173 representa o número de dispositivos ativos que visitaram suas propriedades ontem. O [!UICONTROL Total Trait Population] de 55.757 representa a quantidade de usuários qualificados atualmente para essa característica. A figura [!UICONTROL Total Trait Population] destina-se a mostrar a quantidade total de usuários que podem ser usados para segmentação/direcionamento. Normalmente, os usuários continuarão fazendo parte de uma característica por 120 dias.

Como executamos dois trabalhos computacionais diferentes para calcular as duas populações, o [!UICONTROL Total Trait Population] sempre fica atrás do [!UICONTROL Unique Trait Realizations] em 24 horas. No gráfico acima, você pode ver cerca de 90.400 [!UICONTROL Unique Trait Realizations] e um [!UICONTROL Total Trait Population] de cerca de 90.300 para o dia 5 de fevereiro. Os 90.400 perfis são adicionados a [!UICONTROL Total Trait Population] no dia seguinte.

Para direcionar ainda mais o ponto para casa, se você tivesse um pico de 10.000 visitantes no momento, eles apareceriam no [!UICONTROL Unique Trait Realizations] de amanhã, mas apareceriam apenas 24 horas depois no [!UICONTROL Total Trait Population].

Qualquer alteração nas realizações de características reflete nas populações de segmentos.

## Preenchimento de segmentos em tempo real e preenchimento total de segmentos {#real-time-segment}

![realização de característica única](assets/segment-graph.png)

O [!UICONTROL Real-time Segment Population] conta o número de dispositivos que se qualificaram para o segmento selecionado e que atingiram suas propriedades, dentro do intervalo de tempo selecionado.

O [!UICONTROL Total Segment Population] conta o número de dispositivos que se qualificaram para o segmento selecionado no intervalo de tempo selecionado. O relatório [!UICONTROL 1 Day] representa a contagem de população de segmentos mais atualizada.

Pense nos números desta forma. Na imagem acima, na visualização [Detalhes do segmento](../../features/segments/segment-summary-view.md), 9.993 representa o número de dispositivos ativos, que visitaram suas propriedades ontem e se qualificaram para o segmento. O [!UICONTROL Total Segment Population] de 699.532 representa o número total de dispositivos atualmente qualificados para este segmento. A figura [!UICONTROL Total Segment Population] destina-se a mostrar o número total de dispositivos que podem ser usados para segmentação/direcionamento.

Como executamos dois trabalhos computacionais diferentes para calcular as duas populações, o [!UICONTROL Total Segment Population] sempre fica atrás do [!UICONTROL Real-time Segment Population] em 24 horas. No gráfico acima, você pode ver um 8.116 [!UICONTROL Real-time Segment Population] e um [!UICONTROL Total Segment Population] de 742.000 para o dia 2 de fevereiro. Os 8.116 perfis são adicionados a [!UICONTROL Total Segment Population] no dia seguinte.

Para direcionar ainda mais o ponto para casa, se você tivesse um pico de 10.000 visitantes no momento, eles apareceriam no [!UICONTROL Real-time Segment Population] de amanhã, mas apareceriam apenas 24 horas depois no [!UICONTROL Total Segment Population].

## Limite de qualificação de característica {#trait-qualification-limit}

Nós aplicamos um limite de 150.000 qualificações de características para cada perfil de usuário, seja um perfil autenticado ([DPUUID](../../reference/ids-in-aam.md)) ou uma ID de dispositivo ([UUID](../../reference/ids-in-aam.md)). Observe que, embora os DPUUIDs sejam exclusivos de uma instância específica de [!DNL Audience Manager], os UUIDs são compartilhados na plataforma [!DNL Audience Manager]. Para [!UICONTROL UUID]s, impomos uma política de equidade ao armazenar qualificações de características. Um algoritmo garante que um compartilhamento igual do perfil [!UICONTROL UUID] seja disponibilizado para cada instância de [!DNL Audience Manager].
