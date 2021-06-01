---
description: Um feed de dados privado é uma opção que permite que os provedores limitem o acesso do comprador aos seus dados. Os provedores de dados e compradores devem analisar essas informações antes de criar e assinar feeds de dados privados.
seo-description: Um feed de dados privado é uma opção que permite que os provedores limitem o acesso do comprador aos seus dados. Os provedores de dados e compradores devem analisar essas informações antes de criar e assinar feeds de dados privados.
seo-title: Feeds de dados privados
solution: Audience Manager
title: Feeds de dados privados
uuid: e4ca59ca-bbc9-4897-9374-8f3d54b2beee
feature: Audience Marketplace
exl-id: 34eb6194-c57b-4836-a6df-6889a2cec703
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 1%

---

# Feeds de dados privados {#private-data-feeds}

Um feed de dados privado é uma opção que permite que os provedores limitem o acesso do comprador aos seus dados. Os provedores de dados e compradores devem analisar essas informações antes de criar e assinar feeds de dados privados.

<!-- c_marketplace_privatefeed.xml -->

## Feeds de dados privados para provedores {#private-data-feeds-providers}

Como provedor, seus feeds de dados podem ser públicos ou privados. Um feed de dados privados permite limitar o acesso do comprador aos seus dados, incluindo o nome do vendedor de dados. Você pode criar um feed de dados privados para oferecer ofertas especiais, descontos ou quando o controle de privacidade e acesso for importante. Com um feed de dados privado, você pode revisar e aprovar solicitações de comprador. Depois de aprovar uma solicitação, o feed é semelhante a um feed de dados público ao comprador. Você pode visualizar e gerenciar todos os seus feeds em **[!UICONTROL Audience Marketplace > My Shared Data]**. Como mostrado abaixo, esse tipo de feed é marcado como &quot;Privado&quot; na coluna de status .

![](assets/my_shared_data.png)

### Gerenciar solicitações do feed

Clicar no nome de um feed de dados privado de [!UICONTROL My Shared Data] o direciona para uma página que contém várias guias. Clique em uma guia para gerenciar as solicitações de feed de dados privados.

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
   <td colname="col2"> <p>Lista compradores aprovados que assinaram um feed de dados privado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Assinantes potenciais</span></b> </p> </td> 
   <td colname="col2"> <p>Lista compradores aprovados que não assinaram um feed de dados privado. </p> <p>Uma aprovação permite que os compradores visualizem um feed de dados como se ele fosse público. Isso dá a eles a chance de revisar e avaliar seus feeds antes de se inscrever. Também é possível oferecer descontos nos feeds de dados para compradores listados como possíveis assinantes. Depois que o comprador se inscreve, seu perfil é movido para <b><span class="uicontrol"> Assinantes atuais</span></b>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Solicitações de acesso</span></b> </p> </td>
   <td colname="col2"> <p>Lista novas solicitações de assinatura para um feed de dados privado. Clique nesta guia para revisar, aprovar ou rejeitar solicitações de comprador. </p>
    <ul id="ul_BE0A835A90B14C05B3F63226B79D052D"> 
     <li id="li_2C5686CEB6F4430BA18AED5AD75C330A">Os compradores aprovados mudam para <b><span class="uicontrol"> Assinantes em potencial</span></b>. </li>
     <li id="li_929591FCF81E43A3881813BDBD3AC278">Compradores rejeitados mudam para <b><span class="uicontrol"> Acesso Negado</span></b>. </li>
    </ul> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Solicitações de Detalhes</span></b> </p> </td>
   <td colname="col2"> <p>Lista compradores aprovados que ainda não assinaram um feed de dados e solicitaram mais informações sobre seus feeds. </p> <p>Uma aprovação permite que os compradores visualizem um feed de dados como se ele fosse público. Isso dá a eles a chance de revisar e avaliar seus feeds antes de se inscrever. Também é possível oferecer descontos nos feeds de dados para compradores que solicitem acesso. Responder a uma solicitação de detalhes remove o perfil do comprador dessa guia. Se eles não tiverem assinado, o perfil do comprador ainda estará em <b><span class="uicontrol"> Assinantes em potencial</span></b>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Acesso negado</span></b> </p> </td> 
   <td colname="col2"> <p>Lista solicitações de assinatura rejeitadas para um feed de dados privado. </p> <p>Para aprovar novamente os compradores negados, altere o <span class="wintitle"> Status de Rejeição</span> para <b><span class="uicontrol"> Permitir</span></b>. Isso move o comprador para <b><span class="uicontrol"> Assinantes potenciais</span></b>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Próximas etapas

A documentação a seguir pode ajudar você a começar a usar os feeds de dados privados.

* [Criar um feed de dados público ou privado](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed)
* [Revisar, aprovar ou rejeitar solicitações de feed privado](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests)
* [Feeds de dados privados para compradores](../../features/audience-marketplace/marketplace-private-feeds.md#private-data-feeds-for-buyers)

## Feeds de dados privados para compradores {#private-data-feeds-for-buyers}

Como comprador, os feeds de dados privados aparecem no [Marketplace](../../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#about-marketplace) como qualquer outra oferta. No entanto, nesse caso, a lista de feeds não mostra informações de resumo de características, usuários únicos e sobreposição de usuários. Além disso, o vendedor de dados tem uma opção para mostrar ou ocultar seu nome na coluna [!UICONTROL Provider] da lista [!UICONTROL Marketplace]. Depois que o vendedor aprovar sua solicitação de assinatura, todos os dados em um feed privado serão disponibilizados a você (funcionam como um feed público). O exemplo [!UICONTROL Marketplace] abaixo lista os 3 tipos de feed diferentes disponíveis para você como comprador.

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
   <td colname="col2"> <p>O nome do provedor é definido como "Vendedor privado" e você não pode ver contagens de características, dados exclusivos e dados de sobreposição de características. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Privado com marca</span></b> </p> </td> 
   <td colname="col2"> <p>O nome do provedor aparece na lista, mas não é possível ver contagens de características, dados exclusivos e dados de sobreposição de características. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Próximas etapas

Consulte  [Assine um ](../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) Feed de dados privados para solicitar acesso.

## Como configurar o relacionamento de compartilhamento entre o provedor de dados e o comprador de dados {#set-up-sharing-relationship}

### Etapa 1 - Ativação - Provedor de dados e Comprador de dados

A primeira etapa do processo requer a intervenção da Adobe Consulting ou do Atendimento ao cliente. O provedor de dados e o comprador de dados devem entrar em contato com a Adobe Consulting ou com o Atendimento ao cliente para solicitar a ativação.

### Etapa 2 - Provedor de dados - Criar nova fonte de dados

Na sua conta do Audience Manager, crie uma nova fonte de dados de cookie com:

* **Audience Manager** ID como a chave de entrada;
* A opção **Share Enabled** está marcada.

![](assets/create-datasource.png)

Depois de clicar em **Salvar**, uma nova subpasta é criada automaticamente em **Armazenamento de características > Dados de terceiros**.

![](assets/folder-structure.png)

### Etapa 3 - Provedor de dados - Identificar características para compartilhamento

Nesta etapa, você identifica as características que deseja compartilhar com seu parceiro. Você pode criar novas características ou editar características existentes. Em qualquer caso, você precisa das características:

* Para ser associado à fonte de dados criada como parte da etapa 2.
* Para ser armazenado na subpasta recém-criada, em dados de terceiros.

Leia mais sobre [como criar características](/help/using/features/traits/create-onboarded-rule-based-traits.md) e [editar características](/help/using/features/traits/manage-trait-rules.md#edit-trait).

### Etapa 4 - Provedor de dados - Criar feed de dados

Em seguida, crie um feed de dados para compartilhar suas características com o comprador de dados. Consulte [Criar um feed de dados público ou privado](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md) para obter instruções sobre como criar um feed de dados.

>[!IMPORTANT]
>
>Em Configurações, selecione a opção Privado . Se você definir esse campo como Público, qualquer cliente do Audience Marketplace poderá assinar seu feed.

![](assets/create-data-feed.png)

### Etapa 5 - Comprador de dados - Solicitar acesso

Vá para **Audience Marketplace > Marketplace**. Procure o feed de dados criado pelo provedor de dados na etapa anterior. Clique em **Solicitar acesso**. O contato designado do lado do provedor de dados receberá uma notificação por email. Consulte também [Assinar um feed de dados privados](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed).

### Etapa 6 - Provedor de dados - Conceder acesso

Vá para **Audience Marketplace > Meus dados compartilhados** e pesquise o feed criado na etapa 4. Clique na nova solicitação de acesso e em **Permitir acesso** para aprovar a solicitação. Consulte também [Revisar, Aprovar ou Rejeitar solicitações de feed privado](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests).

### Etapa 7 - Comprador de dados - Ativar assinatura

Depois que o provedor de dados conceder acesso ao feed de dados, você poderá ver o feed em sua conta em **Audience Marketplace > Marketplace**. Revise os detalhes, ative o botão Subscription e clique em **Review &amp; Subscribe**. Consulte [Armazenamento para feeds de dados subscritos](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#find-subscribed-data-fee) para obter informações sobre onde encontrar as características de terceiros.

Observe que essas características só podem ser editadas na conta do provedor de dados.
