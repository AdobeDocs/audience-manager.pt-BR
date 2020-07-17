---
description: As Ferramentas de Gerenciamento em massa permitem que você crie e gerencie vários objetos de uma só vez com uma única operação. Você pode usar as Ferramentas de Gerenciamento em massa para trabalhar com fontes de dados, sinais derivados, destinos, pastas, segmentos e características.
keywords: baaam;BAAAM;download baaam
seo-description: As Ferramentas de Gerenciamento em massa permitem que você crie e gerencie vários objetos de uma só vez com uma única operação. Você pode usar as Ferramentas de Gerenciamento em massa para trabalhar com fontes de dados, sinais derivados, destinos, pastas, segmentos e características.
seo-title: Introdução ao gerenciamento em massa
solution: Audience Manager
title: Introdução ao gerenciamento em massa
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 3%

---


# Introdução ao gerenciamento em massa{#getting-started-with-bulk-management}

O [!DNL Bulk Management Tools] permite que você crie e gerencie vários objetos de uma só vez com uma única operação. Você pode usar [!DNL Bulk Management Tools] para trabalhar com [!UICONTROL data sources], [!UICONTROL derived signals], [!UICONTROL destinations], [!UICONTROL folders], [!UICONTROL models], [!UICONTROL segments]e [!UICONTROL traits].

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>[As permissões](../../features/administration/administration-overview.md) de grupo RBAC atribuídas na interface de [!DNL Audience Manager] usuário são respeitadas na [!UICONTROL Bulk Management Tools].

## Visão geral {#overview}

This feature uses a [!DNL Microsoft Excel] spreadsheet with macros that make secure, authenticated calls to the [!DNL Audience Manager] APIs. A API fornece os métodos e serviços que permitem fazer alterações em massa. Você não precisa saber como codificar ou trabalhar com nossas APIs para usá-lo. A planilha contém cabeçalhos de coluna e guias que executam funções específicas de alteração em massa. Para fazer alterações em massa, basta adicionar os cabeçalhos predefinidos a planilhas específicas, fornecer as informações que deseja alterar em massa e clicar em um botão de ação. A planilha e as APIs fazem o resto do trabalho para você.

## Download {#download}

Download the latest worksheet **[here](assets/BAAAM_V2_20200502.xlsm)**.

## Pré-requisitos {#prereqs}

Para usar o [!DNL Bulk Management Tools], é necessário o seguinte:

* Seu [!DNL Experience Cloud] logon. Como cliente, você já deve ter essas credenciais.
* A [!DNL Bulk Management Tools] planilha. [Baixe a planilha](assets/BAAAM_V2_20200502.xlsm) para obter a versão mais recente.
* [!DNL Microsoft Excel] em execução em [!DNL macOS] ou 64 bits [!DNL Microsoft Windows]. Recomendamos que você use a versão mais recente do [!DNL Microsoft Excel].
* Ao abrir a planilha, você deve **Ativar macros** para que [!DNL Bulk Management Tools] funcionem.

## Requisitos e opções de autenticação {#auth-reqs}

Alterações em massa exigem autenticação. Antes de executar qualquer ação, você deve fazer logon. Como a planilha efetua chamadas de API, é necessário configurá-la para autenticar em sua conta de usuário.

**Requisitos de autenticação da API**

A segunda versão do [!DNL Bulk Management Tools], lançada em outubro de 2019, simplifica o processo de autenticação. As etapas de autenticação nesta versão são descritas abaixo:

1. Abra a planilha e navegue até a **[!UICONTROL Config]** planilha.
2. Siga as etapas descritas na planilha.
   ![](assets/baaam-authentication.png)
3. Após concluir as etapas, você está autorizado a fazer alterações em massa.

Ao fazer alterações em massa, você ainda precisará confirmar que está autorizado a fazer as alterações, mas a autenticação da API é automática.

**Opções de autenticação de domínio**

A autenticação de domínio dá a você a opção de testar solicitações em massa ou aplicá-las diretamente à sua conta de produção. Fazer alterações em massa no ambiente beta não afetará sua conta de produção. As mudanças de produção estão em vigor imediatamente. A folha de gerenciamento em massa permite que você trabalhe nos seguintes ambientes:

* Beta 
* Produção

## Ações e operações {#actions-ops}

A [!UICONTROL Bulk Management Tools] planilha consiste em botões de autenticação, guias de ação, botões de ação e uma **[!UICONTROL Headers]** guia. A **[!UICONTROL Headers]** guia contém os cabeçalhos de coluna pré-formatados usados pelas guias de ação. As guias de ação contêm macros que executam a operação em massa selecionada. Para executar uma operação em massa, copie um conjunto de cabeçalhos na guia de ação apropriada, insira os dados do cabeçalho e clique em um botão de ação.

Após a [autenticação](#auth-reqs), clique em um botão de ação para começar.

![](assets/baaam-worksheet.png)

A tabela abaixo lista as operações que você pode executar e os itens que você pode manipular com as [!UICONTROL Bulk Management Tools] planilhas.

<table id="table_B9B3E09B692E42BAA52FB32C18B00709"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ações </th> 
   <th colname="col2" class="entry"> Objetos </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>As ações em massa aparecem nas guias na parte inferior da planilha e incluem: </p> <p> 
     <ul id="ul_49F46B9E00C045D29E40258EB7BDCFBB"> 
      <li id="li_193C41EA19EF4D738FBA037D2BF9B05C">Solicitações </li> 
      <li id="li_5BE2E13D839F4958AAA5C01B7EFC5096">Atualização </li> 
      <li id="li_4CCCC739795945DF8C89787F9A67EB88">Criar  </li> 
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">Estimativa </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">Excluir </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Os objetos que podem ser alterados em massa estão localizados na guia <b><span class="uicontrol"> Cabeçalhos</span></b> e incluem: </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> Fontes de dados</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> Sinais derivados</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md">Destinos </a> </li> 
      <li> <a href="../../features/algorithmic-models/understanding-models.md"> Modelos</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> Pastas</a> de características e pastas de segmentos </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md">Segmentos </a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md">Características </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemplo de operação em massa**

Como exemplo, vamos ver como criar várias características de uma só vez. Para criar várias características em uma operação em massa, você:

1. Clique na **[!UICONTROL Headers]** guia e copie todos os rótulos sob a [!UICONTROL Create a Trait] opção.
2. Clique na **[!UICONTROL Create]** guia e cole os rótulos começando na linha 1, coluna A.
3. Forneça informações relacionadas a cada cabeçalho de coluna e clique em **[!UICONTROL Create Traits]**. Esta ação solicita que você confirme sua autenticação. Seu trabalho em massa é executado depois que você confirma sua autenticação. Verifique se há uma notificação de status de tarefa no canto inferior esquerdo da planilha.


>[!NOTE]
>
>Ao trabalhar com solicitações grandes, a planilha pode ficar sem resposta e parecer inativa. Nesses casos, deixe-o em paz. A planilha se tornará responsiva quando a solicitação em massa for concluída. Se a planilha não responder por um longo período de tempo, consulte a seção [Solução de](../../reference/bulk-management-tools/bulk-troubleshooting.md)problemas.

