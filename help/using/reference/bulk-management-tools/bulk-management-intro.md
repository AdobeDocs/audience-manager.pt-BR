---
description: As Ferramentas de gerenciamento em massa permitem criar e gerenciar vários objetos de uma só vez com uma única operação. Você pode usar Ferramentas de gerenciamento em massa para trabalhar com fontes de dados, sinais derivados, destinos, pastas, segmentos e características.
keywords: baaam; BAAAM
seo-description: As Ferramentas de gerenciamento em massa permitem criar e gerenciar vários objetos de uma só vez com uma única operação. Você pode usar Ferramentas de gerenciamento em massa para trabalhar com fontes de dados, sinais derivados, destinos, pastas, segmentos e características.
seo-title: Introdução ao gerenciamento em massa
solution: Audience Manager
title: Introdução ao gerenciamento em massa
uuid: 4 bc 6 ae 0 a -315 c -4 ce 7-a 68 e-cc 0 c 6 c 6 aa 2 f 1
translation-type: tm+mt
source-git-commit: f6fd1b99467a35b3f2c978c4b2e28d562eaa3c52

---


# Getting Started With Bulk Management{#getting-started-with-bulk-management}

As Ferramentas de gerenciamento em massa permitem criar e gerenciar vários objetos de uma só vez com uma única operação. Você pode usar Ferramentas de gerenciamento em massa para trabalhar com fontes de dados, sinais derivados, destinos, pastas, segmentos e características.

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Essa ferramenta é fornecida para conveniência e apenas como cortesia. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [As permissões de grupo RBAC](../../features/administration/administration-overview.md) atribuídas na [!DNL Audience Manager] interface do usuário são respeitadas [!UICONTROL Bulk Management Tools].

## Visão geral {#overview}

This feature uses a Microsoft Excel spreadsheet with macros that make secure, authenticated calls to the [!DNL Audience Manager] APIs. A API fornece os métodos e serviços que permitem fazer alterações em massa. Você não precisa saber como codificar ou trabalhar com nossas apis para usá-lo. A planilha contém cabeçalhos de coluna e guias que executam funções de alteração em massa específicas. Para fazer alterações em massa, tudo o que você fizer é adicionar os cabeçalhos predefinidos a planilhas específicas, fornecer as informações que deseja modificar em massa e clicar em um botão de ação. A planilha e as apis fazem o resto do trabalho para você.

## Pré-requisitos {#prereqs}

To use the [!DNL Bulk Management Tools], you need the following:

* Your [!DNL Audience Manager] user name and password. Como cliente, você já deve ter essas credenciais.
* Uma ID de cliente de API e uma chave secreta. Seu gerente de contas pode fornecer essas informações.
* The [!UICONTROL Bulk Management Tools] worksheet. **[Baixe a planilha](assets/BAAAM_August_2018.xlsm)** para obter a versão mais recente.

* Microsoft Excel running on [!DNL Windows] or in a [!DNL Microsoft Windows] virtual machine running on [!DNL macOS X]. You must use 32-bit Excel for the [!UICONTROL Bulk Management Tools] to work.

## Actions and operations {#actions-ops}

The [!UICONTROL Bulk Management Tools] worksheet consists of action tabs, action buttons, and a **[!UICONTROL Headers]** tab. The **[!UICONTROL Headers]** tab contains the pre-formatted column headers used by the action tabs. As guias de ação contêm macros que realizam a operação em massa selecionada. Para executar uma operação em massa, copie um conjunto de cabeçalhos na guia de ação apropriada, digite os dados do cabeçalho e clique em um botão de ação.

Abra a planilha e clique em um botão de ação para começar.

![](assets/bamwrkbk.png)

The table below lists the operations you can perform and items you can manipulate with the [!UICONTROL Bulk Management Tools] worksheets.

<table id="table_B9B3E09B692E42BAA52FB32C18B00709"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ações </th> 
   <th colname="col2" class="entry"> Objetos </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>As ações em massa aparecem em guias na parte inferior da planilha e incluem: </p> <p> 
     <ul id="ul_49F46B9E00C045D29E40258EB7BDCFBB"> 
      <li id="li_193C41EA19EF4D738FBA037D2BF9B05C">Solicitações </li> 
      <li id="li_5BE2E13D839F4958AAA5C01B7EFC5096">Atualização </li> 
      <li id="li_4CCCC739795945DF8C89787F9A67EB88">Criar  </li> 
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">Estimativa </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">Excluir </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>The objects you can change in bulk are located under the <b><span class="uicontrol"> Headers</span></b> tab and include: </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> Fontes de dados</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> Sinais derivados</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md"> Destinos</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> Pastas de características</a> e pastas de segmentos </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md"> Segmentos</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md"> Características</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemplo de operação em massa**

Como exemplo, vejamos como criar várias características de uma vez. Para criar várias características em uma operação em massa, você deve:

1. Click the **[!UICONTROL Headers]** tab and copy all the labels under the [!UICONTROL Create a Trait] option.

2. Click the **[!UICONTROL Create]** tab and paste the labels starting in row 1, column A.
3. Provide information related to each column header and click **[!UICONTROL Create Traits]**. Esta ação solicita que você faça logon. Your bulk job runs after you successfully authenticate (see the [authentication requirements](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) below). Verifique o canto inferior esquerdo da planilha para obter uma notificação de status de trabalho.

>[!NOTE]
>
>Ao trabalhar com solicitações grandes, a planilha pode ficar sem resposta e parecer inativa. Nesses casos, deixe tudo sozinho. A planilha se tornará responsiva quando a solicitação em massa for concluída. If the worksheet does not respond for a long period of time, see the [troubleshooting section](../../reference/bulk-management-tools/bulk-troubleshooting.md).

## Authentication requirements and options {#auth-reqs}

As alterações em massa exigem autenticação. Quando uma ação é selecionada, a planilha solicita o logon. Como a planilha faz chamadas de API, você precisa configurá-la para ler sua chave secreta. And, the **[!UICONTROL Domain]** field lets you make bulk changes in a staging/test environment or against your live, production account.

![](assets/bamauth.png)

**Requisitos de autenticação da API**

Para configurar a autenticação de API, você deve:

* Copie e salve a chave secreta em um arquivo de texto (.txt).
* Nomeie o arquivo de texto com a ID do cliente da API. Por exemplo, se a ID do cliente for &quot;Usuário em massa&quot;, salve a chave em um arquivo chamado &quot;Bulk-User. txt&quot;.
* Salve a chave e a planilha secreta juntas na mesma pasta.

Ao fazer alterações em massa, você ainda precisará inserir um nome de usuário, senha, ID do cliente e domínio, mas a autenticação da API é automática.

**Opções de autenticação de domínio**

A autenticação de domínio oferece a você a opção de testar solicitações em massa ou aplicá-las diretamente à sua conta de produção. Fazer alterações em massa no ambiente de teste não afetará sua conta de produção. As alterações de produção estão vigentes imediatamente. **[!UICONTROL Domain]** O campo aceita os seguintes endereços, dependendo do ambiente que você deseja trabalhar:

* Testes: `api-beta.demdex.com`
* Produção: `api.demdex.com`

>[!MORE_ LIKE_ THIS]
>
>* [Baixar a planilha de gerenciamento em massa](assets/BAAAM_August_2018.xlsm)

