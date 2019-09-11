---
description: Com as Recomendações de característica, ao criar ou editar um segmento no Construtor de segmento, você recebe recomendações sobre as características adicionais que você pode incluir, semelhantes às características na regra de segmento. Adicione as características recomendadas ao segmento para aumentar o público-alvo de destino.
seo-description: Obtenha recomendações de características ao vivo à medida que você cria seus segmentos.
seo-title: Recomendações de característica
solution: Audience Manager
title: Recomendações de característica
uuid: null
translation-type: tm+mt
source-git-commit: 76adee013246c68da7ad871cef57f6ef174a239c

---


# Recomendações de característica

Obtenha recomendações de características ao vivo à medida que você cria seus segmentos.

## Demonstração de vídeo

Comece assistindo o vídeo de Características de características, em seguida, leia para obter mais informações.

>[!VIDEO](https://video.tv.adobe.com/v/26228/?captions=por_br)

## Visão geral

[!UICONTROL Trait Recommendations], com a tecnologia [!DNL Adobe Sensei], traz a ciência de dados para os fluxos de trabalho do dia a dia do Audience Manager.
With [!UICONTROL Trait Recommendations], when you build or edit a segment in [Segment Builder](segment-builder.md), you get recommendations on additional traits you can include, that are similar to the traits in the segment rule. Adicione as características recomendadas ao segmento para aumentar o público-alvo de destino.

![Visão geral das Recomendações de características](assets/trait-recommendations-overview.png)

**Em um ponto:**

* O Audience Manager mostra características originais e características de terceiros dos feeds de dados inscritos atualmente como características recomendadas.
* O Audience Manager mostra um máximo de cinquenta características semelhantes ao da regra de segmento.
* Você pode filtrar as fontes de dados a partir das quais não deseja visualizar nenhuma recomendação.
* Ao calcular similaridades, o Audience Manager considera [uuids](../../reference/ids-in-aam.md) que qualificados para a característica nos últimos 30 dias.
* Se você vir a mensagem de erro "Nenhuma característica similar encontrada. As características podem ser muito novas. ", isso significa que não havia nenhuma atividade para essa característica nos últimos 30 dias, ou o Audience Manager ainda não atualizou as recomendações para essa característica. Tente novamente em 24 horas.

## Casos de uso

Com [!UICONTROL Trait Recommendations], você pode melhorar seus fluxos de trabalho, dependendo de como usar o Audience Manager:

* Como comerciante, você pode encontrar rapidamente públicos-alvo interessados em produtos complementares com a ajuda de características semelhantes, para que você possa aumentar seu alcance.
* Se você usar o Audience Manager como editor, com [!UICONTROL Trait Recommendations], você poderá entender o comportamento do público-alvo e criar segmentos melhores para vendas de anúncios ou aquisição do usuário.

## Diferenças entre as recomendações de característica e os modelos algorítmicos

### Modelos algorítmicos

[!UICONTROL Algorithmic Models] localizar não apenas as características mais influentes, mas também pontuar os usuários com base nessas características e atribuir a cada usuário uma pontuação individual. Em seguida, crie características algorítmicas para direcionar seus usuários. Com controles de precisão e alcance no [!UICONTROL Trait Builder], você pode especificar quais usuários entre todos os que têm as características influentes que deseja direcionar.

[!UICONTROL Algorithmic Models] permite que você selecione usuários em diferentes níveis de precisão e teste em [!UICONTROL Audience Lab] que grupo de usuários é convertido melhor. Consulte o caso de uso detalhado em [Comparar modelos no Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

No [!UICONTROL Algorithmic Models], o modelo é executado a cada 8 dias e atualiza os usuários qualificados para as características algorítmicas.

### Recomendações de característica

[!UICONTROL Trait Recommendations] é uma maneira rápida de obter insights em outras características semelhantes àqueles usados em um segmento.

Você deve usar [!UICONTROL Trait Recommendations] quando:

* Você precisa de insights rápidos ao criar um segmento;
* Você está usando os segmentos para campanhas curtas ou quando deseja suprimir rapidamente o público-alvo que converte;
* Você está tentando maximizar o alcance.

## Fluxo de trabalho

Ao criar ou editar um segmento no Construtor [de segmentos](segment-builder.md), você pode explorar características semelhantes às características na regra do segmento. O fluxo de trabalho do Construtor de segmento é muito semelhante para segmentos novos e existentes:

### Novos segmentos

1. Em **Dados de público-alvo &gt; Segmentos**, selecione **Adicionar novo**.
2. Na caixa suspensa **Características** , adicione pelo menos uma característica à regra do segmento.
3. Agora é possível ver características recomendadas que são semelhantes às características adicionadas à regra do segmento. Role para baixo para ver todas as características recomendadas.
4. (Opcional) Para excluir características recomendadas de determinadas fontes de dados, clique no **símbolo X** para as fontes de dados que deseja excluir.
   > [!NOTE]
   > 
   >As fontes de dados excluídas são mostradas logo acima da lista de características recomendadas. Pressione **X** na caixa cinza para remover as exclusões e ver os resultados das fontes de dados respectivas novamente.
5. Para adicionar características recomendadas à regra de segmento, clique no **símbolo +** .

### Segmentos existentes

1. Vá **[!UICONTROL Audience Data]para &gt;[!UICONTROL Segments]**, selecione o segmento que deseja editar e pressione ![Editar](assets/edit-button.png).
1. Role para baixo até a [!UICONTROL Traits] caixa suspensa.
1. Você pode ver características recomendadas, que são semelhantes às características já presentes na regra do segmento. Role para baixo para ver todas as características recomendadas.
1. (Opcional) Para excluir características recomendadas de determinadas fontes de dados, clique no **símbolo X** para as fontes de dados que deseja excluir.
   > [!NOTE]
   > 
   >As fontes de dados excluídas são mostradas logo acima da lista de características recomendadas. Pressione **X** na caixa cinza para remover as exclusões e ver os resultados das fontes de dados respectivas novamente.
1. Para adicionar características recomendadas à regra de segmento, clique no **símbolo +** .

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

Clicar em um traço abre uma janela pop-up, como mostrado na imagem abaixo. Se os traços recomendados não fizerem parte do segmento, você pode adicioná-los ao segmento pressionando **+**.

![](assets/add_to_segments.png)

> [!TIP]
>
>As fontes de dados excluídas da página principal são consideradas ao gerar recomendações na janela pop-up de informações de características. E, se você excluir fontes de dados nesta exibição, as exclusões serão aplicadas à página principal.

> [!NOTE]
>
> Os traços recomendados podem ser características originais ou características de terceiros de feeds aos quais você está inscrito.

## Como funciona

Para produzir recomendações de características, o Audience Manager calcula a semelhança [do Jaccard](https://en.wikipedia.org/wiki/Jaccard_index) entre a característica de destino e cada outra característica à qual sua conta tem acesso, incluindo dados de terceiros. O Audience Manager exibe até cinquenta características que têm a maior similaridade.

## Pontuação de semelhança característica

O Audience Manager calcula a [!UICONTROL Trait Similarity Score] entre duas características ao calcular a interseção e a união em termos do número de [!UICONTROL UUID]s e dividir os dois. Para duas características A e B, o cálculo é semelhante a:

![](assets/jaccard_similarity.png)

Consulte também os dois exemplos abaixo.

### Exemplo 1 - Pontuação de semelhança de característica baixa

Considerando duas características A e B, considere que cada uma das características tem uma população de 1,000,000 [!UICONTROL UUID]s, 25,000 [!UICONTROL UUID]s das quais se qualificam para ambas as características.
Usando a fórmula acima, isso resultará em: 25,000/1,975,000 = 0.012. Isso é baixo [!UICONTROL Trait Similarity Score], as duas características são muito diferentes.

![](assets/Trait-Recommendations-Low-overlap.png)

### Exemplo 2 - Pontuação de semelhança característica

Se as mesmas características A e B possuírem 400,000 [!UICONTRL uuids]que se qualificam para ambas as características, o [!UICONTROL Trait Similarity Score] é muito maior:
400,000/1,600,000 = 0.25

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

Para empresas que usam [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), é necessário ter permissão para criar e editar segmentos para ver os traços recomendados. E, as características recomendadas que você vê são apenas aquelas das fontes de dados a que você tem acesso. [!UICONTROL RBAC] Leia mais sobre [!UICONTROL RBAC] controles [aqui](../administration/administration-overview.md).

## Limitações

* Atualmente, o Audience Manager não mostra características de pastas como características recomendadas. Leia mais sobre as características de pastas [aqui](../traits/manage-folder-traits.md).
* Ao exibir o Recommendations Recommendations, o Audience Manager não leva em conta [!DNL Boolean] operadores ([!DNL AND][!DNL OR], [!DNL NOT]) nas regras do segmento.