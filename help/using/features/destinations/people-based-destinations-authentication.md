---
description: 'Esta página contém orientações sobre como configurar e gerenciar a integração entre plataformas baseadas em Audience Manager e em pessoas. '
seo-description: 'Esta página contém orientações sobre como configurar e gerenciar a integração entre plataformas baseadas em Audience Manager e em pessoas. '
seo-title: Autenticação com plataformas com base em pessoas
solution: Audience Manager
title: Autenticação com plataformas com base em pessoas
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 2%

---


# Autenticação com plataformas com base em pessoas {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo durante a configuração e o uso deste recurso. Nada aqui contido é aconselhamento jurídico. Consulte o seu próprio advogado para obter orientação jurídica.

Esta página contém orientações sobre como configurar e gerenciar sua integração entre plataformas baseadas em Audience Manager e em pessoas.

>[!NOTE]
>Esta é uma etapa obrigatória para Destinos baseados em pessoas, independentemente do seu cenário de implementação.

## Configurar a autenticação do Platform baseada em pessoas {#configure-authentication}

1. Faça logon em sua conta do Audience Manager e vá para **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Se você tiver uma integração previamente configurada com uma plataforma social, deverá vê-la listada nesta página. Caso contrário, a página estará vazia.
   ![integração baseada em pessoas](assets/pbd-config.png)
2. Clique em **[!UICONTROL Add Account]**.
3. Use o menu **[!UICONTROL People-Based Platform]** suspenso para selecionar a plataforma com a qual você deseja configurar a integração.
   ![plataforma baseada em pessoas](assets/pbd-add.png)
4. Clique em **[!UICONTROL Confirm]** para ser redirecionado para a página de autenticação da plataforma selecionada.
5. Depois de autenticado em sua conta da plataforma social, você é redirecionado para o Audience Manager onde deve ver suas contas de anunciante associadas. Selecione a conta do anunciante que deseja usar e clique em **[!UICONTROL Confirm]**.
6. O Audience Manager exibe uma notificação na parte superior da página para informar se a conta foi adicionada com êxito. A notificação também permite que você adicione um endereço de email de contato para receber notificações da Adobe quando a autenticação da plataforma social estiver prestes a expirar.

## Expiração do token de autenticação e Gerenciamento de notificações {#token-expiration-notification}

O Audience Manager lida com sua integração com plataformas sociais por meio de tokens de autenticação que expiram após um determinado período de tempo. A duração da validade do token está sujeita às regras de integração de cada plataforma social. Quando o token de autenticação expirar, o Audience Manager não poderá enviar seus segmentos de audiência para o destino. Para evitar esse cenário, recomendamos adicionar pelo menos um endereço de email de contato à sua integração, para que você seja notificado assim que o token de autenticação estiver prestes a expirar. Quando isso acontecer, você poderá autenticar novamente para garantir que o destino continue recebendo seus segmentos de audiência.

Veja como adicionar endereços de email às integrações existentes:

1. Faça logon em sua conta do Audience Manager e vá para **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identifique a integração para a qual você deseja receber notificações de expiração de token e clique no **[!UICONTROL Edit]** ícone.
1. Insira os endereços de email para os quais você deseja receber notificações de expiração de token, separados por vírgulas.
1. Clique em **[!UICONTROL Save]**.

## Renovação do token de autenticação {#token-renewal}

Quando um token de autenticação expira, a integração entre o Audience Manager e a plataforma social correspondente é interrompida, de modo que o Audience Manager não pode mais enviar segmentos de audiência para o destino. A [!UICONTROL Integrated Accounts] página mostra o status de expiração de cada integração na [!UICONTROL Expiration] coluna e permite renovar a autenticação a qualquer momento.

Veja como renovar uma autenticação expirada ou prestes a expirar:
1. Faça logon em sua conta do Audience Manager e vá para **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identifique a integração para a qual você precisa renovar a autenticação. As autenticações expiradas são marcadas como [!UICONTROL Expired], enquanto as autenticações que estão prestes a expirar em breve mostram o número restante de dias autenticados.
1. Clique no **[!UICONTROL Renew]** ícone correspondente na [!UICONTROL Expiration] coluna. Isso aciona o **[!UICONTROL Renew Account]** fluxo de trabalho, que o leva de volta pela página de autenticação da plataforma social. Após a autenticação, o token será renovado com a nova data de expiração.
   ![pbd-renew](assets/pbd-renew.png)
