---
description: Para criar Regras de mesclagem de perfis, revise e conclua as etapas em cada um dos procedimentos descritos nesta seção.
seo-description: Para criar Regras de mesclagem de perfis, revise e conclua as etapas em cada um dos procedimentos descritos nesta seção.
seo-title: Introdução às regras de mesclagem de perfis
solution: Audience Manager
title: Introdução às regras de mesclagem de perfis
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Mesclar perfis
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
source-git-commit: b8c8f35376c5a8a85fa4eeace7b447385ee9f339
workflow-type: tm+mt
source-wordcount: '1315'
ht-degree: 4%

---

# Introdução às regras de mesclagem de perfis {#getting-started-with-profile-merge-rules}

Para criar [!UICONTROL Profile Merge Rules], revise e conclua as etapas em cada um dos procedimentos descritos nesta seção.

<!-- merge-rules-start.xml -->

## Criar uma fonte de dados entre dispositivos {#create-data-source}

Para criar uma fonte de dados entre dispositivos, vá para **[!UICONTROL Audience Data > Data Sources > Add New]** e complete as etapas de cada seção descrita aqui. Permissões de administrador são necessárias para criar ou editar uma fonte de dados entre dispositivos.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Consulte [Configurações da fonte de dados e Opções de menu](../datasources-list-and-settings.md#settings-menu-options) para obter descrições desses diferentes controles.

## Detalhes da Fonte de Dados {#details}

Para concluir a seção [!UICONTROL Data Source Details]:

1. Nomeie a fonte de dados.
2. *(Opcional)* Descreva a fonte de dados. Uma descrição concisa ajuda a definir a função ou a finalidade da fonte de dados.
3. Forneça um código de integração. Um código de integração é sua própria ID exclusiva para essa fonte de dados.
4. Na lista **[!UICONTROL ID Type]**, selecione **[!UICONTROL Cross Device]**.
5. Na lista **[!UICONTROL ID Definition]**, selecione uma opção que defina o tipo de fonte de dados. As opções incluem:
   * **[!UICONTROL Person]**: Uma ID que define uma única pessoa. Essa ID pode ser mapeada para várias [!DNL Audience Manager] IDs.
   * **[!UICONTROL Household]**: Uma ID que define um grupo de pessoas. Essa ID pode ser mapeada para várias [!DNL Audience Manager] IDs.

## Controles da exportação de dados {#export-controls}

[Os ](../data-export-controls.md) controles de exportação de dados são regras de classificação opcionais que podem ser aplicadas a uma fonte de dados e destino. Eles impedem que você envie dados para um destino quando essa ação viola uma privacidade de dados ou um contrato de uso. Ignore esta seção se não utilizar [!UICONTROL Data Export Controls].

## Configurações da fonte de dados {#settings}

[!UICONTROL Data Source Settings] A seção fornece várias opções, mas essas duas são importantes para criar uma fonte de dados entre dispositivos:

* **[!UICONTROL Use as Authenticated Profile]**: Selecionada por padrão, essa configuração permite criar um  [!UICONTROL Profile Merge Rule] com seus próprios dados autenticados.

* **[!UICONTROL Use as a Device Graph]**: Esse controle está disponível somente para contas listadas como um provedor de dados. Marcar essa caixa de seleção cria sua fonte de dados como um gráfico de dispositivos e permite compartilhá-la com outros [!DNL Audience Manager] clientes. Trabalhe com seu consultor [!DNL Audience Manager] para configurar como um provedor de dados e especificar com quais clientes esse [!UICONTROL Data Source] deve ser compartilhado. Seu consultor fornecerá a conta e o compartilhamento de gráficos de dispositivos por meio de um processo de provisionamento interno.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Esse controle permite definir o período de retenção de dados para IDs de cliente inativas. Isso determina por quanto tempo o Audience Manager mantém as IDs do cliente em nosso banco de dados depois de serem vistas pela última vez na plataforma Audience Manager. O valor padrão é 24 meses (720 dias). O valor mínimo que você pode definir é 1 mês e o valor máximo é 5 anos. Observe que todos os meses são contados como 30 dias. O Audience Manager executa um processo que exclui IDs do cliente inativas uma vez por semana, de acordo com a retenção de dados definida para IDs do cliente inativas.

Os campos de texto associados a essas configurações permitem renomear o [!UICONTROL Data Source] com um alias que aparece nas [Opções de Regra de mesclagem de perfis](merge-rule-definitions.md). Por exemplo, se você adicionar um alias a **[!UICONTROL Use as Authenticated Profile]**, esse nome aparecerá na lista [!UICONTROL Authenticated Profile Options]. Se você adicionar um alias a **[!UICONTROL Use as a Device Graph]**, esse nome aparecerá na lista [!UICONTROL Device Options].

## Criar uma regra de mesclagem de perfis {#create-profile-merge-rule}

Para criar um [!UICONTROL Profile Merge Rule], vá para **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** e complete as etapas de cada seção descrita aqui.

Você pode criar até 3 regras de mesclagem após configurar uma fonte de dados entre dispositivos. Você obtém acesso a uma Quarta Regra de mesclagem de perfis ([!UICONTROL All Cross-Device Profiles]) se inscrever para [Destinos com base em pessoas](../destinations/people-based-destinations-overview.md).

Permissões de administrador são necessárias para criar, editar ou excluir uma regra. Todos os usuários podem visualizar e usar [!UICONTROL Profile Merge Rules] existente.

<!-- create-profile-merge-rule.xml -->

**Pré-requisitos:** uma fonte de dados entre dispositivos é necessária para criar um  [!UICONTROL Profile Merge Rule]. Consulte [Criar uma fonte de dados](../manage-datasources.md#create-data-source).

>[!TIP]
>
>Consulte [Opções de Regra de mesclagem de perfis definidas](merge-rule-definitions.md) para obter descrições desses diferentes controles.

## Informações básicas {#basic-info}

Para concluir a seção [!UICONTROL Basic Information]:

1. Nomeie o [!UICONTROL Profile Merge Rule].
2. *(Opcional)* Descreva o  [!UICONTROL Profile Merge Rule]. Uma descrição concisa ajuda a definir a função ou a finalidade da regra.
3. *(Opcional)* Selecione  **[!UICONTROL Set as default]** se deseja tornar isso o padrão  [!UICONTROL Profile Merge Rule]. Novos segmentos são associados automaticamente à regra padrão.

## Controles da exportação de dados {#data-export-controls}

[Os ](../data-export-controls.md) controles de exportação de dados são regras de classificação opcionais que podem ser aplicadas ao  [!UICONTROL Profile Merge Rule]. Eles impedem que você envie dados para um destino quando essa ação viola uma privacidade de dados ou um contrato de uso. Ignore esta seção se não utilizar [!UICONTROL Data Export Controls].

## Configuração da Regra de Mesclagem de Perfis {#profile-merge-rule-setup}

Para concluir a seção [!UICONTROL Proflie Merge Rule Setup]:

1. Selecione um **[!UICONTROL Authenticated Option]**. As opções incluem:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Selecione um **[!UICONTROL Authenticated Profile Option]** (até 3, máximo). Essas são as [fontes de dados entre dispositivos](merge-rules-start.md) que você criou anteriormente.
3. Selecione um **[!UICONTROL Device Option]**. As opções incluem:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. Clique em **[!UICONTROL Save]**.

### Considerações para destinos do Adobe Campaign usando IDs entre dispositivos como chaves de ID de usuário {#considerations}

No final de 2019, lançamos uma série de melhorias nas Regras de mesclagem de perfis para melhorar a precisão dos arquivos em lote gerados com IDs de vários dispositivos. Esses aprimoramentos serão rigorosamente cumpridos na sua instância do Audience Manager, a partir de segunda-feira, 16 de março de 2020. Consequentemente, os segmentos mapeados para um destino usando IDs entre dispositivos não produzirão mais exportações em algumas configurações das Regras de mesclagem de perfis.

Para garantir a integração correta entre a instância do Audience Manager e os destinos usando IDs entre dispositivos, como o Adobe Campaign, verifique se você atende aos seguintes requisitos:

1. Revise a Regra de mesclagem de perfis usada pelos segmentos mapeados para o destino de ID declarada da Adobe Campaign. A Regra de mesclagem de perfis deve usar a opção [!UICONTROL Last Authenticated Profile] para que todos os perfis autenticados possam ser incluídos nas exportações. Se a Regra de mesclagem de perfis estiver usando uma opção diferente, alterne-a para [!UICONTROL Last Authenticated Profile].
2. Selecione a fonte de dados da ID declarada da Adobe Campaign nas configurações da Regra de mesclagem de perfis.

>[!NOTE]
>
> Se você atingiu o número máximo de [!UICONTROL Profile Merge Rules] e precisa de assistência para configurá-los com base nas instruções acima, entre em contato com o Atendimento ao cliente.

## Configurar código de regra de mesclagem {#configure-merge-rule-code}

Siga estas instruções para configurar o código [!UICONTROL Adobe Experience Platform Identity Service], [!UICONTROL DIL] e [!DNL SDK] móvel para funcionar com suas regras de mesclagem.

<!-- merge-rules-configure-code.xml -->

### Pré-requisitos

Você deve configurar uma [fonte de dados entre dispositivos](#create-data-source) e [regras de mesclagem de perfis](#create-profile-merge-rule) *antes de* concluir esses procedimentos.

## Para clientes do serviço de identidade da Adobe Experience Platform {#id-service-customers}

As [!UICONTROL Adobe Experience Platform Identity Service] e a versão mais recente de [DIL](../../dil/dil-overview.md) são recomendadas ao trabalhar com [!UICONTROL Profile Merge Rules]. No entanto, você não precisa usar o [!UICONTROL Adobe Experience Platform Identity Service] para trabalhar com esse recurso. Se estiver usando [!UICONTROL DIL], consulte a [seção DIL herdada](#legacy-dil) abaixo.

### Configurar a função Definir ID do cliente

Ao trabalhar com o [!UICONTROL Adobe Experience Platform Identity Service], a função `setCustomerIDs` passa as IDs declaradas para [!DNL Audience Manager]. Para usar uma regra de mesclagem de perfil, você deve modificar `setCustomerIDs` para usar o código de integração especificado ao criar uma fonte de dados entre dispositivos. Por exemplo, considere que você criou uma fonte de dados entre dispositivos com o código de integração `my_datasource_ic`. Para transmitir uma ID declarada, você adicionaria o código de integração à função de ID do visitante, conforme mostrado na amostra de código modificada abaixo.

#### Amostra de código genérico

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

Para obter mais informações, consulte [Criar uma fonte de dados entre dispositivos](#create-data-source) e [IDs do cliente e Estados de autenticação](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html).

### Configurar a função `DIL.create`

As versões mais recentes de [!UICONTROL DIL] agora selecionam automaticamente [!UICONTROL declared ID] da função `visitorService` em `DIL.create` (consulte [Variáveis de ID declaradas](../declared-ids.md#declared-id-variables)). Verifique sua função `DIL.create` para verificar se ela está configurada corretamente, como mostrado na amostra de código abaixo.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

No par de valores chave do namespace, a variável `*`MCORG`*` é a [!DNL Experience Cloud] ID da organização. Se não tiver essa ID, você poderá encontrá-la na seção [!UICONTROL Administration] do painel [!DNL Experience Cloud]. Você precisa de permissões de administrador para exibir este painel. Consulte [Administração: Principais serviços](https://docs.adobe.com/content/help/pt-BR/core-services/interface/manage-users-and-products/admin-getting-started.html).

### Configurar SDKs

Consulte a seção [Configurar SDKs](#configure-sdks-legacy-dil) abaixo.

## DIL herdado {#legacy-dil}

Se você ainda não estiver usando [!DNL Adobe Experience Platform Identity Service], você realmente deve. Mas, entendemos que mover-se para um novo código requer um pensamento cuidadoso e testes. Nesses casos, verifique sua função `DIL.create` para verificar se ela está configurada corretamente, como mostrado na amostra de código abaixo.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Para obter mais informações, consulte a seção herdada [!UICONTROL DIL] em [Variáveis de ID declaradas](../declared-ids.md#declared-id-variables).

### Configurar SDKs {#configure-sdks-legacy-dil}

Verifique os métodos em seu código [!DNL SDK] que permitem passar [!UICONTROL declared IDs] de [!DNL Android] e [!DNL iOS] dispositivos móveis. Os nomes das variáveis das bibliotecas de código [!DNL Android] e [!DNL iOS] são iguais:

* `dpid`: A ID da fonte de dados entre dispositivos.
* `dpuuid`: O  [!UICONTROL declared ID] (ou seja, a ID do usuário).

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

Consulte também [Métodos do Audience Manager para Android](https://docs.adobe.com/content/help/en/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) e [Métodos do Audience Manager para iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [Criar uma fonte de dados](../manage-datasources.md#create-data-source)

