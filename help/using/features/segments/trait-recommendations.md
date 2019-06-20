---
description: Com as Recomendações de característica, ao criar ou editar um segmento no Construtor de segmento, você recebe recomendações sobre as características adicionais que você pode incluir, semelhantes às características na regra de segmento. Adicione as características recomendadas ao segmento para aumentar o público-alvo de destino.
seo-description: Obtenha recomendações de características ao vivo à medida que você cria seus segmentos.
seo-title: Recomendações de característica
solution: Audience Manager
title: Recomendações de característica
uuid: null
translation-type: tm+mt
source-git-commit: e369038fbc83e28d10da24060699488faf783511

---


# Recomendações de característica

Obtenha recomendações de características ao vivo à medida que você cria seus segmentos.

## Visão geral

[!UICONTROL Trait Recommendations], com a tecnologia [!DNL Adobe Sensei], traz a ciência de dados para os fluxos de trabalho do dia a dia do Audience Manager.
With [!UICONTROL Trait Recommendations], when you build or edit a segment in [Segment Builder](segment-builder.md), you get recommendations on additional traits you can include, that are similar to the traits in the segment rule. Adicione as características recomendadas ao segmento para aumentar o público-alvo de destino.

![Visão geral das Recomendações de características](assets/trait-recommendations-overview.png)

**Em um ponto:**

* O Audience Manager mostra características originais e características de terceiros dos feeds de dados inscritos atualmente como características recomendadas.
* O Audience Manager mostra um máximo de cinquenta características semelhantes ao da regra de segmento.
* Você pode filtrar as fontes de dados a partir das quais não deseja visualizar nenhuma recomendação.
* When calculating similarities, Audience Manager considers [UUIDs](../../reference/ids-in-aam.md) that qualified for the trait during the last 30 days.
* Se você vir a mensagem de erro &quot;Nenhuma característica similar encontrada. As características podem ser muito novas. &quot;, isso significa que não havia nenhuma atividade para essa característica nos últimos 30 dias, ou o Audience Manager ainda não atualizou as recomendações para essa característica. Tente novamente em 24 horas.

## Casos de uso

With [!UICONTROL Trait Recommendations], you can improve your workflows, depending on how you use Audience Manager:

* Como comerciante, você pode encontrar rapidamente públicos-alvo interessados em produtos complementares com a ajuda de características semelhantes, para que você possa aumentar seu alcance.
* If you use Audience Manager as a publisher, with [!UICONTROL Trait Recommendations], you can understand audience behavior and build better segments for ad sales or user acquisition.

## Diferenças entre as recomendações de característica e os modelos algorítmicos

### Modelos algorítmicos

[!UICONTROL Algorithmic Models] localizar não apenas as características mais influentes, mas também pontuar os usuários com base nessas características e atribuir a cada usuário uma pontuação individual. Em seguida, crie características algorítmicas para direcionar seus usuários. With accuracy and reach controls in the [!UICONTROL Trait Builder], you can specify which users amongst all those who have the influential traits you want to target.

[!UICONTROL Algorithmic Models] permite que você selecione usuários em diferentes níveis de precisão e teste em [!UICONTROL Audience Lab] que grupo de usuários é convertido melhor. See the detailed use case in [Compare Models in Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

In [!UICONTROL Algorithmic Models], the model runs every 8 days and refreshes the users qualified for algorithmic traits.

### Recomendações de característica

[!UICONTROL Trait Recommendations] é uma maneira rápida de obter insights em outras características semelhantes àqueles usados em um segmento.

You should use [!UICONTROL Trait Recommendations] when:

* Você precisa de insights rápidos ao criar um segmento;
* Você está usando os segmentos para campanhas curtas ou quando deseja suprimir rapidamente o público-alvo que converte;
* Você está tentando maximizar o alcance.

## Fluxo de trabalho

When building or editing a segment in [Segment Builder](segment-builder.md), you can explore traits similar to the traits in the segment rule. O fluxo de trabalho do Construtor de segmento é muito semelhante para segmentos novos e existentes:

### Novos segmentos

1. In **Audience Data &gt; Segments**, select **Add New**.
1. In the **Traits** drop-down box, add at least one trait to the segment rule.
1. Agora é possível ver características recomendadas que são semelhantes às características adicionadas à regra do segmento. Role para baixo para ver todas as características recomendadas.
1. (Optional) To exclude recommended traits from certain data sources, click the **X** symbol for the data sources you want to exclude.
   > [!NOTE]
   > 
   >As fontes de dados excluídas são mostradas logo acima da lista de características recomendadas. Press **X** in the grey box to remove the exclusions and see results from the respective data sources again.
1. To add recommended traits to the segment rule, click the **+** symbol.

### Segmentos existentes

1. Go to **[!UICONTROL Audience Data]&gt;[!UICONTROL Segments]**, select the segment you want to edit and press ![Edit](assets/edit-button.png).
1. Scroll down to the [!UICONTROL Traits] drop-down box.
1. Você pode ver características recomendadas, que são semelhantes às características já presentes na regra do segmento. Role para baixo para ver todas as características recomendadas.
1. (Optional) To exclude recommended traits from certain data sources, click the **X** symbol for the data sources you want to exclude.
   > [!NOTE]
   > 
   >As fontes de dados excluídas são mostradas logo acima da lista de características recomendadas. Press **X** in the grey box to remove the exclusions and see results from the respective data sources again.
1. To add recommended traits to the segment rule, click the **+** symbol.

Ao criar ou editar um segmento e adicionar uma característica à regra de segmento, você verá um máximo de cinquenta características recomendadas, semelhante àquela adicionada. Se a regra de segmento contiver mais de uma característica, o Audience Manager usa um método redondo para mostrar a melhor correspondência para cada característica, e então a segunda melhor correspondência para cada característica, e assim por diante, para as maiores cinquenta características por população, na regra do segmento.

![Três características base](assets/three-base-traits.png)

Por exemplo, quando há três características na regra de segmento, como mostrado abaixo, as características recomendadas são:

1. Melhor correspondência para característica 3 (a característica com a maior população);
2. Melhor correspondência para característica 1;
3. Melhor correspondência para característica 2;
4. A segunda melhor correspondência para característica 3;
5. A segunda melhor correspondência para características 1, e assim por diante até que você chegue até cinquenta características.

Para obter recomendações para uma característica específica, clique nas características da regra de segmento (1) ou nas exibições recomendadas (2).

![](assets/three-base-traits-numbered.png)

Clicar em um traço abre uma janela pop-up, como mostrado na imagem abaixo. If the recommended traits are not part of the segment, you can add them to the segment by pressing **+**.

![](assets/add_to_segments.png)

> [!TIP]
>
>As fontes de dados excluídas da página principal são consideradas ao gerar recomendações na janela pop-up de informações de características. E, se você excluir fontes de dados nesta exibição, as exclusões serão aplicadas à página principal.

> [!NOTE]
>
> Os traços recomendados podem ser características originais ou características de terceiros de feeds aos quais você está inscrito.

## Como funciona

To produce trait recommendations, Audience Manager computes the [Jaccard similarity](https://en.wikipedia.org/wiki/Jaccard_index) between the target trait and every other trait that your account has access to, including third-party data. O Audience Manager exibe até cinquenta características que têm a maior similaridade.

## Pontuação de semelhança característica

Audience Manager calculate the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL UUID]s and then divide the two. Para duas características A e B, o cálculo é semelhante a:

![](assets/jaccard_similarity.png)

Consulte também os dois exemplos abaixo.

### Exemplo 1 - Pontuação de semelhança de característica baixa

Given two traits A and B, let&#39;s say each of the traits has a population of 1,000,000 [!UICONTROL UUID]s, 25,000 [!UICONTROL UUID]s of which qualify for both traits.
Using the formula above, this will result in: 25,000 / 1,975,000 = 0.012. This is a low [!UICONTROL Trait Similarity Score], the two traits are very dissimilar.

![](assets/Trait-Recommendations-Low-overlap.png)

### Exemplo 2 - Pontuação de semelhança característica

If the same traits A and B had 400,000 [!UICONTRL UUID]s that qualify for both traits, the [!UICONTROL Trait Similarity Score] is much higher:
400,000 / 1,600,000 = 0.25

![](assets/Trait-Recommendations-High-overlap.png)

### Como interpretar a Pontuação de semelhança característica

Use a tabela abaixo como um guia aproximado para similaridade característica. Este guia baseia-se nas pontuações de similaridade observadas na maioria das características.

| [!UICONTROL Trait Similarity Score] | Significância |
---------|----------|
| 0.1 e superior | Similaridade alta entre as características |
| 0.03 - 0.1 | Similaridade média entre as características |
| 0.01 - 0.03 | Similaridade baixa entre as características |
| 0 - 0.01 | Similaridade muito baixa entre as características |

## Controle de acesso com base em funções (RBAC)

For companies using [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), you need to have permission to create and edit segments in order to see recommended traits. And, the recommended traits you see are only the ones from data sources that you have access to via [!UICONTROL RBAC]. Read more about [!UICONTROL RBAC] controls [here](../administration/administration-overview.md).

## Limitações

* Atualmente, o Audience Manager não mostra características de pastas como características recomendadas. Read more about folder traits [here](../traits/manage-folder-traits.md).
* When displaying Trait Recommendations, Audience Manager does not take into account [!DNL Boolean] operators ([!DNL AND], [!DNL OR], [!DNL NOT]) in segment rules.