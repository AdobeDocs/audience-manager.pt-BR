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
source-wordcount: '809'
ht-degree: 1%

---

# Referência de qualificação de características e segmentos {#trait-qualification-reference}

A qualificação de característica, ou realização de característica, é tratada de forma diferente no Audience Manager, dependendo do tipo de característica. Consulte [Qualificação de característica por tipo de característica](#trait-type) para obter detalhes sobre qualificação de tipo de característica.

Além disso, consulte [População de segmentos em tempo real e População total de segmentos](#real-time-segment) para obter detalhes sobre a qualificação de segmentos.



## Qualificação de característica por tipo de característica {#trait-type}

| Tipo de característica | Critérios de qualificação |
|---|---|
| Características com base em regras | A qualificação de características acontece em tempo real, à medida que os usuários se qualificam para uma característica em seu navegador. Seus usuários começarão a se qualificar para uma característica com base em regras aproximadamente 4 horas depois de você [criar a característica](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) na interface. As características com base em regras permitem usar [recenticidade e frequência](../segments/recency-and-frequency.md) controles para limite de frequência de anúncio e outros casos de uso. |
| Características integradas | A qualificação de características ocorre após o processamento de um arquivo de entrada, ou seja, o arquivo de entrada é [importado para o Audience Manager](../../faq/faq-inbound-data-ingestion.md) e é quando acontece a qualificação de características. Aguarde aproximadamente 4 horas após a criação de uma característica integrada antes de fazer upload de um arquivo de entrada para processamento. Para características integradas, o número máximo de qualificações para um perfil de usuário é 1. |
| Características algorítmicas | Para características algorítmicas, o número máximo de qualificações para um perfil de usuário é 1. |
| Características de pasta | Uma característica de pasta soma as qualificações de característica das características que contém. Ler [Características da pasta: sobre](about-folder-traits.md) para obter mais informações. |
| Características do público-alvo ativo e características sincronizadas da fonte de dados | Um [!UICONTROL Active Audience] A característica contém todos os dispositivos sob gerenciamento na sua conta Audience Manager. [!UICONTROL Data Source Synced Traits] rastrear todos os usuários associados a uma origem de dados. Leia mais sobre [Características do público-alvo ativo e características sincronizadas da fonte de dados](client-activity-synced-audience-traits.md). |

## Realizações de características únicas e preenchimento total de características {#unique-trait-realizations}

![realização de características únicas](assets/trait-graph.png)

Dependendo do tipo de resultados que você deseja que o gráfico mostre (filtrado por [!UICONTROL Device ID] ou [!UICONTROL Cross-Device ID]), as métricas têm significados diferentes:

Ao filtrar os resultados por [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] é o número de visitantes de dispositivos anônimos que adicionaram a característica ao perfil em intervalos de tempo diferentes.
* [!UICONTROL Total Trait Population] é o número de visitantes de dispositivos anônimos que têm essa característica em seus perfis.

Ao filtrar os resultados por [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] é o número de visitantes autenticados que adicionaram a característica aos perfis, em intervalos de tempo diferentes.
* [!UICONTROL Total Trait Population] é o número de visitantes autenticados que têm essa característica no perfil.

Pense nos números dessa maneira. Na imagem acima, no campo [Detalhes da característica](../../features/traits/trait-details-page.md) visualize, 90.173 representa o número de dispositivos ativos, que visitaram suas propriedades ontem. A variável [!UICONTROL Total Trait Population] de 55.757 representa a quantidade de usuários qualificados atualmente para essa característica. A variável [!UICONTROL Total Trait Population] a figura serve para mostrar a quantidade total de usuários que podem ser usados para segmentação/direcionamento. Normalmente, os usuários permanecerão parte de uma característica por 120 dias.

Como executamos dois trabalhos computacionais diferentes para calcular as duas populações, a variável [!UICONTROL Total Trait Population] sempre fica atrás do [!UICONTROL Unique Trait Realizations] em 24 horas. No gráfico acima, você pode ver cerca de 90.400 [!UICONTROL Unique Trait Realizations] e uma [!UICONTROL Total Trait Population] de cerca de 90.300 para 5 de fevereiro. Os 90.400 perfis são adicionados ao [!UICONTROL Total Trait Population] no dia seguinte.

Para direcionar ainda mais o ponto para casa, se você tivesse um pico de 10 mil visitantes agora, eles apareceriam no amanhã [!UICONTROL Unique Trait Realizations], mas só apareceriam 24 horas depois no [!UICONTROL Total Trait Population].

Qualquer alteração nas realizações de características reflete nas populações do segmento.

## População de segmentos em tempo real e População total de segmentos {#real-time-segment}

![realização de características únicas](assets/segment-graph.png)

A variável [!UICONTROL Real-time Segment Population] O conta o número de dispositivos que se qualificaram para o segmento selecionado e atingiram suas propriedades dentro do intervalo selecionado.

A variável [!UICONTROL Total Segment Population] O conta o número de dispositivos que se qualificaram para o segmento selecionado dentro do intervalo de tempo selecionado. A variável [!UICONTROL 1 Day] representa a contagem de população de segmentos mais atualizada.

Pense nos números dessa maneira. Na imagem acima, no campo [Detalhes do segmento](../../features/segments/segment-summary-view.md) Assim, 9.993 representa o número de dispositivos ativos, que visitaram suas propriedades ontem e se qualificaram para o segmento. A variável [!UICONTROL Total Segment Population] de 699.532 representa o número total de dispositivos qualificados atualmente para esse segmento. A variável [!UICONTROL Total Segment Population] esta figura mostra o número total de dispositivos que podem ser usados para segmentação/direcionamento.

Como executamos dois trabalhos computacionais diferentes para calcular as duas populações, a variável [!UICONTROL Total Segment Population] sempre fica atrás do [!UICONTROL Real-time Segment Population] em 24 horas. No gráfico acima, você pode ver um número de [!UICONTROL Real-time Segment Population] e uma [!UICONTROL Total Segment Population] de 742.000 para 2 de fevereiro. Os 8.116 perfis são adicionados ao [!UICONTROL Total Segment Population] no dia seguinte.

Para direcionar ainda mais o ponto para casa, se você tivesse um pico de 10 mil visitantes agora, eles apareceriam no amanhã [!UICONTROL Real-time Segment Population], mas só apareceriam 24 horas depois no [!UICONTROL Total Segment Population].

## Limite de qualificação de característica {#trait-qualification-limit}

Impomos um limite de 150.000 qualificações de características para cada perfil de usuário, independentemente de ser um perfil autenticado ([DPUUID](../../reference/ids-in-aam.md)) ou uma ID de dispositivo ([UUID](../../reference/ids-in-aam.md)). Observe que, embora os DPUUIDs sejam exclusivos de uma instância específica do [!DNL Audience Manager], as UUIDs são compartilhadas na [!DNL Audience Manager] plataforma. Para [!UICONTROL UUID]Assim, impomos uma política de equidade ao armazenar qualificações de características. Um algoritmo garante que uma parte igual da [!UICONTROL UUID] O perfil do é disponibilizado para cada instância do [!DNL Audience Manager].
