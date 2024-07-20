---
description: Este artigo explica como configurar Públicos-alvo personalizados do Twitter para integrações novas e existentes.
seo-description: This article explains how to configure Twitter Custom Audiences for both new and existing integrations.
seo-title: Configure Twitter Custom Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: Configure os Públicos-alvo personalizados do Twitter como um destino autoatendido com base em dispositivo
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: 72be9e032ec3c92cf09a5286baa872b884feaaa0
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 1%

---

# Configurar [!DNL Twitter Custom Audiences] como um Destino Baseado em Dispositivo de Autoatendimento {#configure-twitter}

Este artigo explica como configurar uma integração com o [Twitter Custom Audiences](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html).

## Pré-requisitos {#prerequisites}

Antes de configurar o destino do [!DNL Twitter Custom Audiences], verifique se você atende aos seguintes pré-requisitos.

* Sua conta [!DNL Twitter Ads] deve ser qualificada para publicidade. As novas contas do [!DNL Twitter Ads] não estão qualificadas para publicidade nas primeiras 2 semanas após a criação delas.
* A conta de usuário [!DNL Twitter] para a qual você autorizou o acesso no Audience Manager deve ter a permissão [Gerente de público-alvo do parceiro](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) habilitada.
* Ao criar o primeiro destino [!DNL Twitter Custom Audiences] na sua instância do Audience Manager, entre em contato com a Adobe Consulting ou com o Atendimento ao cliente para habilitar a sincronização de ID [!DNL Twitter] (Data Source ID = 1123) para sua conta. Isso é necessário para a sincronização correta entre Audience Manager e [!DNL Twitter].

## Adicionar um novo destino [!DNL Twitter Custom Audiences] {#add-new-twitter-destination}

Esta seção descreve as etapas que devem ser seguidas ao configurar um novo destino baseado em dispositivo para [!DNL Twitter Custom Audiences]. Este cenário pressupõe que você não tenha nenhum destino [!DNL Twitter Custom Audiences] existente configurado por meio de seu consultor de Adobe ou do Atendimento ao cliente.

### Etapa 1. Autenticar com [!DNL Twitter Custom Audiences] {#step1-authenticate-with-twitter}

Antes de adicionar o destino baseado em dispositivo, é necessário vincular o Audience Manager e sua conta do [!DNL Twitter Custom Audiences]. Veja como fazer isso:

1. Faça logon em sua conta Audience Manager e vá para **[!DNL Administration > Integrated Accounts]**. Se você tiver uma integração configurada anteriormente com uma plataforma de destino, deverá vê-la listada nesta página. Caso contrário, a página ficará vazia.
1. Clique em **[!DNL Add Account]**.
1. Selecione [!DNL Twitter Custom Audiences] e clique em **[!DNL Confirm]** para ser redirecionado à página de autenticação.

   ![plataformas integradas](assets/dbd-integrated-platforms.png)

1. Após a autenticação, você é redirecionado para o Audience Manager, onde deve ver suas contas de anunciante associadas. Selecione a conta de anunciante que deseja usar e clique em **[!DNL Confirm]**.

### Etapa 2: Criar um novo destino com base em dispositivo {#step2-create-new-destination}

Depois de vincular o Audience Manager e o seu [!DNL Twitter Custom Audiences], você poderá criar o novo destino. Veja como fazer isso:

>[!NOTE]
>
>Não é possível alterar o nome de um destino existente baseado em dispositivo. Forneça um nome que ajudará a identificar o destino corretamente.

1. Faça logon em sua conta Audience Manager, vá para **[!DNL Audience Data > Destinations]** e clique em **[!DNL Create Destination]**.
1. Na seção **[!DNL Basic Information]**, insira um **[!DNL Name]** e **[!DNL Description]** para o novo destino e use as configurações abaixo: ![instalação](assets/dbd-new-basic.png)
1. Clique em **[!DNL Next]**.
1. Escolha os [Rótulos de Exportação de Dados](/help/using/features/data-export-controls.md#controls-labels) que você deseja definir para este destino.
1. Clique em **[!DNL Save]**.
1. Na seção **[!DNL Segment Mappings]**, selecione os segmentos de público-alvo que você deseja enviar para esse destino.
1. Salve o destino.

## Considerações sobre o mapeamento de segmentos {#segment-mapping-considerations}

Ao mapear segmentos de público-alvo para [!UICONTROL Twitter], certifique-se de atender aos seguintes requisitos de nomenclatura de segmento:

* Forneça nomes de mapeamento de segmento legíveis por humanos. Recomendamos usar o mesmo nome usado para os segmentos Audience Manager.
* Não use caracteres especiais (`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`) em nomes de mapeamento de segmento e segmento. Se o nome do segmento Audience Manager contiver esses caracteres, remova-os antes de mapear o segmento para um destino [!UICONTROL Twitter].

### Exemplo

* Nome correto do segmento ou mapeamento: &quot;Compradores dos EUA e da Europa&quot;;
* Nome de segmento ou mapeamento incorreto: &quot;US, European 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>Não é possível alterar os nomes de segmentos já mapeados. O Audience Manager usa os nomes de segmento para identificar corretamente os segmentos na integração.

## Considerações sobre taxas de correspondência {#match-rates-considerations}

* A integração entre o Audience Manager e o [!UICONTROL Twitter Custom Audiences] dá suporte a preenchimentos retroativos de público-alvo histórico. Todas as qualificações de segmento são enviadas para [!UICONTROL Twitter] quando você cria o destino.

## Solução de problemas {#troubleshooting}

Ao configurar ou enviar dados para o destino Twitter Custom Audiences, você pode encontrar os erros descritos abaixo. Esta seção explica o que pode causar os erros e como corrigi-los.

| Mensagem de erro | Ocorrência / Motivo | Resolução |
|---|---|---|
| `Internal server error` | Esta mensagem de erro é exibida na interface do usuário do Audience Manager ao tentar adicionar uma nova conta do [!DNL Twitter] usando uma versão desatualizada da API do Twitter. | Entre em contato com o Atendimento ao cliente da Adobe. |
| `Twitter Error: This request is not properly authenticated` | Esta mensagem de erro é exibida na interface do usuário do Audience Manager ao tentar mapear segmentos com nomes de segmentos não compatíveis para o destino. | Revise os nomes de segmento mapeados e verifique se eles não contêm caracteres não suportados. Consulte [considerações de mapeamento de segmento](#segment-mapping-considerations) para obter a lista de caracteres não suportados. |
| `Twitter Error: Account XXXXXXXXX was not found` | Esta mensagem de erro é exibida na interface do usuário do Audience Manager quando as credenciais configuradas para o destino não estão autorizadas a acessar a conta de anúncios do Twitter correspondente. | <ul><li>Verifique se as credenciais de conta que você está usando atendem aos [pré-requisitos](#prerequisites).</li><li>Navegue até a interface do usuário do Twitter Ads usando as mesmas credenciais e verifique se os públicos-alvo corretos são exibidos na conta `XXXXXXXXX` correspondente. </li></ul> |