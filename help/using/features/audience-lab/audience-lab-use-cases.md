---
description: O Audience Lab permite vários casos de uso, permitindo que você use segmentos de linha de base para criar grupos de teste. É possível dividir grupos de teste em vários segmentos de teste mutuamente exclusivos, mapeá-los para destinos diferentes e determinar qual dos segmentos é mais eficaz em gerar conversões.
seo-description: O Audience Lab permite vários casos de uso, permitindo que você use segmentos de linha de base para criar grupos de teste. É possível dividir grupos de teste em vários segmentos de teste mutuamente exclusivos, mapeá-los para destinos diferentes e determinar qual dos segmentos é mais eficaz em gerar conversões.
seo-title: Casos de uso do Audience Lab
solution: Audience Manager
title: Casos de uso do Audience Lab
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: 'Audience Lab '
exl-id: b68f48bd-0d5d-4b72-84f3-a6f3acea6c49
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---

# Casos de uso do Audience Lab {#audience-lab-use-cases}

[!UICONTROL Audience Lab] O permite vários casos de uso, permitindo que você use segmentos de linha de base para criar grupos de teste. É possível dividir grupos de teste em vários segmentos de teste mutuamente exclusivos, mapeá-los para destinos diferentes e determinar qual dos segmentos é mais eficaz em gerar conversões.

## Comparar modelos no Audience Lab {#compare-models}

Você pode usar vários tipos e fontes diferentes de modelos em [!DNL Audience Manager]. [!UICONTROL Audience Lab] O oferece uma maneira fácil de comparar as taxas de conversão de seus clientes, em todos os modelos ativos.

<!-- audience-lab-compare-models.xml -->

Nesse caso de uso, você está comparando diferentes modelos. Você pode usar modelos criados por um data warehouse interno e importá-los em [!DNL Audience Manager] como [Características integradas](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) ou usar o recurso [Modelos algorítmicos](../../features/algorithmic-models/understanding-models.md) em [!DNL Audience Manager].

1. Crie dois modelos, no [Construtor de Modelos](../../features/algorithmic-models/create-model.md), ou por uma plataforma externa.
1. Crie [características algorítmicas](../../features/traits/create-algorithmic-traits.md) a partir do modelo algorítmico ou importe seus próprios modelos como características integradas.
1. Crie segmentos mutuamente exclusivos para que os usuários em ambos os modelos não se sobreponham:

   * Crie um *Modelo 1 Segmento* e um *Modelo 2 Segmento*.
   * Ter a regra de segmento para *Modelo 1 Segmento* ser característica do modelo 1 [!DNL AND NOT] modelo 2 característica e vice-versa para *Segmento do modelo 2*.

1. [Crie dois ](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) grupos de teste de segmento  [!UICONTROL Audience Lab], um com o  *Modelo 1* Segmentos como linha de base, o outro com o  *Modelo 2* Segmentos como linha de base.

   * Mantenha as variáveis iguais para ambos os grupos de teste: mesmos destinos, criativo, características de conversão.
   * Verifique se os segmentos de teste têm números semelhantes de usuários (por exemplo, 1,6 milhão e 1,8 milhão estão corretos, 1,6 milhão e 16 milhões não estão).
   * Reserve um segmento de controle em cada grupo de teste de segmento de teste. Dessa forma, é possível definir uma pequena parte de cada segmento e não direcioná-los explicitamente no teste.

1. Examine os resultados:

   * A [Exibição de relatório do Audience Lab](../../features/audience-lab/audience-lab-reporting-view.md) mostrará o número de conversões que cada modelo está conduzindo. Para campanhas baseadas em conversão, o segmento de teste que direciona a maioria das conversões significa o modelo que tem o melhor desempenho.
   * Como você tem segmentos de controle, também pode avaliar como o modelo funcionou em relação ao &quot;direcionamento padrão&quot;. Você não está apenas testando um modelo contra o outro, mas também testando a questão de &quot;esse modelo fez melhor do que as práticas normais?&quot;

## Teste de criações em destinos {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Use [!UICONTROL Audience Lab] para medir o número de conversões que um anúncio está conduzindo em destinos diferentes. Esse caso de uso também permite medir as conversões do anúncio em relação às conversões que ocorrem naturalmente.

1. [Crie um grupo](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) de teste de segmento, selecionando o segmento para o qual deseja testar a criação como o segmento de linha de base.
1. Divida o segmento da linha de base em segmentos de teste e segmentos de controle.
1. Mapeie os segmentos de teste para os diferentes destinos que você deseja testar.
1. O segmento de controle pode ser retido e não mapeado para nenhum destino. O segmento de controle não deve ser direcionado pelo criativo de teste para definir uma linha de base de resultados para conversões que ocorrem naturalmente.
1. Especifique uma data de início e uma data de término para o teste.
1. Configure o segmento e o anúncio nos destinos.
1. A [Exibição de relatório do Audience Lab](../../features/audience-lab/audience-lab-reporting-view.md) mostrará o número de conversões que o anúncio está conduzindo pelos destinos.
1. Como você criou um segmento de controle, também pode avaliar como o criativo fez em relação às conversões que ocorrem naturalmente. Você está testando a pergunta: &quot;Esse anúncio gerou uma taxa de conversão mais alta do que as práticas normais?&quot;
