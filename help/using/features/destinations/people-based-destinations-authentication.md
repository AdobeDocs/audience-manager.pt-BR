---
description: 'Esta página contém orientação sobre como configurar e gerenciar a integração entre o Audience Manager e plataformas baseadas em pessoas. '
seo-description: 'Esta página contém orientação sobre como configurar e gerenciar a integração entre o Audience Manager e plataformas baseadas em pessoas. '
seo-title: Autenticação com plataformas baseadas em pessoas
solution: Audience Manager
title: Autenticação com plataformas baseadas em pessoas
translation-type: tm+mt
source-git-commit: 05f334dc3d975a0fe18b93c844889e3edb2dfafa

---


# Autenticação com plataformas baseadas em pessoas {#authentication-with-people-based-platforms}

Esta página contém orientação sobre como configurar e gerenciar a integração entre o Audience Manager e plataformas baseadas em pessoas.

>[!NOTE]
>Esta é uma etapa obrigatória para Destinos baseados em pessoas, independentemente do cenário de implementação.

## Configurar autenticação de plataforma baseada em pessoas {#configure-authentication}

1. Faça logon em sua conta do Audience Manager e vá **[!UICONTROL Administration]** para &gt; **[!UICONTROL Integrated Accounts]**. Se você tiver uma integração configurada anteriormente com uma plataforma social, deverá vê-la listada nesta página. Caso contrário, a página ficará vazia.
   ![integração baseada em pessoas](assets/pbd-config.png)
1. Clique em **[!UICONTROL Add Account]**.
1. Use o **[!UICONTROL People-Based Platform]** menu suspenso para selecionar a plataforma com a qual você deseja configurar a integração.
   ![plataforma baseada em pessoas](assets/pbd-add.png)
1. Clique **[!UICONTROL Confirm]** para ser redirecionado para a página de autenticação da plataforma selecionada.
1. Após ter sido autenticado na conta da plataforma social, você será redirecionado para o Audience Manager onde você deverá visualizar suas contas de anunciante associadas. Selecione a conta do anunciante que deseja usar e clique **[!UICONTROL Confirm]** em.
1. O Audience Manager exibe uma notificação na parte superior da página para informar se a conta foi adicionada com êxito. A notificação também permite que você adicione um endereço de email de contato para receber notificações quando a autenticação da plataforma social estiver prestes a expirar.

## Expiração do token de autenticação e gerenciamento de notificação {#token-expiration-notification}

O Audience Manager trata a integração com plataformas sociais por meio de tokens de autenticação que expiram após um determinado período. A duração de validade do token está sujeita às regras de integração de cada plataforma social. Quando o token de autenticação expirar, o Audience Manager não poderá enviar os segmentos do público-alvo para o destino. Para evitar esse cenário, recomendamos adicionar pelo menos um endereço de email para a integração, para que você receba notificações assim que o token de autenticação estiver prestes a expirar. Quando isso ocorre, você pode realizar a autenticação novamente para garantir que o destino continue recebendo os segmentos do público-alvo.

Veja como adicionar endereços de email às integrações existentes:

1. Faça logon em sua conta do Audience Manager e vá **[!UICONTROL Administration]** para &gt; **[!UICONTROL Integrated Accounts]**.
1. Identifique a integração para a qual você deseja receber notificações de expiração de token e clique no **[!UICONTROL Edit]** ícone.
1. Digite os endereços de email que deseja receber notificações de expiração de token, separadas por vírgulas.
1. Clique em **[!UICONTROL Save]**.

## Renovação do token de autenticação {#token-renewal}

Quando um token de autenticação expira, a integração entre o Audience Manager e a plataforma social correspondente é interrompida, portanto, o Audience Manager não pode enviar segmentos do público para o destino mais. A [!UICONTROL Integrated Accounts] página mostra o status de expiração de cada integração na [!UICONTROL Expiration] coluna e permite renovar a autenticação a qualquer momento.

Veja como renovar uma autenticação expirada ou prestes a expirar:
1. Faça logon em sua conta do Audience Manager e vá **[!UICONTROL Administration]** para &gt; **[!UICONTROL Integrated Accounts]**.
1. Identifique a integração necessária para renovar a autenticação. As autenticações expiradas são marcadas como [!UICONTROL Expired], enquanto as autenticações que estão prestes a expirar em breve mostram o número restante de dias autenticados.
1. Clique no ícone correspondente **[!UICONTROL Renew]** na [!UICONTROL Expiration] coluna. Isso aciona o **[!UICONTROL Renew Account]** fluxo de trabalho, que o leva de volta à página de autenticação da plataforma social. Quando você autenticar, o token será renovado com a nova data de expiração.
   ![pbd-renew](assets/pbd-renew.png)
