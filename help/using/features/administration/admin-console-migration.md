---
description: O gerenciamento de usuários do Audience Manager está sendo transferido para o Adobe Admin Console. Este artigo explica o que é necessário fazer para se preparar para a migração de usuários e o que será alterado após a conclusão da migração.
keywords: rbac; RBAC; baseado em função; baseado em função; controles de acesso baseados em função
seo-description: O gerenciamento de usuários do Audience Manager está sendo transferido para o Adobe Admin Console. Este artigo explica o que é necessário fazer para se preparar para a migração de usuários e o que será alterado após a conclusão da migração.
seo-title: Migração de usuários do Audience Manager para o Admin Console
solution: Audience Manager
title: Migração de usuários do Audience Manager para o Admin Console
feature: Administração
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 3%

---

# [!DNL Audience Manager] migração de usuário para  [!DNL Admin Console] {#user-migration}

## Visão geral {#overview}

[!DNL Audience Manager] o gerenciamento da conta de usuário está migrando para a  [Adobe Admin Console](https://helpx.adobe.com/br/enterprise/using/admin-console.html) para obter uma experiência mais simplificada em suas soluções de Adobe.

Os benefícios de usar o [!DNL Admin Console] incluem:

| Benefícios | Descrição |
|---|---|
| Logon único em soluções | [!DNL Audience Manager] Os usuários do podem fazer logon no  [!DNL Experience Cloud] e em todas as outras soluções usando o  [!DNL Adobe ID] ou  [!DNL Enterprise ID]. Esse logon permite o acesso a soluções integradas e serviços principais em [!DNL Experience Cloud]. Após a migração, os usuários que tentarem fazer logon por meio de logons antigos (`bank.demdex.com`) serão redirecionados para `experiencecloud.adobe.com`. |
| Gerenciar usuários e grupos | Quando a migração estiver concluída, [!DNL Audience Manager] os administradores gerenciarão usuários e grupos exclusivamente no [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/). |
| Gerenciar produtos e serviços | No [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/), os administradores podem: <ul><li>Criar, atualizar e remover usuários</li><li>Conceder acesso a soluções e serviços</li></ul> |

Para facilitar a migração de usuários, pedimos a todos os [!DNL Audience Manager] administradores que comecem a migrar suas contas de usuário para [Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html) o mais rápido possível, seguindo as etapas descritas neste artigo.

## O que os usuários precisam fazer {#what-to-do-users}

Como usuário do Audience Manager, tudo o que você precisa fazer é entrar em contato com o administrador [!DNL Audience Manager] e solicitar que ele crie uma nova conta de usuário para você em [!DNL Admin Console].

## O que os administradores precisam fazer {#what-to-do-admins}

Os administradores do Audience Manager devem seguir as etapas abaixo para migrar os usuários para [!DNL Admin Console].

1. Vá para [https://adminconsole.adobe.com](https://adminconsole.adobe.com) e faça logon usando sua Adobe ID ou Enterprise ID. Se não tiver acesso ao [!DNL Admin Console], entre em contato com o Atendimento ao cliente ou com o consultor do Adobe.
2. Verifique o [!DNL Adobe Admin Console] [guia de ajuda](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html) para obter instruções detalhadas sobre como criar e gerenciar contas de usuário.
3. Crie novas contas de usuário para todos os usuários existentes do Audience Manager.
4. Informe seus usuários sobre as contas de usuário recém-criadas. Depois que os usuários forem migrados para [!DNL Admin Console], eles deverão parar de usar os logons herdados.

## Considerações sobre migração de usuário {#considerations}

Tanto os usuários quanto os administradores devem ter em mente as seguintes considerações para a migração de usuário do Audience Manager:

* Depois que novas contas de usuário forem criadas no Admin Console, suas permissões existentes de suas contas de usuário herdadas ainda serão aplicadas.
* As atualizações das permissões de usuário ainda serão gerenciadas a partir de [!DNL Audience Manager]. O [!DNL Admin Console] abrange apenas o gerenciamento de usuários e grupos.
* Os administradores não precisam desativar contas de usuário herdadas. As contas de usuário antigas serão automaticamente combinadas nas migradas.
