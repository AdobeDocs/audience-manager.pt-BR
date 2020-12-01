---
description: Com as Recomendações de característica, ao criar ou editar um segmento no Construtor de segmento, você recebe recomendações sobre as características adicionais que você pode incluir, semelhantes às características na regra de segmento. Adicione as características recomendadas ao segmento para aumentar o público-alvo de destino.
seo-description: Obtenha recomendações de características ao vivo conforme você cria seus segmentos.
seo-title: Recomendações de característica
solution: Audience Manager
title: Recomendações de característica
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1573'
ht-degree: 8%

---


# Recomendações de característica

Obtenha recomendações de traços ao vivo à medida que você constrói seus segmentos, a partir de suas próprias características originais e [!UICONTROL Audience Marketplace] feeds de dados.

## Demonstração de vídeo

Start assistindo ao vídeo [!UICONTROL Trait Recommendations] abaixo e, em seguida, leia para obter mais informações. A demonstração em vídeo mostra como trabalhar com recomendações de suas próprias características primárias, bem como com as recomendações de características de [!UICONTROL Audience Marketplace] feeds de dados que *você já está inscrito em*.

>[!VIDEO](https://video.tv.adobe.com/v/26228/)

O próximo vídeo descreve o fluxo de trabalho para [!UICONTROL Marketplace Recommendations], mostrando como adicionar características aos seus segmentos, com base em recomendações de feeds de dados em [!UICONTROL Audience Marketplace]. Essas recomendações são baseadas em feeds de dados que *você não está inscrito em*.

>[!VIDEO](https://video.tv.adobe.com/v/29363/)

## Visão geral

[!UICONTROL Trait Recommendations], alimentado por  [!DNL Adobe Sensei], traz a ciência de dados para os workflows do Audience Manager.
Com [!UICONTROL Trait Recommendations], ao criar ou editar um segmento no [Construtor de segmentos](segment-builder.md), você obtém recomendações sobre características adicionais que podem ser incluídas, semelhantes às características na regra de segmento.

O Audience Manager mostra as recomendações de características de suas características originais, na seção **[!UICONTROL Recommendations]** e de **[!UICONTROL Audience Marketplace]**, na seção **[!UICONTROL Recommendations from Marketplace]**.

Adicione as características recomendadas ao segmento para aumentar o público-alvo de destino.

![Visão geral do Trait Recommendations](assets/trait-recommendations-overview-full.png)

**Em poucas palavras:**

* Audience Manager mostra as características principais na seção [!UICONTROL Recommendations]. As recomendações do Marketplace de feeds públicos e privados nos quais você não está inscrito estão visíveis na seção [!UICONTROL Recommendations from Marketplace]. Clique no nome do feed para ir até [!UICONTROL Audience Marketplace] e assinar.
* Audience Manager mostra no máximo cinquenta características semelhantes às da regra de segmento.
* Você pode filtrar as fontes de dados das quais não deseja ver nenhuma recomendação.
* Ao calcular semelhanças, o Audience Manager considera [UUIDs](../../reference/ids-in-aam.md) que se qualificaram para a característica nos últimos 30 dias.
* Se você vir a mensagem de erro &quot;Nenhuma característica semelhante encontrada. As características podem ser muito novas.&quot;, isso significa que ou não havia atividade para essa característica nos últimos 30 dias, ou o Audience Manager ainda não atualizou as recomendações para essa característica. Tente novamente em 24 horas.

## Casos de uso

Com [!UICONTROL Trait Recommendations], você pode melhorar seus workflows, dependendo de como usar o Audience Manager:

* Como comerciante, você pode encontrar rapidamente audiências interessadas em produtos complementares com a ajuda de características semelhantes, para que você possa aumentar seu alcance.
* Se você usar o Audience Manager como editor, com [!UICONTROL Trait Recommendations], poderá entender o comportamento da audiência e criar segmentos melhores para vendas de anúncios ou aquisição de usuários.
* Como um [!UICONTROL Audience Marketplace] comprador de dados, desejo descobrir dados relevantes de terceiros sem navegar por um grande número de feeds.
* Como provedor de dados [!UICONTROL Audience Marketplace], desejo recomendar dados relevantes aos compradores para que eu possa me beneficiar das subscrições ideais e relevantes.

## Diferenças entre os modelos Recommendations de características e algorítmicos

### Modelos algorítmicos

[!UICONTROL Algorithmic Models] não somente encontra as características mais influentes, como também pontua os usuários com base nessas características e atribui a cada usuário uma pontuação individual. Em seguida, você cria características algorítmicas para direcionar os usuários. Com controles de precisão e alcance em [!UICONTROL Trait Builder], você pode especificar quais usuários entre todos aqueles que têm as características influentes que deseja público alvo.

[!UICONTROL Algorithmic Models] permite que você selecione usuários em diferentes níveis de precisão e teste em  [!UICONTROL Audience Lab] qual grupo de usuários converte melhor. Consulte o caso de uso detalhado em [Comparar modelos no Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

Em [!UICONTROL Algorithmic Models], o modelo é executado a cada 8 dias e atualiza os usuários qualificados para características algorítmicas.

### Recomendações de característica

[!UICONTROL Trait Recommendations] é uma maneira rápida de obter insights sobre outras características que são semelhantes àquelas usadas em um segmento.

Você deve usar [!UICONTROL Trait Recommendations] quando:

* Precisar de insights rápidos ao criar um segmento;
* Estiver usando os segmentos para campanhas curtas ou quando deseja suprimir rapidamente o público-alvo que converte;
* Estiver tentando maximizar o alcance.

## Fluxo de trabalho

Ao criar ou editar um segmento no [Construtor de segmentos](segment-builder.md), você pode explorar características semelhantes às características na regra do segmento. O fluxo de trabalho [Construtor de segmentos](segment-builder.md) é muito semelhante para segmentos novos e existentes:

### Novos segmentos

1. Vá para **Dados de Audiência > Segmentos** e clique em **Adicionar novo**.
1. Na caixa suspensa **Características**, adicione pelo menos uma característica à regra do segmento.
1. Você pode ver as características recomendadas e [!UICONTROL Audience Marketplace] as recomendações de características dos feeds aos quais você está inscrito, na seção **[!UICONTROL Recommendations]**. A seção **[!UICONTROL Recommendations from Marketplace]** mostra as recomendações de características dos feeds aos quais você não está inscrito. Todas essas recomendações são semelhantes às características adicionadas à regra de segmento. Role para baixo para ver todas as características recomendadas.
1. (Opcional) Para excluir características primárias recomendadas de determinadas fontes de dados, clique no símbolo **X** das fontes de dados que deseja excluir.

   >[!NOTE]
   >
   >As fontes de dados excluídas são mostradas logo acima da lista de características recomendadas. Clique em **X** na caixa cinza para remover as exclusões e ver os resultados das respectivas fontes de dados novamente.
1. Para adicionar as características recomendadas à regra de segmento, clique no símbolo **+**.

>[!IMPORTANT]
>
>Ao adicionar [!UICONTROL Marketplace] características a um segmento, as características são usadas apenas para a estimativa do segmento, até que você assine o feed de dados correspondente. As características que vêm dos feeds de dados aos quais você não está inscrito são marcadas com um ícone de carrinho de compras na lista de características. Clique no nome da característica para acessar a página de feed de dados e inscrevê-la.
>
>![marketplace-not-subscription](assets/trait-recommendations-marketplace.png)
>
>É possível salvar um segmento com características de terceiros somente depois de assinar os feeds de dados correspondentes.

### Segmentos existentes

1. Vá para **[!UICONTROL Audience Data]>[!UICONTROL Segments]**, selecione o segmento que deseja editar e clique em ![Editar](assets/edit-button.png).
1. Role para baixo até a caixa suspensa [!UICONTROL Traits].
1. Você pode ver as características recomendadas, que são semelhantes às características que já estão na regra de segmento. Role para baixo para ver todas as características recomendadas.
1. (Opcional) Para excluir características recomendadas de determinadas fontes de dados, clique no símbolo **X** para as fontes de dados que deseja excluir.

   >[!NOTE]
   >
   >As fontes de dados excluídas são mostradas logo acima da lista de características recomendadas. Clique em **X** na caixa cinza para remover as exclusões e ver os resultados das respectivas fontes de dados novamente.
1. Para adicionar as características recomendadas à regra de segmento, clique no símbolo **+**.

Ao criar ou editar um segmento e adicionar uma característica à regra de segmento, você verá no máximo cinquenta características recomendadas, semelhantes àquelas adicionadas. Se a regra de segmento contiver mais de uma característica, o Audience Manager usará um método round robin para mostrar a melhor correspondência para cada característica, a segunda melhor correspondência para cada característica e assim por diante, para os cinquenta maiores características por população, na regra de segmento.

![Três características básicas](assets/three-base-traits.png)

Por exemplo, quando há três características na regra de segmento, como mostrado abaixo, as características recomendadas são:

1. Melhor correspondência para o traço 3 (o traço com a maior população);
1. Melhor correspondência para a característica 1;
1. Melhor correspondência para a característica 2;
1. Segunda melhor correspondência para a característica 3;
1. A segunda melhor combinação para a característica 1, e assim por diante, até que você tenha cinquenta características.

Para obter recomendações para uma característica específica, clique nas características na regra de segmento (1) ou na visualização de características recomendadas (2).

![exemplo de características básicas](assets/three-base-traits-numbered.png)

Clicar em uma característica primária abre uma janela pop-up, como mostrado na imagem abaixo. Se as características recomendadas não fizerem parte do segmento, é possível adicioná-las ao segmento pressionando **+**.

![adicionar ao segmento](assets/add_to_segments.png)

>[!TIP]
>
>As fontes de dados excluídas da página principal são consideradas ao gerar recomendações na janela pop-up de informações de características. E, se você excluir fontes de dados nessa visualização, as exclusões se aplicam à página principal.

>[!NOTE]
>
>As características recomendadas podem ser características originais ou de terceiros de feeds de dados aos quais você está inscrito em [!UICONTROL Audience Marketplace].

## Como funciona

Para produzir recomendações de características, o Audience Manager calcula a [similaridade Jaccard](https://en.wikipedia.org/wiki/Jaccard_index) entre a característica do público alvo e todas as outras características a que a sua conta tem acesso, incluindo dados de terceiros. Audience Manager exibe até cinquenta características que têm a maior similaridade.

## Pontuação de semelhança de característica {#trait-similarity-score}

Audience Manager calcula o [!UICONTROL Trait Similarity Score] entre duas características, calculando a interseção e a união em termos do número de [!UICONTROL UUID]s e dividindo as duas. Para duas características A e B, o cálculo é semelhante a:

![similaridade entre cartão de crédito](assets/jaccard_similarity.png)

Veja também os dois exemplos abaixo.

### Exemplo 1 - Pontuação de semelhança de baixa característica

Dados dois traços A e B, digamos que cada um deles tenha uma população de 1.000.000 [!UICONTROL UUID]s, 25.000 [!UICONTROL UUID]s dos quais se qualificam para ambos os traços.
Usando a fórmula acima, isso resultará em: 25.000 / 1.975.000 = 0,012. Este é um [!UICONTROL Trait Similarity Score] baixo, os dois traços são muito diferentes.

![trait-Recomendações-baixa sobreposição](assets/Trait-Recommendations-Low-overlap.png)

### Exemplo 2 - Pontuação de semelhança de característica

Se as mesmas características A e B tivessem 400.000 [!UICONTROL UUID]s que se qualificam para ambas as características, o [!UICONTROL Trait Similarity Score] é muito maior:
400.000 / 1.600.000 = 0,25

![características-recomendações-alta-sobreposição](assets/Trait-Recommendations-High-overlap.png)

### Como interpretar a pontuação de semelhança de característica

Use a tabela abaixo como um guia aproximado para traçar a semelhança. Este guia é baseado nas pontuações de similaridade observadas na maioria das características.

| [!UICONTROL Trait Similarity Score] | Significância |
---------|----------|
| 0.1 e superior | Elevada semelhança entre características |
| 0,03 - 0,1 | Semelhança média entre características |
| 0,01 - 0,03 | Baixa semelhança entre características |
| 0 - 0,01 | Semelhança muito baixa entre características |

## Controle de acesso baseado em função (RBAC)

Para empresas que usam [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), é necessário ter permissão para criar e editar segmentos para ver as características recomendadas. As recomendações de características que você vê são apenas aquelas de fontes de dados às quais você tem acesso via [!UICONTROL RBAC].

>[!IMPORTANT]
>
>Para adicionar [!UICONTROL Marketplace Recommendations] a um segmento, os usuários devem primeiro assinar os feeds de dados correspondentes. Somente os usuários com privilégios de administrador podem assinar os feeds de dados [!UICONTROL Audience Marketplace].

Leia mais sobre [!UICONTROL RBAC] controles [aqui](../administration/administration-overview.md).

## Limitações

* Atualmente, o Audience Manager não mostra as características da pasta como características recomendadas. Leia mais sobre as características da pasta [aqui](../traits/manage-folder-traits.md).
* Ao exibir o Trait Recommendations, o Audience Manager não leva em conta os operadores [!DNL Boolean] ([!DNL AND], [!DNL OR], [!DNL NOT]) nas regras de segmento.
