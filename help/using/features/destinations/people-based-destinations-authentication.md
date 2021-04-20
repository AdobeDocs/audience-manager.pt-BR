---
description: 'Esta página contém orientações sobre como configurar e gerenciar a integração entre o Audience Manager e as plataformas baseadas em pessoas. '
seo-description: 'Esta página contém orientações sobre como configurar e gerenciar a integração entre o Audience Manager e as plataformas baseadas em pessoas. '
seo-title: Autenticação com plataformas com base em pessoas
solution: Audience Manager
title: Autenticação com plataformas com base em pessoas
feature: People-based Destinations
exl-id: d3e136d0-2b06-412a-9b9b-75b661c9aa14
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 2%

---

# Autenticação com plataformas com base em pessoas {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo pela configuração e uso deste recurso. Nada neste documento é de aconselhamento jurídico. Consulte o seu advogado para obter orientação jurídica.

Esta página contém orientações sobre como configurar e gerenciar sua integração
entre o Audience Manager e as plataformas baseadas em pessoas.

>[!NOTE]
>Esta é uma etapa obrigatória para Destinos com base em pessoas, independentemente do cenário de implementação.

## Configurar a autenticação de plataforma baseada em pessoas {#configure-authentication}

1. Faça logon na sua conta do Audience Manager e acesse **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Se você tiver uma integração configurada anteriormente com uma plataforma social, ela deverá ser exibida nesta página. Caso contrário, a página ficará vazia.
   ![integração com base em pessoas](assets/pbd-config.png)
2. Clique em **[!UICONTROL Add Account]**.
3. Use o menu suspenso **[!UICONTROL People-Based Platform]** para selecionar a plataforma com a qual deseja configurar a integração.
   ![plataforma baseada em pessoas](assets/pbd-add.png)
4. Clique em **[!UICONTROL Confirm]** para ser redirecionado para a página de autenticação da plataforma selecionada.
5. Depois de autenticar na conta da plataforma social, você é redirecionado para o Audience Manager, onde deve ver as contas de anunciante associadas. Selecione a conta do anunciante que deseja usar e clique em **[!UICONTROL Confirm]**.
6. O Audience Manager exibe uma notificação na parte superior da página para que você saiba se a conta foi adicionada com êxito. A notificação também permite adicionar um endereço de email de contato para receber notificações do Adobe quando a autenticação da plataforma social estiver prestes a expirar.

## Expiração do token de autenticação e Gerenciamento de notificações {#token-expiration-notification}

O Audience Manager trata sua integração com plataformas sociais por meio de tokens de autenticação que expiram após um determinado período. A duração da validade do token está sujeita às regras de integração de cada plataforma social. Quando o token de autenticação expira, o Audience Manager não pode enviar seus segmentos de público-alvo para o destino. Para evitar esse cenário, recomendamos adicionar pelo menos um endereço de email de contato à sua integração, para que você seja notificado assim que o token de autenticação estiver prestes a expirar. Quando isso ocorre, é possível autenticar novamente para garantir que o destino continue a receber seus segmentos de público-alvo.

Veja como adicionar endereços de email às integrações existentes:

1. Faça logon na sua conta do Audience Manager e acesse **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identifique a integração para a qual deseja receber notificações de expiração de token e clique no ícone **[!UICONTROL Edit]**.
1. Insira os endereços de email para os quais você deseja receber notificações de expiração de token, separadas por vírgulas.
1. Clique em **[!UICONTROL Save]**.

## Renovação de Token de Autenticação {#token-renewal}

Quando um token de autenticação expira, a integração entre o Audience Manager e a plataforma social correspondente é interrompida, portanto, o Audience Manager não pode mais enviar segmentos de público-alvo para o destino. A página [!UICONTROL Integrated Accounts] mostra o status de expiração de cada integração na coluna [!UICONTROL Expiration] e permite renovar a autenticação a qualquer momento.

Veja como renovar uma autenticação expirada ou prestes a expirar:
1. Faça logon na sua conta do Audience Manager e acesse **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identifique a integração para a qual você precisa renovar a autenticação. As autenticações expiradas são marcadas como [!UICONTROL Expired], enquanto as autenticações que estão prestes a expirar em breve mostram o número restante de dias autenticados.
1. Clique no ícone **[!UICONTROL Renew]** correspondente na coluna [!UICONTROL Expiration]. Isso aciona o workflow **[!UICONTROL Renew Account]**, que retorna pela página de autenticação da plataforma social. Depois de autenticar, o token será renovado com a nova data de expiração.
   ![pbd-renew](assets/pbd-renew.png)
