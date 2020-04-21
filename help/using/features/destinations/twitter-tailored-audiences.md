---
description: Este artigo explica como configurar Audiências personalizadas do Twitter para integrações novas e existentes.
seo-description: Este artigo explica como configurar Audiências personalizadas do Twitter para integrações novas e existentes.
seo-title: Configure Audiências personalizadas do Twitter como um destino autoatendido baseado em dispositivo
solution: Audience Manager
title: Configure Audiências personalizadas do Twitter como um destino autoatendido baseado em dispositivo
translation-type: tm+mt
source-git-commit: fb1bec17023b7b70c53659d68e2fbc431d9022fa

---


# Configurar [!DNL Twitter Tailored Audiences] como um Destino Baseado em Dispositivo Self-Service {#configure-twitter}

Este artigo explica como configurar uma integração com Audiências [personalizadas do](https://business.twitter.com/en/targeting/tailored-audiences.html)Twitter.

## Pré-requisitos {#prerequisites}

Antes de configurar seu [!DNL Twitter Tailored Audiences] destino, certifique-se de revisar os seguintes pré-requisitos do Twitter que você precisa atender.

1. Sua [!DNL Twitter Ads] conta deve estar qualificada para publicidade. As novas [!DNL Twitter Ads] contas não são qualificadas para publicidade nas primeiras 2 semanas após a sua criação.
2. Sua conta de [!DNL Twitter] usuário para a qual você autorizou o acesso no Gerenciador de Audiências deve ter a permissão de gerente [de audiência de](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) parceiro ativada.
3. Ao criar o primeiro [!DNL Twitter Tailored Audiences] destino na instância do Gerenciador de Audiências, entre em contato com a Adobe Consulting ou com o Atendimento ao cliente para ativar a sincronização da [!DNL Twitter] ID (ID da fonte de dados = 1123) para sua conta. Isso é necessário para a sincronização correta entre o Gerenciador de Audiências e [!DNL Twitter].

## Adicionar um novo [!DNL Twitter Tailored Audiences] destino {#add-new-twitter-destination}

Esta seção descreve as etapas que você precisa seguir ao configurar um novo destino baseado em dispositivo para [!DNL Twitter Tailored Audiences]. Esse cenário supõe que você não tenha nenhum [!DNL Twitter Tailored Audiences] destino configurado por meio do consultor da Adobe ou do Atendimento ao cliente.

### Etapa 1. Autentique com [!DNL Twitter Tailored Audiences]{#step1-authenticate-with-twitter}

Antes de adicionar o destino baseado em dispositivo, é necessário vincular o Gerenciador de Audiências e sua [!DNL Twitter Tailored Audiences] conta. Veja como fazer isso:

1. Faça logon em sua conta do Gerenciador de Audiências e vá para **[!DNL Administration > Integrated Accounts]**. Se você tiver uma integração previamente configurada com uma plataforma de destino, deverá vê-la listada nesta página. Caso contrário, a página estará vazia.
1. Clique em **[!DNL Add Account]**.
1. Selecione [!DNL Twitter Tailored Audiences] e clique em **[!DNL Confirm]** para ser redirecionado para a página de autenticação.                     ![plataformas integradas](assets/dbd-integrated-platforms.png)
1. Após a autenticação, você será redirecionado para o Gerenciador de Audiências, onde deverá ver suas contas de anunciante associadas. Selecione a conta do anunciante que deseja usar e clique em **[!DNL Confirm]**.

### Etapa 2: Criar um novo destino baseado em dispositivo {#step2-create-new-destination}

Depois de vincular o Gerenciador de Audiências e seu [!DNL Twitter Tailored Audiences], você pode criar o novo destino. Veja como fazer isso:

>[!NOTE]
>
>Não é possível alterar o nome de um destino baseado em dispositivo existente. Forneça um nome que o ajudará a identificar o destino corretamente.

1. Faça logon em sua conta do Audiência Manager, vá para **[!DNL Audience Data > Destinations]** e clique em **[!DNL Create Destination]**.
1. Na **[!DNL Basic Information]** seção, digite um **[!DNL Name]** e **[!DNL Description]** para seu novo destino e use as configurações abaixo: ![configuração](assets/dbd-new-basic.png)
1. Clique em **[!DNL Next]**.
1. Escolha os Rótulos [de Exportação de](/help/using/features/data-export-controls.md#controls-labels) Dados que deseja definir para este destino.
1. Clique em **[!DNL Save]**.
1. Na **[!DNL Segment Mappings]** seção, selecione os segmentos de audiência que deseja enviar para esse destino.
1. Salve o destino.

<!--
## Update Existing Twitter Integrations To Self-Service Administration {#update-existing-twitter-integrations}

To improve the user experience and streamline the configuration process, we are upgrading the [!DNL Twitter Tailored Audiences] integration to a self-service model, where you can perform the configuration yourself, from the Audience Manager UI. This section describes the steps you need to take to update your existing Twitter integration.

>[!IMPORTANT]
>
>The steps described below only apply if you have an existing integration with [!DNL Twitter Tailored Audiences], configured by an Audience Manager consultant or Customer Care.
> See item number 3 in [Prerequisites](#prerequisites) before migrating your [!DNL Twitter Tailored Audiences] to the self-service model.

Follow the steps below to migrate your existing [!DNL Twitter Tailored Audiences] destination to the self-service model.

1. Log in to your Audience Manager account and go to **[!DNL Administration > Integrated Accounts]**.
2. Click **[!DNL Add Account]**.
3. Select [!DNL Twitter Tailored Audiences] and click **[!DNL Confirm]** to be redirected to the authentication page. ![integrated-platforms](assets/dbd-integrated-platforms.png)
4. Once you've authenticated with your [!DNL Twitter] account, you are redirected to Audience Manager where you should see your associated advertiser accounts. Select the advertiser account that you want to use and click **[!DNL Confirm]**.
5. Go to **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** and click the Twitter destination that you need to configure.
6. Click **[!UICONTROL Edit]**. In the **[!UICONTROL Basic Information]** section, click the **[!UICONTROL Integrated Account]** drop-down menu and select the [!DNL Twitter] account that you have authenticated with at Step 4.
7. **[!UICONTROL Save]** the destination.

## Validating the Migration to Self-Service Administration {#migration-validation}

The complete migration of existing [!DNL Twitter] integrations to self-service administration can take up to 7 days. Once the migration is complete, Audience Manager shows you a notification in the UI.

You will also see a new set of audiences in your [!DNL Twitter] account, with their names prefixed by [[!DNL Adobe DMP Audience]]. Please allow up to 7 days for the audience population to be completely backfilled. Once the migration is complete, you should use these new audiences instead of the old ones. -->

## Considerações sobre o mapeamento de segmentos {#segment-mapping-considerations}

Ao mapear segmentos de audiência para [!UICONTROL Twitter], certifique-se de atender aos seguintes requisitos de nomeação de segmento:

* Forneça nomes de mapeamento de segmentos legíveis para humanos. Recomendamos usar o mesmo nome que você usou para os segmentos do Gerenciador de Audiências.
* Não use caracteres especiais (`,``%` `:``;` `@``/` `=` `?` `$`) nos nomes de mapeamento de segmentos e segmentos. Se o nome do segmento do Gerenciador de Audiências contiver esses caracteres, remova-os antes de mapear o segmento para um [!UICONTROL Twitter] destino.

### Exemplo

* Nome correto do segmento ou mapeamento: &quot;Compradores dos EUA e da Europa&quot;;
* Nome de segmento ou mapeamento incorreto: &quot;EUA, Europa 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>Não é possível alterar os nomes de segmentos já mapeados. O Gerenciador de Audiências usa os nomes dos segmentos para identificar corretamente os segmentos na integração.

## Considerações sobre Taxas de Correspondência {#match-rates-considerations}

* Ao usar [!UICONTROL Twitter Tailored Audiences], as [!UICONTROL Segment Addressable Audience] métricas e [!UICONTROL Segment Match Rate] da página de destino não exibirão valores. Esse é o comportamento normal, já que a correspondência de audiências com as taxas de correspondência para esse destino é manipulada e hospedada pela [!UICONTROL Twitter]Adobe, não pela Adobe.
* A integração entre o Gerenciador de Audiências e [!UICONTROL Twitter Tailored Audiences] suporta preenchimentos retroativos históricos de audiência. Todas as qualificações de segmento são enviadas para [!UICONTROL Twitter] quando você cria o destino.
