---
description: O Audience Lab permite vários casos de uso, permitindo que você use segmentos de linha de base para criar grupos de teste. É possível dividir os grupos de teste em vários segmentos de teste mutuamente exclusivos, mapeá-los para destinos diferentes e determinar quais dos segmentos são mais eficazes para gerar conversões.
seo-description: O Audience Lab permite vários casos de uso, permitindo que você use segmentos de linha de base para criar grupos de teste. É possível dividir os grupos de teste em vários segmentos de teste mutuamente exclusivos, mapeá-los para destinos diferentes e determinar quais dos segmentos são mais eficazes para gerar conversões.
seo-title: Casos de uso do Audience Lab
solution: Audience Manager
title: Casos de uso do Audience Lab
topic: API DIL
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Casos de uso do Audience Lab {#audience-lab-use-cases}

[!UICONTROL Audience Lab] permite vários casos de uso, permitindo que você use segmentos de linha de base para criar grupos de teste. É possível dividir os grupos de teste em vários segmentos de teste mutuamente exclusivos, mapeá-los para destinos diferentes e determinar quais dos segmentos são mais eficazes para gerar conversões.

## Comparar modelos no Audience Lab {#compare-models}

Você pode usar vários tipos diferentes e fontes de modelos em [!DNL Audience Manager]. [!UICONTROL Audience Lab] oferece uma maneira fácil de comparar as taxas de conversão de seus clientes em seus modelos ativos.

<!-- audience-lab-compare-models.xml -->

Neste caso de uso, você está comparando diferentes modelos. Você pode usar modelos criados por meio de um data warehouse interno e importá-los [!DNL Audience Manager] como Características [](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) integradas ou usar o recurso Modelos [](../../features/algorithmic-models/understanding-models.md) algorítmicos em [!DNL Audience Manager].

1. Crie dois modelos, no Construtor [de modelos](../../features/algorithmic-models/create-model.md)ou por uma plataforma externa.
1. Crie características [](../../features/traits/create-algorithmic-traits.md) algorítmicas a partir do modelo algorítmico ou importe seus próprios modelos como características integradas.
1. Crie segmentos mutuamente exclusivos para que os usuários em ambos os modelos não se sobreponham:

   * Crie um segmento *do* Modelo 1 e um segmento *do* Modelo 2.
   * Faça com que a regra de segmento para o *Modelo 1 Segmento* seja modelo 1 característica [!DNL AND NOT] 2 característica e vice-versa para o *Modelo 2 Segmento*.

1. [Crie dois grupos](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) de teste de segmento no [!UICONTROL Audience Lab], um com *Modelo 1 Segmento* como linha de base, o outro com *Modelo 2 Segmento* como linha de base.

   * Mantenha as variáveis iguais para ambos os grupos de teste: os mesmos destinos, características criativas e de conversão.
   * Certifique-se de que os segmentos de teste tenham números semelhantes de usuários (por exemplo, 1,6 milhão e 1,8 milhão está certo, 1,6 milhão e 16 milhões não).
   * Reservar um segmento de controle em cada grupo de teste de segmento de teste. Dessa forma, você pode reservar uma pequena parte de cada segmento e não direcioná-los explicitamente no teste.

1. Examine os resultados:

   * A exibição [de relatório do Laboratório de](../../features/audience-lab/audience-lab-reporting-view.md) público-alvo mostrará o número de conversões que cada modelo está acionando. Para campanhas com base em conversão, o segmento de teste que direciona a maioria das conversões significa o modelo que tem melhor desempenho.
   * Como você tem segmentos de controle, também é possível avaliar como o modelo funcionou em relação à "definição de metas padrão". Vocês não estão apenas testando um modelo versus o outro, mas também a questão de "este modelo fez melhor do que as práticas normais?"

## Testando criativos em destinos {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Use [!UICONTROL Audience Lab] para medir o número de conversões que um anúncio está conduzindo em diferentes destinos. Esse caso de uso também permite medir as conversões do anúncio em relação às conversões que ocorrem naturalmente.

1. [Crie um grupo](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)de teste de segmento, selecionando o segmento para o qual deseja testar o anúncio como o segmento de linha de base.
1. Dividir o segmento da linha de base em segmentos de teste e controle.
1. Mapeie os segmentos de teste para os diferentes destinos que você deseja testar.
1. O segmento de controle pode ser retido e não mapeado para nenhum destino. O segmento de controle não deve ser direcionado pelo anúncio de teste para definir uma linha de base de resultados para conversões que ocorrem naturalmente.
1. Especifique uma data de início e uma data de término para o teste.
1. Configure o segmento e o anúncio nos destinos.
1. A exibição [de relatórios do Laboratório de](../../features/audience-lab/audience-lab-reporting-view.md) público-alvo mostrará o número de conversões que o anúncio está conduzindo nos destinos.
1. Como você criou um segmento de controle, também é possível avaliar como o anúncio fez em relação às conversões que ocorrem naturalmente. Você está testando a pergunta: "Esse anúncio gerou uma taxa de conversão mais alta do que as práticas normais?"
