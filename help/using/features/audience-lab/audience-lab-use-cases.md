---
description: O Audience Lab permite vários casos de uso permitindo que você use segmentos de linha de base para criar grupos de teste. Você pode dividir grupos de teste em vários segmentos de teste mutuamente exclusivos, mapeá-los para destinos diferentes e determinar qual dos segmentos são mais eficazes na condução de conversões.
seo-description: O Audience Lab permite vários casos de uso permitindo que você use segmentos de linha de base para criar grupos de teste. Você pode dividir grupos de teste em vários segmentos de teste mutuamente exclusivos, mapeá-los para destinos diferentes e determinar qual dos segmentos são mais eficazes na condução de conversões.
seo-title: Casos de uso do laboratório de público-alvo
solution: Audience Manager
title: Casos de uso do laboratório de público-alvo
topic: API DIL
uuid: 727 bec 8 a-df 9 a -40 cc-b 8 a 7-e 1980 d 146 a 84
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab Use Cases {#audience-lab-use-cases}

[!UICONTROL Audience Lab] ativa vários casos de uso permitindo que você use segmentos de linha de base para criar grupos de teste. Você pode dividir grupos de teste em vários segmentos de teste mutuamente exclusivos, mapeá-los para destinos diferentes e determinar qual dos segmentos são mais eficazes na condução de conversões.

## Compare Models in Audience Lab {#compare-models}

You can use several different types and sources of models in [!DNL Audience Manager]. [!UICONTROL Audience Lab] oferece uma maneira fácil de comparar as taxas de conversão de seus clientes, em seus modelos ativos.

<!-- audience-lab-compare-models.xml -->

Nesse caso de uso, você está comparando modelos diferentes. You can either use models created via an in-house data warehouse and import them in [!DNL Audience Manager] as [Onboarded Traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) or you can use the [Algorithmic Models](../../features/algorithmic-models/understanding-models.md) feature in [!DNL Audience Manager].

1. Create two models, either in the [Model Builder](../../features/algorithmic-models/create-model.md), or via an outside platform.
1. Create [algorithmic traits](../../features/traits/create-algorithmic-traits.md) from the algorithmic model or import your own models as onboarded traits.
1. Crie segmentos mutuamente exclusivos para que os usuários em ambos os modelos não se sobreponham:

   * Create a *Model 1 Segment* and a *Model 2 Segment*.
   * Have the segment rule for *Model 1 Segment* be model 1 trait [!DNL AND NOT] model 2 trait, and vice-versa for *Model 2 Segment*.

1. [Crie dois grupos de teste de segmento](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) em [!UICONTROL Audience Lab], um com o *Modelo 1 Segmento* como a linha de base, o outro com *o Modelo 2 Segmento* como a linha de base.

   * Mantenha as variáveis iguais para os dois grupos de teste: mesmos destinos, criação e traços de conversão.
   * Verifique se os segmentos de teste têm números semelhantes de usuários (por exemplo, 1.6 milhões e 1.8 milhões estão corretos, 1.6 milhões e 16 milhões não são).
   * Reserve um segmento de controle em cada grupo de teste do segmento de teste. Dessa forma, você pode definir uma pequena parte de cada segmento e não os direcioná-los explicitamente no teste.

1. Examine os resultados:

   * The [Audience Lab reporting view](../../features/audience-lab/audience-lab-reporting-view.md) will show the number of conversions each model is driving. Para campanhas com base em conversão, o segmento de teste que impulsiona mais conversões significa o modelo que está melhor desempenho.
   * Como você possui os segmentos de controle, também é possível avaliar como o modelo foi comparado a &quot;definição padrão&quot;. Você não está apenas testando um modelo em comparação a outro, mas testando a pergunta de &quot;este modelo faz melhor do que as práticas normais?&quot;

## Testing Creatives Across Destinations {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Use [!UICONTROL Audience Lab] to measure the number of conversions a creative is driving across different destinations. Esse caso de uso também permite medir as conversões do anúncio contra conversões naturalmente ocorridas.

1. [Criar um grupo de teste de segmento](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups), selecionando o segmento que deseja testar em relação ao segmento de linha de base.
1. Divida o segmento da linha de base em segmentos de teste e controle os segmentos.
1. Mapeie os segmentos de teste para os destinos diferentes que deseja testar.
1. O segmento de controle pode ser negado e não mapeado para qualquer destino. O segmento de controle não deve ser direcionado pelo teste criativo para definir uma linha de base de resultados para conversões naturalmente ocorridas.
1. Especifique uma data de início e uma data final para o teste.
1. Configure o segmento e o anúncio nos destinos.
1. The [Audience Lab reporting view](../../features/audience-lab/audience-lab-reporting-view.md) will show the number of conversions the creative is driving across the destinations.
1. Como você criou um segmento de controle, também pode avaliar como o anúncio ocorreu contra conversões naturalmente ocorrendo. Você está testando a pergunta: &quot; Este anúncio gerou uma taxa de conversão maior do que as práticas normais? &quot;
