---
description: Visão geral e fluxo de trabalho para compradores de dados que desejam comprar dados de terceiros no Audience Manager
seo-description: Visão geral e fluxo de trabalho para compradores de dados que desejam comprar dados de terceiros no Audience Manager
seo-title: Audience Marketplace para Compradores de Dados
solution: Audience Manager
title: Audience Marketplace para Compradores de Dados
topic: API DIL
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
translation-type: tm+mt
source-git-commit: d9a4244f68e95c872d3686da10ee3a774250fbfe

---


# Audience Marketplace para Compradores de Dados {#audience-marketplace-for-data-buyers}

Visão geral e fluxo de trabalho para compradores de dados que desejam comprar dados de terceiros de dentro [!DNL Audience Manager].

>[!NOTE]
>[Permissões](../../../reporting/reports-dashboard.md) baseadas em funções controlam o acesso aos [!UICONTROL Audience Marketplace] recursos.
>
>* Os administradores podem criar feeds de dados, gerenciar assinantes e assinar feeds de dados.
>* Os usuários podem pesquisar e exibir somente feeds.


## O Mercado: About {#about-marketplace}

<!-- c_marketplace_about.xml -->

O [!UICONTROL Marketplace] é um [!DNL Audience Manager] recurso para compradores de dados que lista feeds de dados que você pode assinar. Ele lista feeds de dados privados, [!DNL CPM]e de taxa fixa. Esses feeds são fornecidos por fornecedores terceirizados que usam [!DNL Audience Manager] para vender dados.

No [!UICONTROL Marketplace], as ferramentas de relatório permitem rastrear o uso do feed e a sobreposição entre suas características e as de um feed de dados inscrito. Por fim, com [!UICONTROL Audience Marketplace], [!DNL Adobe] cuida das NFFs e dos pagamentos de taxa (embora você tenha que relatar o uso automaticamente quando estiver inscrito em um [!DNL CPM] feed). Esses recursos permitem que você encontre fontes de dados eficazes sem perder tempo procurando um provedor de dados.

>[!TIP]
>
>Use o **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** para encontrar feeds de dados de alta qualidade que você possa assinar. Em seguida, volte para a interface do usuário do Audience Manager ou use a API [do](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) Audience Marketplace Buyer para assinar os feeds encontrados.

![comprador-mercado-visão geral](assets/buyer-marketplace-overview.png)

A [!UICONTROL Marketplace] lista contém informações que você pode classificar e pesquisar para encontrar o feed de dados certo para você. Os itens da lista de [!UICONTROL Marketplace] compradores incluem:

* **[!UICONTROL Search]**: Encontre feeds de dados por nome ou descrição de texto.
* **[!UICONTROL Similar Traits]**: Mostra o número de características semelhantes de um feed de dados. Essa coluna é exibida depois que você insere uma característica ou segmento para filtrar na **[!UICONTROL Similarity To]** seção.
* **[!UICONTROL Name]**: Nome do feed de dados.
* **[!UICONTROL Description]**: Informações sobre o conteúdo de um feed de dados.
* **[!UICONTROL Provider]**: Nome do provedor de dados.
* **[!UICONTROL Traits]**: O número de características em um feed de dados.
* **[!UICONTROL 30 Day Provider Unique Users]**: O número de usuários únicos vistos nos últimos 30 dias.
* **[!UICONTROL 30 Day Overlapped Uniques]**: O número de usuários em sua conta que se sobrepõem aos usuários na conta do provedor.
* **[!UICONTROL Feed Overlap]**: O valor único sobreposto de 30 dias, exibido em porcentagens, calculado como: Comprador de dados: 30 dias sobrepostos únicos / Comprador de dados, 30 dias únicos) x 100.
* **[!UICONTROL Private Feeds]**: Consulte Feeds [de dados](../../../features/audience-marketplace/marketplace-private-feeds.md)privados.
* **[!UICONTROL Currently Subscribed Plan Count]**: O número de assinaturas que você tem com um provedor de dados.

Para encontrar facilmente os melhores feeds de dados para suas necessidades, use os seguintes filtros disponíveis no lado esquerdo da [!UICONTROL Marketplace] página:

* **[!UICONTROL Similarity To]**: Filtre os feeds de dados com base na semelhança deles com uma característica ou segmento de sua escolha. Ao inserir a característica ou o segmento para comparar, você pode usar a ID de característica ou segmento ou seus respectivos nomes.
* **[!UICONTROL Similarity Cutoff]**: Arraste o controle deslizante para filtrar os feeds de dados com base na semelhança entre suas características e a característica ou segmento selecionado.
* **[!UICONTROL Subscription Status]**: Filtre os feeds de dados com base no status da sua assinatura.
* **[!UICONTROL Plan Use Case]**: Filtrar feeds de dados com base em seus casos de uso suportados: **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]** e **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Filtrar feeds de dados com base em seu tipo de preço.

Assista ao vídeo abaixo para obter uma visão geral de como usar esses filtros.

## Como encontrar traços semelhantes {#finding-similar-traits}

[!UICONTROL Audience Marketplace] oferece a opção de localizar características de vários feeds de dados, com base na similaridade com suas características ou segmentos existentes. Veja como fazer isso:

1. Vá até **[!UICONTROL Audience Marketplace]** &gt; **[!UICONTROL Marketplace]**.
2. Use o **[!UICONTROL Similarity To]** seletor para escolher entre filtragem com base em uma característica ou segmento. Você pode filtrar com base na ID ou no nome do traço/segmento. A caixa de pesquisa mostra automaticamente sugestões relevantes com base na sua entrada.
3. Depois de identificar a característica ou o segmento pelo qual deseja filtrar, clique nele na lista de sugestões.
4. Para restringir os resultados, use o **[!UICONTROL Similarity Cutoff]** controle deslizante para mover de características menos semelhantes para outras mais semelhantes.

Quando a filtragem estiver concluída, você verá uma nova coluna na página de resultados: **[!UICONTROL Similar Traits]**. Esta coluna mostra o número de características semelhantes àquelas que você filtrou, de cada feed de dados que atende aos critérios de filtragem.

Para ver a lista completa de características semelhantes, clique no número na **[!UICONTROL Similar Traits]** coluna.

>[!NOTE]
>
> O Audience Marketplace exibe os 500 principais resultados de características semelhantes de todos os feeds de dados.

Assista ao vídeo abaixo para obter uma visão geral completa de como encontrar características semelhantes.

>[!VIDEO](https://video.tv.adobe.com/v/29370/?captions=por_br)


## Feeds de dados privados {#private-data-feeds}

Na [!UICONTROL Marketplace] lista, às vezes os dados de nome e característica do provedor são marcados como privados. Isso indica um feed [de dados](../../../features/audience-marketplace/marketplace-private-feeds.md)privados. Um feed de dados privados permite que os vendedores limitem o acesso do comprador aos seus dados. Os vendedores podem tornar os feeds privados quando oferecem negócios especiais, descontos ou quando a privacidade e o controle de acesso são importantes para eles. Como comprador, você deve enviar uma solicitação de assinatura ao vendedor se quiser acessar um feed privado. Consulte [Assinar um feed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) de dados privados para obter detalhes.

>[!MORE_LIKE_THIS]
>
>* [Como entender a página de detalhes do plano no Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Descontos para Data Buyers](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

