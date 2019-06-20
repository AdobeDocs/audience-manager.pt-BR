---
description: Um feed de dados exige um nome, descrição, fonte de dados e um tipo de plano. Os feeds são desativados até que você salve e ative o feed. Configurar feeds de dados públicos ou privados no Audience Marketplace > Meus dados compartilhados. Disponível apenas para vendedores de dados.
seo-description: Um feed de dados exige um nome, descrição, fonte de dados e um tipo de plano. Os feeds são desativados até que você salve e ative o feed. Configurar feeds de dados públicos ou privados no Audience Marketplace > Meus dados compartilhados. Disponível apenas para vendedores de dados.
seo-title: Criar, Price e Gerenciar feeds de dados
solution: Audience Manager
title: Criar, Price e Gerenciar feeds de dados
topic: API DIL
uuid: e 28 c 20 b 3-33 fc -4485-8 ee 9-8530 d 126 f 741
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create, Price, and Manage Data Feeds {#create-price-and-manage-data-feeds}

Um feed de dados exige um nome, descrição, fonte de dados e um tipo de plano. Os feeds são desativados até que você salve e ative o feed. Set up public or private data feeds in [!UICONTROL Audience Marketplace] &gt; [!UICONTROL My Shared Data]. Disponível apenas para vendedores de dados.

## Create a Public or Private Data Feed {#create-public-private-data-feed}

Um feed de dados exige um nome, descrição, fonte de dados e um tipo de plano. Os feeds são desativados até que você salve e ative o feed. Set up public or private data feeds in **[!UICONTROL Audience Marketplace > My Shared Data]**. Disponível apenas para vendedores de dados.

<!-- t_data_feed.xml -->

É necessário ter direitos de administrador para criar um feed de dados público ou privado.
Para criar um feed de dados:

1. Clique em **[!UICONTROL New Data Feed]**.
1. Dê um nome para o feed de dados. Os compradores de dados podem pesquisar seu feed com base no nome.
1. Forneça uma descrição curta (maximum 55 caracteres máximo).

   Uma boa descrição deve descrever seu feed com precisão. For example, you could include text for marketing categories, demographics, and geographic coverage (e.g., [!DNL US] or North America). O texto da descrição é pesquisável e ajuda os compradores a encontrar ou avaliar seu feed. Uma boa descrição é uma parte importante de atrair assinantes para o feed de dados.
1. Select a data source from the **[!UICONTROL Data Source]** options.

   >[!IMPORTANT]
   >
   >Quaisquer características atuais e futuras pertencentes a essa fonte de dados serão compartilhadas com seus compradores de dados, como parte deste feed.

1. In [!UICONTROL Plan Types], select the options you want to use and click **[!UICONTROL Add Plan]**.

   Os feeds podem conter vários planos. Os planos podem conter vários casos de uso. For details, see [Plan Types for Data Feeds](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types).

1. Click **[!UICONTROL Save]** to save your data fee *without* activating it.
1. Para salvar e ativar um feed de dados:
   1. Move the **[!UICONTROL Availability]** slider to **[!UICONTROL Active]**.
   1. Clique em **[!UICONTROL Save]**.
   >[!NOTE]
   >
   >* Feeds de dados salvos e ativados não podem ser excluídos.
   >* Os compradores veem apenas feeds ativos.


### Opcional: Criar um feed de dados privados

In the [!UICONTROL Settings] section, move the slider to:

* **[!UICONTROL Private]** e **[!UICONTROL Branded]**: A [!UICONTROL Marketplace] lista do comprador mostra o nome do vendedor na coluna do provedor e todos os outros dados estão ocultos.

* **[!UICONTROL Private]** e **[!UICONTROL Unbranded]**: A [!UICONTROL Marketplace] lista do comprador mostra apenas o nome e a descrição do feed de dados. The data provider name appears as [!UICONTROL Private Seller].

To see what a private feed looks like to buyers, see the buyers section in [Private Data Feeds](../../../features/audience-marketplace/marketplace-private-feeds.md).

>[!MORE_ LIKE_ THIS]
>
>* [Feeds de dados privados](../../../features/audience-marketplace/marketplace-private-feeds.md)


## Desativar o feed de dados de um assinante {#deactivate-data-feed}

As an [!UICONTROL Audience Marketplace] data provider, you can revoke buyer access to a subscribed data feed. Você pode remover um comprador de um feed por motivos como pagamento atrasado/não pagamento de taxas ou caso usem dados características incorretamente.

<!-- marketplace-deactiva4te-subscribers.xml -->

Para revogar um assinante:

1. In [!UICONTROL My Shared Data], find the feed the subscriber is using.

   >[!NOTE]
   >
   >Os feeds de dados com contas atrasadas são marcados com um ícone de triângulo/ponto de exclamação.

1. In the [!UICONTROL Subscribers] column, click the blue number that counts subscribers for that feed. Isso abre a página de detalhes da assinatura.
1. Move the **[!UICONTROL Subscription]** slider to **[!UICONTROL Off]**. Isso abre uma janela de diálogo de confirmação.
1. In the [!UICONTROL Confirmation] pop, click **[!UICONTROL Yes]** to deactivate a subscription or **[!UICONTROL Cancel]** to quit without making subscription changes.

### O que acontece depois de desativar um assinante

Revogar o acesso a um feed de dados envia um email de notificação a todos os usuários administradores na conta do comprador de dados. O e-mail inclui um anexo que lista características revogadas. Essa lista ajuda os assinantes a localizar e remover traços desativados de seus segmentos e modelos.

### Faturamento e desativação do feed

Depois de remover o acesso a um feed de dados, os assinantes são responsáveis por taxas do mês anterior ou atual, dependendo de quando o feed foi desativado.

## Plan Types for Data Feeds {#plan-types}

[!DNL Plan types] são componentes essenciais em um [!UICONTROL Audience Marketplace] feed de dados. Como um provedor de dados, eles permitem que você crie vários casos de uso e opções de preço para seus feeds. Além disso, pode ser uma boa estratégia criar alguns planos para cada feed de dados. Isso oferece aos compradores opções diferentes para escolher quando estão procurando por dados para modelar ou enviar para um destino.

[Crie um feed de dados](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) para selecionar [!UICONTROL Plan Types].

![](assets/plan_types.png)

## Plan Types and Use Case Options {#plan-types-use-cases}

<!-- c_feed_options.xml -->

The [!UICONTROL Use Case] settings let sellers control how buyers can use your data.

### Segmentos e sobreposição

A **[!UICONTROL Segments and Overlap]** use case creates a plan that lets buyers compare trait data in a [trait-to-trait overlap report](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report). Furthermore, buyers can add your data to segments and make comparisons with the [segment-to-trait](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) and [segment-to-segment](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) reports.

Each data feed must include at least one [!UICONTROL Segments and Overlap] use case. Buyers cannot subscribe to other plans in a data feed if the feed does not contain a [!UICONTROL Segments and Overlap] use case, either by itself or in combination with another use case.

Comparações de sobreposição podem ajudar compradores:

* **Estender o alcance do público-alvo:** A sobreposição baixa sugere que seus traços contenham usuários que o comprador não tenha visto anteriormente. Como resultado, os compradores podem desejar que esses características adicionem novos usuários aos segmentos do público-alvo.
* **Aprimorar públicos-alvo existentes:** A sobreposição alta sugere que seus traços contenham usuários semelhantes àqueles que um comprador já conhece. Como resultado, os compradores podem querer essas características para ajudar a fazer melhorias direcionadas e incrementais para públicos-alvo desenvolvidos.

Price this use case da seguinte maneira:

* Unidade de medida: Taxa simples
* Preço: Gratuito ($ 0.00)

### Modelagem

A **[!UICONTROL Modeling]** use case creates a plan that lets buyers compare your traits to theirs with [algorithmic modeling](../../../features/algorithmic-models/understanding-models.md#understanding-models). Os compradores analisam os resultados do modelo para encontrar novos públicos em seus dados que compartilham atributos de conversão semelhantes. Price this use case da seguinte maneira:

* Unidade de medida: Taxa simples
* Preço: Preço com desconto ou preço de mercado

### Activation

An **[!UICONTROL Activation]** use case lets buyers send data to a [destination](../../../features/destinations/destinations.md). Com esse caso de uso, os compradores não podem comparar dados com um relatório de sobreposição ou em um modelo algorítmico. Price this use case da seguinte maneira:

* Unit of Measure: [!DNL CPM]
* Price: [!DNL CPM] market rate

## Billing and Price Options {#billing}

As opções de cobrança e preço controlam como os compradores pagam pelos seus dados.

<table id="table_CCEAAF24295942EA82F20753827D1A23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opção </th> 
   <th colname="col2" class="entry"> Descrição </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Ciclo de cobrança</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Mensalmente, em Backars</span></b> é a única opção. O ciclo de cobrança termina no 10 º dia de cada mês. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Unidade de medida</span></b> </td> 
   <td colname="col2">Cobra compradores de dados em uma taxa CPM ou taxa fixa. 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> Com o preço de CPM, os compradores de dados são necessários para o uso de autorelatório. </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">Quando o preço de taxa fixa é fixado, os compradores de dados não informam o uso porque cobram uma taxa fixa. </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Preço</span></b> </td>
   <td colname="col2"> A quantia que um vendedor cobra o comprador como taxa de CPM ou preço de taxa fixa, em dólares. </td>
  </tr> 
 </tbody> 
</table>

## Plan Notes {#plan-notes}

In the **[!UICONTROL Additional Notes]** field, take some time to describe each data plan in a feed. Uma descrição boa e breve ajuda os compradores a compreender o conteúdo ou a finalidade de cada plano em um feed de dados. Os compradores podem ler feed de dados e planejar descrições enquanto procuram ou avaliam novas fontes de dados.

## Manage Private Data Feed Requests {#manage-private-requests}

Fluxos de trabalho do provedor para gerenciar solicitações de feed privadas de compradores.

To review, approve, or reject buyer requests, go to [!UICONTROL My Shared Data] and:

<!-- t_private_feed_workflows.xml -->

1. Clique no nome do feed de dados privados.
2. Click **[!UICONTROL Access Requests]** to review all the buyers who want access to your data feed.
3. In the [!UICONTROL Allow Access] section of each request box, click the check mark to approve a request or the X to deny access.
4. Confirme ou cancele a ação selecionada na pop-up de confirmação.

>[!MORE_ LIKE_ THIS]
>
>* [Feeds de dados privados](../../../features/audience-marketplace/marketplace-private-feeds.md)


## Discounts for Data Providers {#discounts}

In [!UICONTROL Audience Marketplace], discounts let you reduce the published price of a data feed for individual subscribers. Você pode oferecer descontos aos assinantes que enviaram uma solicitação de assinatura ou aos assinantes que solicitaram detalhes sobre um feed de dados. Discounts apply to [!DNL CPM] and flat rate feeds. Os descontos podem ser úteis quando você deseja fornecer incentivos de assinatura para novos clientes ou para recompensar a fidelidade do cliente.

## Apply Discounts to a Data Feed {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

Para desfazer um feed, adicione um valor de desconto como % ao campo de desconto e confirme suas alterações. Data providers can discount a data feeds in [!UICONTROL Audience Marketplace] from either:

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

In these examples, the seller has added 10% discount to the [!UICONTROL Software Audience] data feed.

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Review Discounted Feeds {#review-discounted-feeds}

Data providers can see all of their subscribers and discounted feeds in **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**.

![](assets/subscribers.png)