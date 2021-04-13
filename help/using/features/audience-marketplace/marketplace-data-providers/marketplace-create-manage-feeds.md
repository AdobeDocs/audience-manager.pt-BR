---
description: Um feed de dados requer um nome, uma descrição, uma fonte de dados e um tipo de plano. Os feeds são desativados até que você salve e ative o feed. Configure os feeds de dados públicos ou privados no Audience Marketplace > Meus dados compartilhados. Disponível somente para vendedores de dados.
seo-description: Um feed de dados requer um nome, uma descrição, uma fonte de dados e um tipo de plano. Os feeds são desativados até que você salve e ative o feed. Configure os feeds de dados públicos ou privados no Audience Marketplace > Meus dados compartilhados. Disponível somente para vendedores de dados.
seo-title: Criar, precificar e gerenciar feeds de dados
solution: Audience Manager
title: Criar, precificar e gerenciar feeds de dados
uuid: e28c20b3-33fc-4485-8ee9-8530d126f741
feature: Audience Marketplace
exl-id: e8605e94-e62a-430c-9aef-875f995fb436
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '1306'
ht-degree: 2%

---

# Criar, precificar e gerenciar feeds de dados {#create-price-and-manage-data-feeds}

## Criar um feed de dados público ou privado {#create-public-private-data-feed}

Um feed de dados requer um nome, uma descrição, uma fonte de dados e um tipo de plano. Os feeds são desativados até que você salve e ative o feed. Configure os feeds de dados públicos ou privados em **[!UICONTROL Audience Marketplace > My Shared Data]**. Disponível somente para vendedores de dados.

<!-- t_data_feed.xml -->

Você deve ter direitos de administrador para criar um feed de dados público ou privado.
Para criar um feed de dados:

1. Clique em **[!UICONTROL New Data Feed]**.
1. Nomeie o feed de dados. Os compradores de dados podem pesquisar seu feed com base no nome.
1. Forneça uma breve descrição (máximo de 255 caracteres).

   Uma boa descrição deve descrever seu feed com precisão. Por exemplo, você pode incluir texto para categorias de marketing, demografia e cobertura geográfica (por exemplo, [!DNL US] ou América do Norte). O texto da descrição é pesquisável e ajuda os compradores a encontrar ou avaliar seu feed. Uma boa descrição é uma parte importante da atração de assinantes ao feed de dados.
1. Selecione uma fonte de dados nas opções **[!UICONTROL Data Source]** . Os feeds de dados são limitados a uma única fonte de dados. Não é possível atribuir várias fontes de dados ao mesmo feed de dados.

   >[!IMPORTANT]
   >
   >Qualquer característica atual e futura pertencente a essa fonte de dados será compartilhada com seus compradores de dados, como parte desse feed.

1. Em [!UICONTROL Plan Types], selecione as opções que deseja usar e clique em **[!UICONTROL Add Plan]**.

   Os feeds podem conter vários planos. Os planos podem conter vários casos de uso. Para obter detalhes, consulte [Tipos de Plano para Feeds de Dados](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types).

1. Clique em **[!UICONTROL Save]** para salvar o feed de dados *sem* ativá-lo.
1. Para salvar e ativar um feed de dados:
   1. Mova o controle deslizante **[!UICONTROL Availability]** para **[!UICONTROL Active]**.
   1. Clique em **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >* Os feeds de dados salvos e ativados não podem ser excluídos.
   >* Os compradores veem apenas feeds ativos.


### Opcional: Criar um feed de dados privado

Na seção [!UICONTROL Settings], mova o controle deslizante para:

* **[!UICONTROL Private]** e  **[!UICONTROL Branded]**: A  [!UICONTROL Marketplace] lista do comprador mostra o nome do vendedor na coluna do provedor e todos os outros dados estão ocultos.

* **[!UICONTROL Private]** e  **[!UICONTROL Unbranded]**: A  [!UICONTROL Marketplace] lista do comprador mostra somente o nome e a descrição do feed de dados. O nome do provedor de dados aparece como [!UICONTROL Private Seller].

Para ver a aparência de um feed privado para compradores, consulte a seção compradores em [Feeds de dados privados](../../../features/audience-marketplace/marketplace-private-feeds.md).

## Desativar o feed de dados de um assinante {#deactivate-data-feed}

Como provedor de dados [!UICONTROL Audience Marketplace], você pode revogar o acesso do comprador a um feed de dados assinado. Você pode desejar remover um comprador de um feed por motivos como atraso de pagamento/não pagamento de tarifas ou se ele usar dados de características incorretamente.

<!-- marketplace-deactiva4te-subscribers.xml -->

Para revogar um assinante:

1. Em [!UICONTROL My Shared Data], encontre o feed que o assinante está usando.

   >[!NOTE]
   >
   >Os feeds de dados com contas vencidas são marcados com um ícone de triângulo/ponto de exclamação.

1. Na coluna [!UICONTROL Subscribers], clique no número azul que conta os assinantes desse feed. Isso abre a página de detalhes da assinatura.
1. Mova o controle deslizante **[!UICONTROL Subscription]** para **[!UICONTROL Off]**. Isso abre uma janela de diálogo de confirmação.
1. No pop [!UICONTROL Confirmation], clique em **[!UICONTROL Yes]** para desativar uma assinatura ou em **[!UICONTROL Cancel]** para sair sem fazer alterações de assinatura.

### O que acontece depois que você desativa um assinante

Revisar o acesso a um feed de dados envia um email de notificação para todos os usuários administradores na conta do comprador de dados. O email inclui um anexo que lista características revogadas. Essa lista ajuda os assinantes a localizar e remover características desativadas de seus segmentos e modelos.

### Faturamento e desativação do feed

Depois de remover o acesso a um feed de dados, os assinantes são responsáveis pelas tarifas do mês anterior ou atual, dependendo de quando você desativou o feed.

## Tipos de plano para feeds de dados {#plan-types}

[!DNL Plan types] são componentes essenciais em um feed  [!UICONTROL Audience Marketplace] de dados. Como provedor de dados, eles permitem criar vários casos de uso e opções de preço para seus feeds. Além disso, pode ser uma boa estratégia criar alguns planos para cada feed de dados. Isso dá aos compradores opções diferentes de quando eles estão procurando dados para modelar ou enviar para um destino.

[Crie um ](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) feed de dados para selecionar  [!UICONTROL Plan Types].

![](assets/plan_types.png)

## Tipos de Plano e Opções de Caso de Uso {#plan-types-use-cases}

<!-- c_feed_options.xml -->

As configurações [!UICONTROL Use Case] permitem que os vendedores controlem como os compradores podem usar seus dados.

### Segmentos e sobreposição

Um caso de uso **[!UICONTROL Segments and Overlap]** cria um plano que permite aos compradores comparar dados de características em um [relatório de sobreposição de característica por característica](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report). Além disso, os compradores podem adicionar seus dados aos segmentos e fazer comparações com os relatórios [segmento para característica](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) e [segmento para segmento](../../../reporting/dynamic-reports/segment-segment-overlap-report.md).

Cada feed de dados deve incluir pelo menos um [!UICONTROL Segments and Overlap] caso de uso. Os compradores não podem assinar outros planos em um feed de dados se o feed não contiver um caso de uso [!UICONTROL Segments and Overlap], sozinho ou em combinação com outro caso de uso.

Comparações de sobreposição podem ajudar os compradores:

* **Estender o alcance do público-alvo:** as sobreposições baixas sugerem que suas características contêm usuários que o comprador não viu antes. Como resultado, os compradores podem desejar que essas características adicionem novos usuários aos segmentos de público-alvo.
* **Aprimorar públicos-alvo existentes:** a alta sobreposição sugere que suas características contêm usuários semelhantes àqueles que um comprador já conhece. Como resultado, os compradores podem desejar que essas características ajudem a fazer melhorias direcionadas e incrementais para públicos desenvolvidos.

Aplique o seguinte preço a este caso de uso:

* Unidade de Medida: Taxa fixa
* Preço: Gratuito ($0,00)

### Modelagem

Um caso de uso **[!UICONTROL Modeling]** cria um plano que permite aos compradores comparar suas características com as delas com [modelagem algorítmica](../../../features/algorithmic-models/understanding-models.md#understanding-models). Os compradores observam os resultados do modelo para encontrar novos públicos-alvo nos dados que compartilham atributos de conversão semelhantes aos seus. Aplique o seguinte preço a este caso de uso:

* Unidade de Medida: Taxa fixa
* Preço: Preço descontado ou à taxa de mercado

### Activation

Um caso de uso **[!UICONTROL Activation]** permite que os compradores enviem dados para um [destino](../../../features/destinations/destinations.md). Com esse caso de uso, os compradores não podem comparar dados com um relatório de sobreposição ou em um modelo algorítmico. Aplique o seguinte preço a este caso de uso:

* Unidade de Medida: [!DNL CPM]
* Preço: [!DNL CPM] taxa de mercado

## Opções de faturamento e preço {#billing}

As opções de faturamento e preço controlam como os compradores pagam pelos seus dados.

<table id="table_CCEAAF24295942EA82F20753827D1A23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opção </th> 
   <th colname="col2" class="entry"> Descrição </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Ciclo de Faturamento</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Mensalmente em </span></b> Arrearsis a única opção. O ciclo de faturamento termina no décimo dia de cada mês. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Unidade de medida</span></b> </td> 
   <td colname="col2">Cobre compradores de dados em uma taxa CPM ou taxa fixa. 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> Com os preços do CPM, os compradores de dados são solicitados a relatar o uso automaticamente. </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">Com o preço de taxa fixa, os compradores de dados não reportam o uso porque são cobrados de uma taxa fixa. </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Preço</span></b> </td>
   <td colname="col2"> O montante que um vendedor cobra ao comprador como taxa CPM ou preço fixo de taxa, em dólares. </td>
  </tr> 
 </tbody> 
</table>

## Notas do Plano {#plan-notes}

No campo **[!UICONTROL Additional Notes]**, reserve um tempo para descrever cada plano de dados em um feed. Uma descrição boa e breve ajuda os compradores a entender o conteúdo ou a finalidade de cada plano em um feed de dados. Os compradores podem ler o feed de dados e as descrições do plano conforme pesquisam ou avaliam novas fontes de dados.

## Gerenciar solicitações privadas do feed de dados {#manage-private-requests}

Fluxos de trabalho do provedor para gerenciar solicitações de feed privados de compradores.

Para revisar, aprovar ou rejeitar solicitações de comprador, vá para [!UICONTROL My Shared Data] e:

<!-- t_private_feed_workflows.xml -->

1. Clique no nome do feed de dados privado.
2. Clique em **[!UICONTROL Access Requests]** para revisar todos os compradores que desejam acessar o feed de dados.
3. Na seção [!UICONTROL Allow Access] de cada caixa de solicitação, clique na marca de seleção para aprovar uma solicitação ou no X para negar acesso.
4. Confirme ou cancele a ação selecionada na janela pop-up de confirmação.

## Descontos para provedores de dados {#discounts}

Em [!UICONTROL Audience Marketplace], os descontos permitem reduzir o preço publicado de um feed de dados para assinantes individuais. É possível oferecer descontos para assinantes que enviaram uma solicitação de assinatura ou para assinantes que solicitaram detalhes sobre um feed de dados. Os descontos se aplicam a [!DNL CPM] e feeds de taxa fixa. Os descontos podem ser úteis quando você deseja fornecer incentivos de assinatura para novos clientes ou recompensar a fidelidade dos clientes.

## Aplicar descontos a um feed de dados {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

Para descontar um feed, adicione um valor de desconto como % ao campo de desconto e confirme suas alterações. Os provedores de dados podem descontar um feed de dados em [!UICONTROL Audience Marketplace] de:

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

Nesses exemplos, o vendedor adicionou 10% de desconto ao feed de dados [!UICONTROL Software Audience].

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Revisar feeds descontados {#review-discounted-feeds}

Os provedores de dados podem ver todos os assinantes e feeds com desconto em **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**.

![](assets/subscribers.png)

>[!MORELIKETHIS]
>
>* [Feeds de dados privados](../../../features/audience-marketplace/marketplace-private-feeds.md)

