---
description: 'Esta página contém orientações sobre como configurar e gerenciar a integração entre o Audience Manager e as plataformas baseadas em pessoas. '
seo-description: 'Esta página contém orientações sobre como configurar e gerenciar a integração entre o Audience Manager e as plataformas baseadas em pessoas. '
seo-title: Autenticação com plataformas baseadas em pessoas
solution: Audience Manager
title: Autenticação com plataformas baseadas em pessoas
translation-type: tm+mt
source-git-commit: 6093def9c5853572c064a4e398d5e328bcb9d181

---


# Autenticação com plataformas baseadas em pessoas {#authentication-with-people-based-platforms}

Esta página contém orientações sobre como configurar e gerenciar sua integração entre o Audience Manager e as plataformas baseadas em pessoas.

>[!NOTE]
>Esta é uma etapa obrigatória para Destinos baseados em pessoas, independentemente do seu cenário de implementação.

## Configurar a autenticação de plataforma baseada em pessoas {#configure-authentication}

1. Faça logon em sua conta do Audience Manager e vá para **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Se você tiver uma integração previamente configurada com uma plataforma social, deverá vê-la listada nesta página. Caso contrário, a página estará vazia.
   ![integração baseada em pessoas](assets/pbd-config.png)
1. Clique em **[!UICONTROL Add Account]**.
1. Use o menu **[!UICONTROL People-Based Platform]** suspenso para selecionar a plataforma com a qual deseja configurar a integração.
   ![plataforma baseada em pessoas](assets/pbd-add.png)
1. Clique em **[!UICONTROL Confirm]** para ser redirecionado para a página de autenticação da plataforma selecionada.
1. Depois de autenticar em sua conta da plataforma social, você será redirecionado para o Audience Manager, onde deverá ver suas contas de anunciante associadas. Selecione a conta do anunciante que deseja usar e clique em **[!UICONTROL Confirm]**.
1. O Audience Manager exibe uma notificação na parte superior da página para informá-lo se a conta foi adicionada com êxito. A notificação também permite que você adicione um endereço de email de contato para receber notificações da Adobe quando a autenticação da plataforma social estiver prestes a expirar.

## Expiração do token de autenticação e Gerenciamento de notificações {#token-expiration-notification}

O Audience Manager lida com sua integração com plataformas sociais por meio de tokens de autenticação que expiram após um determinado período de tempo. A duração da validade do token está sujeita às regras de integração de cada plataforma social. Quando o token de autenticação expirar, o Audience Manager não poderá enviar seus segmentos de público-alvo para seu destino. Para evitar esse cenário, recomendamos adicionar pelo menos um endereço de email de contato à sua integração, para que você seja notificado assim que o token de autenticação estiver prestes a expirar. Quando isso acontece, você pode autenticar novamente para garantir que o destino continue recebendo seus segmentos de público-alvo.

Veja como adicionar endereços de email às integrações existentes:

1. Faça logon em sua conta do Audience Manager e vá para **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**.
1. Identifique a integração para a qual você deseja receber notificações de expiração de token e clique no **[!UICONTROL Edit]** ícone.
1. Insira os endereços de email para os quais você deseja receber notificações de expiração de token, separados por vírgulas.
1. Clique em **[!UICONTROL Save]**.

## Renovação do token de autenticação {#token-renewal}

When an authentication token expires, the integration between Audience Manager and the corresponding social platform is interrupted, so Audience Manager cannot send audience segments to the destination anymore. The  page shows you the expiration status of each integration in the  column, and allows you to renew the authentication at any time.[!UICONTROL Integrated Accounts][!UICONTROL Expiration]

Here's how to renew an expired or about-to-expire authentication:
1. Log in to your Audience Manager account and go to  &gt; .**[!UICONTROL Administration]****[!UICONTROL Integrated Accounts]**
1. Identify the integration that you need to renew authentication for. Expired authentications are marked as [!UICONTROL Expired], while authentications that are about to expire soon show the remaining number of authenticated days.
1. Click the corresponding  icon in the  column. **[!UICONTROL Renew]**[!UICONTROL Expiration] This triggers the  workflow, which takes you back through the social platform's authentication page. **[!UICONTROL Renew Account]** Once you authenticate, the token is renewed with the new expiration date.
   ![pbd-renew](assets/pbd-renew.png)
