---
description: Visão geral e fluxo de trabalho para compradores de dados que desejam comprar dados de terceiros do Audience Manager
seo-description: Visão geral e fluxo de trabalho para compradores de dados que desejam comprar dados de terceiros do Audience Manager
seo-title: Audience Marketplace para compradores de dados
solution: Audience Manager
title: Audience Marketplace para compradores de dados
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 3%

---

# [!UICONTROL Audience Marketplace] para compradores de dados  {#audience-marketplace-for-data-buyers}

Visão geral e fluxo de trabalho para compradores de dados que desejam comprar dados de terceiros de dentro de [!DNL Audience Manager].

>[!NOTE]
>[As permissões baseadas em funções](../../../reporting/reports-dashboard.md) controlam o acesso aos recursos [!UICONTROL Audience Marketplace].
>
>* Os administradores podem criar feeds de dados, gerenciar assinantes e assinar feeds de dados.
>* Os usuários podem pesquisar e exibir somente feeds.


## O [!UICONTROL Marketplace]: Sobre {#about-marketplace}

O [!UICONTROL Marketplace] é um recurso [!DNL Audience Manager] para compradores de dados que lista feeds de dados que você pode assinar. Ele lista a taxa fixa, [!DNL CPM] e os feeds de dados privados. Esses feeds são fornecidos por fornecedores terceirizados que usam [!DNL Audience Manager] para vender dados.

No [!UICONTROL Marketplace], as ferramentas de relatório permitem rastrear o uso do feed e a sobreposição entre seu [!UICONTROL traits] e aqueles em um feed de dados assinado. Finalmente, com [!UICONTROL Audience Marketplace], [!DNL Adobe] cuida de faturas e pagamentos de taxas (embora você tenha que relatar o uso automaticamente quando inscrito em um feed [!DNL CPM]). Esses recursos permitem que você encontre fontes de dados eficazes sem perder tempo procurando um provedor de dados.

>[!TIP]
>
>Use o **[Localizador de público-alvo do Adobe](https://www.adobe-audience-finder.com/)** para encontrar feeds de dados de alta qualidade que você possa assinar. Em seguida, volte para a interface do usuário [!DNL Audience Manager] ou use a [API do Comprador de Audience Marketplace](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) para assinar os feeds encontrados.

![visão geral do comprador](assets/buyer-marketplace-overview.png)

A lista [!UICONTROL Marketplace] contém informações que você pode classificar e pesquisar para encontrar o feed de dados certo para você. Os itens na lista do [!UICONTROL Marketplace] comprador incluem:

* **[!UICONTROL Search]**: Encontre feeds de dados por nome ou descrição de texto.
* **[!UICONTROL Similar Traits]**: Mostra o número de semelhante  [!UICONTROL traits] de um feed de dados. Essa coluna é exibida depois de inserir um [!UICONTROL trait] ou [!UICONTROL segment] para filtrar na seção **[!UICONTROL Similarity To]**.
* **[!UICONTROL Name]**: Nome do feed de dados.
* **[!UICONTROL Description]**: Informações sobre o conteúdo de um feed de dados.
* **[!UICONTROL Provider]**: Nome do provedor de dados.
* **[!UICONTROL Traits]**: O número de  [!UICONTROL traits] em um feed de dados.
* **[!UICONTROL 30 Day Provider Unique Users]**: O número de usuários únicos vistos nos últimos 30 dias.
* **[!UICONTROL 30 Day Overlapped Uniques]**: O número de usuários em sua conta que se sobrepõem aos usuários na conta do provedor.
* **[!UICONTROL Feed Overlap]**: O valor exclusivo sobreposto de 30 dias, exibido em porcentagens, calculado como: Comprador de dados com 30 dias sobrepostos únicos / Comprador de dados com 30 dias (únicos) x 100.
* **[!UICONTROL Private Feeds]**: Consulte Feeds de dados  [privados](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: O número de subscrições que você tem com um provedor de dados.

 

Para encontrar facilmente os melhores feeds de dados para suas necessidades, use os seguintes filtros disponíveis no lado esquerdo da página [!UICONTROL Marketplace]:

* **[!UICONTROL Similarity To]**: Filtre os feeds de dados com base em sua similaridade com um  [!UICONTROL trait] ou  [!UICONTROL segment] de sua escolha. Ao inserir o [!UICONTROL trait] ou segmento para comparar, você pode usar a ID [!UICONTROL trait] ou [!UICONTROL segment] ou seus respectivos nomes.
* **[!UICONTROL Similarity Cutoff]**: Arraste o controle deslizante para filtrar os feeds de dados com base na  [!UICONTROL traits] similaridade deles com a  [!UICONTROL trait] ou  [!UICONTROL segment]selecionada. Para saber mais sobre [!UICONTROL trait] pontuações de similaridade, consulte [Pontuação de similaridade de característica](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: Filtre os feeds de dados com base no status da assinatura.
* **[!UICONTROL Plan Use Case]**: Filtre os feeds de dados com base em seus casos de uso suportados:  **[!UICONTROL Activation]**,  **[!UICONTROL Segments and Overlap]**, e  **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Filtre os feeds de dados com base em seu tipo de preço.

## Localizando [!UICONTROL Traits] {#finding-similar-traits} Semelhante

[!UICONTROL Audience Marketplace] O oferece a opção  [!UICONTROL traits] de localizar a partir de vários feeds de dados, com base na similaridade com seus segmentos  [!UICONTROL traits] ou existentes. Veja como fazer isso:

1. Vá para **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Use o seletor **[!UICONTROL Similarity To]** para escolher entre filtragem com base em [!UICONTROL trait] ou [!UICONTROL segment]. Você pode filtrar com base na ID ou no nome [!UICONTROL trait]/[!UICONTROL segment]. A caixa de pesquisa mostra automaticamente as sugestões relevantes com base em sua entrada.
3. Depois de identificar a característica ou o segmento pelo qual deseja filtrar, clique nela na lista de sugestões.
4. Para restringir os resultados, use o controle deslizante **[!UICONTROL Similarity Cutoff]** para mover de [!UICONTROL traits] menos semelhante, para mais semelhantes.

Quando a filtragem for concluída, você verá uma nova coluna na página de resultados: **[!UICONTROL Similar Traits]**. Essa coluna mostra o número de [!UICONTROL traits] semelhante ao que você filtrou, de cada feed de dados que atende aos critérios de filtragem.

Para ver a lista completa de características semelhantes, clique no número na coluna **[!UICONTROL Similar Traits]** .

>[!NOTE]
>
> O Audience Marketplace exibe os 500 principais resultados [!UICONTROL trait] semelhantes dos feeds de dados.

Assista ao vídeo abaixo para obter uma visão geral completa de como encontrar um [!UICONTROL traits] semelhante.

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Feeds de dados privados {#private-data-feeds}

Na lista [!UICONTROL Marketplace], às vezes o nome e os dados do provedor [!UICONTROL trait] são marcados como privados. Isso indica um [feed de dados privados](../../../features/audience-marketplace/marketplace-private-feeds.md). Um feed de dados privados permite que os vendedores limitem o acesso do comprador aos seus dados. Os vendedores podem tornar os feeds privados quando oferecem ofertas especiais, descontos ou quando a privacidade e o controle de acesso são importantes para eles. Como comprador, você deve enviar uma solicitação de assinatura ao vendedor se quiser acessar um feed privado. Consulte [Assinar um feed de dados privado](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) para obter detalhes.

>[!MORELIKETHIS]
>
>* [Como entender a página de detalhes do plano no Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Descontos para compradores de dados](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

