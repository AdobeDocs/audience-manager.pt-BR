---
description: Para criar Regras de mesclagem de perfil, revise e conclua as etapas em cada um dos procedimentos descritos nesta seção.
seo-description: Para criar Regras de mesclagem de perfil, revise e conclua as etapas em cada um dos procedimentos descritos nesta seção.
seo-title: Introdução às regras de mesclagem de perfil
solution: Audience Manager
title: Introdução às regras de mesclagem de perfil
uuid: 7 d 32 c 60 f -467 c -42 dd-afa 9-437 fd 7 c 473 c 5
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Getting Started with Profile Merge Rules {#getting-started-with-profile-merge-rules}

To create [!UICONTROL Profile Merge Rules], review and complete the steps in each of the procedures described in this section.

<!-- merge-rules-start.xml -->

## Create a Cross-Device Data Source {#create-data-source}

To create a cross-device data source, go to **[!UICONTROL Audience Data > Data Sources > Add New]** and complete the steps for each section described here. As permissões de administrador são necessárias para criar ou editar uma fonte de dados entre dispositivos.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>See [Data Source Settings and Menu Options](../../features/datasources-list-and-settings.md#settings-menu-options) for descriptions of these different controls.

## Data Source Details {#details}

To complete the [!UICONTROL Data Source Details] section:

1. Dê um nome para a fonte de dados.
1. *(Opcional)* Descreva a fonte de dados. Uma descrição concisa ajuda a definir a função ou finalidade da fonte de dados.
1. Forneça um código de integração. Um código de integração é sua própria ID exclusiva para essa fonte de dados.
1. In the **[!UICONTROL ID Type]** list, select **[!UICONTROL Cross Device]**.
1. In the **[!UICONTROL ID Definition]** list, select an option that defines the data source type. As opções incluem:
   * **[!UICONTROL Person]**: Uma ID que define uma única pessoa. This ID can be mapped to multiple [!DNL Audience Manager] IDs.
   * **[!UICONTROL Household]**: Uma ID que define um grupo de pessoas. This ID can be mapped to multiple [!DNL Audience Manager] IDs.

## Controles da exportação de dados {#export-controls}

[Os controles de exportação de dados](../../features/data-export-controls.md) são regras de classificação opcionais que podem ser aplicadas a uma fonte de dados e destino. Eles impedem que você envie dados para um destino quando essa ação violar a privacidade de dados ou usar o contrato. Skip this section if you do not use [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

[!UICONTROL Data Source Settings] fornece várias opções, mas essas 2 são importantes para criar uma fonte de dados entre dispositivos:

* **[!UICONTROL Use as Authenticated Profile]**: Selecionado por padrão, essa configuração permite que você crie um [!UICONTROL Profile Merge Rule] com seus próprios dados autenticados.

* **[!UICONTROL Use as a Device Graph]**: Esse controle está disponível apenas para contas listadas como um provedor de dados. Selecting this check box creates your data source as a device graph and lets you share it with other [!DNL Audience Manager] customers. Work with your [!DNL Audience Manager] consultant to get set up as a data provider and to specify which customers this [!UICONTROL Data Source] should be shared with. Seu consultor fornecerá sua conta e o compartilhamento de gráficos de dispositivo por meio de processos internos de provisionamento.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Esse controle permite definir o período de retenção de dados para IDs inativas do cliente. Isso determina quanto tempo o Audience Manager mantém as IDs do cliente em nosso banco de dados depois que elas foram vistas pela última vez na plataforma do Audience Manager. O valor padrão é de 24 meses (720 dias). O valor mínimo que pode ser definido é de 1 mês e o valor máximo é de 5 anos. Observe que contamos todos os meses como 30 dias. O Audience Manager executa um processo que exclui IDs inativas do cliente uma vez por semana, de acordo com a retenção de dados definida para IDs inativas do cliente.

The text fields associated with these settings let you rename the [!UICONTROL Data Source] with an alias that appears in the [Profile Merge Rule options](../../features/profile-merge-rules/merge-rule-definitions.md). For example, if you add an alias to **[!UICONTROL Use as Authenticated Profile]**, that name appears in the [!UICONTROL Authenticated Profile Options] list. If you add an alias to **[!UICONTROL Use as a Device Graph]**, that name appears in the [!UICONTROL Device Options] list.

>[!MORE_ LIKE_ THIS]
>
>* [Criar uma fonte de dados](../../features/manage-datasources.md#create-data-source)


## Create a Profile Merge Rule {#create-profile-merge-rule}

To create a [!UICONTROL Profile Merge Rule], go to **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** and complete the steps for each section described here. É possível criar até cinco regras de mesclagem depois de configurar uma fonte de dados entre dispositivos. As permissões do administrador são necessárias para criar, editar ou excluir uma regra. All users can view and use existing [!UICONTROL Profile Merge Rules].

<!-- create-profile-merge-rule.xml -->

**Pré-requisitos:** Uma fonte de dados entre dispositivos é necessária para criar [!UICONTROL Profile Merge Rule]a. See [Create a Data Source](../../features/manage-datasources.md#create-data-source).

>[!TIP]
>
>See [Profile Merge Rule Options Defined](../../features/profile-merge-rules/merge-rule-definitions.md) for descriptions of these different controls.

## Informações básicas {#basic-info}

To complete the [!UICONTROL Basic Information] section:

1. Name the [!UICONTROL Profile Merge Rule].
2. *(Opcional)* Descreva o [!UICONTROL Profile Merge Rule]. Uma descrição concisa ajuda a definir a função ou finalidade da sua regra.
3. *(Opcional)* Selecione **[!UICONTROL Set as default]** se deseja tornar esse padrão o padrão [!UICONTROL Profile Merge Rule]. Novos segmentos são associados automaticamente à regra padrão.

## Controles da exportação de dados {#data-export-controls}

[Os controles de exportação de dados](../../features/data-export-controls.md) são regras de classificação opcionais que podem ser aplicadas a seu [!UICONTROL Profile Merge Rule]. Eles impedem que você envie dados para um destino quando essa ação violar a privacidade de dados ou usar o contrato. Skip this section if you do not use [!UICONTROL Data Export Controls].

## Profile Merge Rule Setup {#profile-merge-rule-setup}

To complete the [!UICONTROL Proflie Merge Rule Setup] section:

1. Select an **[!UICONTROL Authenticated Option]**. As opções incluem:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Select an **[!UICONTROL Authenticated Profile Option]** (up to 3, maximum). These are the [cross-device data sources](../../features/profile-merge-rules/merge-rules-start.md) you have created previously.
3. Selecione um **[!UICONTROL Device Option]**. As opções incluem:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. Clique em **[!UICONTROL Save]**.

## Configure Merge Rule Code {#configure-merge-rule-code}

Follow these instructions to set up the [!UICONTROL Experience Cloud ID Service], [!UICONTROL DIL], and mobile [!DNL SDK] code to work with your merge rules.

<!-- merge-rules-configure-code.xml -->

### Pré-requisitos

You must set up a [cross-device data source](#create-data-source) and [profile merge rules](#create-profile-merge-rule) *before* completing these procedures.

## For Experience Cloud ID Service Customers {#id-service-customers}

The [!UICONTROL Experience Cloud ID Service] and the latest version of [DIL](../../dil/dil-overview.md) are recommended when working with [!UICONTROL Profile Merge Rules]. However, you don't have to use the [!UICONTROL Experience Cloud ID Service] to work with this feature. If you're just using [!UICONTROL DIL], see the [legacy DIL section](../../features/profile-merge-rules/merge-rules-start.md#legacy-dil) below.

### Configurar a função Definir ID do cliente

When working with the [!UICONTROL Experience Cloud ID Service], the `setCustomerIDs` function passes declared IDs to [!DNL Audience Manager]. To use a profile merge rule, you must modify `setCustomerIDs` to use the integration code specified when you created a cross-device data source. For example, say you've created a cross-device data source with the integration code `my_datasource_ic`. Para enviar uma ID declarada, adicione o código de integração à função da ID de visitante, como mostrado na amostra de código modificada abaixo.

#### Amostra de código genérica

```javascript
visitor.setCustomerIDs({
  "userid":{
      "id":"12345",
      "authState":Visitor.AuthState.AUTHENTICATED
```

#### Amostra de código modificada

```javascript
visitor.setCustomerIDs({
  "my_datasource_ic":{
     "id":"12345",
     "authState":Visitor.AuthState.AUTHENTICATED
```

For more information, see [Create a Cross-Device Data Source](#create-data-source) and [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_customer_ids.html).

### `DIL.create` Função Configurar

The latest versions of [!UICONTROL DIL] now automatically pick up the [!UICONTROL declared ID] from the `visitorService` function in `DIL.create` (see [Declared ID Variables](../../features/declared-ids.md#declared-id-variables)). Check your `DIL.create` function to make sure this is set up properly as shown in the code sample below.

<pre class="js"><code>var vdil = DIL. create ({parceiro: " nome do parceiro ",
 visitorservice: {namespace: "<i>INSERT-MCORG-ID-HERE</i>"}});</code>
</pre>

In the namespace key-value pair, the `*`MCORG`*` variable is your [!DNL Experience Cloud] Organization ID. If you don't have this ID, you can find it in the [!UICONTROL Administration] section of the [!DNL Experience Cloud] dashboard. Você precisa de permissões de administrador para visualizar esse painel. See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

### Configurar sdks

See the [Configure SDKs](../../features/profile-merge-rules/merge-rules-start.md#configure-sdks) section below.

## Legacy DIL {#legacy-dil}

If you're not using [!DNL Experience Cloud ID Service] yet, you really ought to. Contudo, entendemos que mover para novo código requer um teste e teste cuidadoso. In these cases, check your `DIL.create` function to make sure this is set up properly as shown in the code sample below.

<pre class="js"><code>DIL. create ({parceiro: " nome do parceiro ",
 declaredid: {dpuuid:<i>dpuuid</i>,
 dpid:<i>dpid</i>}});</code>
</pre>

For more information, see the legacy [!UICONTROL DIL] section in [Declared ID Variables](../../features/declared-ids.md#declared-id-variables).

### Configure SDKs {#configure-sdks-legacy-dil}

Check the methods in your [!DNL SDK] code that let you pass [!UICONTROL declared IDs] from [!DNL Android] and [!DNL iOS] mobile devices. The variable names for the [!DNL Android] and [!DNL iOS] code libraries are the same:

* `dpid`: A ID de fonte de dados entre dispositivos.
* `dpuuid`: A [!UICONTROL declared ID] (ou seja, a ID do usuário).

<table id="table_2ACA3E5F316D4413B10A4403B786CC23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de dispositivo </th> 
   <th colname="col2" class="entry"> Método </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b> Android </b> </p> </td> 
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>Sintaxe:</b> </p> <p> <pre> public static void setdpidanddpuuid (String dpid, String dpuuid); </pre> </p> <p> <b>Exemplo:</b> </p> <p> <pre> Audiencemanager. setdpidanddpuuid ("mydpid", "mydpuuid"); </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS </b> </p> </td> 
   <td colname="col2"> <p> <code> Audiencesetdpid: dpuuid </code> </p> <p> <b>Sintaxe:</b> </p><p>
    <code class="javascript">+ (void) audiencesetdpid: (Nsstring *) dpid 
 dpuuid: (Nsstring *) dpuuid; </code>
 </p>
    <p> <b>Exemplo:</b> </p><p>
    <code class="javascript">[Adbmobile audiencesetdpid: @ "290" dpuuid: @ "99301393923940"]; </code>
 </p>
    </td>
  </tr>
 </tbody>
</table>

See also, [Audience Manager Methods for Android](https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=c_audience_manager_methods.html) and [Audience Manager Methods for iOS](https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=aam_methods.html).
