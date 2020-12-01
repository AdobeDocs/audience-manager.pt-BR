---
description: Este artigo explica como configurar Audiências personalizadas do Twitter para integrações novas e existentes.
seo-description: Este artigo explica como configurar Audiências personalizadas do Twitter para integrações novas e existentes.
seo-title: Configure públicos personalizados do Twitter como um destino autoatendido com base em dispositivo
solution: Audience Manager
title: Configure públicos personalizados do Twitter como um destino autoatendido com base em dispositivo
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: 8ff76decc1cbd7f7babd619dd1ce9fe047541337
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 4%

---


# Configure [!DNL Twitter Tailored Audiences] como um Destino Baseado em Dispositivo Self-Service {#configure-twitter}

Este artigo explica como configurar uma integração com [Audiências personalizadas do Twitter](https://business.twitter.com/en/targeting/tailored-audiences.html).

## Pré-requisitos {#prerequisites}

Antes de configurar seu destino [!DNL Twitter Tailored Audiences], certifique-se de revisar os seguintes pré-requisitos do Twitter que você precisa atender.

1. Sua conta [!DNL Twitter Ads] deve estar qualificada para publicidade. As novas contas [!DNL Twitter Ads] não são elegíveis para publicidade nas primeiras 2 semanas após a sua criação.
2. Sua conta de usuário [!DNL Twitter] para a qual você autorizou acesso no Audience Manager deve ter a permissão [Gerente de audiência do parceiro](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) ativada.
3. Ao criar o primeiro destino [!DNL Twitter Tailored Audiences] em sua instância do Audience Manager, entre em contato com a Adobe Consultoria ou com o Atendimento ao cliente para ativar a sincronização de [!DNL Twitter] ID (ID da fonte de dados = 1123) para sua conta. Isso é necessário para a sincronização correta entre Audience Manager e [!DNL Twitter].

## Adicionar um novo destino [!DNL Twitter Tailored Audiences] {#add-new-twitter-destination}

Esta seção descreve as etapas que você precisa seguir ao configurar um novo destino baseado em dispositivo para [!DNL Twitter Tailored Audiences]. Esse cenário supõe que você não tenha nenhum destino [!DNL Twitter Tailored Audiences] existente configurado por meio do seu consultor de Adobe ou do Atendimento ao cliente.

### Etapa 1. Autentique com [!DNL Twitter Tailored Audiences] {#step1-authenticate-with-twitter}

Antes de adicionar o destino baseado em dispositivo, é necessário vincular o Audience Manager e a conta [!DNL Twitter Tailored Audiences]. Veja como fazer isso:

1. Faça logon na sua conta do Audience Manager e vá para **[!DNL Administration > Integrated Accounts]**. Se você tiver uma integração previamente configurada com uma plataforma de destino, deverá vê-la listada nesta página. Caso contrário, a página estará vazia.
1. Clique em **[!DNL Add Account]**.
1. Selecione [!DNL Twitter Tailored Audiences] e clique em **[!DNL Confirm]** para ser redirecionado para a página de autenticação.                     ![plataformas integradas](assets/dbd-integrated-platforms.png)
1. Depois de autenticado, você é redirecionado para o Audience Manager onde deve ver suas contas de anunciante associadas. Selecione a conta do anunciante que deseja usar e clique em **[!DNL Confirm]**.

### Etapa 2: Criar um novo destino baseado em dispositivo {#step2-create-new-destination}

Depois de vincular o Audience Manager e seu [!DNL Twitter Tailored Audiences], você pode criar o novo destino. Veja como fazer isso:

>[!NOTE]
>
>Não é possível alterar o nome de um destino baseado em dispositivo existente. Forneça um nome que o ajudará a identificar o destino corretamente.

1. Faça logon em sua conta do Audience Manager, vá para **[!DNL Audience Data > Destinations]** e clique em **[!DNL Create Destination]**.
1. Na seção **[!DNL Basic Information]**, insira **[!DNL Name]** e **[!DNL Description]** para seu novo destino e use as configurações abaixo: ![configuração](assets/dbd-new-basic.png)
1. Clique em **[!DNL Next]**.
1. Escolha as [Etiquetas de Exportação de Dados](/help/using/features/data-export-controls.md#controls-labels) que deseja definir para este destino.
1. Clique em **[!DNL Save]**.
1. Na seção **[!DNL Segment Mappings]**, selecione os segmentos de audiência que deseja enviar para esse destino.
1. Salve o destino.

## Considerações sobre o mapeamento de segmentos {#segment-mapping-considerations}

Ao mapear segmentos de audiência para [!UICONTROL Twitter], certifique-se de atender aos seguintes requisitos de nomeação de segmento:

* Forneça nomes de mapeamento de segmentos legíveis para humanos. Recomendamos usar o mesmo nome que você usou para os segmentos de Audience Manager.
* Não use caracteres especiais (`,` `%` `:` `;` `@` `/` `=` `?` `$`) nos nomes de mapeamento de segmentos e segmentos. Se o nome do segmento Audience Manager contiver esses caracteres, remova-os antes de mapear o segmento para um destino [!UICONTROL Twitter].

### Exemplo

* Nome correto do segmento ou mapeamento: &quot;Compradores dos EUA e da Europa&quot;;
* Nome de segmento ou mapeamento incorreto: &quot;EUA, Europa 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>Não é possível alterar os nomes de segmentos já mapeados. O Audience Manager usa os nomes dos segmentos para identificar corretamente os segmentos na integração.

## Considerações sobre Taxas de Correspondência {#match-rates-considerations}

* A integração entre Audience Manager e [!UICONTROL Twitter Tailored Audiences] oferece suporte a preenchimentos retroativos históricos de audiência. Todas as qualificações de segmento são enviadas para [!UICONTROL Twitter] quando você cria o destino.
