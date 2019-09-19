---
description: Visão geral e fluxo de trabalho para compradores de dados que desejam comprar dados de terceiros no Audience Manager
seo-description: Visão geral e fluxo de trabalho para compradores de dados que desejam comprar dados de terceiros no Audience Manager
seo-title: Audience Marketplace para Compradores de Dados
solution: Audience Manager
title: ' Audience Marketplace para Compradores de Dados'
topic: API DIL
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
translation-type: tm+mt
source-git-commit: 12cc02103902a77b8b5967c319f4ac18746a700e

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

O [!UICONTROL Marketplace] é um [!DNL Audience Manager] recurso para compradores de dados que lista feeds de dados que você pode assinar. Ele lista feeds de dados de taxa fixa [!DNL CPM]ou privados. Esses feeds são fornecidos por fornecedores terceirizados que usam [!DNL Audience Manager] para vender dados. No [!UICONTROL Marketplace], as ferramentas de relatório permitem rastrear o uso do feed e a sobreposição entre suas características e as de um feed de dados inscrito. Por fim, com [!UICONTROL Audience Marketplace], [!DNL Adobe] cuida das NFFs e dos pagamentos de taxa (embora você tenha que relatar o uso automaticamente quando estiver inscrito em um [!DNL CPM] feed). Esses recursos permitem que você encontre fontes de dados eficazes sem perder tempo procurando um provedor de dados.

>[!TIP]
> 
>Use o **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** para encontrar feeds de dados de alta qualidade que você possa assinar. Em seguida, volte para a interface do usuário do Audience Manager ou use a API [do](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) Audience Marketplace Buyer para assinar os feeds encontrados.

![](assets/buyer_marketplace.png)

A [!UICONTROL Marketplace] lista contém informações que você pode classificar e pesquisar para encontrar o feed de dados certo para você. Os itens da lista de [!UICONTROL Marketplace] compradores incluem:

* **[!UICONTROL Search]** : Encontre feeds de dados por nome ou descrição de texto.
* **[!UICONTROL Name]** : Nome do feed de dados.
* **[!UICONTROL Description]** : Informações sobre o conteúdo de um feed de dados.
* **[!UICONTROL Provider]** :Nome do provedor de dados.
* **[!UICONTROL Traits]** : O número de características em um feed de dados.
* **[!UICONTROL 30 Day Provider Unique Users]** : O número de usuários únicos vistos nos últimos 30 dias.
* **[!UICONTROL 30 Day Overlapped Uniques]** : O número de usuários em sua conta que se sobrepõem aos usuários na conta do provedor.
* **[!UICONTROL Feed Overlap]** : O valor único sobreposto de 30 dias, exibido em porcentagens, calculado como: Comprador de dados: 30 dias sobrepostos únicos / Comprador de dados, 30 dias únicos) x 100.
* **[!UICONTROL Private Feeds]** : Consulte Feeds [de dados](../../../features/audience-marketplace/marketplace-private-feeds.md)privados.
* **[!UICONTROL Currently Subscribed Plan Count]** : O número de assinaturas que você tem com um provedor de dados.

## Feeds de dados privados {#private-data-feeds}

Na [!UICONTROL Marketplace] lista, às vezes os dados de nome e característica do provedor são marcados como privados. Isso indica um feed [de dados](../../../features/audience-marketplace/marketplace-private-feeds.md)privados. Um feed de dados privados permite que os vendedores limitem o acesso do comprador aos seus dados. Os vendedores podem tornar os feeds privados quando oferecem negócios especiais, descontos ou quando a privacidade e o controle de acesso são importantes para eles. Como comprador, você deve enviar uma solicitação de assinatura ao vendedor se quiser acessar um feed privado. Consulte [Assinar um feed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) de dados privados para obter detalhes.

>[!MORE_LIKE_THIS]
>
>* [Como entender a página de detalhes do plano no Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Descontos para Data Buyers](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

