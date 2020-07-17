---
description: Um feed de dados requer um nome, uma descrição, uma fonte de dados e um tipo de plano. Os feeds são desativados até que você salve e ative o feed. Configure feeds de dados públicos ou privados em Audience Marketplace > Meus dados compartilhados. Disponível somente para vendedores de dados.
seo-description: Um feed de dados requer um nome, uma descrição, uma fonte de dados e um tipo de plano. Os feeds são desativados até que você salve e ative o feed. Configure feeds de dados públicos ou privados em Audience Marketplace > Meus dados compartilhados. Disponível somente para vendedores de dados.
seo-title: Criar, precificar e gerenciar feeds de dados
solution: Audience Manager
title: Criar, precificar e gerenciar feeds de dados
topic: DIL API
uuid: e28c20b3-33fc-4485-8ee9-8530d126f741
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 2%

---


# Criar, precificar e gerenciar feeds de dados {#create-price-and-manage-data-feeds}

## Criar um feed de dados público ou privado {#create-public-private-data-feed}

Um feed de dados requer um nome, uma descrição, uma fonte de dados e um tipo de plano. Os feeds são desativados até que você salve e ative o feed. Configure feeds de dados públicos ou privados em **[!UICONTROL Audience Marketplace > My Shared Data]**. Disponível somente para vendedores de dados.

<!-- t_data_feed.xml -->

Você deve ter direitos de administrador para criar um feed de dados público ou privado.
Para criar um feed de dados:

1. Clique em **[!UICONTROL New Data Feed]**.
1. Nomeie o feed de dados. Os compradores de dados podem pesquisar seu feed com base no nome.
1. Forneça uma breve descrição (máximo de 255 caracteres).

   Uma boa descrição deve descrever seu feed com precisão. Por exemplo, você pode incluir texto para categorias de marketing, demografia e cobertura geográfica (por exemplo, [!DNL US] ou América do Norte). O texto de descrição é pesquisável e ajuda os compradores a localizar ou avaliar seu feed. Uma boa descrição é uma parte importante para atrair assinantes para o feed de dados.
1. Selecione uma fonte de dados nas **[!UICONTROL Data Source]** opções. Os feeds de dados são limitados a uma única fonte de dados. Não é possível atribuir várias fontes de dados ao mesmo feed de dados.

   >[!IMPORTANT]
   >
   >Quaisquer características atuais e futuras pertencentes a essa fonte de dados serão compartilhadas com seus compradores de dados, como parte desse feed.

1. Em [!UICONTROL Plan Types], selecione as opções que deseja usar e clique em **[!UICONTROL Add Plan]**.

   Os feeds podem conter vários planos. Os planos podem conter vários casos de uso. Para obter detalhes, consulte Tipos de [plano para feeds](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types)de dados.

1. Clique em **[!UICONTROL Save]** para salvar seu feed de dados *sem* ativá-lo.
1. Para salvar e ativar um feed de dados:
   1. Mova o **[!UICONTROL Availability]** controle deslizante para **[!UICONTROL Active]**.
   1. Clique em **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >* Os feeds de dados salvos e ativados não podem ser excluídos.
   >* Os compradores veem apenas feeds ativos.


### Opcional: Criar um feed de dados privados

Na [!UICONTROL Settings] seção, mova o controle deslizante para:

* **[!UICONTROL Private]** e **[!UICONTROL Branded]**: A [!UICONTROL Marketplace] lista do comprador mostra o nome do vendedor na coluna do provedor e todos os outros dados estão ocultos.

* **[!UICONTROL Private]** e **[!UICONTROL Unbranded]**: A [!UICONTROL Marketplace] lista do comprador mostra somente o nome e a descrição do feed de dados. O nome do provedor de dados é exibido como [!UICONTROL Private Seller].

Para ver a aparência de um feed privado para os compradores, consulte a seção compradores nos Feeds [de dados](../../../features/audience-marketplace/marketplace-private-feeds.md)privados.

## Desativar o feed de dados de um assinante {#deactivate-data-feed}

Como um provedor [!UICONTROL Audience Marketplace] de dados, você pode revogar o acesso do comprador a um feed de dados inscrito. Você pode desejar remover um comprador de um feed por motivos como atraso no pagamento / não pagamento de taxas ou se ele usar dados de características incorretamente.

<!-- marketplace-deactiva4te-subscribers.xml -->

Para revogar um assinante:

1. Em [!UICONTROL My Shared Data], localize o feed que o assinante está usando.

   >[!NOTE]
   >
   >Os feeds de dados com contas vencidas são marcados com um ícone de triângulo/ponto de exclamação.

1. Na [!UICONTROL Subscribers] coluna, clique no número azul que conta os assinantes desse feed. Isso abre a página de detalhes da subscrição.
1. Mova o **[!UICONTROL Subscription]** controle deslizante para **[!UICONTROL Off]**. Isso abre uma janela de diálogo de confirmação.
1. No [!UICONTROL Confirmation] pop, clique **[!UICONTROL Yes]** para desativar uma subscrição ou **[!UICONTROL Cancel]** para encerrar sem fazer alterações na subscrição.

### O que acontece depois que você desativa um assinante

Revogar o acesso a um feed de dados envia um email de notificação para todos os usuários administradores na conta do comprador de dados. O email inclui um anexo que lista características revogadas. Essa lista ajuda os assinantes a localizar e remover características desativadas de seus segmentos e modelos.

### Faturamento e desativação do feed

Depois de remover o acesso a um feed de dados, os assinantes são responsáveis pelas taxas do mês anterior ou atual, dependendo de quando você desativou o feed.

## Tipos de plano para feeds de dados {#plan-types}

[!DNL Plan types] são componentes essenciais em um feed [!UICONTROL Audience Marketplace] de dados. Como provedor de dados, eles permitem que você crie vários casos de uso e opções de preço para seus feeds. Além disso, pode ser uma boa estratégia criar alguns planos para cada feed de dados. Isso dá aos compradores opções diferentes para escolher quando eles estão procurando dados para modelar ou enviar para um destino.

[Crie um feed](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) de dados para selecionar [!UICONTROL Plan Types].

![](assets/plan_types.png)

## Tipos de Plano e Opções de Caso de Uso {#plan-types-use-cases}

<!-- c_feed_options.xml -->

As [!UICONTROL Use Case] configurações permitem que os vendedores controlem como os compradores podem usar seus dados.

### Segmentos e sobreposição

Um caso de **[!UICONTROL Segments and Overlap]** uso cria um plano que permite aos compradores comparar os dados de características em um relatório [de sobreposição](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)característica-a-característica. Além disso, os compradores podem adicionar seus dados aos segmentos e fazer comparações com os relatórios [segmento a característica](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) e [segmento a segmento](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) .

Cada feed de dados deve incluir pelo menos um caso de [!UICONTROL Segments and Overlap] uso. Os compradores não podem assinar outros planos em um feed de dados se o feed não contiver um caso de [!UICONTROL Segments and Overlap] uso, seja por si só ou em combinação com outro caso de uso.

As comparações de sobreposição podem ajudar os compradores:

* **Amplie o alcance da audiência:** A baixa sobreposição sugere que suas características contêm usuários que o comprador não viu antes. Como resultado, os compradores podem desejar que essas características adicionem novos usuários aos seus segmentos de audiência.
* **Aprimorar audiências existentes:** A sobreposição alta sugere que suas características contêm usuários semelhantes àqueles que um comprador já conhece. Como resultado, os compradores podem querer que essas características ajudem a fazer melhorias direcionadas e incrementais para audiências desenvolvidas.

Coloque este caso de uso no preço a seguir:

* Unidade de Medida: Taxa fixa
* Preço: Gratuito ($0.00)

### Modelagem

Um caso de **[!UICONTROL Modeling]** uso cria um plano que permite aos compradores comparar seus traços com os deles com modelagem [](../../../features/algorithmic-models/understanding-models.md#understanding-models)algorítmica. Os compradores verificam os resultados do modelo para encontrar novas audiências em seus dados que compartilham atributos de conversão semelhantes aos seus. Coloque este caso de uso no preço a seguir:

* Unidade de Medida: Taxa fixa
* Preço: Preço com desconto ou taxa de mercado

### Activation

Um caso de **[!UICONTROL Activation]** uso permite que os compradores enviem dados para um [destino](../../../features/destinations/destinations.md). Com esse caso de uso, os compradores não podem comparar dados com um relatório de sobreposição ou em um modelo algorítmico. Coloque este caso de uso no preço a seguir:

* Unidade de Medida: [!DNL CPM]
* Preço: [!DNL CPM] taxa de mercado

## Opções de Faturamento e Preço {#billing}

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
   <td colname="col2"> <b><span class="uicontrol"> Mensalmente em Arrears</span></b> é a única opção. O ciclo de cobrança termina no décimo dia de cada mês. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Unidade de Medida</span></b> </td> 
   <td colname="col2">Cobrar compradores de dados em uma taxa CPM ou taxa fixa. 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> Com os preços do CPM, os compradores de dados precisam relatar o uso. </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">Com o preço de tarifa fixa, os compradores de dados não relatam o uso porque lhes é cobrada uma taxa fixa. </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Preço</span></b> </td>
   <td colname="col2"> O montante que um vendedor cobra ao comprador como taxa CPM ou preço fixo, em dólares. </td>
  </tr> 
 </tbody> 
</table>

## Notas do plano {#plan-notes}

No **[!UICONTROL Additional Notes]** campo, leve algum tempo para descrever cada plano de dados em um feed. Uma descrição boa e breve ajuda os compradores a entender o conteúdo ou a finalidade de cada plano em um feed de dados. Os compradores podem ler os feeds de dados e as descrições do plano à medida que pesquisam ou avaliam novas fontes de dados.

## Gerenciar solicitações de feed de dados privados {#manage-private-requests}

workflows do provedor para gerenciar solicitações de feed privadas de compradores.

Para revisar, aprovar ou rejeitar solicitações do comprador, vá para [!UICONTROL My Shared Data] e:

<!-- t_private_feed_workflows.xml -->

1. Clique no nome do feed de dados privados.
2. Clique em **[!UICONTROL Access Requests]** para revisar todos os compradores que desejam acessar seu feed de dados.
3. Na [!UICONTROL Allow Access] seção de cada caixa de solicitação, clique na marca de seleção para aprovar uma solicitação ou no X para negar o acesso.
4. Confirme ou cancele a ação selecionada no pop-up de confirmação.

## Descontos para provedores de dados {#discounts}

Em [!UICONTROL Audience Marketplace]outros, os descontos permitem reduzir o preço publicado de um feed de dados para assinantes individuais. Você pode oferta de descontos para assinantes que enviaram uma solicitação de subscrição ou para assinantes que solicitaram detalhes sobre um feed de dados. Os descontos se aplicam aos feeds de taxa fixa [!DNL CPM] e aos feeds de taxa fixa. Os descontos podem ser úteis quando você deseja fornecer incentivos subscrições para novos clientes ou recompensar a fidelidade dos clientes.

## Aplicar descontos a um feed de dados {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

Para descontar um feed, adicione um valor de desconto como % ao campo de desconto e confirme suas alterações. Os provedores de dados podem excluir feeds de dados de: [!UICONTROL Audience Marketplace]

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

Nesses exemplos, o vendedor adicionou 10% de desconto ao feed de [!UICONTROL Software Audience] dados.

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Revisar feeds descontados {#review-discounted-feeds}

Os provedores de dados podem ver todos os seus assinantes e feeds com desconto em **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**.

![](assets/subscribers.png)

>[!MORELIKETHIS]
>
>* [Feeds de dados privados](../../../features/audience-marketplace/marketplace-private-feeds.md)

