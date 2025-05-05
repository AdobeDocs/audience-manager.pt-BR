---
description: O gerenciamento de usuários do Audience Manager está sendo transferido para o Adobe Admin Console. Este artigo explica o que é necessário fazer para se preparar para a migração de usuários e o que será alterado após a conclusão da migração.
keywords: rbac;RBAC;baseado em função;baseado em função;controles de acesso baseados em função
seo-description: Audience Manager user management is moving to Adobe Admin Console. This article explains what you need to do to prepare for user migration, and what will change once the migration is complete.
seo-title: Audience Manager User Migration to Admin Console
solution: Audience Manager
title: Migração de usuário do Audience Manager para o Admin Console
feature: Administration
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 1%

---

# [!DNL Audience Manager] migração de usuário para [!DNL Admin Console] {#user-migration}

## Visão geral {#overview}

O gerenciamento de conta de usuário do [!DNL Audience Manager] está migrando para o [Adobe Admin Console](https://helpx.adobe.com/br/enterprise/using/admin-console.html) para proporcionar uma experiência mais simplificada nas soluções Adobe.

Os benefícios de usar o [!DNL Admin Console] incluem:

| Benefícios | Descrição |
|---|---|
| Logon único em todas as soluções | [!DNL Audience Manager] usuários podem entrar no [!DNL Experience Cloud] e em todas as outras soluções usando o [!DNL Adobe ID] ou [!DNL Enterprise ID]. Esta entrada habilita o acesso a soluções integradas e serviços principais em [!DNL Experience Cloud]. Após a migração, os usuários que tentarem entrar por meio de logons antigos (`bank.demdex.com`) serão redirecionados para `experiencecloud.adobe.com`. |
| Gerenciar usuários e grupos | Quando a migração for concluída, os administradores do [!DNL Audience Manager] gerenciarão usuários e grupos exclusivamente no [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/). |
| Gerenciar produtos e serviços | A partir de [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/), os administradores podem: <ul><li>Criar, atualizar e remover usuários</li><li>Conceder acesso a soluções e serviços</li></ul> |

Para facilitar a migração de usuários, pedimos a todos os administradores do [!DNL Audience Manager] que comecem a migrar suas contas de usuário para o [Adobe Admin Console](https://helpx.adobe.com/br/enterprise/using/admin-console.html) o mais rápido possível, seguindo as etapas descritas neste artigo.

## O que os usuários precisam fazer {#what-to-do-users}

Como usuário do Audience Manager, basta contatar o administrador do [!DNL Audience Manager] e solicitar que ele crie uma nova conta de usuário para você no [!DNL Admin Console].

## O que os administradores precisam fazer {#what-to-do-admins}

Os administradores de Audience Manager devem seguir as etapas abaixo para migrar usuários para o [!DNL Admin Console].

1. Vá para [https://adminconsole.adobe.com](https://adminconsole.adobe.com) e faça logon usando sua Adobe ID ou Enterprise ID. Se você não tiver acesso a [!DNL Admin Console], entre em contato com o Atendimento ao cliente ou com o consultor da Adobe.
2. Consulte o [!DNL Adobe Admin Console] [guia de ajuda](https://helpx.adobe.com/br/enterprise/admin-guide.html/enterprise/using/users.ug.html) para obter instruções detalhadas sobre como criar e gerenciar contas de usuário.
3. Crie novas contas de usuário para todos os seus usuários Audience Manager existentes.
4. Informe os usuários sobre as contas de usuário recém-criadas. Depois que os usuários forem migrados para [!DNL Admin Console], eles deverão parar de usar logons herdados.

## Considerações sobre a migração de usuários {#considerations}

Tanto os usuários quanto os administradores devem ter em mente as seguintes considerações para a migração de usuários do Audience Manager:

* Depois que novas contas de usuário forem criadas no Admin Console, suas permissões existentes de suas contas de usuário herdadas ainda serão aplicadas.
* As atualizações de permissões de usuário ainda serão gerenciadas de [!DNL Audience Manager]. O [!DNL Admin Console] abrange apenas o gerenciamento de usuários e grupos.
* Os administradores não precisam desativar contas de usuário herdadas. As contas de usuário antigas serão mescladas automaticamente com as migradas.
