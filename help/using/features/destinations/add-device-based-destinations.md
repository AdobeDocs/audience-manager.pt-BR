---
description: Este artigo explica como configurar novos destinos baseados em dispositivos da interface do usuário do Audience Manager.
seo-description: Este artigo explica como configurar novos destinos baseados em dispositivos da interface do usuário do Audience Manager.
seo-title: Adicionar novos destinos baseados em dispositivo
solution: Audience Manager
title: Adicionar novos destinos baseados em dispositivo
translation-type: tm+mt
source-git-commit: b492065756d45ee6dfb185cc387409dea72a9923

---


# Adicionar novos destinos baseados em dispositivo {#add-new-device-based-destinations}

Este artigo explica como configurar novos destinos baseados em dispositivos da interface do usuário do Audience Manager.

## Visão geral {#overview}

O processo de adição de um novo destino baseado em dispositivo consiste em duas etapas principais. Primeiro, você precisa configurar a integração entre o Audience Manager e o parceiro de destino. Depois de fazer isso, você pode criar um novo destino baseado em dispositivo.

>[!IMPORTANT]
>
>Nem todos os destinos baseados em dispositivo são elegíveis para o fluxo de trabalho de configuração de autoatendimento. Se o destino do dispositivo que você precisa adicionar não for exibido na lista de destinos, entre em contato com seu consultor da Adobe ou com o Suporte ao cliente para obter assistência.

## Etapa 1. Autenticar com uma plataforma de destino {#step1}

Antes de criar um novo destino baseado em dispositivo, é necessário configurar a integração entre o Audience Manager e a plataforma de destino. Veja como fazer isso:

1. Faça logon em sua conta do Audience Manager e vá **[!DNL Administration > Integrated Accounts]** para. Se você tiver uma integração configurada anteriormente com uma plataforma de destino, deverá vê-la listada nesta página. Caso contrário, a página ficará vazia.
2. Clique em **[!DNL Add Account]**.
3. Selecione a plataforma de destino com a qual deseja autenticar e clique **[!DNL Confirm]** para ser redirecionado para a página de autenticação da plataforma selecionada. ![plataformas integradas](assets/dbd-integrated-platforms.png)
4. Depois que você tiver se autenticado na conta da plataforma de destino, será redirecionado ao Audience Manager onde você deverá visualizar suas contas de anunciante associadas. Selecione a conta do anunciante que deseja usar e clique **[!DNL Confirm]** em.

## Etapa 2: Criar um novo destino baseado em dispositivo {#step2}

Depois de configurar a integração da plataforma de destino, você pode criar o novo destino. Veja como fazer isso:

>[!NOTE]
>
>Não é possível alterar o nome de um destino existente baseado em dispositivo. Certifique-se de fornecer um nome que ajudará a identificar o destino corretamente.

1. Faça logon na conta do Audience Manager, vá para **[!DNL Audience Data > Destinations]** e clique **[!DNL Create Destination]** em.
2. Na **[!DNL Basic Information]** seção, digite a **[!DNL Name]** e **[!DNL Description]** para o novo destino e use as configurações na lista abaixo: ![configuração](assets/dbd-new-basic.png)
3. Clique em **[!DNL Next]**.
4. Escolha [os Rótulos](/help/using/features/data-export-controls.md#controls-labels) de exportação de dados que você deseja definir para esse destino.
5. Clique em **[!DNL Save]**.
6. Na **[!DNL Segment Mappings]** seção, selecione os segmentos do público-alvo que você deseja enviar para este destino.
7. Salve o destino.

* **[!DNL Category]**: [!DNL Integrated Platforms];
* **[!DNL Type]**: [!DNL Device-Based];
* **[!DNL Platform]**: selecione a plataforma de destino para a qual deseja enviar os segmentos do público-alvo.
* **[!DNL Account]**: selecione a conta de anunciante desejada associada à plataforma selecionada.