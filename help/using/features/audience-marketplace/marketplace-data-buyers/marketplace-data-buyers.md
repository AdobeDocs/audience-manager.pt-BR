---
description: Visão geral e fluxo de trabalho para compradores de dados que desejam comprar dados de terceiros de dentro do Audience Manager
seo-description: Visão geral e fluxo de trabalho para compradores de dados que desejam comprar dados de terceiros de dentro do Audience Manager
seo-title: Audience Marketplace para compradores de dados
solution: Audience Manager
title: Audience Marketplace para compradores de dados
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 3%

---


# [!UICONTROL Audience Marketplace] para Data Buyers {#audience-marketplace-for-data-buyers}

Visão geral e fluxo de trabalho para compradores de dados que desejam comprar dados de terceiros de dentro [!DNL Audience Manager].

>[!NOTE]
>[Permissões](../../../reporting/reports-dashboard.md) baseadas em funções controlam o acesso aos [!UICONTROL Audience Marketplace] recursos.
>
>* Os administradores podem criar feeds de dados, gerenciar assinantes e assinar feeds de dados.
>* Os usuários podem pesquisar e visualização somente nos feeds.


## A [!UICONTROL Marketplace]: About {#about-marketplace}

O recurso [!UICONTROL Marketplace] é um [!DNL Audience Manager] recurso para compradores de dados ao qual você pode assinar os feeds de dados do lista. Ele lista feeds de dados privados, [!DNL CPM]e de taxa fixa. Esses feeds são fornecidos por fornecedores terceirizados que usam [!DNL Audience Manager] para vender dados.

No [!UICONTROL Marketplace], as ferramentas de relatórios permitem rastrear o uso do feed e a sobreposição entre o feed de dados [!UICONTROL traits] e os de um feed de dados inscrito. Por fim, com [!UICONTROL Audience Marketplace], [!DNL Adobe] cuida das NFFs e dos pagamentos de taxa (embora você tenha que relatar o uso automaticamente quando estiver inscrito em um [!DNL CPM] feed). Esses recursos permitem que você encontre fontes de dados eficazes sem perder tempo procurando um provedor de dados.

>[!TIP]
>
>Use o Localizador **[de Audiências da](https://www.adobe-audience-finder.com/)**Adobe para encontrar feeds de dados de alta qualidade que você possa assinar. Em seguida, volte à interface do[!DNL Audience Manager]usuário ou use a API[do](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API)Audience Marketplace Buyer para assinar os feeds encontrados.

![comprador-mercado-visão geral](assets/buyer-marketplace-overview.png)

A [!UICONTROL Marketplace] lista contém informações que você pode classificar e pesquisar para encontrar o feed de dados certo para você. Os itens na lista do [!UICONTROL Marketplace] comprador incluem:

* **[!UICONTROL Search]**: Encontre feeds de dados por nome ou descrição de texto.
* **[!UICONTROL Similar Traits]**: Mostra o número de semelhantes [!UICONTROL traits] de um feed de dados. Essa coluna é mostrada depois que você digita um [!UICONTROL trait] ou [!UICONTROL segment] para filtrar na **[!UICONTROL Similarity To]** seção.
* **[!UICONTROL Name]**: Nome do feed de dados.
* **[!UICONTROL Description]**: Informações sobre o conteúdo de um feed de dados.
* **[!UICONTROL Provider]**: Nome do provedor de dados.
* **[!UICONTROL Traits]**: O número de [!UICONTROL traits] em um feed de dados.
* **[!UICONTROL 30 Day Provider Unique Users]**: O número de usuários únicos vistos nos últimos 30 dias.
* **[!UICONTROL 30 Day Overlapped Uniques]**: O número de usuários em sua conta que se sobrepõem aos usuários na conta do provedor.
* **[!UICONTROL Feed Overlap]**: O valor único sobreposto de 30 dias, exibido em porcentagens, calculado como: Comprador de dados: 30 dias sobrepostos únicos / Comprador de dados, 30 dias únicos) x 100.
* **[!UICONTROL Private Feeds]**: Consulte Feeds [de dados](../../../features/audience-marketplace/marketplace-private-feeds.md)privados.
* **[!UICONTROL Currently Subscribed Plan Count]**: O número de subscrições que você tem com um provedor de dados.

 

Para encontrar facilmente os melhores feeds de dados para suas necessidades, use os seguintes filtros disponíveis no lado esquerdo da [!UICONTROL Marketplace] página:

* **[!UICONTROL Similarity To]**: Filtre os feeds de dados com base na semelhança deles com um ou [!UICONTROL trait] [!UICONTROL segment] outro de sua escolha. Ao inserir o segmento ou [!UICONTROL trait] para comparar, você pode usar a ID [!UICONTROL trait] ou [!UICONTROL segment] ID, ou seus respectivos nomes.
* **[!UICONTROL Similarity Cutoff]**: Arraste o controle deslizante para filtrar os feeds de dados com base na semelhança que eles [!UICONTROL traits] têm com os feeds selecionados [!UICONTROL trait] ou [!UICONTROL segment]. Para saber mais sobre as pontuações de [!UICONTROL trait] similaridade, consulte Pontuação de [similaridade de características](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: Filtre os feeds de dados com base no status da subscrição.
* **[!UICONTROL Plan Use Case]**: Filtrar feeds de dados com base em seus casos de uso suportados: **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]** e **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Filtrar feeds de dados com base em seu tipo de preço.

## Encontrar semelhante [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] oferece a opção de localizar [!UICONTROL traits] a partir de vários feeds de dados, com base na semelhança deles com seus segmentos [!UICONTROL traits] ou segmentos existentes. Veja como fazer isso:

1. Vá até **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Use o **[!UICONTROL Similarity To]** seletor para escolher entre filtragem com base em uma [!UICONTROL trait] ou [!UICONTROL segment]. Você pode filtrar com base na [!UICONTROL trait]/[!UICONTROL segment] ID ou nome. A caixa de pesquisa mostra automaticamente sugestões relevantes com base na sua entrada.
3. Depois de identificar a característica ou o segmento pelo qual deseja filtrar, clique nele na lista de sugestões.
4. Para restringir os resultados, use o **[!UICONTROL Similarity Cutoff]** controle deslizante para mover de menos semelhantes [!UICONTROL traits]para mais semelhantes.

Quando a filtragem estiver concluída, você verá uma nova coluna na página de resultados: **[!UICONTROL Similar Traits]**. Essa coluna mostra o número de semelhante [!UICONTROL traits] ao que você filtrou, de cada feed de dados que atende aos critérios de filtragem.

Para ver a lista completa de características semelhantes, clique no número na **[!UICONTROL Similar Traits]** coluna.

>[!NOTE]
>
> O Audience Marketplace exibe os 500 principais [!UICONTROL trait] resultados semelhantes de todos os feeds de dados.

Assista ao vídeo abaixo para obter uma visão geral completa de como encontrar algo semelhante [!UICONTROL traits].

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Feeds de dados privados {#private-data-feeds}

Na [!UICONTROL Marketplace] lista, às vezes o nome e os [!UICONTROL trait] dados do provedor são marcados como privados. Isso indica um feed [de dados](../../../features/audience-marketplace/marketplace-private-feeds.md)privados. Um feed de dados privados permite que os vendedores limitem o acesso do comprador aos seus dados. Os vendedores podem tornar os feeds privados quando estão oferecendo negócios especiais, descontos ou quando privacidade e controle de acesso são importantes para eles. Como comprador, você tem que enviar uma solicitação de subscrição ao vendedor se quiser acessar um feed privado. Consulte [Assinar um feed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) de dados privados para obter detalhes.

>[!MORELIKETHIS]
>
>* [Como entender a página de detalhes do plano no Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Descontos para Data Buyers](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

