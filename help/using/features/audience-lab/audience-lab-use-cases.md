---
description: O Audience Lab permite vários casos de uso, permitindo que você use segmentos de linha de base para criar grupos de teste. Você pode dividir grupos de teste em vários segmentos de teste mutuamente exclusivos, mapeá-los para destinos diferentes e determinar quais dos segmentos são mais eficazes em gerar conversões.
seo-description: Audience Lab enables several use cases by allowing you to use baseline segments for creating test groups. You can divide test groups into several mutually exclusive test segments, map these to different destinations and then determine which of the segments are most effective in driving conversions.
seo-title: Audience Lab Use Cases
solution: Audience Manager
title: Casos de uso do Audience Lab
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
exl-id: b68f48bd-0d5d-4b72-84f3-a6f3acea6c49
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---

# Casos de uso do Audience Lab {#audience-lab-use-cases}

O [!UICONTROL Audience Lab] habilita vários casos de uso permitindo que você use segmentos de linha de base para criar grupos de teste. Você pode dividir grupos de teste em vários segmentos de teste mutuamente exclusivos, mapeá-los para destinos diferentes e determinar quais dos segmentos são mais eficazes em gerar conversões.

## Comparar modelos no Audience Lab {#compare-models}

Você pode usar vários tipos e fontes diferentes de modelos no [!DNL Audience Manager]. O [!UICONTROL Audience Lab] oferece uma maneira fácil de comparar as taxas de conversão dos seus clientes com os seus modelos ativos.

<!-- audience-lab-compare-models.xml -->

Nesse caso de uso, você está comparando modelos diferentes. Você pode usar modelos criados por um data warehouse interno e importá-los em [!DNL Audience Manager] como [Características integradas](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) ou usar o recurso [Modelos algorítmicos](../../features/algorithmic-models/understanding-models.md) no [!DNL Audience Manager].

1. Crie dois modelos, no [Construtor de Modelos](../../features/algorithmic-models/create-model.md) ou por meio de uma plataforma externa.
1. Crie [características algorítmicas](../../features/traits/create-algorithmic-traits.md) a partir do modelo algorítmico ou importe seus próprios modelos como características integradas.
1. Crie segmentos mutuamente exclusivos para que os usuários em ambos os modelos não se sobreponham:

   * Crie um *Segmento do Modelo 1* e um *Segmento do Modelo 2*.
   * Faça com que a regra de segmento para *Modelo 1 Segmento* seja característica do modelo 1 característica [!DNL AND NOT] modelo 2 e vice-versa para *Modelo 2 Segmento*.

1. [Criar dois grupos de teste de segmento](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) em [!UICONTROL Audience Lab], um com *Segmento do Modelo 1* como linha de base e o outro com *Segmento do Modelo 2* como linha de base.

   * Mantenha as variáveis as mesmas para ambos os grupos de teste: mesmos destinos, características criativas e de conversão.
   * Verifique se os segmentos de teste têm números semelhantes de usuários (por exemplo, 1,6 milhão e 1,8 milhão estão corretos, 1,6 milhão e 16 milhão não).
   * Reserve um segmento de controle em cada grupo de teste de segmento de teste. Dessa forma, é possível separar uma pequena parte de cada segmento e não direcioná-los explicitamente no teste.

1. Examine os resultados:

   * A [exibição de relatórios do Audience Lab](../../features/audience-lab/audience-lab-reporting-view.md) mostrará o número de conversões que cada modelo está conduzindo. Para campanhas baseadas em conversão, o segmento de teste que direciona mais conversões indicará o modelo com melhor desempenho.
   * Como você tem segmentos de controle, também é possível avaliar o desempenho do modelo em relação ao &quot;direcionamento padrão&quot;. Você não está apenas testando um modelo em relação ao outro, mas testando a questão de &quot;esse modelo teve um desempenho melhor do que as práticas normais?&quot;

## Teste de criações em destinos {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Use o [!UICONTROL Audience Lab] para medir o número de conversões que um criativo está conduzindo em diferentes destinos. Esse caso de uso também permite medir as conversões do criativo em relação às conversões que ocorrem naturalmente.

1. [Crie um Grupo de teste de segmento](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups), selecionando o segmento no qual deseja testar a criação como o segmento de linha de base.
1. Divida o segmento da linha de base em segmentos de teste e segmentos de controle.
1. Mapeie os segmentos de teste para os diferentes destinos que deseja testar.
1. O segmento de controle pode ser retido e não mapeado para nenhum destino. O segmento de controle não deve ser direcionado pelo criativo de teste para definir uma linha de base de resultados para conversões que ocorrem naturalmente.
1. Especifique uma data de início e uma data de término para o teste.
1. Configure o segmento e o criativo nos destinos.
1. A [exibição de relatórios do Audience Lab](../../features/audience-lab/audience-lab-reporting-view.md) mostrará o número de conversões que a criação está conduzindo nos destinos.
1. Como você criou um segmento de controle, também é possível avaliar como a criação ocorreu em relação às conversões que ocorrem naturalmente. Você está testando a pergunta: &quot;Esse criativo gerou uma taxa de conversão mais alta do que as práticas normais?&quot;
