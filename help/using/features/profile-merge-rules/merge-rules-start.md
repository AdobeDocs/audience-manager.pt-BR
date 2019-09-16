---
description: Para criar Regras de mesclagem de perfil, reveja e conclua as etapas em cada um dos procedimentos descritos nesta seção.
seo-description: Para criar Regras de mesclagem de perfil, reveja e conclua as etapas em cada um dos procedimentos descritos nesta seção.
seo-title: Introdução às regras de mesclagem de perfil
solution: Audience Manager
title: Introdução às regras de mesclagem de perfil
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
translation-type: tm+mt
source-git-commit: 28d1292140a56cf1627a8921876d9483221876ca

---


# Introdução às regras de mesclagem de perfil {#getting-started-with-profile-merge-rules}

Para criar [!UICONTROL Profile Merge Rules], reveja e conclua as etapas em cada um dos procedimentos descritos nesta seção.

<!-- merge-rules-start.xml -->

## Criar uma fonte de dados entre dispositivos {#create-data-source}

Para criar uma fonte de dados entre dispositivos, vá até **[!UICONTROL Audience Data > Data Sources > Add New]** e conclua as etapas para cada seção descrita aqui. São necessárias permissões de administrador para criar ou editar uma fonte de dados entre dispositivos.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Consulte Configurações da fonte de [dados e Opções](../../features/datasources-list-and-settings.md#settings-menu-options) de menu para obter descrições desses diferentes controles.

## Detalhes da fonte de dados {#details}

Para concluir a [!UICONTROL Data Source Details] seção:

1. Nomeie a fonte de dados.
1. *(Opcional)* Descreva a fonte de dados. Uma descrição concisa ajuda a definir a função ou a finalidade da fonte de dados.
1. Forneça um código de integração. Um código de integração é sua própria ID exclusiva para essa fonte de dados.
1. Na **[!UICONTROL ID Type]** lista, selecione **[!UICONTROL Cross Device]**.
1. Na **[!UICONTROL ID Definition]** lista, selecione uma opção que defina o tipo de fonte de dados. As opções incluem:
   * **[!UICONTROL Person]**: Uma ID que define uma única pessoa. Essa ID pode ser mapeada para várias [!DNL Audience Manager] IDs.
   * **[!UICONTROL Household]**: Uma ID que define um grupo de pessoas. Essa ID pode ser mapeada para várias [!DNL Audience Manager] IDs.

## Controles da exportação de dados {#export-controls}

[Os Controles](../../features/data-export-controls.md) de exportação de dados são regras de classificação opcionais que podem ser aplicadas a uma fonte de dados e destino. Elas impedem que você envie dados para um destino quando essa ação viola a privacidade dos dados ou o contrato de uso. Ignore esta seção se não usar [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

[!UICONTROL Data Source Settings] fornece várias opções, mas essas 2 são importantes para criar uma fonte de dados entre dispositivos:

* **[!UICONTROL Use as Authenticated Profile]**: Selecionada por padrão, essa configuração permite criar um [!UICONTROL Profile Merge Rule] com seus próprios dados autenticados.

* **[!UICONTROL Use as a Device Graph]**: Esse controle está disponível somente para contas listadas como um provedor de dados. Marcar essa caixa de seleção cria sua fonte de dados como um gráfico de dispositivo e permite que você compartilhe-o com outros [!DNL Audience Manager] clientes. Entre em contato com seu [!DNL Audience Manager] consultor para configurar como um provedor de dados e especificar com quais clientes isso [!UICONTROL Data Source] deve ser compartilhado. Seu consultor fornecerá o compartilhamento de gráficos de conta e dispositivo por meio de um processo de provisionamento interno.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Esse controle permite definir o período de retenção de dados para IDs de cliente inativas. Isso determina por quanto tempo o Audience Manager mantém as IDs do cliente em nosso banco de dados após serem vistas pela última vez na plataforma do Audience Manager. O valor padrão é 24 meses (720 dias). O valor mínimo que você pode definir é 1 mês e o valor máximo é 5 anos. Observe que todos os meses são contados como 30 dias. O Audience Manager executa um processo que exclui IDs de cliente inativas uma vez por semana, de acordo com a retenção de dados definida para IDs de cliente inativas.

Os campos de texto associados a essas configurações permitem que você renomeie o arquivo com um alias que aparece nas opções [!UICONTROL Data Source] Regra de mesclagem de [](../../features/profile-merge-rules/merge-rule-definitions.md)perfil. Por exemplo, se você adicionar um alias a **[!UICONTROL Use as Authenticated Profile]**, esse nome será exibido na [!UICONTROL Authenticated Profile Options] lista. Se você adicionar um alias a **[!UICONTROL Use as a Device Graph]**, esse nome será exibido na [!UICONTROL Device Options] lista.

>[!MORE_LIKE_THIS]
>
>* [Criar uma fonte de dados](../../features/manage-datasources.md#create-data-source)


## Criar uma regra de mesclagem de perfil {#create-profile-merge-rule}

Para criar um [!UICONTROL Profile Merge Rule], vá até **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** e conclua as etapas para cada seção descrita aqui. É possível criar até 3 regras de mesclagem após configurar uma fonte de dados entre dispositivos. Permissões de administrador são necessárias para criar, editar ou excluir uma regra. Todos os usuários podem exibir e usar os existentes [!UICONTROL Profile Merge Rules].

<!-- create-profile-merge-rule.xml -->

**** Pré-requisitos: Uma fonte de dados entre dispositivos é necessária para criar um [!UICONTROL Profile Merge Rule]. Consulte [Criar uma fonte](../../features/manage-datasources.md#create-data-source)de dados.

>[!TIP]
>
>Consulte Opções de regra de mesclagem de [perfil definidas](../../features/profile-merge-rules/merge-rule-definitions.md) para obter descrições desses diferentes controles.

## Informações básicas {#basic-info}

Para concluir a [!UICONTROL Basic Information] seção:

1. Dê um nome ao [!UICONTROL Profile Merge Rule].
2. *(Opcional)* Descreva o [!UICONTROL Profile Merge Rule]. Uma descrição concisa ajuda a definir a função ou a finalidade de sua regra.
3. *(Opcional)* Selecione **[!UICONTROL Set as default]** se deseja tornar esse o padrão [!UICONTROL Profile Merge Rule]. Novos segmentos são associados automaticamente à regra padrão.

## Controles da exportação de dados {#data-export-controls}

[Os Controles](../../features/data-export-controls.md) de exportação de dados são regras de classificação opcionais que podem ser aplicadas ao seu [!UICONTROL Profile Merge Rule]. Elas impedem que você envie dados para um destino quando essa ação viola a privacidade dos dados ou o contrato de uso. Ignore esta seção se não usar [!UICONTROL Data Export Controls].

## Configuração da regra de mesclagem de perfil {#profile-merge-rule-setup}

Para concluir a [!UICONTROL Proflie Merge Rule Setup] seção:

1. Selecione um **[!UICONTROL Authenticated Option]**. As opções incluem:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Selecione um **[!UICONTROL Authenticated Profile Option]** (máximo de 3). Essas são as fontes [de dados](../../features/profile-merge-rules/merge-rules-start.md) entre dispositivos que você criou anteriormente.
3. Selecione um **[!UICONTROL Device Option]**. As opções incluem:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. Clique em **[!UICONTROL Save]**.

## Configurar o código da regra de mesclagem {#configure-merge-rule-code}

Siga estas instruções para configurar o [!UICONTROL Experience Cloud ID Service], [!UICONTROL DIL]e o [!DNL SDK] código móvel para trabalhar com suas regras de mesclagem.

<!-- merge-rules-configure-code.xml -->

### Pré-requisitos

É necessário configurar uma fonte [de dados](#create-data-source) entre dispositivos e regras [de mesclagem de](#create-profile-merge-rule) perfil *antes* de concluir esses procedimentos.

## Para clientes do serviço da Experience Cloud ID {#id-service-customers}

A versão [!UICONTROL Experience Cloud ID Service] e a versão mais recente da [DIL](../../dil/dil-overview.md) são recomendadas ao trabalhar com [!UICONTROL Profile Merge Rules]. No entanto, você não precisa usar o para [!UICONTROL Experience Cloud ID Service] trabalhar com esse recurso. Se você estiver usando apenas [!UICONTROL DIL], consulte a seção [DIL](../../features/profile-merge-rules/merge-rules-start.md#legacy-dil) herdada abaixo.

### Configurar a função Definir ID do cliente

Ao trabalhar com o [!UICONTROL Experience Cloud ID Service], a `setCustomerIDs` função passa as IDs declaradas para [!DNL Audience Manager]. Para usar uma regra de mesclagem de perfil, é necessário modificar `setCustomerIDs` para usar o código de integração especificado ao criar uma fonte de dados entre dispositivos. Por exemplo, considere que você criou uma fonte de dados entre dispositivos com o código de integração `my_datasource_ic`. Para passar uma ID declarada, adicione o código de integração à função de ID de visitante, conforme mostrado na amostra de código modificada abaixo.

#### Exemplo de código genérico

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

Para obter mais informações, consulte [Criar uma fonte](#create-data-source) de dados entre dispositivos e IDs e estados [de autenticação](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_customer_ids.html)do cliente.

### Configurar `DIL.create` função

As versões mais recentes do [!UICONTROL DIL] agora coletam automaticamente [!UICONTROL declared ID] a `visitorService` função em `DIL.create` (consulte Variáveis [](../../features/declared-ids.md#declared-id-variables)de ID declaradas). Verifique sua `DIL.create` função para verificar se ela está configurada corretamente, conforme mostrado na amostra de código abaixo.

<pre class="js"><code>
var vDil = DIL.create({ parceiro:"nome do parceiro", visitorService:{ namespace:"<i>INSERT-MCORG-ID-HERE</i>" }});
</code></pre>

No par de valores chave do namespace, a variável `*`MCORG`*` é a ID da [!DNL Experience Cloud] organização. Se você não tiver essa ID, poderá encontrá-la na [!UICONTROL Administration] seção do [!DNL Experience Cloud] painel. Você precisa de permissões de administrador para exibir este painel. See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

### Configurar SDKs

Consulte a seção [Configurar SDKs](#configure-sdks-legacy-dil) abaixo.

## DIL herdado {#legacy-dil}

Se você não está usando [!DNL Experience Cloud ID Service] ainda, você realmente deveria. Mas, nós entendemos que a mudança para um novo código requer um pensamento cuidadoso e testes. Nesses casos, verifique sua `DIL.create` função para verificar se ela está configurada corretamente, conforme mostrado na amostra de código abaixo.

<pre class="js"><code>
DIL.create({ parceiro:"nome do parceiro", declareId:{ dpuuid:<i>dpuuid</i>, dpid:<i>dpid</i>}});
</code></pre>

Para obter mais informações, consulte a [!UICONTROL DIL] seção herdada em Variáveis [de ID](../../features/declared-ids.md#declared-id-variables)declaradas.

### Configurar SDKs {#configure-sdks-legacy-dil}

Verifique os métodos em seu [!DNL SDK] código que permitem a passagem [!UICONTROL declared IDs] de dispositivos [!DNL Android] e dispositivos [!DNL iOS] móveis. Os nomes das variáveis para as bibliotecas de código [!DNL Android] e [!DNL iOS] de código são os mesmos:

* `dpid`: A ID da fonte de dados entre dispositivos.
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
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>Sintaxe:</b> </p> <p> <pre> public static void setDpidAndDpuuid(String dpid, String dpuuid); </pre> </p> <p> <b>Exemplo:</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid("myDpid","myDpuuid"); </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS </b> </p> </td> 
   <td colname="col2"> <p> <code> audienceSetDpid:dpuuid </code> </p> <p> <b>Sintaxe:</b> </p><p>
    <code class="javascript">
      + (void) audienceSetDpid:(NSString *)dpid dpuuid:(NSString *)dpuuid; 
    </code></p>
    <p> <b>Exemplo:</b> </p><p>
    <code class="javascript">
      [ADBMobile audienceSetDpid:@"290" dpuuid:@"99301393923940"];
    </code></p>
    </td>
  </tr>
 </tbody>
</table>

Consulte também Métodos do [Audience Manager para Android](https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=c_audience_manager_methods.html) e Métodos do [Audience Manager para iOS](https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=aam_methods.html).
