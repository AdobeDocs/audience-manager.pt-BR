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
source-wordcount: '724'
ht-degree: 1%

---

# [!UICONTROL Audience Marketplace] para compradores de dados {#audience-marketplace-for-data-buyers}

Visão geral e fluxo de trabalho para compradores de dados que desejam comprar dados de terceiros no [!DNL Audience Manager].

>[!NOTE]
>[Permissões baseadas em função](../../../reporting/reports-dashboard.md) controlam o acesso aos recursos [!UICONTROL Audience Marketplace].
>
>* Os administradores podem criar feeds de dados, gerenciar assinantes e assinar feeds de dados.
>* Os usuários podem pesquisar e visualizar apenas feeds.

## O [!UICONTROL Marketplace]: Sobre {#about-marketplace}

O [!UICONTROL Marketplace] é um recurso [!DNL Audience Manager] para compradores de dados que lista feeds de dados que você pode assinar. Ele lista feeds de dados de taxa uniforme, [!DNL CPM] e privado. Esses feeds são fornecidos por fornecedores terceirizados que usam o [!DNL Audience Manager] para vender dados.

No [!UICONTROL Marketplace], as ferramentas de relatórios permitem rastrear o uso do feed e a sobreposição entre o [!UICONTROL traits] e aqueles em um feed de dados assinado. Por fim, com o [!UICONTROL Audience Marketplace], o [!DNL Adobe] cuida das faturas e dos pagamentos de taxas (embora você precise usar o relatório quando estiver inscrito em um feed do [!DNL CPM]). Esses recursos permitem encontrar fontes de dados eficazes sem perder tempo procurando um provedor de dados.

>[!TIP]
>
>Use o **[Localizador de Público-Alvo do Adobe](https://www.adobe-audience-finder.com/)** para encontrar feeds de dados de alta qualidade nos quais você pode se inscrever. Volte para a interface de usuário do [!DNL Audience Manager] ou use a [API de Audience Marketplace](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) para assinar os feeds encontrados.

![visão geral-do-marketplace](assets/buyer-marketplace-overview.png)

A lista [!UICONTROL Marketplace] contém informações que você pode classificar e pesquisar para encontrar o feed de dados adequado para você. Os itens na lista de compradores [!UICONTROL Marketplace] incluem:

* **[!UICONTROL Search]**: Localizar feeds de dados por nome ou descrição de texto.
* **[!UICONTROL Similar Traits]**: Mostra o número de [!UICONTROL traits] semelhantes de um feed de dados. Esta coluna é mostrada depois que você insere um [!UICONTROL trait] ou [!UICONTROL segment] para filtrar na seção **[!UICONTROL Similarity To]**.
* **[!UICONTROL Name]**: Nome do feed de dados.
* **[!UICONTROL Description]**: Informações sobre o conteúdo de um feed de dados.
* **[!UICONTROL Provider]**: Nome do provedor de dados.
* **[!UICONTROL Traits]**: O número de [!UICONTROL traits] em um feed de dados.
* **[!UICONTROL 30 Day Provider Unique Users]**: o número de usuários únicos vistos nos últimos 30 dias.
* **[!UICONTROL 30 Day Overlapped Uniques]**: o número de usuários em sua conta que se sobrepõem aos usuários na conta do provedor.
* **[!UICONTROL Feed Overlap]**: O valor de únicos sobrepostos de 30 dias, exibido em porcentagens, calculado como: únicos sobrepostos de 30 dias do comprador de dados / únicos de 30 dias do comprador de dados x 100.
* **[!UICONTROL Private Feeds]**: Consulte [Feeds De Dados Privados](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: o número de assinaturas que você tem com um provedor de dados.

 

Para encontrar facilmente os melhores feeds de dados de acordo com suas necessidades, use os seguintes filtros disponíveis no lado esquerdo da página [!UICONTROL Marketplace]:

* **[!UICONTROL Similarity To]**: filtre feeds de dados com base na similaridade com um [!UICONTROL trait] ou [!UICONTROL segment] de sua escolha. Ao inserir o [!UICONTROL trait] ou segmento para comparação, você pode usar a ID [!UICONTROL trait] ou [!UICONTROL segment], ou seus respectivos nomes.
* **[!UICONTROL Similarity Cutoff]**: Arraste o controle deslizante para filtrar os feeds de dados com base na semelhança de seus [!UICONTROL traits] com o [!UICONTROL trait] ou [!UICONTROL segment] selecionado. Para saber mais sobre [!UICONTROL trait] pontuações de similaridade, consulte [Pontuação de similaridade de característica](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: filtre os feeds de dados com base no status da sua assinatura.
* **[!UICONTROL Plan Use Case]**: filtre feeds de dados com base nos casos de uso com suporte: **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]** e **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: filtrar feeds de dados de acordo com seu tipo de preço.

## Encontrando [!UICONTROL Traits] Semelhante {#finding-similar-traits}

[!UICONTROL Audience Marketplace] oferece a opção de encontrar [!UICONTROL traits] de vários feeds de dados, com base na similaridade com seus [!UICONTROL traits] ou segmentos existentes. Veja como fazer isso:

1. Vá para **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Use o seletor **[!UICONTROL Similarity To]** para escolher entre filtragem baseada em [!UICONTROL trait] ou [!UICONTROL segment]. Você pode filtrar com base na ID ou no nome de [!UICONTROL trait]/[!UICONTROL segment]. A caixa de pesquisa mostra automaticamente sugestões relevantes com base em sua entrada.
3. Depois de identificar a característica ou o segmento pelo qual deseja filtrar, clique na lista de sugestões.
4. Para restringir os resultados, use o controle deslizante **[!UICONTROL Similarity Cutoff]** para mover de [!UICONTROL traits] menos semelhantes para mais semelhantes.

Quando a filtragem for concluída, você verá uma nova coluna na página de resultados: **[!UICONTROL Similar Traits]**. Esta coluna mostra o número de [!UICONTROL traits] semelhantes ao que você filtrou, de cada feed de dados que atende aos critérios de filtragem.

Para ver a lista completa de características semelhantes, clique no número na coluna **[!UICONTROL Similar Traits]**.

>[!NOTE]
>
> O Audience Marketplace exibe os 500 principais resultados semelhantes de [!UICONTROL trait] dos feeds de dados.

Assista ao vídeo abaixo para obter uma visão geral de como encontrar [!UICONTROL traits] semelhantes.

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## os feeds de dados privados {#private-data-feeds}

Na lista [!UICONTROL Marketplace], às vezes o nome do provedor e os dados [!UICONTROL trait] são marcados como particulares. Isso indica um [feed de dados privado](../../../features/audience-marketplace/marketplace-private-feeds.md). Um feed de dados privado permite que os vendedores limitem o acesso do comprador aos seus dados. Os vendedores podem tornar os feeds privados quando estão oferecendo ofertas especiais, descontos ou quando a privacidade e o controle de acesso são importantes para eles. Como comprador, você precisa enviar uma solicitação de subscrição ao vendedor se quiser acesso a um feed privado. Consulte [Assinar um Feed de Dados Privado](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) para obter detalhes.

>[!MORELIKETHIS]
>
>* [Como entender a página de detalhes do plano no Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Descontos para compradores de dados](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)
