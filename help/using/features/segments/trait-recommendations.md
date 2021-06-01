---
description: Com as Recomendações de característica, ao criar ou editar um segmento no Construtor de segmento, você recebe recomendações sobre as características adicionais que você pode incluir, semelhantes às características na regra de segmento. Adicione as características recomendadas ao segmento para aumentar o público-alvo de destino.
seo-description: Obtenha recomendações de características ao vivo à medida que você constrói seus segmentos.
seo-title: Recomendações de característica
solution: Audience Manager
title: Recomendações de característica
feature: 'Segmentos '
exl-id: 7ef862a9-7354-49fb-9af0-925d827a5165
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1574'
ht-degree: 8%

---

# Recomendações de característica

Obtenha recomendações de características ao vivo enquanto cria seus segmentos, a partir de suas próprias características originais e [!UICONTROL Audience Marketplace] feeds de dados.

## Demonstração de vídeo

Comece assistindo ao vídeo [!UICONTROL Trait Recommendations] abaixo e leia para obter mais informações. A demonstração em vídeo mostra como trabalhar com recomendações de suas próprias características originais, bem como com recomendações de características de [!UICONTROL Audience Marketplace] feeds de dados que *você já está inscrito em*.

>[!VIDEO](https://video.tv.adobe.com/v/26228/)

O próximo vídeo descreve o fluxo de trabalho de [!UICONTROL Marketplace Recommendations], mostrando como adicionar características aos seus segmentos, com base nas recomendações dos feeds de dados em [!UICONTROL Audience Marketplace]. Essas recomendações são baseadas em feeds de dados que *você não está inscrito em*.

>[!VIDEO](https://video.tv.adobe.com/v/29363/)

## Visão geral

[!UICONTROL Trait Recommendations]O , desenvolvido pelo  [!DNL Adobe Sensei], traz a ciência de dados para seus fluxos de trabalho Audience Manager.
Com [!UICONTROL Trait Recommendations], ao criar ou editar um segmento no [Construtor de segmento](segment-builder.md), você recebe recomendações sobre as características adicionais que você pode incluir, semelhantes às características na regra de segmento.

O Audience Manager mostra as recomendações de características tanto das características originais como na seção **[!UICONTROL Recommendations]** e de **[!UICONTROL Audience Marketplace]**, na seção **[!UICONTROL Recommendations from Marketplace]**.

Adicione as características recomendadas ao segmento para aumentar o público-alvo de destino.

![Visão geral do Trait Recommendations](assets/trait-recommendations-overview-full.png)

**Em poucas palavras:**

* O Audience Manager mostra características originais na seção [!UICONTROL Recommendations]. As recomendações do Marketplace de feeds públicos e privados para os quais você não está inscrito estão visíveis na seção [!UICONTROL Recommendations from Marketplace]. Clique no nome do feed para ir até [!UICONTROL Audience Marketplace] e assinar.
* O Audience Manager mostra no máximo cinquenta características semelhantes à da regra de segmento.
* Você pode filtrar as fontes de dados das quais não deseja ver nenhuma recomendação.
* Ao calcular semelhanças, o Audience Manager considera [UUIDs](../../reference/ids-in-aam.md) que se qualificaram para a característica nos últimos 30 dias.
* Se você vir a mensagem de erro &quot;Nenhuma característica semelhante foi encontrada. As características podem ser muito novas.&quot;, isso significa que não houve atividade para essa característica nos últimos 30 dias ou o Audience Manager ainda não atualizou as recomendações para essa característica. Tente novamente em 24 horas.

## Casos de uso

Com [!UICONTROL Trait Recommendations], você pode melhorar seus fluxos de trabalho, dependendo de como você usa o Audience Manager:

* Como comerciante, você pode encontrar rapidamente públicos-alvo interessados em produtos complementares com a ajuda de características semelhantes, para que possa aumentar seu alcance.
* Se você usa o Audience Manager como editor, com [!UICONTROL Trait Recommendations], é possível entender o comportamento do público-alvo e criar segmentos melhores para vendas de anúncios ou aquisição de usuários.
* Como um [!UICONTROL Audience Marketplace] comprador de dados, desejo descobrir dados de terceiros relevantes sem navegar por um grande número de feeds.
* Como provedor de dados [!UICONTROL Audience Marketplace], desejo recomendar dados relevantes aos compradores para que eu possa me beneficiar das subscrições ideais e relevantes.

## Diferenças entre a Recommendations de características e os modelos algorítmicos

### Modelos algorítmicos

[!UICONTROL Algorithmic Models] não só encontra as características mais influentes, como também pontua os usuários com base nessas características e atribui a cada usuário uma pontuação individual. Em seguida, você cria características algorítmicas para direcionar os usuários. Com controles de precisão e alcance no [!UICONTROL Trait Builder], você pode especificar quais usuários entre todos aqueles que têm as características influentes você deseja direcionar.

[!UICONTROL Algorithmic Models] permite que você selecione usuários em diferentes níveis de precisão e teste em  [!UICONTROL Audience Lab] que grupo de usuários converte melhor. Consulte o caso de uso detalhado em [Comparar modelos no Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

Em [!UICONTROL Algorithmic Models], o modelo é executado a cada 8 dias e atualiza os usuários qualificados para características algorítmicas.

### Recomendações de característica

[!UICONTROL Trait Recommendations] é uma maneira rápida de obter insights sobre outras características semelhantes àquelas que você está usando em um segmento.

Você deve usar [!UICONTROL Trait Recommendations] quando:

* Precisar de insights rápidos ao criar um segmento;
* Estiver usando os segmentos para campanhas curtas ou quando deseja suprimir rapidamente o público-alvo que converte;
* Estiver tentando maximizar o alcance.

## Fluxo de trabalho

Ao criar ou editar um segmento no [Construtor de segmentos](segment-builder.md), você pode explorar características semelhantes às características na regra de segmento. O fluxo de trabalho do [Construtor de segmentos](segment-builder.md) é muito semelhante para segmentos novos e existentes:

### Novos segmentos

1. Vá para **Dados do público-alvo > Segmentos** e clique em **Adicionar novo**.
1. Na caixa suspensa **Traits** , adicione pelo menos uma característica à regra de segmento.
1. Você pode ver características recomendadas e [!UICONTROL Audience Marketplace] recomendações de características próprias dos feeds aos quais você está inscrito, na seção **[!UICONTROL Recommendations]**. A seção **[!UICONTROL Recommendations from Marketplace]** mostra as recomendações de características dos feeds aos quais você não está inscrito. Todas essas recomendações são semelhantes às características adicionadas à regra de segmento. Role para baixo para ver todas as características recomendadas.
1. (Opcional) Para excluir características primárias recomendadas de determinadas fontes de dados, clique no símbolo **X** das fontes de dados que deseja excluir.

   >[!NOTE]
   >
   >As fontes de dados excluídas são mostradas logo acima da lista de características recomendadas. Clique em **X** na caixa cinza para remover as exclusões e ver os resultados das respectivas fontes de dados novamente.
1. Para adicionar características recomendadas à regra de segmento, clique no símbolo **+**.

>[!IMPORTANT]
>
>Ao adicionar [!UICONTROL Marketplace] características a um segmento, as características são usadas somente para estimativa de segmento, até que você se inscreva no feed de dados correspondente. As características que vêm dos feeds de dados para os quais você não se inscreveu são marcadas com um ícone de carrinho de compras na lista de características. Clique no nome da característica para ir até a página do feed de dados e assinar.
>
>![marketplace-not subscribed](assets/trait-recommendations-marketplace.png)
>
>É possível salvar um segmento com características de terceiros somente depois de assinar os feeds de dados correspondentes.

### Segmentos existentes

1. Vá para **[!UICONTROL Audience Data]>[!UICONTROL Segments]**, selecione o segmento que deseja editar e clique em ![Editar](assets/edit-button.png).
1. Role para baixo até a caixa suspensa [!UICONTROL Traits].
1. É possível ver características recomendadas, semelhantes às características já presentes na regra de segmento. Role para baixo para ver todas as características recomendadas.
1. (Opcional) Para excluir características recomendadas de determinadas fontes de dados, clique no símbolo **X** das fontes de dados que deseja excluir.

   >[!NOTE]
   >
   >As fontes de dados excluídas são mostradas logo acima da lista de características recomendadas. Clique em **X** na caixa cinza para remover as exclusões e ver os resultados das respectivas fontes de dados novamente.
1. Para adicionar características recomendadas à regra de segmento, clique no símbolo **+**.

Ao criar ou editar um segmento e adicionar uma característica à regra de segmento, você vê no máximo cinquenta características recomendadas, semelhantes às adicionadas. Se a regra de segmento contiver mais de uma característica, o Audience Manager usará um método round robin para mostrar a melhor correspondência para cada característica, em seguida, a segunda melhor correspondência para cada característica e assim por diante, para as maiores cinquenta características por população, na regra de segmento.

![Três características básicas](assets/three-base-traits.png)

Por exemplo, quando há três características na regra de segmento, como mostrado abaixo, as características recomendadas são:

1. Melhor correspondência para a característica 3 (a característica com a maior população);
1. Melhor correspondência para a característica 1;
1. Melhor correspondência para a característica 2;
1. Segunda melhor correspondência para a característica 3;
1. A segunda melhor correspondência para a característica 1, e assim por diante, até atingir cinquenta características.

Para obter recomendações para uma característica específica, você pode clicar nas características na regra de segmento (1) ou na visualização de características recomendadas (2).

![exemplo de base de características](assets/three-base-traits-numbered.png)

Clicar em uma característica própria abre uma janela pop-up, como mostrado na imagem abaixo. Se as características recomendadas não fizerem parte do segmento, você poderá adicioná-las ao segmento pressionando **+**.

![adicionar a um segmento](assets/add_to_segments.png)

>[!TIP]
>
>As fontes de dados excluídas da página principal são consideradas ao gerar recomendações na janela pop-up de informações de características. E, se você excluir fontes de dados nessa visualização, as exclusões se aplicam à página principal.

>[!NOTE]
>
>As características recomendadas podem ser suas características originais ou características de terceiros dos feeds de dados aos quais você está inscrito em [!UICONTROL Audience Marketplace].

## Como funciona

Para produzir recomendações de características, o Audience Manager calcula a [semelhança do cartão Jaccard](https://en.wikipedia.org/wiki/Jaccard_index) entre a característica de destino e todas as outras características às quais a sua conta tem acesso, incluindo dados de terceiros. Audience Manager exibe até cinquenta características que têm a maior similaridade.

## Pontuação de similaridade de característica {#trait-similarity-score}

O Audience Manager calcula o [!UICONTROL Trait Similarity Score] entre duas características calculando a interseção e união em termos do número de [!UICONTROL UUID]s e depois divide as duas. Para duas características A e B, o cálculo tem a seguinte aparência:

![semelhança de cartão de acesso](assets/jaccard_similarity.png)

Veja também os dois exemplos abaixo.

### Exemplo 1 - Pontuação de similaridade de característica baixa

Dadas as duas características A e B, digamos que cada uma das características tenha uma população de 1.000.000 [!UICONTROL UUID]s, 25.000 [!UICONTROL UUID]s das quais se qualificam para ambas as características.
Usando a fórmula acima, isso resultará em: 25.000 / 1.975.000 = 0.012. Esta é uma [!UICONTROL Trait Similarity Score] baixa, as duas características são muito diferentes.

![trait-recommendations-low-overlap](assets/Trait-Recommendations-Low-overlap.png)

### Exemplo 2 - Pontuação de similaridade de característica

Se as mesmas características A e B tiverem 400.000 [!UICONTROL UUID]s que se qualificam para ambas as características, [!UICONTROL Trait Similarity Score] será muito maior:
400.000 / 1.600.000 = 0,25

![trait-recommendations-high-overlap](assets/Trait-Recommendations-High-overlap.png)

### Como interpretar a pontuação de similaridade de característica

Use a tabela abaixo como um guia detalhado para traçar similaridade. Este guia é baseado nas pontuações de similaridade observadas na maioria das características.

| [!UICONTROL Trait Similarity Score] | Significância |
---------|----------|
| 0.1 e superior | Alta semelhança entre características |
| 0.03 - 0.1 | Similaridade média entre características |
| 0.01 - 0.03 | Baixa semelhança entre características |
| 0 - 0,01 | Similaridade muito baixa entre características |

## Controle de acesso com base em função (RBAC)

Para empresas que usam [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), você precisa ter permissão para criar e editar segmentos para ver as características recomendadas. As recomendações de características que você vê são apenas aquelas de fontes de dados às quais você tem acesso por meio de [!UICONTROL RBAC].

>[!IMPORTANT]
>
>Para adicionar [!UICONTROL Marketplace Recommendations] a um segmento, os usuários devem primeiro assinar os feeds de dados correspondentes. Somente usuários com privilégios de administrador podem assinar feeds de dados [!UICONTROL Audience Marketplace].

Leia mais sobre [!UICONTROL RBAC] controles [aqui](../administration/administration-overview.md).

## Limitações

* Atualmente, o Audience Manager não mostra as características da pasta como características recomendadas. Leia mais sobre as características da pasta [aqui](../traits/manage-folder-traits.md).
* Ao exibir o Trait Recommendations, o Audience Manager não leva em conta os operadores [!DNL Boolean] ([!DNL AND], [!DNL OR], [!DNL NOT]) nas regras do segmento.
