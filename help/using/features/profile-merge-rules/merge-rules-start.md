---
description: Para criar Regras de mesclagem de perfis, revise e conclua as etapas em cada um dos procedimentos descritos nesta seção.
seo-description: To create Profile Merge Rules review and complete the steps in each of the procedures described in this section.
seo-title: Getting Started with Profile Merge Rules
solution: Audience Manager
title: Introdução às regras de mesclagem de perfis
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 3%

---

# Introdução às regras de mesclagem de perfis {#getting-started-with-profile-merge-rules}

Para criar [!UICONTROL Profile Merge Rules], revise e conclua as etapas em cada um dos procedimentos descritos nesta seção.

<!-- merge-rules-start.xml -->

## Criar uma fonte de dados entre dispositivos {#create-data-source}

Para criar uma fonte de dados entre dispositivos, vá para **[!UICONTROL Audience Data > Data Sources > Add New]** e conclua as etapas para cada seção descrita aqui. As permissões de administrador são necessárias para criar ou editar uma fonte de dados entre dispositivos.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Consulte [Configurações da fonte de dados e opções de menu](../datasources-list-and-settings.md#settings-menu-options) para obter descrições desses diferentes controles.

## Detalhes da fonte de dados {#details}

Para concluir o [!UICONTROL Data Source Details] seção:

1. Nomeie a fonte de dados.
2. *(Opcional)* Descreva a fonte de dados. Uma descrição concisa ajuda a definir a função ou a finalidade da fonte de dados.
3. Forneça um código de integração. Um código de integração é o seu próprio identificador exclusivo para essa fonte de dados.
4. No **[!UICONTROL ID Type]** selecione **[!UICONTROL Cross Device]**.
5. No **[!UICONTROL ID Definition]** selecione uma opção que defina o tipo de fonte de dados. As opções incluem:
   * **[!UICONTROL Person]**: uma ID que define uma única pessoa. Essa ID pode ser mapeada para vários [!DNL Audience Manager] IDs.
   * **[!UICONTROL Household]**: uma ID que define um grupo de pessoas. Essa ID pode ser mapeada para vários [!DNL Audience Manager] IDs.

## Controles da exportação de dados {#export-controls}

[Controles da exportação de dados](../data-export-controls.md) são regras de classificação opcionais que podem ser aplicadas a uma origem e um destino de dados. Eles impedem que você envie dados para um destino quando essa ação viola uma privacidade de dados ou um contrato de uso. Pule esta seção se não usar [!UICONTROL Data Export Controls].

## Configurações da fonte de dados {#settings}

[!UICONTROL Data Source Settings] A seção fornece várias opções, mas essas duas são importantes para criar uma fonte de dados entre dispositivos:

* **[!UICONTROL Use as Authenticated Profile]**: selecionada por padrão, essa configuração permite criar um [!UICONTROL Profile Merge Rule] com seus próprios dados autenticados.

* **[!UICONTROL Use as a Device Graph]**: esse controle está disponível somente para contas listadas como um provedor de dados. Marcar essa caixa de seleção cria sua fonte de dados como um gráfico de dispositivos e permite compartilhá-lo com outras pessoas [!DNL Audience Manager] clientes. Trabalhe com o seu [!DNL Audience Manager] consultor para ser configurado como provedor de dados e especificar quais clientes esse [!UICONTROL Data Source] deve ser compartilhado com. O consultor provisionará sua conta e o compartilhamento do gráfico do dispositivo por meio de processos internos de provisionamento.

* **[!UICONTROL Data retention for inactive Customer IDs]**: esse controle permite definir o período de retenção de dados para IDs de cliente inativas. Isso determina por quanto tempo o Audience Manager mantém as IDs do cliente em nosso banco de dados após serem vistas pela última vez na plataforma Audience Manager. O valor padrão é de 24 meses (720 dias). O valor mínimo que pode ser definido é 1 mês e o máximo é 5 anos. Observe que contamos todos os meses como 30 dias. O Audience Manager executa um processo que exclui IDs do cliente inativas uma vez por semana, de acordo com a retenção de dados definida para IDs do cliente inativas.

Os campos de texto associados a essas configurações permitem renomear o [!UICONTROL Data Source] com um alias que aparece na variável [Opções de Regra de mesclagem de perfis](merge-rule-definitions.md). Por exemplo, se você adicionar um alias a **[!UICONTROL Use as Authenticated Profile]**, esse nome aparece no campo [!UICONTROL Authenticated Profile Options] lista. Se você adicionar um alias a **[!UICONTROL Use as a Device Graph]**, esse nome aparece no campo [!UICONTROL Device Options] lista.

## Criar uma regra de mesclagem de perfis {#create-profile-merge-rule}

Para criar um [!UICONTROL Profile Merge Rule], vá para **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** e conclua as etapas para cada seção descrita aqui.

Você pode criar até três regras de mesclagem após configurar uma fonte de dados entre dispositivos. Você obtém acesso a uma 4ª Regra de mesclagem de perfis ([!UICONTROL All Cross-Device Profiles]) se você se inscrever para [Destinos com base em pessoas](../destinations/people-based-destinations-overview.md).

São necessárias permissões de administrador para criar, editar ou excluir uma regra. Todos os usuários podem visualizar e usar o existente [!UICONTROL Profile Merge Rules].

<!-- create-profile-merge-rule.xml -->

**Pré-requisitos:** É necessária uma fonte de dados entre dispositivos para criar uma [!UICONTROL Profile Merge Rule]. Consulte [Criar uma fonte de dados](../manage-datasources.md#create-data-source).

>[!TIP]
>
>Consulte [Definição das Opções de Regra de Mesclagem de Perfis](merge-rule-definitions.md) para obter descrições desses diferentes controles.

## Informações básicas {#basic-info}

Para concluir o [!UICONTROL Basic Information] seção:

1. Nomeie o [!UICONTROL Profile Merge Rule].
2. *(Opcional)* Descreva a [!UICONTROL Profile Merge Rule]. Uma descrição concisa ajuda a definir a função ou a finalidade da regra.
3. *(Opcional)* Selecionar **[!UICONTROL Set as default]** se você quiser tornar isso o padrão [!UICONTROL Profile Merge Rule]. Novos segmentos são associados automaticamente à regra padrão.

## Controles da exportação de dados {#data-export-controls}

[Controles da exportação de dados](../data-export-controls.md) são regras de classificação opcionais que podem ser aplicadas ao seu [!UICONTROL Profile Merge Rule]. Eles impedem que você envie dados para um destino quando essa ação viola uma privacidade de dados ou um contrato de uso. Pule esta seção se não usar [!UICONTROL Data Export Controls].

## Configuração da regra de mesclagem de perfis {#profile-merge-rule-setup}

Para concluir o [!UICONTROL Proflie Merge Rule Setup] seção:

1. Selecione um **[!UICONTROL Authenticated Option]**. As opções incluem:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Selecione um **[!UICONTROL Authenticated Profile Option]** (até 3, no máximo). Estas são as [fontes de dados entre dispositivos](merge-rules-start.md) você criou anteriormente.
3. Selecione um **[!UICONTROL Device Option]**. As opções incluem:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
4. Clique em **[!UICONTROL Save]**.

### Considerações para destinos do Adobe Campaign que usam IDs entre dispositivos como chaves de ID de usuário {#considerations}

No final de 2019, lançamos uma série de melhorias nas Regras de mesclagem de perfis para melhorar a precisão dos arquivos em lote gerados com IDs entre dispositivos. Esses aprimoramentos serão estritamente honrados em sua instância do Audience Manager a partir de segunda-feira, 16 de março de 2020. Consequentemente, os segmentos mapeados para um destino usando IDs de vários dispositivos deixarão de produzir exportações em algumas configurações de Regras de mesclagem de perfis.

Para garantir a integração correta entre sua instância do Audience Manager e destinos usando IDs entre dispositivos, como o Adobe Campaign, verifique se você atende aos seguintes requisitos:

1. Revise a Regra de mesclagem de perfis usada pelos segmentos mapeados para o destino da sua ID declarada do Adobe Campaign. A Regra de mesclagem de perfis deve usar o [!UICONTROL Last Authenticated Profile] para que todos os perfis autenticados pudessem ser incluídos nas exportações. Se sua Regra de mesclagem de perfis estiver usando uma opção diferente, alterne-a para [!UICONTROL Last Authenticated Profile].
2. Selecione a fonte de dados ID declarada da Adobe Campaign nas configurações da Regra de mesclagem de perfis.

>[!NOTE]
>
> Se tiver atingido o número máximo de [!UICONTROL Profile Merge Rules] e precisar de assistência para configurá-los com base nas instruções acima, entre em contato com o Atendimento ao cliente.

## Configurar código de regra de mesclagem {#configure-merge-rule-code}

Siga estas instruções para configurar o [!UICONTROL Adobe Experience Platform Identity Service], [!UICONTROL DIL]e dispositivos móveis [!DNL SDK] para trabalhar com as regras de mesclagem.

<!-- merge-rules-configure-code.xml -->

### Pré-requisitos

Você deve configurar um [fonte de dados entre dispositivos](#create-data-source) e [regras de mesclagem de perfis](#create-profile-merge-rule) *antes* procedimentos.

## Para clientes do serviço de identidade da Adobe Experience Platform {#id-service-customers}

A variável [!UICONTROL Adobe Experience Platform Identity Service] e a versão mais recente de [DIL](../../dil/dil-overview.md) são recomendadas ao trabalhar com [!UICONTROL Profile Merge Rules]. No entanto, você não precisa usar o [!UICONTROL Adobe Experience Platform Identity Service] para trabalhar com esse recurso. Se você estiver apenas usando [!UICONTROL DIL], consulte o [seção DIL herdada](#legacy-dil) abaixo.

### Configurar a função Definir ID do cliente

Ao trabalhar com a [!UICONTROL Adobe Experience Platform Identity Service], o `setCustomerIDs` A função passa IDs declaradas para [!DNL Audience Manager]. Para usar uma regra de mesclagem de perfis, você deve modificar `setCustomerIDs` para usar o código de integração especificado ao criar uma fonte de dados entre dispositivos. Por exemplo, digamos que você tenha criado uma fonte de dados entre dispositivos com o código de integração `my_datasource_ic`. Para transmitir uma ID declarada, você adicionaria o código de integração à função de ID de visitante, conforme mostrado na amostra de código modificada abaixo.

#### Amostra de código genérico

```javascript
visitor.setCustomerIDs({
  "userid":{
      "id":"12345",
      "authState":Visitor.AuthState.AUTHENTICATED
```

#### Exemplo de código modificado

```javascript
visitor.setCustomerIDs({
  "my_datasource_ic":{
     "id":"12345",
     "authState":Visitor.AuthState.AUTHENTICATED
```

Para obter mais informações, consulte [Criar uma fonte de dados entre dispositivos](#create-data-source) e [Estados de autenticação e IDs do cliente](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html).

### Configurar `DIL.create` função

As versões mais recentes da [!UICONTROL DIL] agora, selecione automaticamente a variável [!UICONTROL declared ID] do `visitorService` função em `DIL.create` (consulte [Variáveis de ID declaradas](../declared-ids.md#declared-id-variables)). Verifique o seu `DIL.create` para garantir que isso esteja configurado corretamente, conforme mostrado na amostra de código abaixo.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

No par de valor-chave do namespace, a variável `*`MCORG`*` é a sua [!DNL Experience Cloud] ID da organização. Se você não tiver essa ID, poderá encontrá-la na [!UICONTROL Administration] seção do [!DNL Experience Cloud] painel. Você precisa de permissões de administrador para visualizar este painel. Consulte [Administração: Serviços principais](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

### Configurar SDKs

Consulte a [Configurar SDKs](#configure-sdks-legacy-dil) abaixo.

## DIL herdado {#legacy-dil}

Se você não estiver usando [!DNL Adobe Experience Platform Identity Service] ainda assim, você realmente deveria. Porém, entendemos que a mudança para um novo código requer pensamento e testes cuidadosos. Nesses casos, verifique o `DIL.create` para garantir que isso esteja configurado corretamente, conforme mostrado na amostra de código abaixo.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Para obter mais informações, consulte a antiga [!UICONTROL DIL] seção em [Variáveis de ID declaradas](../declared-ids.md#declared-id-variables).

### Configurar SDKs {#configure-sdks-legacy-dil}

Verifique os métodos no [!DNL SDK] código que permite passar [!UICONTROL declared IDs] de [!DNL Android] e [!DNL iOS] dispositivos móveis. Os nomes das variáveis para a variável [!DNL Android] e [!DNL iOS] as bibliotecas de código são as mesmas:

* `dpid`: a ID da fonte de dados entre dispositivos.
* `dpuuid`: A variável [!UICONTROL declared ID] (ou seja, a ID do usuário).

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

Consulte também, [Métodos do Audience Manager para Android](https://experienceleague.adobe.com/docs/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) e [Métodos Audience Manager para o iOS](https://experienceleague.adobe.com/docs/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [Criar uma fonte de dados](../manage-datasources.md#create-data-source)

