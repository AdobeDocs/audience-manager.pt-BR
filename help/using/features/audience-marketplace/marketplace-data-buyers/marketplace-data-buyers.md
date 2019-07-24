---
description: Visão geral e fluxo de trabalho para compradores de dados que desejam adquirir dados de terceiros no Audience Manager
seo-description: Visão geral e fluxo de trabalho para compradores de dados que desejam adquirir dados de terceiros no Audience Manager
seo-title: Audience Marketplace for Data Stores
solution: Audience Manager
title: Audience Marketplace for Data Stores
topic: API DIL
uuid: f 505 b 5 f 4-4231-4 e 84-993 a-cd 64128 b 540 f
translation-type: tm+mt
source-git-commit: 12cc02103902a77b8b5967c319f4ac18746a700e

---


# Audience Marketplace for Data Buyers {#audience-marketplace-for-data-buyers}

Overview and workflow for data buyers who want to purchase third-party data from within [!DNL Audience Manager].

>[!NOTE]
>[Permissões com base em funções](../../../reporting/reports-dashboard.md) controlam o acesso aos [!UICONTROL Audience Marketplace] recursos.
>
>* Os administradores podem criar feeds de dados, gerenciar assinantes e assinar feeds de dados.
>* Os usuários podem pesquisar e exibir apenas feeds.


## The Marketplace: About {#about-marketplace}

<!-- c_marketplace_about.xml -->

The [!UICONTROL Marketplace] is an [!DNL Audience Manager] feature for data buyers that lists data feeds you can subscribe to. It lists flat rate, [!DNL CPM], or private data feeds. These feeds are provided by third-party vendors that use [!DNL Audience Manager] to sell data. In the [!UICONTROL Marketplace], reporting tools let you track feed usage and the overlap between your traits and those in a subscribed data feed. Finally, with [!UICONTROL Audience Marketplace], [!DNL Adobe] takes care of invoices and fee payments (though you do have to self-report usage when subscribed to a [!DNL CPM] feed). Esses recursos permitem encontrar fontes de dados eficientes sem perder tempo procurando por um provedor de dados.

>[!TIP]
> 
>Use the **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** to find high quality data feeds that you can subscribe to. Then, go back into the Audience Manager UI or use the [Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) to subscribe to the feeds you found.

![](assets/buyer_marketplace.png)

[!UICONTROL Marketplace] A lista contém informações que você pode classificar e pesquisar para encontrar o feed de dados que é adequado para você. Items in the [!UICONTROL Marketplace] buyer's list include:

* **[!UICONTROL Search]:** Encontre feeds de dados por nome ou descrição de texto.
* **[!UICONTROL Name]:** Nome do feed de dados.
* **[!UICONTROL Description]:** Informações sobre o conteúdo de um feed de dados.
* **[!UICONTROL Provider]:** Nome do provedor de dados.
* **[!UICONTROL Traits]:** O número de características em um feed de dados.
* **[!UICONTROL 30 Day Provider Unique Users]:** O número de usuários únicos vistos nos últimos 30 dias.
* **[!UICONTROL 30 Day Overlapped Uniques]:** O número de usuários em sua conta que se sobrepõem com os usuários na conta do provedor.
* **[!UICONTROL Feed Overlap]:** O valor de únicos exclusivos de 30 dias, exibido em porcentagens, calculado como: Comprador de dados 30 dias sobrepostos por únicos/comprador de dados de 30 dias) x 100.
* **[!UICONTROL Private Feeds]:** Consulte [Feeds de dados privados](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]:** O número de assinaturas que você possui com um provedor de dados.

## Feeds de dados privados {#private-data-feeds}

In the [!UICONTROL Marketplace] list, sometimes the provider's name and trait data are marked as private. This indicates a [private data feed](../../../features/audience-marketplace/marketplace-private-feeds.md). Um feed de dados privados permite que os vendedores limite o acesso do comprador aos seus dados. Os vendedores podem tornar os feeds privados quando oferecem ofertas especiais, descontos ou quando a privacidade e o controle de acesso são importantes para eles. Como comprador, você deve enviar uma solicitação de assinatura para o vendedor se quiser acesso a um feed privado. See [Subscribe to a Private Data Feed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) for details.

>[!MORE_ LIKE_ THIS]
>
>* [Como entender a página de detalhes do plano no Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Descontos para compradores de dados](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

