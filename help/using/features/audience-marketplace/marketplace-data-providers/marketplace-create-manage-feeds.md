---
description: Um feed de dados exige um nome, uma descrição, uma fonte de dados e um tipo de plano. Os feeds são desativados até que você salve e ative o feed. Configure feeds de dados públicos ou privados em Audience Marketplace > Meus dados compartilhados. Disponível somente para vendedores de dados.
seo-description: A data feed requires a name, description, data source, and a plan type. Feeds are disabled until you save and activate the feed. Set up public or private data feeds in Audience Marketplace > My Shared Data. Available to data sellers only.
seo-title: Create, Price, and Manage Data Feeds
solution: Audience Manager
title: Criar, precificar e gerenciar feeds de dados
uuid: e28c20b3-33fc-4485-8ee9-8530d126f741
feature: Audience Marketplace
exl-id: e8605e94-e62a-430c-9aef-875f995fb436
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '1257'
ht-degree: 2%

---

# Criar, precificar e gerenciar feeds de dados {#create-price-and-manage-data-feeds}

## Criar um feed de dados público ou privado {#create-public-private-data-feed}

Um feed de dados exige um nome, uma descrição, uma fonte de dados e um tipo de plano. Os feeds são desativados até que você salve e ative o feed. Configurar feeds de dados públicos ou privados no **[!UICONTROL Audience Marketplace > My Shared Data]**. Disponível somente para vendedores de dados.

<!-- t_data_feed.xml -->

Você deve ter direitos de administrador para criar um feed de dados público ou privado.
Para criar um feed de dados:

1. Clique em **[!UICONTROL New Data Feed]**.
1. Nomeie o feed de dados. Os compradores de dados podem pesquisar seu feed com base no nome.
1. Forneça uma breve descrição (máximo de 255 caracteres).

   Uma boa descrição deve descrever o feed com precisão. Por exemplo, você pode incluir texto para categorias de marketing, demografia e cobertura geográfica (por exemplo, [!DNL US] ou América do Norte). O texto de descrição pode ser pesquisado e ajuda os compradores a encontrar ou avaliar o feed. Uma boa descrição é uma parte importante para atrair assinantes para o feed de dados.
1. Selecione uma fonte de dados na **[!UICONTROL Data Source]** opções. Os feeds de dados são limitados a uma única fonte de dados. Não é possível atribuir várias fontes de dados ao mesmo feed de dados.

   >[!IMPORTANT]
   >
   >Quaisquer características atuais e futuras pertencentes a essa fonte de dados serão compartilhadas com seus compradores de dados, como parte desse feed.

1. Entrada [!UICONTROL Plan Types], selecione as opções que deseja usar e clique em **[!UICONTROL Add Plan]**.

   Os feeds podem conter vários planos. Os planos podem conter vários casos de uso. Para obter detalhes, consulte [Tipos de plano para feeds de dados](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types).

1. Clique em **[!UICONTROL Save]** para salvar o feed de dados *sem* ativando-o.
1. Para salvar e ativar um feed de dados:
   1. Mova as **[!UICONTROL Availability]** controle deslizante para **[!UICONTROL Active]**.
   1. Clique em **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >* Os feeds de dados salvos e ativados não podem ser excluídos.
   >* Os compradores veem somente feeds ativos.


### Opcional: Criar um Feed de Dados Privado

No [!UICONTROL Settings] mova o controle deslizante para:

* **[!UICONTROL Private]** e **[!UICONTROL Branded]**: O do comprador [!UICONTROL Marketplace] lista mostra o nome do vendedor na coluna provedor e todos os outros dados ficam ocultos.

* **[!UICONTROL Private]** e **[!UICONTROL Unbranded]**: O do comprador [!UICONTROL Marketplace] A lista mostra somente o nome e a descrição do feed de dados. O nome do provedor de dados aparece como [!UICONTROL Private Seller].

Para ver a aparência de um feed privado para os compradores, consulte a seção compradores em [Feeds de dados privados](../../../features/audience-marketplace/marketplace-private-feeds.md).

## Desativar o feed de dados de um assinante {#deactivate-data-feed}

Como um [!UICONTROL Audience Marketplace] provedor de dados, você pode revogar o acesso do comprador a um feed de dados assinado. Você pode querer remover um comprador de um feed por motivos como atraso de pagamento/não pagamento de taxas ou se eles usarem os dados de características incorretamente.

<!-- marketplace-deactiva4te-subscribers.xml -->

Para revogar um assinante:

1. Entrada [!UICONTROL My Shared Data], localize o feed que o assinante está usando.

   >[!NOTE]
   >
   >Os feeds de dados com contas vencidas são sinalizados com um ícone de triângulo/ponto de exclamação.

1. No [!UICONTROL Subscribers] clique no número azul que conta os assinantes para esse feed. Isso abre a página de detalhes da assinatura.
1. Mova as **[!UICONTROL Subscription]** controle deslizante para **[!UICONTROL Off]**. Isso abre uma janela de diálogo de confirmação.
1. No [!UICONTROL Confirmation] pop, clique **[!UICONTROL Yes]** para desativar uma assinatura ou **[!UICONTROL Cancel]** para encerrar sem fazer alterações na assinatura.

### O que Acontece Depois que Você Desativa um Assinante

A revogação do acesso a um feed de dados envia um email de notificação para todos os usuários administradores na conta do comprador de dados. O email inclui um anexo que lista características revogadas. Essa lista ajuda os assinantes a encontrar e remover características desativadas de seus segmentos e modelos.

### Desativação de Faturamento e Feed

Depois de remover o acesso a um feed de dados, os assinantes são responsáveis pelas tarifas do mês anterior ou atual, dependendo de quando você desativou o feed.

## Tipos de plano para feeds de dados {#plan-types}

[!DNL Plan types] são componentes essenciais de uma [!UICONTROL Audience Marketplace] feed de dados. Como provedor de dados, eles permitem criar vários casos de uso e opções de preço para seus feeds. Além disso, pode ser uma boa estratégia criar alguns planos para cada feed de dados. Isso oferece aos compradores opções diferentes para escolher quando estão procurando dados para modelar ou enviar para um destino.

[Criar um feed de dados](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) para selecionar [!UICONTROL Plan Types].

![](assets/plan_types.png)

## Tipos de Plano e Opções de Caso de Uso {#plan-types-use-cases}

<!-- c_feed_options.xml -->

A variável [!UICONTROL Use Case] as configurações permitem que os vendedores controlem como os compradores podem usar seus dados.

### Segmentos e sobreposição

A **[!UICONTROL Segments and Overlap]** caso de uso cria um plano que permite aos compradores comparar os dados de características em uma [relatório de sobreposição de característica por característica](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report). Além disso, os compradores podem adicionar seus dados aos segmentos e fazer comparações com a [segmento por característica](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) e [segmento por segmento](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) relatórios.

Cada feed de dados deve incluir pelo menos um [!UICONTROL Segments and Overlap] caso de uso. Os compradores não podem assinar outros planos em um feed de dados se o feed não contiver uma [!UICONTROL Segments and Overlap] caso de uso, sozinho ou em combinação com outro caso de uso.

As comparações de sobreposição podem ajudar os compradores a:

* **Estender alcance do público:** A baixa sobreposição sugere que suas características contêm usuários que o comprador não viu antes. Como resultado, os compradores podem querer que essas características adicionem novos usuários aos segmentos de público-alvo.
* **Melhorar públicos existentes:** A alta sobreposição sugere que suas características contêm usuários semelhantes àqueles que um comprador já conhece. Como resultado, os compradores podem querer que essas características ajudem a fazer melhorias direcionadas e incrementais nos públicos desenvolvidos.

Avalie esse caso de uso da seguinte maneira:

* Unidade de Medida: Taxa fixa
* Preço: Gratuito ($0.00)

### Modelagem

A **[!UICONTROL Modeling]** caso de uso cria um plano que permite aos compradores comparar suas características com as deles [modelagem algorítmica](../../../features/algorithmic-models/understanding-models.md#understanding-models). Os compradores analisam os resultados do modelo para encontrar novos públicos-alvo em seus dados que compartilham atributos de conversão semelhantes aos seus próprios. Avalie esse caso de uso da seguinte maneira:

* Unidade de Medida: Taxa fixa
* Preço: Descontado ou preço de taxa de mercado

### Ativação

Um **[!UICONTROL Activation]** caso de uso permite que os compradores enviem dados para um [destino](../../../features/destinations/destinations.md). Com esse caso de uso, os compradores não podem comparar os dados com um relatório de sobreposição ou em um modelo algorítmico. Avalie esse caso de uso da seguinte maneira:

* Unidade de Medida: [!DNL CPM]
* Preço: [!DNL CPM] taxa de mercado

## Opções de Preço e Faturamento {#billing}

As opções de preço e faturamento controlam como os compradores pagam pelos seus dados.

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
   <td colname="col2"> <b><span class="uicontrol"> Mensal em atraso</span></b> O é a única opção. O ciclo de faturamento termina no décimo dia de cada mês. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Unidade de Medida</span></b> </td> 
   <td colname="col2">Cobre aos compradores de dados uma taxa de CPM ou taxa única. 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> Com os preços do CPM, os compradores de dados precisam relatar o uso por conta própria. </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">Com preços de taxa única, os compradores de dados não relatam o uso porque são cobrados uma taxa fixa. </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Preço</span></b> </td>
   <td colname="col2"> A quantia que um vendedor cobra do comprador como taxa CPM ou preço de taxa única, em dólares. </td>
  </tr> 
 </tbody> 
</table>

## Notas do Plano {#plan-notes}

No **[!UICONTROL Additional Notes]** leve algum tempo para descrever cada plano de dados em um feed. Uma boa e breve descrição ajuda os compradores a entender o conteúdo ou a finalidade de cada plano em um feed de dados. Os compradores podem ler o feed de dados e as descrições do plano enquanto pesquisam ou avaliam novas fontes de dados.

## Gerenciar solicitações privadas de feed de dados {#manage-private-requests}

Fluxos de trabalho de provedor para gerenciar solicitações de feed privadas de compradores.

Para revisar, aprovar ou rejeitar solicitações de compradores, vá para [!UICONTROL My Shared Data] e:

<!-- t_private_feed_workflows.xml -->

1. Clique no nome do feed de dados privado.
2. Clique em **[!UICONTROL Access Requests]** para revisar todos os compradores que desejam acessar seu feed de dados.
3. No [!UICONTROL Allow Access] de cada caixa de solicitação, clique na marca de seleção para aprovar uma solicitação ou no X para negar acesso.
4. Confirme ou cancele a ação selecionada na janela pop-up de confirmação.

## Descontos para provedores de dados {#discounts}

Entrada [!UICONTROL Audience Marketplace], os descontos permitem reduzir o preço publicado de um feed de dados para assinantes individuais. Você pode oferecer descontos a assinantes que enviaram uma solicitação de assinatura ou que solicitaram detalhes sobre um feed de dados. Os descontos se aplicam a [!DNL CPM] forfetárias. Descontos podem ser úteis quando você quer fornecer incentivos de assinatura para novos clientes ou recompensar a fidelidade do cliente.

## Aplicar descontos a um feed de dados {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

Para descontar um feed, adicione um valor de desconto como uma % ao campo de desconto e confirme as alterações. Os provedores de dados podem descontar os feeds de dados no [!UICONTROL Audience Marketplace] de:

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

Nesses exemplos, o vendedor adicionou 10% de desconto à [!UICONTROL Software Audience] feed de dados.

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Revisar feeds com desconto {#review-discounted-feeds}

Os provedores de dados podem visualizar todos os seus assinantes e feeds com desconto na **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**.

![](assets/subscribers.png)

>[!MORELIKETHIS]
>
>* [Feeds de dados privados](../../../features/audience-marketplace/marketplace-private-feeds.md)

