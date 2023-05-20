---
description: Visão geral e fluxo de trabalho para compradores de dados que desejam comprar dados de terceiros no Audience Manager
seo-description: Overview and workflow for data buyers who want to purchase third-party data from within Audience Manager
seo-title: Audience Marketplace for Data Buyers
solution: Audience Manager
title: Audience Marketplace para compradores de dados
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 2%

---

# [!UICONTROL Audience Marketplace] para compradores de dados {#audience-marketplace-for-data-buyers}

Visão geral e fluxo de trabalho para compradores de dados que desejam comprar dados de terceiros no [!DNL Audience Manager].

>[!NOTE]
>[Permissões baseadas em função](../../../reporting/reports-dashboard.md) controlar acesso a [!UICONTROL Audience Marketplace] recursos.
>
>* Os administradores podem criar feeds de dados, gerenciar assinantes e assinar feeds de dados.
>* Os usuários podem pesquisar e visualizar apenas feeds.


## A variável [!UICONTROL Marketplace]: Sobre {#about-marketplace}

A variável [!UICONTROL Marketplace] é um [!DNL Audience Manager] recurso para compradores de dados que lista feeds de dados que você pode assinar. Enumera as taxas forfetárias, [!DNL CPM]e feeds de dados privados. Esses feeds são fornecidos por fornecedores terceirizados que usam o [!DNL Audience Manager] dados de vendas.

No [!UICONTROL Marketplace], as ferramentas de relatórios permitem rastrear o uso do feed e a sobreposição entre [!UICONTROL traits] e em um feed de dados assinado. Por último, com [!UICONTROL Audience Marketplace], [!DNL Adobe] cuida de faturas e pagamentos de taxas (embora você tenha que relatar o uso quando estiver subscrito em um [!DNL CPM] feed). Esses recursos permitem encontrar fontes de dados eficazes sem perder tempo procurando um provedor de dados.

>[!TIP]
>
>Use o **[Localizador de público-alvo Adobe](https://www.adobe-audience-finder.com/)** para encontrar feeds de dados de alta qualidade nos quais você pode se inscrever. Em seguida, volte para a guia [!DNL Audience Manager] ou use o [API do comprador do Audience Marketplace](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) para se inscrever nos feeds encontrados.

![comprador-marketplace-visão geral](assets/buyer-marketplace-overview.png)

A variável [!UICONTROL Marketplace] A lista contém informações que você pode classificar e pesquisar para encontrar o feed de dados certo para você. Itens na lista [!UICONTROL Marketplace] a lista de compradores inclui:

* **[!UICONTROL Search]**: encontre feeds de dados por nome ou descrição do texto.
* **[!UICONTROL Similar Traits]**: mostra o número de eventos semelhantes [!UICONTROL traits] de um feed de dados. Essa coluna é mostrada depois que você insere um [!UICONTROL trait] ou [!UICONTROL segment] para filtrar por na **[!UICONTROL Similarity To]** seção.
* **[!UICONTROL Name]**: Nome do feed de dados.
* **[!UICONTROL Description]**: informações sobre o conteúdo de um feed de dados.
* **[!UICONTROL Provider]**: Nome do provedor de dados.
* **[!UICONTROL Traits]**: o número de [!UICONTROL traits] de dados.
* **[!UICONTROL 30 Day Provider Unique Users]**: o número de usuários únicos vistos nos últimos 30 dias.
* **[!UICONTROL 30 Day Overlapped Uniques]**: o número de usuários em sua conta que se sobrepõem aos usuários na conta do provedor.
* **[!UICONTROL Feed Overlap]**: o valor de únicos sobrepostos de 30 dias, exibido em porcentagens, calculado como: únicos sobrepostos do comprador de dados de 30 dias / únicos do comprador de dados de 30 dias) x 100.
* **[!UICONTROL Private Feeds]**: Consulte [Feeds de dados privados](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: o número de assinaturas que você tem com um provedor de dados.

 

Para encontrar facilmente os melhores feeds de dados para suas necessidades, use os seguintes filtros disponíveis no lado esquerdo do [!UICONTROL Marketplace] página:

* **[!UICONTROL Similarity To]**: filtre os feeds de dados com base na semelhança com um [!UICONTROL trait] ou [!UICONTROL segment] de sua escolha. Ao inserir a variável [!UICONTROL trait] ou segmento para comparação, você pode usar o [!UICONTROL trait] ou [!UICONTROL segment] ID ou seus respectivos nomes.
* **[!UICONTROL Similarity Cutoff]**: arraste o controle deslizante para filtrar os feeds de dados com base na semelhança dos [!UICONTROL traits] são para o(a) selecionado(a) [!UICONTROL trait] ou [!UICONTROL segment]. Para saber mais sobre [!UICONTROL trait] pontuações de similaridade, consulte [Pontuação de similaridade de característica](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: filtre os feeds de dados com base no status da assinatura.
* **[!UICONTROL Plan Use Case]**: filtre feeds de dados com base nos casos de uso compatíveis: **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]**, e **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: filtre os feeds de dados com base no tipo de preço.

## Localizando semelhante [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] oferece a opção de encontrar [!UICONTROL traits] de vários feeds de dados, com base na semelhança deles com o seu [!UICONTROL traits] ou segmentos. Veja como fazer isso:

1. Ir para **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Use o **[!UICONTROL Similarity To]** seletor para escolher entre filtrar com base em um [!UICONTROL trait] ou [!UICONTROL segment]. Você pode filtrar com base em [!UICONTROL trait]/[!UICONTROL segment] ID ou nome. A caixa de pesquisa mostra automaticamente sugestões relevantes com base em sua entrada.
3. Depois de identificar a característica ou o segmento pelo qual deseja filtrar, clique na lista de sugestões.
4. Para restringir os resultados, use o **[!UICONTROL Similarity Cutoff]** controle deslizante para mover de menos semelhante [!UICONTROL traits], para outros semelhantes.

Quando a filtragem estiver concluída, você verá uma nova coluna na página de resultados: **[!UICONTROL Similar Traits]**. Essa coluna mostra o número de [!UICONTROL traits] para o que você filtrou por, de cada feed de dados que atende aos critérios de filtragem.

Para ver a lista completa de características semelhantes, clique no número no **[!UICONTROL Similar Traits]** coluna.

>[!NOTE]
>
> Audience Marketplace exibe os 500 principais semelhantes [!UICONTROL trait] resultados em todos os feeds de dados.

Assista ao vídeo abaixo para obter uma visão geral completa de como encontrar [!UICONTROL traits].

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Feeds de dados privados {#private-data-feeds}

No [!UICONTROL Marketplace] , às vezes o nome do provedor e [!UICONTROL trait] os dados são marcados como privados. Isso indica uma [feed de dados privado](../../../features/audience-marketplace/marketplace-private-feeds.md). Um feed de dados privado permite que os vendedores limitem o acesso do comprador aos seus dados. Os vendedores podem tornar os feeds privados quando estão oferecendo ofertas especiais, descontos ou quando a privacidade e o controle de acesso são importantes para eles. Como comprador, você precisa enviar uma solicitação de subscrição ao vendedor se quiser acesso a um feed privado. Consulte [Assinar um feed de dados privado](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) para obter detalhes.

>[!MORELIKETHIS]
>
>* [Como entender a página de detalhes do plano no Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Descontos para compradores de dados](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

