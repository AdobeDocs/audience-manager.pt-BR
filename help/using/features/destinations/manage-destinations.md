---
description: A página inicial de Destino lista todos os destinos de URL, cookie e servidor para servidor. Ele fornece recursos que permitem criar, editar, pesquisar e gerar relatórios sobre destinos. A página de aterrissagem está localizada em Dados de público-alvo > Destinos.
seo-description: A página inicial de Destino lista todos os destinos de URL, cookie e servidor para servidor. Ele fornece recursos que permitem criar, editar, pesquisar e gerar relatórios sobre destinos. A página de aterrissagem está localizada em Dados de público-alvo > Destinos.
seo-title: Gerenciar destinos
solution: Audience Manager
title: Gerenciar destinos
uuid: 6 b 66 ff 42-0075-49 a 7-a 58 f -7 f 8 ea 2295 fdc
translation-type: tm+mt
source-git-commit: 1d516c49a16c38adcc22827dc254da1ebada0734

---


# Manage Destinations {#manage-destinations}

The [!UICONTROL Destination] landing page lists all of your [!DNL URL], cookie, and server-to-server destinations. Ele fornece recursos que permitem criar, editar, pesquisar e gerar relatórios sobre destinos. The landing page is located in **[!UICONTROL Audience Data > Destinations]**.

## Default Landing Page {#default-landing-page}

<!-- destinations-home.xml -->

A página de aterrissagem padrão lista seus destinos, com base no tipo. É possível filtrar os destinos usando as quatro guias disponíveis:

* **Todos**: mostra todos os tipos de destinos.
* **Adobe Experience Cloud**: mostra destinos que enviam dados para outras soluções da Adobe Experience Cloud. Atualmente, a única opção suportada é o Adobe Analytics. See [Configure an Analytics Destination](/help/using/features/destinations/create-analytics-destination.md).
* **Plataformas integradas**: mostra destinos baseados em pessoas e baseados em dispositivos (também nomes de servidor a servidor). Observe que os destinos baseados em pessoas atualmente são um recurso beta apenas disponível para clientes selecionados.
* **Personalizado**: mostra os destinos de cookie e URL.


![](assets/destinations-landing.png)

## Addressable Audiences Landing Page {#audiences-landing-page}

To see audience data and match rates for your server-to-server destination, select **[!UICONTROL Integrated Platforms > Device-Based]**.

For more information about the displayed information, see [Addressable Audiences Interface](/help/using/features/addressable-audiences.md#addressable-audience-interface).

![](/help/using/features/assets/addressable-audiences-landing.png)

## Destination Builder {#destination-builder}

[!UICONTROL Destination Builder] permite criar os destinos com [!DNL URL] base em cookies. You cannot create server-to-server ([!DNL S2S]) destinations with [!UICONTROL Destination Builder], but you can manage their segment mappings. Contact your consultant to set up a [!DNL S2S] destination. [!UICONTROL Destination Builder] está localizado **[!UICONTROL Audience Data > Destinations]**.

### Destination Builder Settings {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] consiste nas seguintes seções e configurações:

| [!UICONTROL Destination Builder] Seção | Propósito |
|--- |--- |
| Informações básicas | Used to name the destination, describe it, and select destination type ([!DNL URL] or [!DNL cookie]), and platform (all, [!DNL Android], browser, or [!DNL iOS]). |
| Configuração | Includes controls for: <br/><ul><li>Passing in key-value data to [!DNL URL] destinations. É possível enviar dados como pares de valor chave individuais ou serializados. For details see, [Destination Serialization](../../features/destinations/key-value-pairs.md#destination-serialized) and [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md). </li><li>Elementos de um destino de cookie, como nome do cookie, domínio, tamanho, intervalo de expiração, formato de dados etc.</li></ul> |
| Mapeamentos de segmento | Permite: <br/><ul><li>Pesquise, adicione e gerencie segmentos associados a todos os tipos de destino. </li><li>Set delivery priorities on individual segments (for [!DNL cookie]-based segments only).</li></ul> |

### Data Delivery Methods {#data-delivery-methods}

Send information to a destination by passing it in through a [!DNL URL] string, by writing to a browser [!DNL cookie], or through offline server-to-server data transfers.

* [!DNL URL] e os destinos baseados em cookies transmitem dados sincronicamente, à medida que um usuário executa uma ação em uma página.
* A transmissão de dados de servidor para servidor é assíncrona e pode ocorrer long depois que um usuário saiu da página. O tipo de entrega selecionado depende dos seus requisitos de negócios e de como um parceiro de dados específico deseja, ou pode, receber dados.

See [How to Choose a Destination Type](../../features/destinations/destinations.md) for more information.

>[!MORE_ LIKE_ THIS]
>
>* [Criar um destino do cookie](../../features/destinations/manage-destinations.md#create-cookie-destination)
>* [Criar um destino de URL](../../features/destinations/manage-destinations.md#configure-url-destination)


## Configure a Cookie Destination {#create-cookie-destination}

Um destino de cookie retorna e grava dados em um cookie no navegador do usuário. O cookie contém dados que podem ser lidos por outras plataformas que têm acesso à página. Follow these instructions to create a cookie destination with [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

To create a new cookie destination, go to **[!UICONTROL Audience Data > Destinations > Create New Destination]** and complete the sections as described below.

### Informações básicas {#basic-information}

Esta seção contém campos e opções que iniciam o processo de criação de destino do cookie. Para concluir esta seção:

1. Click **[!UICONTROL Basic Information]** to expose the controls.
2. Dê um nome ao destino. Evite abreviações e caracteres especiais.
3. *(Opcional)* Descreva o destino. Uma descrição concisa é uma maneira eficaz de definir ou fornecer mais informações sobre um destino.
4. In the **[!UICONTROL Category]** list, choose **[!UICONTROL Custom]**.
5. In the **[!UICONTROL Environment]** list, select **[!UICONTROL Browser]**. Não é possível configurar destinos de cookies para ambientes móveis nativos, como aplicativos Android ou iOS.
6. In the **[!UICONTROL Type]** list, click **[!UICONTROL Cookie]**.
7. *(Opcional)* Selecione um **[!UICONTROL Auto-fill Destination Mapping]**. As opções incluem:
   * **[!UICONTROL Segment ID]**: Adiciona e envia automaticamente a ID do segmento para o destino.
   * **[!UICONTROL Integration Code Value]**: Adiciona e envia automaticamente o código de integração do segmento para o mapeamento de destino. O código de integração é um identificador exclusivo criado e utilizado pelo cliente. É limitada a 255 caracteres, máximo.
8. Click **[!UICONTROL Next]** to go to the [!UICONTROL Configuration] settings or click **[!UICONTROL Data Export Labels]** to apply export controls to the destination.

### Data Export Labels {#data-export-labels-cookies}

This section contains options that apply [data export controls](../../features/data-export-controls.md) to a cookie destination. Pule esta etapa se você não usar controles de exportação de dados. Para concluir esta seção:

1. Click **[!UICONTROL Data Export Labels]** to expose the controls.
2. Select a label that corresponds to data export control applied to the destination (see [Add Export Labels to a Destination](../../features/destinations/manage-destinations.md#add-data-export-labels) for details).
3. Clique em **[!UICONTROL Save]**.

### Configuração {#configuration}

Esta seção contém campos e opções que permitem configurar o cookie para o destino.

>[!NOTE]
>
>[!DNL Audience Manager] codifica dados gravados no cookie de destino. For example, spaces are encoded as `%20` and semicolons are encoded as `%3B`.

Para concluir esta seção:

1. Click **[!UICONTROL Configuration]** to expose the controls
1. Nomeie o cookie. Evite abreviações e caracteres especiais.
1. Escolha uma opção de formato de dados. Essas opções permitem escolher os delimitadores e separadores para os pares de valores chave que enviam dados de segmento para um destino. As opções de formato incluem:
   * **Chave única:** Permite definir a chave em um par de valor chave. You'll set the value after you select a segment in the [!UICONTROL Segment Mappings] section below.
   * **Várias chaves:** Permite definir a chave e o valor para um par de valor chave. Você criará o par de valor chave depois de selecionar um segmento na seção Mapeamentos de segmento abaixo.
See [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md) for more information about these data elements.
1. Clique em **[!UICONTROL Save]**.

Todas as outras configurações são opcionais. For more information about the **[!UICONTROL Cookie Domain]** and **[!UICONTROL Publish data to]** settings, see [Optional Settings for Cookie Destinations](../../features/destinations/manage-destinations.md#optional-settings-cookies).

### Segment Mappings {#segments-mapping}

Esta seção permite pesquisar e adicionar segmentos ao destino. Para concluir esta seção:

1. Click **[!UICONTROL Segment Mappings]** to expose the controls.
1. In the **[!UICONTROL Search and Add Segments]** box, start typing the name of a segment or click **[!UICONTROL Browse All Segments]** to browse a list of available segments.
1. Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
1. In the [!UICONTROL Edit Mapping] dialog:
   * **[!UICONTROL Mapping]** permite definir um valor para a chave especificada na seção Configuração acima.
   * **[!UICONTROL Publish from]** permite definir a data de início e fim do destino. Se a data final estiver em branco, o destino nunca expirará.
1. Clique em **[!UICONTROL Save]**.
1. Clique em **[!UICONTROL Done]**.

## Configure a URL Destination {#configure-url-destination}

A [!DNL URL] destination makes pixel calls from a page to your destination. Follow these instructions to create a [!DNL URL] destination with [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

To create a new [!DNL URL] destination, go to **[!UICONTROL Audience Data > Destinations > Create New Destination]** and complete the sections as described below.

### Informações básicas {#basic-info}

Esta seção contém campos e opções que iniciam o processo de criação de destino do URL. Para concluir esta seção:

1. Click **[!UICONTROL Basic Information]** to expose the controls.
1. Dê um nome ao destino. Evite abreviações e caracteres especiais.
1. *(Opcional)* Descreva o destino. Uma descrição concisa é uma maneira eficaz de definir ou fornecer mais informações sobre um destino.
1. In the **[!UICONTROL Category]** list, choose **[!UICONTROL Custom]**.
1. In the **[!UICONTROL Environment]** list, select the environment in which to trigger the URL destination.
1. In the **[!UICONTROL Type]** list, click **[!UICONTROL URL]**.
1. *(Opcional)* Selecione um **[!UICONTROL Auto-fill Destination Mapping]**. As opções incluem:
   * **[!UICONTROL Segment ID]**: Adiciona e envia automaticamente a ID do segmento para o destino.
   * **[!UICONTROL Integration Code Value]**: Adiciona e envia automaticamente o código de integração do segmento para o mapeamento de destino. O código de integração é um identificador exclusivo criado e utilizado pelo cliente. É limitada a 255 caracteres, máximo.
1. Click **[!UICONTROL Next]** to go to the [!UICONTROL Configuration] settings or click **[!UICONTROL Data Export Labels]** to apply export controls to the destination.

### Data Export Labels {#data-export-labels-dest}

This section contains options that apply [data export controls](../../features/data-export-controls.md) to a [!DNL URL] destination. Pule esta etapa se você não usar controles de exportação de dados. Para concluir esta seção:

1. Click **[!UICONTROL Data Export Labels]** to expose the controls.
2. Select a label that corresponds to the data export control applied to the destination (see [Add Export Labels to a Destination](../../features/destinations/manage-destinations.md#add-data-export-labels) for details).
3. Clique em **[!UICONTROL Save]**.

### Configuração {#configure-base-data}

This section contains options that let you set a base [!DNL URL] and data delimiters passed in by the [!DNL URL] string. Esta seção é opcional. Para concluir esta seção:

1. Click **[!UICONTROL Configuration]** to expose the controls.
1. *(Opcional)* Marque a caixa **[!UICONTROL Serialize]** de seleção.
Isso permite que você envie segmentos para um destino sequencialmente, em vez de fazer chamadas separadas para cada segmento. A serialização ajuda a tornar as transferências de dados eficientes. Marcar essa caixa de seleção expõe os campos de URL e delimitador. For more information, see [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md).
1. If you select **[!UICONTROL Serialize]**, then you must also configure the URL and delimiter fields described below.

| Campo | Descrição |
|--- |--- |
| URL básica | The base part of a standard `HTTP` [!DNL URL] that does not change. Also, you need to place the `%ALIAS%`  [placeholder macro](../../features/destinations/destination-macros.md#destination-macros-defined) in the base URL. Exemplo: `https://www.myCompany.com/%alias%...` |
| URL seguro | The base part of a secure `HTTPS` [!DNL URL] that does not change. Also, you need to place the `%ALIAS%`   [placeholder macro](../../features/destinations/destination-macros.md#destination-macros-defined) in the base URL. Exemplo: `https://www.myCompany.com/%alias%...` |
| Delimitador | The symbol that separates the segment variables in the [!DNL URL] string. Normalmente, é uma vírgula ou ponto-e-vírgula. Obtenha essas informações do parceiro de destino. |

### Segment Mappings {#segment-mappings}

Esta seção permite pesquisar e adicionar segmentos ao destino. Para concluir esta seção:

1. Click **[!UICONTROL Segment Mappings]** to expose the controls.
1. In the **[!UICONTROL Search and Add Segments]** box, start typing the name of a segment or click **[!UICONTROL Browse All Segments]** browse a list of available segments.
1. Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
1. Em [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Forneça os pares de valores chave usados pelo segmento.
   * **[!UICONTROL Start Date]** e **[!UICONTROL End Date]**: Escolha uma data de início e fim para o destino. Se a data final estiver em branco, o destino nunca expirará.
1. Clique em **[!UICONTROL Done]**.

### Optional Settings for Cookie Destinations {#optional-settings-cookies}

In [!UICONTROL Destination Builder], the [!UICONTROL Configuration section] contains the [!UICONTROL Cookie Domain] and [!UICONTROL Publish Data To] fields. Eles permitem que você crie regras para determinar se um destino define um cookie ou retorna um cookie. [!UICONTROL Cookie Domain] e [!UICONTROL Publish Data To] trabalhar independentemente entre si e são opcionais. É possível criar um destino de cookie sem usar qualquer um deles.

## Cookie Domain: Syntax and Examples {#cookie-domain-syntax}

<!-- cookie-destination-options.xml -->

<table id="table_4F4F7562AFEE49F8917AAE5712B5CCE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domínio do cookie </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Sintaxe</b> </p> </td> 
   <td colname="col2"> <p>The <span class="wintitle"> Cookie Domain</span> field accepts a simple text string that lets you set cookies on a specified domain or all domains. Ao usar este recurso: </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">Defina apenas um domínio para cada destino de cookie. Do not type multiple domains in the <span class="wintitle"> Cookie Domain</span> field. Create another <span class="wintitle"> Destination</span> instead. </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">Não use caracteres curingas. </li> 
     </ul> </p> <p> Leave the <span class="wintitle"> Cookie Domain</span> field blank to set a cookie on all domains. Esta é a configuração padrão. </p> <p>Para definir cookies em um domínio e subdomínios específicos: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Type the name of the domain in the <span class="wintitle"> Cookie Domain</span> field. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">Inicie o nome do domínio com um período. For example, <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">The <code> https://www</code> prefix is not required. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exemplo</b> </p> </td> 
   <td colname="col2"> <p>Como exemplo simples, digamos que temos um site fictício chamado sports. com. Sports.com tem domínios para golf, beisebol e futebol. To set a cookie in all the sports domains, you would type that in the <span class="wintitle"> Cookie Domain</span> box as shown below: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>This tells <span class="keyword"> Audience Manager</span> to set a cookie in any domain that contains the pattern <code><i>something</i></code>.sports.com. Veja abaixo um conjunto mais complexo de exemplos. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exemplos de domínio de cookie complexos

These examples show you if [!DNL Audience Manager] will set a cookie based on how the [!UICONTROL Cookie Domain] option is configured.

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Site </th> 
   <th colname="col2" class="entry">Domínio do cookie: .sports.com <p>Conjunto de cookies </p> </th> 
   <th colname="col3" class="entry">Domínio do cookie: .golf.sports.com <p>Conjunto de cookies </p> </th> 
   <th colname="col4" class="entry">Domínio do cookie: Em branco <p>Conjunto de cookies </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>sports.com</b> </p> </td> 
   <td colname="col2"> Sim </td> 
   <td colname="col3"> Não </td> 
   <td colname="col4"> Sim </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>golf.sports.com</b> </p> </td> 
   <td colname="col2"> Sim </td> 
   <td colname="col3"> Sim </td> 
   <td colname="col4"> Sim </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>baseball.sports.com</b> </p> </td> 
   <td colname="col2"> Sim </td> 
   <td colname="col3"> Não </td> 
   <td colname="col4"> Sim </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>sports.golf.com</b> </p> </td> 
   <td colname="col2"> Não </td> 
   <td colname="col3"> Não </td> 
   <td colname="col4"> Sim </td> 
  </tr> 
 </tbody> 
</table>

## Publish Data To {#publish-data-to}

The [!UICONTROL Publish Data To] settings return a cookie if the domain meets the criteria set by the options you select. As opções incluem:

* **[!UICONTROL All of our domains]**: (Padrão) Retorna um [!DNL cookie] para qualquer domínio.
* **[!UICONTROL Only the selected domains]**: Retorna um cookie apenas para os domínios selecionados na lista de domínios.
* **[!UICONTROL All of our domains except the selected domains]**: Impede que os domínios selecionados recebam [!DNL cookie]a. All other domains can receive a [!DNL cookie].

>[!MORE_ LIKE_ THIS]
>
>* [Criar um destino do cookie](../../features/destinations/manage-destinations.md#create-cookie-destination)


## Add or Edit Segments for Server-to-Server Destinations {#add-edit-segments}

You can only add or edit segments for a server-to-server ([!DNL S2S]) destination. You cannot create [!DNL S2S] destinations with [!UICONTROL Destination Builder]. Contact your consultant to set up [!DNL S2S] destinations. Follow these instructions to add or edit segments for an [!DNL S2S] destination.

<!-- destination-s2s-edit.xml -->

To add or edit segment mappings for an [!DNL S2S] destination:

1. Go to **[!UICONTROL Audience Data > Destinations]**. Select **Integrated Platforms &gt; Device-Based** and find the [!DNL S2S] destination you want to work with.
1. In the [!UICONTROL Action] column, click the pencil icon to edit the destination.
   * In the **[!UICONTROL Search and Add Segments]** box, start typing the name of a segment or click **[!UICONTROL Browse All Segments]** browse a list of available segments.
   * Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
   * Em [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Defina um valor para o par [de valor chave](../../features/destinations/key-value-pairs.md) usado por esse destino.
      * **[!UICONTROL Start Date]** e **[!UICONTROL End Date]**: Escolha uma data de início e fim para o destino. Se a data final estiver em branco, o destino nunca expirará.
1. Click **[!UICONTROL Save]** and then click **[!UICONTROL Done]**.

## Add Data Export Labels to a Destination {#add-data-export-labels}

[!DNL Data Export Labels] trabalhar com o [!DNL Export Controls] conjunto definido em uma fonte de dados. [!DNL Data Export Labels] impedir que você adicione traços restritos a um segmento e envie dados de segmento para um destino. You can set multiple export labels to a new or existing [!DNL cookie] or [!DNL URL] destination.

>[!NOTE]
>
>To add an export label, you need administrator permissions *or* sufficient privileges to create or edit a destination.

<!-- t_export_labels.xml -->

Para adicionar rótulos de exportação a um destino:

1. Clique em **[!UICONTROL Audience Data]**:
   * For new destinations: Click **[!UICONTROL Create New Destination]**. Complete the [!UICONTROL Basic Information] section before you select a data export label. See [Create a Cookie Destination](../../features/destinations/manage-destinations.md#create-cookie-destination) or [Create a URL Destination](../../features/destinations/manage-destinations.md#configure-url-destination) for information.
   * For existing destinations: Use the [!DNL Search] box to find your destination or scroll through the list and click on the destination name to open it.
1. Selecione um [!DNL Data Export Label]. Deixe as caixas de seleção em branco se não quiser definir quaisquer restrições de exportação. Os rótulos de exportação incluem as seguintes opções:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Export restrictions will not work unless you set a [matching export control](../../features/data-export-controls.md) on a data source.
1. Clique em **[!UICONTROL Save]**.

>[!MORE_ LIKE_ THIS]
>
>* [Criar uma fonte de dados](../../features/manage-datasources.md#create-data-source)

