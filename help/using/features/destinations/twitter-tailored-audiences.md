---
description: Este artigo explica como configurar Públicos personalizados do Twitter para integrações novas e existentes.
seo-description: This article explains how to configure Twitter Custom Audiences for both new and existing integrations.
seo-title: Configure Twitter Custom Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: Configurar públicos-alvo personalizados do Twitter como um destino baseado em dispositivo de autoatendimento
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: 72be9e032ec3c92cf09a5286baa872b884feaaa0
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 1%

---

# Configurar [!DNL Twitter Custom Audiences] como um destino baseado em dispositivo de autoatendimento {#configure-twitter}

Este artigo explica como configurar uma integração com o [Públicos-alvo personalizados do twitter](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html).

## Pré-requisitos {#prerequisites}

Antes de configurar o [!DNL Twitter Custom Audiences] de destino, certifique-se de atender aos seguintes pré-requisitos.

* Seu [!DNL Twitter Ads] deve ser elegível para publicidade. Novo [!DNL Twitter Ads] as contas não são elegíveis para publicidade nas primeiras 2 semanas após a criação.
* Seu [!DNL Twitter] a conta de usuário para a qual você autorizou o acesso no Audience Manager deve ter a variável [Gerente de público-alvo do parceiro](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) permissão ativada.
* Ao criar o primeiro [!DNL Twitter Custom Audiences] na sua instância do Audience Manager, entre em contato com a Adobe Consulting ou com o Atendimento ao cliente para ativar o [!DNL Twitter] Sincronização de ID (ID da fonte de dados = 1123) para sua conta. Isso é necessário para a sincronização correta entre o Audience Manager e o [!DNL Twitter].

## Adicionar um novo [!DNL Twitter Custom Audiences] Destino {#add-new-twitter-destination}

Esta seção descreve as etapas que você precisa seguir ao configurar um novo destino com base em dispositivo para o [!DNL Twitter Custom Audiences]. Esse cenário pressupõe que você não tenha [!DNL Twitter Custom Audiences] destino configurado por meio do consultor do Adobe ou pelo Atendimento ao cliente.

### Etapa 1. Autentique com [!DNL Twitter Custom Audiences] {#step1-authenticate-with-twitter}

Antes de adicionar o destino baseado em dispositivo, é necessário vincular o Audience Manager e o [!DNL Twitter Custom Audiences] conta. Veja como fazer isso:

1. Faça logon na sua conta do Audience Manager e acesse **[!DNL Administration > Integrated Accounts]**. Se você tiver uma integração configurada anteriormente com uma plataforma de destino, ela deverá ser exibida nesta página. Caso contrário, a página ficará vazia.
1. Clique em **[!DNL Add Account]**.
1. Selecionar [!DNL Twitter Custom Audiences] e clique em **[!DNL Confirm]** para ser redirecionado para a página de autenticação.

   ![plataformas integradas](assets/dbd-integrated-platforms.png)

1. Depois de autenticar, você será redirecionado para o Audience Manager, onde deverá ver suas contas de anunciante associadas. Selecione a conta do anunciante que deseja usar e clique em **[!DNL Confirm]**.

### Etapa 2: Criar um novo destino com base em dispositivo {#step2-create-new-destination}

Depois de vincular o Audience Manager e o [!DNL Twitter Custom Audiences], é possível criar o novo destino. Veja como fazer isso:

>[!NOTE]
>
>Não é possível alterar o nome de um destino baseado em dispositivo existente. Certifique-se de fornecer um nome que ajudará a identificar o destino corretamente.

1. Faça logon na sua conta do Audience Manager, acesse **[!DNL Audience Data > Destinations]** e clique em **[!DNL Create Destination]**.
1. No **[!DNL Basic Information]** digite uma **[!DNL Name]** e **[!DNL Description]** para seu novo destino e use as configurações abaixo: ![configuração](assets/dbd-new-basic.png)
1. Clique em **[!DNL Next]**.
1. Escolha a [Rótulos de exportação de dados](/help/using/features/data-export-controls.md#controls-labels) que você deseja definir para esse destino.
1. Clique em **[!DNL Save]**.
1. No **[!DNL Segment Mappings]** selecione os segmentos de público-alvo que deseja enviar para esse destino.
1. Salve o destino.

## Considerações sobre o mapeamento de segmentos {#segment-mapping-considerations}

Ao mapear segmentos de público-alvo para [!UICONTROL Twitter], certifique-se de atender aos seguintes requisitos de nomenclatura de segmento:

* Forneça nomes de mapeamento de segmentos legíveis ao ser humano. Recomendamos o uso do mesmo nome usado para os segmentos do Audience Manager.
* Não use caracteres especiais (`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`) nos nomes de mapeamento de segmento e segmento. Se o nome do segmento de Audience Manager contém esses caracteres, remova-os antes de mapear o segmento para um [!UICONTROL Twitter] destino.

### Exemplo

* Nome correto de segmento ou mapeamento: &quot;Compradores dos EUA e da Europa&quot;;
* Nome de segmento ou mapeamento incorreto: &quot;US, European 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>Não é possível alterar os nomes dos segmentos já mapeados. O Audience Manager usa os nomes de segmento para identificar corretamente os segmentos na integração.

## Considerações sobre taxas de correspondência {#match-rates-considerations}

* A integração entre o Audience Manager e o [!UICONTROL Twitter Custom Audiences] O suporta preenchimentos retroativos de público-alvo históricos. Todas as qualificações de segmento são enviadas para [!UICONTROL Twitter] ao criar o destino.

## Solução de problemas {#troubleshooting}

Ao configurar ou enviar dados para o destino de Públicos personalizados da Twitter, você pode encontrar os erros descritos abaixo. Esta seção explica o que pode causar os erros e como corrigi-los.

| Mensagem de erro | Ocorrência / Motivo | Resolução |
|---|---|---|
| `Internal server error` | Esta mensagem de erro é exibida na interface do usuário do Audience Manager ao tentar adicionar um novo [!DNL Twitter] conta usando uma versão desatualizada da API do Twitter. | Entre em contato com o Atendimento ao cliente da Adobe. |
| `Twitter Error: This request is not properly authenticated` | Essa mensagem de erro é exibida na interface do usuário do Audience Manager ao tentar mapear segmentos com nomes de segmentos não suportados para o destino. | Revise os nomes de segmentos mapeados e verifique se eles não contêm caracteres não suportados. Consulte [considerações sobre o mapeamento de segmento](#segment-mapping-considerations) para a lista de caracteres não suportados. |
| `Twitter Error: Account XXXXXXXXX was not found` | Essa mensagem de erro é exibida na interface do usuário do Audience Manager quando as credenciais configuradas para o destino não estão autorizadas a acessar a conta do Twitter Ads correspondente. | <ul><li>Verifique se as credenciais da conta que você está usando atendem ao [pré-requisitos](#prerequisites).</li><li>Navegue até a interface do usuário do Twitter Ads usando as mesmas credenciais e verifique se os públicos-alvo corretos são exibidos no cabeçalho correspondente `XXXXXXXXX` conta. </li></ul> |