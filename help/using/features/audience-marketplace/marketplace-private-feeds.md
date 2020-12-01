---
description: Um feed de dados privado é uma opção que permite aos provedores limitar o acesso do comprador aos seus dados. Os provedores de dados e compradores devem revisar essas informações antes de criar e assinar feeds de dados privados.
seo-description: Um feed de dados privado é uma opção que permite aos provedores limitar o acesso do comprador aos seus dados. Os provedores de dados e compradores devem revisar essas informações antes de criar e assinar feeds de dados privados.
seo-title: Feeds de dados privados
solution: Audience Manager
title: Feeds de dados privados
uuid: e4ca59ca-bbc9-4897-9374-8f3d54b2beee
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1090'
ht-degree: 1%

---


# Feeds de dados privados {#private-data-feeds}

Um feed de dados privado é uma opção que permite aos provedores limitar o acesso do comprador aos seus dados. Os provedores de dados e compradores devem revisar essas informações antes de criar e assinar feeds de dados privados.

<!-- c_marketplace_privatefeed.xml -->

## Feeds de dados privados para provedores {#private-data-feeds-providers}

Como provedor, seus feeds de dados podem ser públicos ou privados. Um feed de dados privado permite limitar o acesso do comprador aos seus dados, incluindo o nome do vendedor de dados. Você pode criar um feed de dados privados para oferta de negócios especiais, descontos ou quando privacidade e controle de acesso forem importantes. Com um feed de dados privados, você pode revisar e aprovar solicitações do comprador. Depois de aprovar uma solicitação, o feed se parece com um feed de dados público para o comprador. Você pode visualização e gerenciar todos os seus feeds em **[!UICONTROL Audience Marketplace > My Shared Data]**. Como mostrado abaixo, esse tipo de feed é marcado como &quot;Privado&quot; na coluna de status.

![](assets/my_shared_data.png)

### Gerenciando solicitações de feed

Clicar no nome de um feed de dados privado de [!UICONTROL My Shared Data] o leva até uma página que contém várias guias. Clique em uma guia para gerenciar suas solicitações de feed de dados privados.

![](assets/shared_data_tabs.png)

A tabela a seguir define a função ou funções fornecidas por cada guia de ação.

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
   <td colname="col2"> <p>As listas aprovaram compradores que se inscreveram em um feed de dados privado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Assinantes potenciais</span></b> </p> </td> 
   <td colname="col2"> <p>As listas aprovaram compradores que não se inscreveram em um feed de dados privado. </p> <p>Uma aprovação permite que os compradores visualizações um feed de dados como se fosse público. Isso lhes dá a oportunidade de revisar e avaliar seus feeds antes de assinar. Você também pode oferta descontos em feeds de dados para compradores listados como potenciais assinantes. Quando o comprador se inscreve, seu perfil se move para <b><span class="uicontrol"> Assinantes atuais</span></b>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Solicitações de acesso</span></b> </p> </td>
   <td colname="col2"> <p>Lista novas solicitações de subscrição para um feed de dados privado. Clique nesta guia para revisar, aprovar ou rejeitar solicitações do comprador. </p>
    <ul id="ul_BE0A835A90B14C05B3F63226B79D052D"> 
     <li id="li_2C5686CEB6F4430BA18AED5AD75C330A">Compradores aprovados mudam para <b><span class="uicontrol"> Assinantes potenciais</span></b>. </li>
     <li id="li_929591FCF81E43A3881813BDBD3AC278">Compradores rejeitadas mudam para <b><span class="uicontrol"> Acesso Negado</span></b>. </li>
    </ul> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Solicitações de Detalhes</span></b> </p> </td>
   <td colname="col2"> <p>O Lista aprovou compradores que ainda não se inscreveram em um feed de dados e solicitaram mais informações sobre seus feeds. </p> <p>Uma aprovação permite que os compradores visualizações um feed de dados como se fosse público. Isso lhes dá a oportunidade de revisar e avaliar seus feeds antes de assinar. Você também pode oferta descontos nos feeds de dados para compradores que solicitem acesso. Responder a uma solicitação de detalhes remove o perfil comprador desta guia. Se eles não se inscreveram, o perfil comprador ainda está em <b><span class="uicontrol"> Assinantes potenciais</span></b>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Acesso negado</span></b> </p> </td> 
   <td colname="col2"> <p>O Lista rejeitou solicitações de subscrição para um feed de dados privado. </p> <p>Para reaprovar compradores negados, altere o <span class="wintitle"> Status de Rejeição</span> para <b><span class="uicontrol"> Permitir</span></b>. Isso move o comprador para <b><span class="uicontrol"> Assinantes potenciais</span></b>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Próximas etapas

A documentação a seguir pode ajudá-lo a começar a usar feeds de dados privados.

* [Criar um feed de dados público ou privado](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed)
* [Revisar, Aprovar ou Rejeitar Solicitações de Feed Privado](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests)
* [Feeds de dados privados para compradores](../../features/audience-marketplace/marketplace-private-feeds.md#private-data-feeds-for-buyers)

## Feeds de dados privados para compradores {#private-data-feeds-for-buyers}

Como comprador, os feeds de dados privados são exibidos no [Marketplace](../../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#about-marketplace) como qualquer outra oferta. Entretanto, nesse caso, a lista de feed não mostra informações de resumo das características, usuários únicos e sobreposição de usuários. Além disso, o vendedor de dados tem uma opção para mostrar ou ocultar seu nome na coluna [!UICONTROL Provider] da lista [!UICONTROL Marketplace]. Depois que o vendedor aprovar sua solicitação de subscrição, todos os dados em um feed privado ficarão disponíveis para você (funciona como um feed público). O exemplo [!UICONTROL Marketplace] abaixo lista os 3 diferentes tipos de feed disponíveis para você como comprador.

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
   <td colname="col2"> <p>O nome do provedor é definido como "Vendedor Privado" e você não pode ver as contagens de características, dados únicos e dados de sobreposição de características. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Privado com marca</span></b> </p> </td> 
   <td colname="col2"> <p>O nome do provedor é exibido na lista, mas não é possível visualizar as contagens de características, os dados exclusivos e os dados de sobreposição de características. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Próximas etapas

Consulte  [Assine um ](../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) feed de dados privados para solicitar acesso.

## Como configurar a relação de compartilhamento entre o Provedor de dados e o Data Buyer {#set-up-sharing-relationship}

### Etapa 1 - Ativação - Provedor de dados e Data Buyer

A primeira etapa do processo requer a intervenção da Adobe Consulting ou do Atendimento ao cliente. O provedor de dados e o comprador de dados devem entrar em contato com a Adobe Consulting ou com o Atendimento ao cliente para solicitar a ativação.

### Etapa 2 - Provedor de dados - Criar nova fonte de dados

Na sua conta do Audience Manager, crie uma nova fonte de dados de cookie com:

* **Audience Manager** ID como a chave de entrada;
* A opção **Compartilhar ativado** está marcada.

![](assets/create-datasource.png)

Depois de clicar em **Salvar**, uma nova subpasta será criada automaticamente em **Armazenamento de características > Dados de terceiros**.

![](assets/folder-structure.png)

### Etapa 3 - Provedor de dados - Identificar características para compartilhamento

Nesta etapa, você identifica as características que deseja compartilhar com seu parceiro. Você pode criar novas características ou editar características existentes. Em qualquer caso, você precisa das características:

* A ser associado à fonte de dados criada como parte da etapa 2.
* A ser armazenado na subpasta recém-criada, em dados de terceiros.

Leia mais sobre [criar características](/help/using/features/traits/create-onboarded-rule-based-traits.md) e [editar características](/help/using/features/traits/manage-trait-rules.md#edit-trait).

### Etapa 4 - Provedor de dados - Criar feed de dados

Em seguida, crie um feed de dados para compartilhar suas características com o comprador de dados. Consulte [Criar um feed de dados público ou privado](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md) para obter instruções sobre como criar um feed de dados.

>[!IMPORTANT]
>
>Em Configurações, selecione a opção Privado. Se você definir esse campo como Público, qualquer cliente Audience Marketplace poderá se inscrever no feed.

![](assets/create-data-feed.png)

### Etapa 5 - Data Buyer - Solicitar acesso

Vá para **Audience Marketplace > Marketplace**. Procure o feed de dados criado pelo provedor de dados na etapa anterior. Clique em **Solicitar acesso**. O contato designado do lado do provedor de dados receberá uma notificação por email. Consulte também, [Inscrever-se em um Feed de dados privado](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed).

### Etapa 6 - Provedor de dados - Conceder acesso

Vá para **Audience Marketplace > Meus dados compartilhados** e pesquise pelo feed criado na etapa 4. Clique na nova solicitação de acesso e clique em **Permitir acesso** para aprovar a solicitação. Consulte também [Revisar, Aprovar ou Rejeitar Solicitações de Feed Privado](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests).

### Etapa 7 - Comprador de dados - Ativar Subscrição

Depois que o provedor de dados conceder acesso ao feed de dados, você poderá ver o feed em sua conta em **Audience Marketplace > Marketplace**. Revise os detalhes, ative o botão de Subscrição e clique em **Revisar e assinar**. Consulte [Armazenamento para feeds de dados assinados](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#find-subscribed-data-fee) para obter informações sobre onde localizar as características de terceiros.

Observe que essas características só podem ser editadas na conta do provedor de dados.




