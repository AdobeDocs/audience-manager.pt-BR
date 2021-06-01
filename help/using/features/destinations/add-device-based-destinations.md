---
description: Este artigo explica como configurar novos destinos com base em dispositivos na interface do usuário do Audience Manager.
seo-description: Este artigo explica como configurar novos destinos com base em dispositivos na interface do usuário do Audience Manager.
seo-title: Adicionar novos destinos com base em dispositivo
solution: Audience Manager
title: Adicionar novos destinos com base em dispositivo
feature: Noções básicas sobre o destino
exl-id: c5d7de2e-085d-48b9-a596-381503c79f55
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 4%

---

# Adicionar novos destinos com base em dispositivo {#add-new-device-based-destinations}

Este artigo explica como configurar novos destinos com base em dispositivos na interface do usuário do Audience Manager.

>[!IMPORTANT]
>
>Atualmente, a maioria dos destinos com base em dispositivos não está qualificada para o fluxo de trabalho de configuração de autoatendimento. Se o destino baseado em dispositivo que você precisa adicionar não for exibido na lista de destinos, entre em contato com o consultor do Adobe ou com o Suporte ao cliente para obter assistência.

## Visão geral {#overview}

O processo de adição de um novo destino baseado em dispositivo consiste em duas etapas principais. Primeiro, você precisa configurar a integração entre o Audience Manager e o parceiro de destino. Depois disso, você poderá criar um novo destino com base em dispositivo.

## Pré-requisitos {#prerequisites}

Ao criar o primeiro destino baseado em dispositivo com uma plataforma integrada, entre em contato com a Adobe Consulting ou com o Atendimento ao cliente para habilitar a sincronização de ID entre o Audience Manager e a plataforma integrada para sua conta. Isso é necessário para a sincronização correta entre o Audience Manager e a plataforma de destino.

## Etapa 1. Autenticar com uma plataforma de destino {#step1}

Antes de criar um novo destino com base em dispositivo, é necessário configurar a integração entre o Audience Manager e a plataforma de destino. Veja como fazer isso:

1. Faça logon na sua conta do Audience Manager e vá para **[!DNL Administration > Integrated Accounts]**. Se você tiver uma integração configurada anteriormente com uma plataforma de destino, ela deverá ser exibida nesta página. Caso contrário, a página ficará vazia.
1. Clique em **[!DNL Add Account]**.
1. Selecione a plataforma de destino com a qual você deseja autenticar e clique em **[!DNL Confirm]** para ser redirecionado para a página de autenticação da plataforma selecionada.

   ![plataformas integradas](assets/dbd-integrated-platforms.png)

1. Depois de autenticar para a conta da plataforma de destino, você será redirecionado para o Audience Manager, onde deverá ver as contas de anunciante associadas. Selecione a conta do anunciante que deseja usar e clique em **[!DNL Confirm]**.

## Etapa 2: Criar um novo destino com base em dispositivo {#step2}

Após configurar a integração da plataforma de destino, é possível criar o novo destino. Veja como fazer isso:

>[!NOTE]
>
>Não é possível alterar o nome de um destino baseado em dispositivo existente. Certifique-se de fornecer um nome que ajudará a identificar o destino corretamente.

1. Faça logon na sua conta do Audience Manager, vá para **[!DNL Audience Data > Destinations]** e clique em **[!DNL Create Destination]**.
1. Na seção **[!DNL Basic Information]** , digite um **[!DNL Name]** e **[!DNL Description]** para o novo destino e use as configurações na lista abaixo:

   ![configuração](assets/dbd-new-basic.png)

   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**:  [!DNL Device-Based];
   * **[!DNL Platform]**: selecione a plataforma de destino para a qual deseja enviar segmentos de público-alvo.
   * **[!DNL Account]**: selecione a conta do anunciante desejada associada à plataforma selecionada.
1. Clique em **[!DNL Next]**.
1. Escolha os [Rótulos de Exportação de Dados](/help/using/features/data-export-controls.md#controls-labels) que deseja definir para este destino.
1. Clique em **[!DNL Save]**.
1. Na seção **[!DNL Segment Mappings]**, selecione os segmentos de público-alvo que deseja enviar para esse destino.
1. Salve o destino.
