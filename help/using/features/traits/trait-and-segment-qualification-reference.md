---
description: A qualificação de características, ou realização de características, é tratada de forma diferente em Audience Manager, dependendo do tipo de característica. Consulte a tabela abaixo para obter informações detalhadas sobre qualificação de características.
keywords: trait qualification;trait realization;Unique Trait Realizations;UTR;Total Trait Population;TTP
seo-description: A qualificação de características, ou realização de características, é tratada de forma diferente em Audience Manager, dependendo do tipo de característica. Consulte a tabela abaixo para obter informações detalhadas sobre qualificação de características.
seo-title: Referência de qualificação de característica
solution: Audience Manager
title: Referência de qualificação de característica
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 2%

---


# Referência de qualificação de características e segmentos {#trait-qualification-reference}

A qualificação de características, ou realização de características, é tratada de forma diferente em Audience Manager, dependendo do tipo de característica. Consulte Qualificação de [características por tipo](#trait-type) de característica para obter detalhes sobre a qualificação de tipo de característica.

Além disso, consulte População de segmentos em tempo [real e População](#real-time-segment) total de segmentos para obter detalhes sobre a qualificação de segmentos.



## Qualificação de característica por tipo de característica {#trait-type}

| Tipo de característica | Critérios de qualificação |
|---|---|
| Características baseadas em regras | A qualificação de características acontece em tempo real, já que os usuários se qualificam para uma característica em seu navegador. Seus usuários se qualificarão para uma característica baseada em regras aproximadamente 4 horas depois que você [criar a característica](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) na interface do usuário. Características baseadas em regras permitem usar controles de [recenticidade e frequência](../segments/recency-and-frequency.md) para o limite de frequência de anúncio e outros casos de uso. |
| Características integradas | A qualificação de características ocorre depois que um arquivo de entrada é processado, isto é, o arquivo de entrada é [importado para o Audience Manager](../../faq/faq-inbound-data-ingestion.md) e é quando a qualificação de características acontece. Aguarde aproximadamente 4 horas após criar uma característica integrada antes de carregar um arquivo de entrada para processamento. Para características integradas, o número máximo de qualificações para um perfil de usuário é 1. |
| Características algorítmicas | Para características algorítmicas, o número máximo de qualificações para um perfil de usuário é 1. |
| Características da pasta | Uma característica de pasta resume as qualificações de característica das características que ela contém. Ler características [da pasta: Sobre](about-folder-traits.md) para obter mais informações. |
| Características do público-alvo ativo e características sincronizadas da fonte de dados | Uma [!UICONTROL Active Audience] característica contém todos os dispositivos sob gerenciamento na sua conta de Audience Manager. [!UICONTROL Data Source Synced Traits] rastreie todos os usuários associados a uma fonte de dados. Leia mais sobre Características de Audiência [ativas e Características](client-activity-synced-audience-traits.md)sincronizadas da fonte de dados. |

## Realizações de características únicas e população de características totais {#unique-trait-realizations}

![realização de características únicas](assets/trait-graph.png)

Dependendo do tipo de resultados que você deseja que o gráfico mostre (filtrado por [!UICONTROL Device ID] ou [!UICONTROL Cross-Device ID]), as métricas têm significados diferentes:

Ao filtrar os resultados por [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] é o número de visitantes anônimos do dispositivo que adicionaram a característica ao perfil dentro de intervalos de tempo diferentes.
* [!UICONTROL Total Trait Population] é o número de visitantes anônimos do dispositivo que têm esta característica no perfil.

Ao filtrar os resultados por [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] é o número de visitantes autenticados que adicionaram a característica ao perfil, dentro de intervalos de tempo diferentes.
* [!UICONTROL Total Trait Population] é o número de visitantes autenticados que têm esta característica no perfil.

Pense nos números desta forma. Na imagem acima, da visualização Detalhes [da](../../features/traits/trait-details-page.md) característica, 90.173 representa o número de dispositivos ativos que visitaram suas propriedades ontem. A [!UICONTROL Total Trait Population] de 55.757 representa a quantidade de usuários atualmente qualificados para essa característica. A [!UICONTROL Total Trait Population] figura destina-se a mostrar a quantidade total de usuários que podem ser usados para segmentação/definição de metas. Normalmente, os usuários permanecerão parte de uma característica por 120 dias.

Porque nós executamos dois trabalhos computacionais diferentes para calcular as duas populações, as [!UICONTROL Total Trait Population] sempre ficam para trás [!UICONTROL Unique Trait Realizations] por 24 horas. No gráfico acima, você pode ver cerca de 90.400 [!UICONTROL Unique Trait Realizations] e um [!UICONTROL Total Trait Population] de 90.300 para o dia 5 de fevereiro. Os 90.400 perfis são adicionados ao [!UICONTROL Total Trait Population] no dia seguinte.

Para levar o ponto para casa mais longe, se você experienciasse um pico de 10.000 visitantes agora, eles apareceriam na casa de amanhã [!UICONTROL Unique Trait Realizations], mas só apareceriam 24 horas depois na [!UICONTROL Total Trait Population].

Qualquer alteração nas realizações de características reflete nas populações de segmentos.

## População de segmentos em tempo real e preenchimento total de segmentos {#real-time-segment}

![realização de características únicas](assets/segment-graph.png)

A [!UICONTROL Real-time Segment Population] conta o número de dispositivos que se qualificaram para o segmento selecionado e que atingiram suas propriedades, dentro do intervalo de tempo selecionado.

A [!UICONTROL Total Segment Population] conta o número de dispositivos que se qualificaram para o segmento selecionado dentro do intervalo de tempo selecionado. O [!UICONTROL 1 Day] relatório representa a contagem de população de segmentos mais atualizada.

Pense nos números desta forma. Na imagem acima, da visualização Detalhes [do](../../features/segments/segment-summary-view.md) segmento, 9.993 representa o número de dispositivos ativos, que visitaram suas propriedades ontem e se qualificaram para o segmento. O número [!UICONTROL Total Segment Population] de 699.532 representa o número total de dispositivos atualmente qualificados para esse segmento. A [!UICONTROL Total Segment Population] figura deve mostrar o número total de dispositivos que podem ser usados para segmentação/definição de metas.

Porque nós executamos dois trabalhos computacionais diferentes para calcular as duas populações, as [!UICONTROL Total Segment Population] sempre ficam para trás [!UICONTROL Real-time Segment Population] por 24 horas. No gráfico acima, você pode ver um 8.116 [!UICONTROL Real-time Segment Population] e um [!UICONTROL Total Segment Population] de 742.000 para o dia 2 de fevereiro. Os 8.116 perfis são adicionados ao [!UICONTROL Total Segment Population] no dia seguinte.

Para levar o ponto para casa mais longe, se você experienciasse um pico de 10.000 visitantes agora, eles apareceriam na casa de amanhã [!UICONTROL Real-time Segment Population], mas só apareceriam 24 horas depois na [!UICONTROL Total Segment Population].

## Limite de qualificação de características {#trait-qualification-limit}

Nós aplicamos um limite de 150.000 qualificações de características para cada perfil de usuário, seja um perfil autenticado ([DPUUID](../../reference/ids-in-aam.md)) ou uma ID de dispositivo ([UUID](../../reference/ids-in-aam.md)). Observe que, embora os DPUUIDs sejam exclusivos de uma instância específica do [!DNL Audience Manager], os UUIDs são compartilhados na [!DNL Audience Manager] plataforma. Para [!UICONTROL UUID]nós, impomos uma política de equidade ao armazenarmos qualificações profissionais. Um algoritmo garante que um compartilhamento igual do [!UICONTROL UUID] perfil seja disponibilizado para cada instância do [!DNL Audience Manager].

