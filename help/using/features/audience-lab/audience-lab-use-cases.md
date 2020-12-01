---
description: O Laboratório de audiências permite vários casos de uso, permitindo que você use segmentos de linha de base para criar grupos de teste. É possível dividir os grupos de teste em vários segmentos de teste mutuamente exclusivos, mapeá-los para destinos diferentes e determinar quais dos segmentos são mais eficazes para gerar conversões.
seo-description: O Laboratório de audiências permite vários casos de uso, permitindo que você use segmentos de linha de base para criar grupos de teste. É possível dividir os grupos de teste em vários segmentos de teste mutuamente exclusivos, mapeá-los para destinos diferentes e determinar quais dos segmentos são mais eficazes para gerar conversões.
seo-title: Casos de uso do Audience Lab
solution: Audience Manager
title: Casos de uso do Audience Lab
topic: DIL API
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 1%

---


# Casos de uso do Audience Lab {#audience-lab-use-cases}

[!UICONTROL Audience Lab] permite vários casos de uso, permitindo que você use segmentos de linha de base para criar grupos de teste. É possível dividir os grupos de teste em vários segmentos de teste mutuamente exclusivos, mapeá-los para destinos diferentes e determinar quais dos segmentos são mais eficazes para gerar conversões.

## Comparar modelos no Audiência Lab {#compare-models}

Você pode usar vários tipos e fontes diferentes de modelos em [!DNL Audience Manager]. [!UICONTROL Audience Lab] ofertas são uma maneira fácil de comparar as taxas de conversão de seus clientes, em seus modelos ativos.

<!-- audience-lab-compare-models.xml -->

Neste caso de uso, você está comparando diferentes modelos. Você pode usar modelos criados por meio de um data warehouse interno e importá-los em [!DNL Audience Manager] como [Características integradas](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) ou usar o recurso [Modelos algorítmicos](../../features/algorithmic-models/understanding-models.md) em [!DNL Audience Manager].

1. Crie dois modelos, no [Construtor de modelos](../../features/algorithmic-models/create-model.md) ou por meio de uma plataforma externa.
1. Crie [características algorítmicas](../../features/traits/create-algorithmic-traits.md) a partir do modelo algorítmico ou importe seus próprios modelos como características integradas.
1. Crie segmentos mutuamente exclusivos para que os usuários em ambos os modelos não se sobreponham:

   * Crie um *Segmento do Modelo 1* e um *Segmento do Modelo 2*.
   * Tenha a regra de segmento para *Modelo 1 Segmento* ser modelo 1 característica [!DNL AND NOT] modelo 2 característica, e vice-versa para *Modelo 2 Segmento*.

1. [Crie dois ](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) grupos de teste de segmento  [!UICONTROL Audience Lab], um com o  *Modelo 1* Segmentado como linha de base e outro com o  *Modelo 2* Segmentos como linha de base.

   * Mantenha as variáveis iguais para ambos os grupos de teste: os mesmos destinos, características criativas e de conversão.
   * Certifique-se de que os segmentos de teste tenham números semelhantes de usuários (por exemplo, 1,6 milhão e 1,8 milhão está certo, 1,6 milhão e 16 milhões não).
   * Reservar um segmento de controle em cada grupo de teste de segmento de teste. Dessa forma, você pode reservar uma pequena parte de cada segmento e não público alvo explicitamente no teste.

1. Examine os resultados:

   * A visualização de relatórios [Audiência Lab](../../features/audience-lab/audience-lab-reporting-view.md) mostrará o número de conversões que cada modelo está acionando. Para campanhas baseadas em conversão, o segmento de teste que direciona a maioria das conversões significa o modelo que tem melhor desempenho.
   * Como você tem segmentos de controle, também é possível avaliar como o modelo funcionou em relação à &quot;definição de metas padrão&quot;. Vocês não estão apenas testando um modelo versus o outro, mas também a questão de &quot;este modelo fez melhor do que as práticas normais?&quot;

## Testando criativos em destinos {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Use [!UICONTROL Audience Lab] para medir o número de conversões que um anúncio está conduzindo para diferentes destinos. Esse caso de uso também permite medir as conversões do anúncio em relação às conversões que ocorrem naturalmente.

1. [Crie um grupo](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) de teste de segmento, selecionando o segmento para o qual deseja testar o anúncio como o segmento de linha de base.
1. Dividir o segmento da linha de base em segmentos de teste e controle.
1. Mapeie os segmentos de teste para os diferentes destinos que você deseja testar.
1. O segmento de controle pode ser retido e não mapeado para nenhum destino. O segmento de controle não deve ser direcionado pelo criativo de teste para definir uma linha de base de resultados para conversões que ocorrem naturalmente.
1. Especifique uma data de start e uma data de término para o teste.
1. Configure o segmento e o anúncio nos destinos.
1. A visualização [relatórios do Laboratório de Audiências](../../features/audience-lab/audience-lab-reporting-view.md) mostrará o número de conversões que o creative está conduzindo pelos destinos.
1. Como você criou um segmento de controle, também é possível avaliar como o anúncio fez em relação às conversões que ocorrem naturalmente. Você está testando a pergunta: &quot;Esse criativo gerou uma taxa de conversão maior do que as práticas normais?&quot;
