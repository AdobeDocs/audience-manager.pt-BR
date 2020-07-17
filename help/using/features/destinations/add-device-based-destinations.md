---
description: Este artigo explica como configurar novos destinos baseados em dispositivos a partir da interface do usuário do Audience Manager.
seo-description: Este artigo explica como configurar novos destinos baseados em dispositivos a partir da interface do usuário do Audience Manager.
seo-title: Adicionar novos destinos com base em dispositivo
solution: Audience Manager
title: Adicionar novos destinos com base em dispositivo
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 4%

---


# Adicionar novos destinos com base em dispositivo {#add-new-device-based-destinations}

Este artigo explica como configurar novos destinos baseados em dispositivos a partir da interface do usuário do Audience Manager.

>[!IMPORTANT]
>
>Atualmente, a maioria dos destinos baseados em dispositivos não são elegíveis para o fluxo de trabalho de configuração de autoatendimento. Se o destino baseado em dispositivo que você precisa adicionar não for exibido na lista de destinos, entre em contato com seu consultor da Adobe ou com o Suporte ao cliente para obter assistência.

## Visão geral {#overview}

O processo de adicionar um novo destino baseado em dispositivo consiste em duas etapas principais. Primeiro, é necessário configurar a integração entre o Audience Manager e o parceiro de destino. Depois de fazer isso, você pode criar um novo destino baseado em dispositivo.

## Pré-requisitos {#prerequisites}

Ao criar o primeiro destino baseado em dispositivo com uma plataforma integrada, entre em contato com a Adobe Consulting ou com o Atendimento ao cliente para ativar a sincronização de ID entre o Audience Manager e a plataforma integrada para sua conta. Isso é necessário para a sincronização correta entre o Audience Manager e a plataforma de destino.

## Etapa 1. Autenticar com um Platform de destino {#step1}

Antes de criar um novo destino baseado em dispositivo, é necessário configurar a integração entre o Audience Manager e a plataforma de destino. Veja como fazer isso:

1. Faça logon na sua conta do Audience Manager e vá para **[!DNL Administration > Integrated Accounts]**. Se você tiver uma integração previamente configurada com uma plataforma de destino, deverá vê-la listada nesta página. Caso contrário, a página estará vazia.
1. Clique em **[!DNL Add Account]**.
1. Selecione a plataforma de destino com a qual deseja autenticar e clique em **[!DNL Confirm]** para ser redirecionado para a página de autenticação da plataforma selecionada.

   ![plataformas integradas](assets/dbd-integrated-platforms.png)

1. Depois de autenticar na sua conta da plataforma de destino, você será redirecionado para o Audience Manager onde deverá ver as contas do anunciante associadas. Selecione a conta do anunciante que deseja usar e clique em **[!DNL Confirm]**.

## Etapa 2: Criar um novo destino baseado em dispositivo {#step2}

Depois de configurar a integração da plataforma de destino, você pode criar o novo destino. Veja como fazer isso:

>[!NOTE]
>
>Não é possível alterar o nome de um destino baseado em dispositivo existente. Forneça um nome que o ajudará a identificar o destino corretamente.

1. Faça logon em sua conta do Audience Manager, vá para **[!DNL Audience Data > Destinations]** e clique em **[!DNL Create Destination]**.
1. Na **[!DNL Basic Information]** seção, digite um **[!DNL Name]** e **[!DNL Description]** para seu novo destino e use as configurações na lista abaixo:

   ![configuração](assets/dbd-new-basic.png)

   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**: selecione a plataforma de destino para a qual deseja enviar segmentos de audiência.
   * **[!DNL Account]**: selecione a conta do anunciante desejada associada à plataforma selecionada.
1. Clique em **[!DNL Next]**.
1. Escolha os Rótulos [de Exportação de](/help/using/features/data-export-controls.md#controls-labels) Dados que deseja definir para este destino.
1. Clique em **[!DNL Save]**.
1. Na **[!DNL Segment Mappings]** seção, selecione os segmentos de audiência que deseja enviar para esse destino.
1. Salve o destino.
