---
description: As Ferramentas de Gerenciamento em massa permitem que você crie e gerencie vários objetos de uma só vez com uma única operação. Você pode usar as Ferramentas de Gerenciamento em massa para trabalhar com fontes de dados, sinais derivados, destinos, pastas, segmentos e características.
keywords: baaam;BAAAM
seo-description: As Ferramentas de Gerenciamento em massa permitem que você crie e gerencie vários objetos de uma só vez com uma única operação. Você pode usar as Ferramentas de Gerenciamento em massa para trabalhar com fontes de dados, sinais derivados, destinos, pastas, segmentos e características.
seo-title: Introdução ao Gerenciamento em massa
solution: Audience Manager
title: Introdução ao Gerenciamento em massa
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c0c6c6aa2f1
translation-type: tm+mt
source-git-commit: 215054718e9248bd44ba99baeb2a10236701d98e

---


# Getting Started With Bulk Management{#getting-started-with-bulk-management}

As Ferramentas de Gerenciamento em massa permitem que você crie e gerencie vários objetos de uma só vez com uma única operação. Você pode usar as Ferramentas de Gerenciamento em massa para trabalhar com fontes de dados, sinais derivados, destinos, pastas, segmentos e características.

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>Os [!UICONTROL Bulk Management Tools] não *são suportados por* [!DNL Audience Manager]. Esta ferramenta é fornecida apenas para conveniência e cortesia. Para alterações em massa, recomendamos que você trabalhe com as APIs [do](../../api/rest-api-main/aam-api-getting-started.md) Audience Manager. [As permissões](../../features/administration/administration-overview.md) de grupo RBAC atribuídas na [!DNL Audience Manager] interface do usuário são respeitadas na [!UICONTROL Bulk Management Tools].

## Visão geral {#overview}

Este recurso usa uma planilha do Microsoft Excel com macros que fazem chamadas seguras e autenticadas para as [!DNL Audience Manager] APIs. A API fornece os métodos e serviços que permitem fazer alterações em massa. Você não precisa saber como codificar ou trabalhar com nossas APIs para usá-lo. A planilha contém cabeçalhos de coluna e guias que executam funções específicas de alteração em massa. Para fazer alterações em massa, basta adicionar os cabeçalhos predefinidos a planilhas específicas, fornecer as informações que deseja alterar em massa e clicar em um botão de ação. A planilha e as APIs fazem o resto do trabalho para você.

## Download {#download}

Baixe a planilha mais recente **[aqui](assets/BAAAM_August_2018.xlsm)**.

## Pré-requisitos {#prereqs}

Para usar o [!DNL Bulk Management Tools], é necessário o seguinte:

* Seu nome de [!DNL Audience Manager] usuário e senha. Como cliente, você já deve ter essas credenciais.
* Uma ID de cliente da API e uma chave secreta. O seu gerente de conta pode fornecê-los.
* A [!UICONTROL Bulk Management Tools] planilha. [Baixe a planilha](/help/using/reference/bulk-management-tools/bulk-management-intro.md#download) para obter a versão mais recente.

* Microsoft Excel em execução em [!DNL Windows] ou em uma máquina [!DNL Microsoft Windows] virtual em execução [!DNL macOS X]. É necessário usar o Excel de 32 bits para que [!UICONTROL Bulk Management Tools] funcione.

## Ações e operações {#actions-ops}

A [!UICONTROL Bulk Management Tools] planilha consiste em guias de ação, botões de ação e uma **[!UICONTROL Headers]** guia. A **[!UICONTROL Headers]** guia contém os cabeçalhos de coluna pré-formatados usados pelas guias de ação. As guias de ação contêm macros que executam a operação em massa selecionada. Para executar uma operação em massa, copie um conjunto de cabeçalhos na guia de ação apropriada, insira os dados do cabeçalho e clique em um botão de ação.

Abra a planilha e clique em um botão de ação para começar.

![](assets/bamwrkbk.png)

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
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md"> Destinos</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> Pastas</a> de características e pastas de segmentos </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md"> Segmentos</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md"> Características</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemplo de operação em massa**

Como exemplo, vamos ver como criar várias características de uma só vez. Para criar várias características em uma operação em massa, você:

1. Clique na **[!UICONTROL Headers]** guia e copie todos os rótulos sob a [!UICONTROL Create a Trait] opção.

2. Clique na **[!UICONTROL Create]** guia e cole os rótulos começando na linha 1, coluna A.
3. Forneça informações relacionadas a cada cabeçalho de coluna e clique em **[!UICONTROL Create Traits]**. Esta ação solicita que você faça logon. Seu trabalho em massa é executado depois que você autentica com êxito (consulte os requisitos [de](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) autenticação abaixo). Verifique se há uma notificação de status de tarefa no canto inferior esquerdo da planilha.

>[!NOTE]
>
>Ao trabalhar com solicitações grandes, a planilha pode ficar sem resposta e parecer inativa. Nesses casos, deixe-o em paz. A planilha se tornará responsiva quando a solicitação em massa for concluída. Se a planilha não responder por um longo período, consulte a seção [Solução de](../../reference/bulk-management-tools/bulk-troubleshooting.md)problemas.

## Requisitos e opções de autenticação {#auth-reqs}

Alterações em massa exigem autenticação. Quando você seleciona uma ação, a planilha solicita que você faça logon. Como a planilha efetua chamadas de API, é necessário configurá-la para ler sua chave secreta. Além disso, o **[!UICONTROL Domain]** campo permite fazer alterações em massa em um ambiente de teste/armazenamento temporário ou em relação à sua conta de produção ativa.

![](assets/bamauth.png)

**Requisitos de autenticação da API**

Para configurar a autenticação da API, é necessário:

* Copie e salve a chave secreta em um arquivo de texto (.txt).
* Nomeie o arquivo de texto com sua ID de cliente da API. Por exemplo, se a ID do cliente for "Usuário em massa", salve a chave em um arquivo chamado "Usuário em massa.txt".
* Salve a chave secreta e a planilha juntas na mesma pasta.

Ao fazer alterações em massa, você ainda precisará digitar um nome de usuário, senha, ID de cliente e domínio, mas a autenticação da API será automática.

**Opções de autenticação de domínio**

A autenticação de domínio dá a você a opção de testar solicitações em massa ou aplicá-las diretamente à sua conta de produção. Fazer alterações em massa no ambiente de teste não afetará sua conta de produção. As mudanças de produção estão em vigor imediatamente. O **[!UICONTROL Domain]** campo aceita os seguintes endereços, dependendo do ambiente no qual você deseja trabalhar:

* Testes: `api-beta.demdex.com`
* Produção: `api.demdex.com`

>[!MORE_LIKE_THIS]
>
>* [Download da Planilha de Gerenciamento em Massa](assets/BAAAM_August_2018.xlsm)

