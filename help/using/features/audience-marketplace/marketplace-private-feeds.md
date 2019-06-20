---
description: Um feed de dados privados é uma opção que permite aos provedores limitar o acesso do comprador aos seus dados. Fornecedores de dados e compradores devem analisar essas informações antes de criar e assinar feeds de dados privados.
seo-description: Um feed de dados privados é uma opção que permite aos provedores limitar o acesso do comprador aos seus dados. Fornecedores de dados e compradores devem analisar essas informações antes de criar e assinar feeds de dados privados.
seo-title: Feeds de dados privados
solution: Audience Manager
title: Feeds de dados privados
uuid: e 4 ca 59 ca-bbc 9-4897-9374-8 f 3 d 54 b 2 beee
translation-type: tm+mt
source-git-commit: 21b2505ac6cdf97b401bf0b0ac80bf1964f084b8

---


# Feeds de dados privados {#private-data-feeds}

Um feed de dados privados é uma opção que permite aos provedores limitar o acesso do comprador aos seus dados. Fornecedores de dados e compradores devem analisar essas informações antes de criar e assinar feeds de dados privados.

<!-- c_marketplace_privatefeed.xml -->

## Private Data Feeds for Providers {#private-data-feeds-providers}

Como provedor, os feeds de dados podem ser públicos ou privados. Um feed de dados privados permite limitar o acesso do comprador aos seus dados, incluindo o nome do vendedor de dados. Você pode criar um feed de dados privados para oferecer transações especiais, descontos ou quando a privacidade e o controle de acesso são importantes. Com um feed de dados privados, você pode analisar e aprovar solicitações de comprador. Depois de aprovar uma solicitação, o feed é semelhante a um feed de dados público ao comprador. You can view and manage all your feeds in **[!UICONTROL Audience Marketplace > My Shared Data]**. Como mostrado abaixo, esse tipo de feed é marcado como &quot;Privado&quot; na coluna de status.

![](assets/my_shared_data.png)

### Gerenciamento de solicitações de feed

Clicking the name of a private data feed from [!UICONTROL My Shared Data] takes you to a page that contains several tabs. Clique em uma guia para gerenciar suas solicitações de feed de dados privados.

![](assets/shared_data_tabs.png)

A tabela a seguir define a função ou as funções fornecidas por cada guia de ação.

<table id="table_AFB429CA52A34658859448D9A5215F9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tabulação </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Assinantes atuais</span></b> </p> </td> 
   <td colname="col2"> <p>Lista os compradores aprovados que assinaram um feed de dados privados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Assinantes potenciais</span></b> </p> </td> 
   <td colname="col2"> <p>Lista compradores aprovados que não assinaram um feed de dados privados. </p> <p>Uma aprovação permite que os compradores visualizem um feed de dados como se fossem público. Isso lhes dá a oportunidade de analisar e avaliar seus feeds antes de assinar. Você também pode oferecer descontos em feeds de dados para compradores listados como assinantes potenciais. Once the buyer subscribes, their profile moves to <b><span class="uicontrol"> Current Subscribers</span></b>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Solicitações de acesso</span></b> </p> </td>
   <td colname="col2"> <p>Lista novas solicitações de assinatura para um feed de dados privados. Clique nessa guia para analisar, aprovar ou rejeitar solicitações de comprador. </p>
    <ul id="ul_BE0A835A90B14C05B3F63226B79D052D"> 
     <li id="li_2C5686CEB6F4430BA18AED5AD75C330A">Approved buyers move to <b><span class="uicontrol"> Potential Subscribers</span></b>. </li>
     <li id="li_929591FCF81E43A3881813BDBD3AC278">Rejected buyers move to <b><span class="uicontrol"> Denied Access</span></b>. </li>
    </ul> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Solicitações de detalhes</span></b> </p> </td>
   <td colname="col2"> <p>Lista os compradores aprovados que ainda não assinaram um feed de dados e solicitou mais informações sobre os feeds. </p> <p>Uma aprovação permite que os compradores visualizem um feed de dados como se fossem público. Isso lhes dá a oportunidade de analisar e avaliar seus feeds antes de assinar. Também é possível oferecer descontos em feeds de dados para compradores que solicitam acesso. Responder a uma solicitação de detalhes remove o perfil de comprador desta guia. If they haven't subscribed, the buyer profile is still in <b><span class="uicontrol"> Potential Subscribers</span></b>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Acesso negado</span></b> </p> </td> 
   <td colname="col2"> <p>Lista solicitações de assinatura rejeitadas para um feed de dados privados. </p> <p>To re-approve denied buyers, change the <span class="wintitle"> Rejection Status</span> to <b><span class="uicontrol"> Allow</span></b>. This moves the buyer to <b><span class="uicontrol"> Potential Subscribers</span></b>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Próximas etapas

A documentação a seguir pode ajudá-lo a começar a usar feeds de dados privados.

* [Criar um feed de dados público ou privado](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed)
* [Revisar, aprovar ou rejeitar solicitações de feed privado](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests)
* [Feeds de dados privados para compradores](../../features/audience-marketplace/marketplace-private-feeds.md#private-data-feeds-for-buyers)

## Private Data Feeds for Buyers {#private-data-feeds-for-buyers}

As a buyer, private data feeds appear in the [Marketplace](../../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#about-marketplace) like any other offer. No entanto, nesse caso, a lista de feed não mostra informações de resumo para características, usuários exclusivos e sobreposição do usuário. Also, the data seller has an option to show or hide their name in the [!UICONTROL Provider] column of the [!UICONTROL Marketplace] list. Depois que o vendedor aprovar sua solicitação de assinatura, todos os dados em um feed privado estarão disponíveis para você (funciona exatamente como um feed público). The [!UICONTROL Marketplace] example below lists the 3 different feed types available to you as a buyer.

![](assets/buyer_marketplace.png)

Os tipos de feed incluem:

A tabela descreve como esses diferentes tipos de feed mostram ou ocultam dados.

<table id="table_41D4A798ACF548A3A03ACB427CA4652D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de feed </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Público</span></b> </p> </td> 
   <td colname="col2"> <p>O nome, a característica e os dados exclusivos do provedor são exibidos na lista. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Privado sem marca</span></b> </p> </td> 
   <td colname="col2"> <p>O nome do provedor é definido como "Vendedor privado" e não é possível visualizar contagens de características, dados exclusivos e dados de sobreposição de característica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Privado com marca</span></b> </p> </td> 
   <td colname="col2"> <p>O nome do provedor aparece na lista, mas não é possível visualizar contagens de características, dados exclusivos e dados de sobreposição de característica. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Próximas etapas

Consulte [Assine um feed de dados privados](../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) para solicitar acesso.

## How to set up the Sharing Relationship between Data Provider and Data Buyer {#set-up-sharing-relationship}

### Etapa 1 - Ativação - Provedor de dados e comprador de dados

A primeira etapa do processo requer intervenção da Adobe Consulting ou do Atendimento ao cliente. O provedor de dados e o comprador de dados devem entrar em contato com o Adobe Consulting ou o Atendimento ao cliente para solicitar a ativação.

### Etapa 2 - Provedor de dados - Criar nova fonte de dados

Na conta do Audience Manager, crie uma nova fonte de dados de cookie com:

* **ID do Audience Manager** como a chave de entrada;
* The **Share Enabled** option checked.

![](assets/create-datasource.png)

After you click **Save**, a new subfolder is automatically created in **Traits Storage &gt; 3rd Party Data**.

![](assets/folder-structure.png)

### Etapa 3 - Provedor de dados - Identificar características do compartilhamento

Nesta etapa, você identifica as características que deseja compartilhar com o seu parceiro. Você pode criar novos traços ou editar características existentes. Em qualquer caso, você precisa das características:

* Para ser associado à fonte de dados criada como parte da etapa 2.
* Para ser armazenado na subpasta recém-criada, em dados de terceiros.

Read more about [creating traits](/help/using/features/traits/create-onboarded-rule-based-traits.md) and [editing traits](/help/using/features/traits/manage-trait-rules.md#edit-trait).

### Etapa 4 - Provedor de dados - Criar feed de dados

Em seguida, crie um feed de dados para compartilhar suas características com o comprador de dados. Refer to [Create a Public or Private Data Feed](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md) for instructions on how to create a data feed.

>[!IMPORTANT]
>
>Em Configurações, selecione a opção Privado. Se você definir esse campo como Público, qualquer cliente do Audience Marketplace poderá assinar o feed.

![](assets/create-data-feed.png)

### Etapa 5 - Comprador de dados - Solicitar acesso

Go to **Audience Marketplace &gt; Marketplace**. Pesquise pelo feed de dados criado pelo provedor de dados na etapa anterior. Click **Request Access**. O contato designado do lado do provedor de dados receberá uma notificação por email. See also, [Subscribe to a Private Data Feed](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed).

### Etapa 6 - Provedor de dados - Conceder acesso

Go to **Audience Marketplace &gt; My Shared Data** and search for the feed you created in step 4. Click into the new access request and click **Allow Access** to approve the request. See also, [Review, Approve, or Reject Private Feed Requests](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests).

### Etapa 7 - Comprador de dados - Ativar assinatura

After the data provider grants access to the data feed, you can see the feed in your account in **Audience Marketplace &gt; Marketplace**. Review the details, turn the Subscription button ON, and click **Review &amp; Subscribe**. See [Storage for Subscribed Data Feeds](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#find-subscribed-data-fee) for information on where to find the 3rd party traits.

Observe que esses traços só podem ser editados na conta do provedor de dados.




