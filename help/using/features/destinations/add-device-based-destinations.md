---
description: Este artigo explica como configurar novos destinos com base em dispositivos na interface do usuário do Audience Manager.
seo-description: This article explains how to configure new device-based destinations from the Audience Manager user interface.
seo-title: Add New Device-Based Destinations
solution: Audience Manager
title: Adicionar novos destinos com base em dispositivo
feature: Destination Basics
exl-id: c5d7de2e-085d-48b9-a596-381503c79f55
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 3%

---

# Adicionar novos destinos com base em dispositivo {#add-new-device-based-destinations}

Este artigo explica como configurar novos destinos com base em dispositivos na interface do usuário do Audience Manager.

>[!IMPORTANT]
>
>Atualmente, a maioria dos destinos com base em dispositivos não está qualificada para o fluxo de trabalho de configuração de autoatendimento. Se o destino baseado em dispositivo que você precisa adicionar não for exibido na lista de destinos, entre em contato com o consultor da Adobe ou com o Suporte ao cliente para obter assistência.

## Visão geral {#overview}

O processo de adicionar um novo destino baseado em dispositivo consiste em duas etapas principais. Primeiro, é necessário configurar a integração entre o Audience Manager e o parceiro de destino. Depois de fazer isso, você pode criar um novo destino baseado em dispositivo.

## Pré-requisitos {#prerequisites}

Ao criar o primeiro destino baseado em dispositivo com uma plataforma integrada, entre em contato com a Adobe Consulting ou com o Atendimento ao cliente para ativar a sincronização de ID entre o Audience Manager e a plataforma integrada da sua conta. Isso é necessário para a sincronização correta entre o Audience Manager e a plataforma de destino.

## Etapa 1. Autenticar com uma plataforma de destino {#step1}

Antes de criar um novo destino baseado em dispositivo, é necessário configurar a integração entre o Audience Manager e a plataforma de destino. Veja como fazer isso:

1. Faça logon na sua conta Audience Manager e acesse **[!DNL Administration > Integrated Accounts]**. Se você tiver uma integração configurada anteriormente com uma plataforma de destino, deverá vê-la listada nesta página. Caso contrário, a página ficará vazia.
1. Clique em **[!DNL Add Account]**.
1. Selecione a plataforma de destino com a qual você deseja autenticar e clique em **[!DNL Confirm]** para ser redirecionado à página de autenticação da plataforma selecionada.

   ![plataformas integradas](assets/dbd-integrated-platforms.png)

1. Depois de autenticar em sua conta da plataforma de destino, você é redirecionado para o Audience Manager, onde deve ver suas contas de anunciante associadas. Selecione a conta de anunciante que deseja usar e clique em **[!DNL Confirm]**.

## Etapa 2: Criar um novo destino com base em dispositivo {#step2}

Após configurar a integração da plataforma de destino, é possível criar o novo destino. Veja como fazer isso:

>[!NOTE]
>
>Não é possível alterar o nome de um destino existente baseado em dispositivo. Forneça um nome que ajudará a identificar o destino corretamente.

1. Faça logon em sua conta Audience Manager, acesse **[!DNL Audience Data > Destinations]** e clique em **[!DNL Create Destination]**.
1. No **[!DNL Basic Information]** , insira um **[!DNL Name]** e **[!DNL Description]** para seu novo destino e use as configurações da lista abaixo:

   ![configuração](assets/dbd-new-basic.png)

   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**: selecione a plataforma de destino para a qual deseja enviar segmentos de público-alvo.
   * **[!DNL Account]**: selecione a conta de anunciante desejada associada à plataforma selecionada.
1. Clique em **[!DNL Next]**.
1. Escolha o [Rótulos de exportação de dados](/help/using/features/data-export-controls.md#controls-labels) que deseja definir para este destino.
1. Clique em **[!DNL Save]**.
1. No **[!DNL Segment Mappings]** selecione os segmentos de público-alvo que deseja enviar para esse destino.
1. Salve o destino.
