---
description: Para criar Regras de mesclagem de Perfis, reveja e conclua as etapas em cada um dos procedimentos descritos nesta seção.
seo-description: Para criar Regras de mesclagem de Perfis, reveja e conclua as etapas em cada um dos procedimentos descritos nesta seção.
seo-title: Introdução às regras de mesclagem de perfis
solution: Audience Manager
title: Introdução às regras de mesclagem de perfis
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1327'
ht-degree: 4%

---


# Introdução às regras de mesclagem de perfis {#getting-started-with-profile-merge-rules}

Para criar [!UICONTROL Profile Merge Rules], reveja e conclua as etapas em cada um dos procedimentos descritos nesta seção.

<!-- merge-rules-start.xml -->

## Create a Cross-Device Data Source {#create-data-source}

Para criar uma fonte de dados entre dispositivos, vá até **[!UICONTROL Audience Data > Data Sources > Add New]** e conclua as etapas para cada seção descrita aqui. São necessárias permissões de administrador para criar ou editar uma fonte de dados entre dispositivos.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Consulte Configurações da fonte de [dados e Opções](../datasources-list-and-settings.md#settings-menu-options) de menu para obter descrições desses diferentes controles.

## Detalhes da fonte de dados {#details}

Para concluir a [!UICONTROL Data Source Details] seção:

1. Nomeie a fonte de dados.
2. *(Opcional)* Descreva a fonte de dados. Uma descrição concisa ajuda a definir a função ou a finalidade da fonte de dados.
3. Forneça um código de integração. Um código de integração é sua própria ID exclusiva para essa fonte de dados.
4. Na **[!UICONTROL ID Type]** lista, selecione **[!UICONTROL Cross Device]**.
5. Na **[!UICONTROL ID Definition]** lista, selecione uma opção que defina o tipo de fonte de dados. As opções incluem:
   * **[!UICONTROL Person]**: Uma ID que define uma única pessoa. Essa ID pode ser mapeada para várias [!DNL Audience Manager] IDs.
   * **[!UICONTROL Household]**: Uma ID que define um grupo de pessoas. Essa ID pode ser mapeada para várias [!DNL Audience Manager] IDs.

## Controles da exportação de dados {#export-controls}

[Os Controles](../data-export-controls.md) de exportação de dados são regras de classificação opcionais que podem ser aplicadas a uma fonte de dados e destino. Elas impedem que você envie dados para um destino quando essa ação viola a privacidade dos dados ou o contrato de uso. Ignore esta seção se não usar [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

[!UICONTROL Data Source Settings] fornece várias opções, mas essas 2 são importantes para criar uma fonte de dados entre dispositivos:

* **[!UICONTROL Use as Authenticated Profile]**: Selecionada por padrão, essa configuração permite criar um [!UICONTROL Profile Merge Rule] com seus próprios dados autenticados.

* **[!UICONTROL Use as a Device Graph]**: Esse controle está disponível somente para contas listadas como um provedor de dados. Marcar essa caixa de seleção cria sua fonte de dados como um gráfico de dispositivo e permite que você compartilhe-o com outros [!DNL Audience Manager] clientes. Entre em contato com seu [!DNL Audience Manager] consultor para configurar como um provedor de dados e especificar com quais clientes isso [!UICONTROL Data Source] deve ser compartilhado. Seu consultor fornecerá seu compartilhamento de gráficos de conta e dispositivo por meio de um processo de provisionamento interno.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Esse controle permite que você defina o período de retenção de dados para IDs de cliente inativas. Isso determina por quanto tempo a Audience Manager mantém as IDs do cliente em nosso banco de dados após serem vistas pela última vez na plataforma do Audience Manager. O valor padrão é 24 meses (720 dias). O valor mínimo que você pode definir é 1 mês e o valor máximo é 5 anos. Observe que todos os meses são contados como 30 dias. O Audience Manager executa um processo que exclui IDs de clientes inativas uma vez por semana, de acordo com a retenção de dados definida para IDs de clientes inativas.

Os campos de texto associados a essas configurações permitem renomear o [!UICONTROL Data Source] com um alias que aparece nas opções [de Regra de mesclagem de](merge-rule-definitions.md)Perfis. Por exemplo, se você adicionar um alias a **[!UICONTROL Use as Authenticated Profile]**, esse nome será exibido na [!UICONTROL Authenticated Profile Options] lista. Se você adicionar um alias a **[!UICONTROL Use as a Device Graph]**, esse nome será exibido na [!UICONTROL Device Options] lista.

## Criar uma regra de mesclagem de Perfis {#create-profile-merge-rule}

Para criar um [!UICONTROL Profile Merge Rule], vá até **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** e conclua as etapas para cada seção descrita aqui.

É possível criar até 3 regras de mesclagem após configurar uma fonte de dados entre dispositivos. Você terá acesso a uma quarta regra de mesclagem de Perfis ([!UICONTROL All Cross-Device Profiles]) se se inscrever em Destinos [baseados em](../destinations/people-based-destinations-overview.md)pessoas.

Permissões de administrador são necessárias para criar, editar ou excluir uma regra. Todos os usuários podem visualização e usar os existentes [!UICONTROL Profile Merge Rules].

<!-- create-profile-merge-rule.xml -->

**Pré-requisitos:** Uma fonte de dados entre dispositivos é necessária para criar um [!UICONTROL Profile Merge Rule]. See [Create a Data Source](../manage-datasources.md#create-data-source).

>[!TIP]
>
>Consulte Opções de regra de mesclagem de [Perfis Definidas](merge-rule-definitions.md) para obter descrições desses diferentes controles.

## Informações básicas {#basic-info}

Para concluir a [!UICONTROL Basic Information] seção:

1. Dê um nome ao [!UICONTROL Profile Merge Rule].
2. *(Opcional)* Descreva o [!UICONTROL Profile Merge Rule]. Uma descrição concisa ajuda a definir a função ou a finalidade de sua regra.
3. *(Opcional)* Selecione **[!UICONTROL Set as default]** se deseja tornar esse o padrão [!UICONTROL Profile Merge Rule]. Novos segmentos são associados automaticamente à regra padrão.

## Controles da exportação de dados {#data-export-controls}

[Os Controles](../data-export-controls.md) de exportação de dados são regras de classificação opcionais que podem ser aplicadas ao seu [!UICONTROL Profile Merge Rule]. Elas impedem que você envie dados para um destino quando essa ação viola a privacidade dos dados ou o contrato de uso. Ignore esta seção se não usar [!UICONTROL Data Export Controls].

## Configuração da regra de mesclagem de Perfis {#profile-merge-rule-setup}

Para concluir a [!UICONTROL Proflie Merge Rule Setup] seção:

1. Selecione um **[!UICONTROL Authenticated Option]**. As opções incluem:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Selecione um **[!UICONTROL Authenticated Profile Option]** (até 3, no máximo). Essas são as fontes [de dados](merge-rules-start.md) entre dispositivos que você criou anteriormente.
3. Selecione um **[!UICONTROL Device Option]**. As opções incluem:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. Clique em **[!UICONTROL Save]**.

### Considerações para destinos de Adobe Campaign usando IDs entre dispositivos como chaves de ID de usuário {#considerations}

No final de 2019, lançamos uma série de melhorias nas Regras de mesclagem de Perfis para melhorar a precisão dos arquivos em lote gerados com IDs de vários dispositivos. Esses aprimoramentos serão rigorosamente respeitados em sua instância do Audience Manager a partir de segunda-feira, 16 de março de 2020. Consequentemente, os segmentos mapeados para um destino usando IDs entre dispositivos pararão de produzir exportações em algumas configurações de Regras de mesclagem de Perfis.

Para garantir a integração correta entre a instância do Audience Manager e os destinos usando IDs de dispositivos cruzados, como o Adobe Campaign, verifique se você atende aos seguintes requisitos:

1. Revise a Regra de mesclagem de Perfil usada pelos segmentos mapeados para o destino da ID declarada do Adobe Campaign. A regra de mesclagem de Perfis deve usar a [!UICONTROL Last Authenticated Profile] opção, para que todos os perfis autenticados possam ser incluídos nas exportações. Se a Regra de mesclagem de Perfis estiver usando uma opção diferente, alterne para [!UICONTROL Last Authenticated Profile].
2. Selecione a fonte de dados de ID declarada do Adobe Campaign nas configurações da Regra de mesclagem do Perfil.

>[!NOTE]
>
> Aumentamos o limite da Regra de mesclagem de Perfil em 1 para clientes que enfrentam essa situação, para que você possa criar uma Regra de mesclagem de Perfis dedicada para os segmentos mapeados para o destino da ID declarada de Adobe Campaign, sem alterar as Regras de mesclagem de Perfis para outros casos de uso.

## Configurar o código da regra de mesclagem {#configure-merge-rule-code}

Siga estas instruções para configurar o [!UICONTROL Adobe Experience Platform Identity Service], [!UICONTROL DIL]e o [!DNL SDK] código móvel para trabalhar com suas regras de mesclagem.

<!-- merge-rules-configure-code.xml -->

### Pré-requisitos

É necessário configurar uma fonte [de dados](#create-data-source) entre dispositivos e regras [de mesclagem de](#create-profile-merge-rule) perfis *antes* de concluir esses procedimentos.

## Para clientes do serviço de identidade Adobe Experience Platform {#id-service-customers}

A versão [!UICONTROL Adobe Experience Platform Identity Service] e a versão mais recente da [DIL](../../dil/dil-overview.md) são recomendadas ao trabalhar com [!UICONTROL Profile Merge Rules]. No entanto, você não precisa usar o para [!UICONTROL Adobe Experience Platform Identity Service] trabalhar com esse recurso. Se você estiver usando apenas [!UICONTROL DIL], consulte a seção [DIL](#legacy-dil) herdada abaixo.

### Configurar a função Definir ID do cliente

Ao trabalhar com o [!UICONTROL Adobe Experience Platform Identity Service], a `setCustomerIDs` função passa as IDs declaradas para [!DNL Audience Manager]. Para usar uma regra de união de perfis, é necessário modificar `setCustomerIDs` para usar o código de integração especificado ao criar uma fonte de dados entre dispositivos. Por exemplo, considere que você criou uma fonte de dados entre dispositivos com o código de integração `my_datasource_ic`. Para passar uma ID declarada, adicione o código de integração à função de ID do visitante, conforme mostrado na amostra de código modificada abaixo.

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

Para obter mais informações, consulte [Criar uma fonte](#create-data-source) de dados entre dispositivos e IDs e estados [de autenticação](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)do cliente.

### Configurar `DIL.create` função

As versões mais recentes do [!UICONTROL DIL] agora coletam automaticamente [!UICONTROL declared ID] a `visitorService` função em `DIL.create` (consulte Variáveis [](../declared-ids.md#declared-id-variables)de ID declaradas). Verifique sua `DIL.create` função para verificar se ela está configurada corretamente, conforme mostrado na amostra de código abaixo.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

No par de valores chave de namespace, a variável `*`MCORG`*` é a ID da [!DNL Experience Cloud] organização. Se você não tiver essa ID, poderá encontrá-la na [!UICONTROL Administration] seção do [!DNL Experience Cloud] painel. Você precisa de permissões de administrador para visualização deste painel. See [Administration: Core Services](https://docs.adobe.com/content/help/pt-BR/core-services/interface/manage-users-and-products/admin-getting-started.html).

### Configurar SDKs

Consulte a seção [Configurar SDKs](#configure-sdks-legacy-dil) abaixo.

## DIL herdado {#legacy-dil}

Se você não está usando [!DNL Adobe Experience Platform Identity Service] ainda, você realmente deveria. Mas, nós entendemos que a mudança para um novo código requer um pensamento cuidadoso e testes. Nesses casos, verifique sua `DIL.create` função para verificar se ela está configurada corretamente, conforme mostrado na amostra de código abaixo.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Para obter mais informações, consulte a [!UICONTROL DIL] seção herdada em Variáveis [de ID](../declared-ids.md#declared-id-variables)declaradas.

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
      +&nbsp;(void)&nbsp;audienceSetDpid:(NSString&nbsp;*)dpid 
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:(NSString&nbsp;*)dpuuid; 
    </code></p>
    <p> <b>Exemplo:</b> </p><p>
    <code class="javascript">
      [ADBMobile&nbsp;audienceSetDpid:@"290"
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:@"99301393923940"];
    </code></p>
    </td>
  </tr>
 </tbody>
</table>

Consulte também Métodos de [Audience Manager para Android](hhttps://docs.adobe.com/content/help/en/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) e Métodos de [Audience Manager para iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [Criar uma fonte de dados](../manage-datasources.md#create-data-source)

