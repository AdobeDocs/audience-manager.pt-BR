---
description: Este artigo explica como configurar Públicos personalizados do Twitter para integrações novas e existentes.
seo-description: Este artigo explica como configurar Públicos personalizados do Twitter para integrações novas e existentes.
seo-title: Configurar públicos-alvo personalizados do Twitter como um destino baseado em dispositivo de autoatendimento
solution: Audience Manager
title: Configurar públicos-alvo personalizados do Twitter como um destino baseado em dispositivo de autoatendimento
translation-type: tm+mt
source-git-commit: c6318921b49603015b4670a361ec85ffa29abb30

---


# Configurar [!DNL Twitter Tailored Audiences] como um Destino Baseado em Dispositivo Self-Service {#configure-twitter}

Este artigo explica como configurar Públicos-alvo [personalizados do](https://business.twitter.com/en/targeting/tailored-audiences.html) Twitter para integrações novas e existentes.

## Pré-requisitos {#prerequisites}

Antes de configurar seu [!DNL Twitter Tailored Audiences] destino, certifique-se de revisar os seguintes pré-requisitos do Twitter que você precisa atender.

1. Sua [!DNL Twitter Ads] conta deve estar qualificada para publicidade. As novas [!DNL Twitter Ads] contas não são qualificadas para publicidade nas primeiras 2 semanas após a sua criação.
1. Sua conta de usuário do Twitter para a qual você autorizou acesso no Audience Manager deve ter a permissão de gerente [de público-alvo do](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) Parceiro ativada.
1. Se você estiver [atualizando sua integração existente do Twitter para a administração](#update-existing-twitter-integrations)de autoatendimento, sua conta de usuário do Twitter deverá ter a permissão [Ad manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) ativada.
1. Ao criar o primeiro [!DNL Twitter Tailored Audiences] destino na sua instância do Audience Manager, entre em contato com a Adobe Consulting ou com o Atendimento ao cliente para ativar a sincronização da [!DNL Twitter] ID (ID da fonte de dados = 1123) para sua conta. Isso é necessário para a sincronização correta entre o Audience Manager e [!DNL Twitter].

## Adicionar um novo [!DNL Twitter Tailored Audiences] destino {#add-new-twitter-destination}

Esta seção descreve as etapas que você precisa seguir ao configurar um novo destino baseado em dispositivo para [!DNL Twitter Tailored Audiences]. Esse cenário supõe que você não tenha nenhum [!DNL Twitter Tailored Audiences] destino configurado por meio do consultor da Adobe ou do Atendimento ao cliente.

### Etapa 1. Autentique com [!DNL Twitter Tailored Audiences]{#step1-authenticate-with-twitter}

Antes de adicionar o destino baseado em dispositivo, é necessário vincular o Audience Manager e sua [!DNL Twitter Tailored Audiences] conta. Veja como fazer isso:

1. Faça logon em sua conta do Audience Manager e vá para **[!DNL Administration > Integrated Accounts]**. Se você tiver uma integração previamente configurada com uma plataforma de destino, deverá vê-la listada nesta página. Caso contrário, a página estará vazia.
2. Clique em **[!DNL Add Account]**.
3. Selecione [!DNL Twitter Tailored Audiences] e clique em **[!DNL Confirm]** para ser redirecionado para a página de autenticação.                     ![plataformas integradas](assets/dbd-integrated-platforms.png)
4. Após a autenticação, você será redirecionado para o Audience Manager, onde deverá ver suas contas de anunciante associadas. Selecione a conta do anunciante que deseja usar e clique em **[!DNL Confirm]**.

### Etapa 2: Criar um novo destino baseado em dispositivo {#step2-create-new-destination}

Depois de vincular o Audience Manager e seu [!DNL Twitter Tailored Audiences], você pode criar o novo destino. Veja como fazer isso:

>[!NOTE]
>
>Não é possível alterar o nome de um destino baseado em dispositivo existente. Make sure to provide a name that will help you identify the destination correctly.

1. Log in to your Audience Manager account, go to , and click .**[!DNL Audience Data > Destinations]****[!DNL Create Destination]**
2. In the **[!DNL Basic Information]** section, enter a **[!DNL Name]** and **[!DNL Description]** for your new destination, and use the settings below: ![setup](assets/dbd-new-basic.png)
3. Clique em **[!DNL Next]**.
4. Choose the [Data Export Labels](/help/using/features/data-export-controls.md#controls-labels) that you want to set for this destination.
5. Clique em **[!DNL Save]**.
6. In the  section, select the audience segments that you want to send to this destination.**[!DNL Segment Mappings]**
7. Save the destination.

## Update Existing Twitter Integrations To Self-Service Administration {#update-existing-twitter-integrations}

To improve the user experience and streamline the configuration process, we are upgrading the  integration to a self-service model, where you can perform the configuration yourself, from the Audience Manager UI. [!DNL Twitter Tailored Audiences] This section describes the steps you need to take to update your existing Twitter integration.

>[!IMPORTANT]
>
>The steps described below only apply if you have an existing integration with , configured by an Audience Manager consultant or Customer Care. [!DNL Twitter Tailored Audiences] The full upgrade process of your destination to the self-service model may take up to 5 business days. In the meantime, your destination is still active and Audience Manager continues to send audiences to it.
> See item number 3 in Prerequisites before migrating your  to the self-service model.[](#prerequisites)[!DNL Twitter Tailored Audiences]

Follow the steps below to migrate your existing  destination to the self-service model.[!DNL Twitter Tailored Audiences]

1. Faça logon em sua conta do Audience Manager e vá para **[!DNL Administration > Integrated Accounts]**.
1. Clique em **[!DNL Add Account]**.
1. Select  and click  to be redirected to the authentication page. [!DNL Twitter Tailored Audiences]**[!DNL Confirm]** ![plataformas integradas](assets/dbd-integrated-platforms.png)
1. Depois de autenticar com sua [!DNL Twitter] conta, você será redirecionado para o Audience Manager, onde deverá ver suas contas de anunciante associadas. Selecione a conta do anunciante que deseja usar e clique em **[!DNL Confirm]**.
1. Vá até **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Destinations]** e clique no destino do Twitter que você precisa configurar.
1. Clique em **[!UICONTROL Edit]**. Na **[!UICONTROL Basic Information]** seção, clique no menu **[!UICONTROL Integrated Account]** suspenso e selecione a [!DNL Twitter] conta na qual você se autenticou na Etapa 4.
1. **[!UICONTROL Save]** o destino.

## Validando a migração para a administração de autoatendimento {#migration-validation}

A migração completa das integrações existentes [!DNL Twitter] para a administração de autoatendimento pode levar até 7 dias. Quando a migração estiver concluída, o Audience Manager mostrará uma notificação na interface do usuário.

Você também verá um novo conjunto de públicos-alvo em sua [!DNL Twitter] conta, com seus nomes prefixados por [[!DNL Adobe DMP Audience]]. Aguarde até 7 dias para que a população de público-alvo seja completamente preenchida. Quando a migração estiver concluída, você deverá usar esses novos públicos em vez dos antigos.

## Considerações sobre o mapeamento de segmentos {#segment-mapping-considerations}

Ao mapear segmentos de público-alvo para o Twitter, certifique-se de atender aos seguintes requisitos de nomeação de segmento:

* Forneça nomes de mapeamento de segmentos legíveis para humanos. Recomendamos usar o mesmo nome que você usou para os segmentos do Audience Manager.
* Não use vírgulas nos nomes de mapeamento de segmentos e segmentos.

### Exemplo

* Nome correto do segmento ou mapeamento: "Compradores dos EUA e da Europa";
* Nome de segmento ou mapeamento incorreto: "EUA, Europa 5h0pP3rs".

>[!IMPORTANT]
>
>Não é possível alterar os nomes de segmentos já mapeados. O Audience Manager usa os nomes dos segmentos para identificar corretamente os segmentos na integração.

## Considerações sobre Taxas de Correspondência {#match-rates-considerations}

Ao usar [!UICONTROL Twitter Tailored Audiences], as [!UICONTROL Segment Addressable Audience] métricas e [!UICONTROL Segment Match Rate] da página de destino não exibirão valores. Esse é o comportamento normal, já que a correspondência do público-alvo com as taxas de correspondência para esse destino é feita e hospedada pela [!UICONTROL Twitter]Adobe, não pela Adobe.
