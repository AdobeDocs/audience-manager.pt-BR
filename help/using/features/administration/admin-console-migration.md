---
description: O gerenciamento de usuários do Audience Manager está migrando para o Adobe Admin Console. Este artigo explica o que você precisa fazer para se preparar para a migração do usuário e o que mudará quando a migração for concluída.
keywords: rbac;RBAC;baseado em função;baseado em função;controles de acesso baseados em função
seo-description: O gerenciamento de usuários do Audience Manager está migrando para o Adobe Admin Console. Este artigo explica o que você precisa fazer para se preparar para a migração do usuário e o que mudará quando a migração for concluída.
seo-title: Migração de usuário Audience Manager para Admin Console
solution: Audience Manager
title: Migração de usuário Audience Manager para Admin Console
feature: Administration
translation-type: tm+mt
source-git-commit: 04504d4561414f9558a1f1f4db33cbcf535d54af
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 3%

---


# [!DNL Audience Manager] migração do usuário para  [!DNL Admin Console] {#user-migration}

## Visão geral {#overview}

[!DNL Audience Manager] o gerenciamento de conta de usuário está migrando para a  [Adobe Admin Console](https://helpx.adobe.com/br/enterprise/using/admin-console.html) para obter uma experiência mais simplificada nas soluções de Adobe.

Os benefícios do uso do [!DNL Admin Console] incluem:

| Benefícios | Descrição |
|---|---|
| Logon único em soluções | [!DNL Audience Manager] os usuários podem fazer logon  [!DNL Experience Cloud] e todas as outras soluções usando seus  [!DNL Adobe ID] ou  [!DNL Enterprise ID]. Esse logon permite o acesso a soluções integradas e serviços principais em [!DNL Experience Cloud]. Após a migração, os usuários que tentarem fazer logon por meio de logons herdados (`bank.demdex.com`) serão redirecionados para `experiencecloud.adobe.com`. |
| Gerenciar usuários e grupos | Quando a migração estiver concluída, [!DNL Audience Manager] os administradores gerenciarão usuários e grupos exclusivamente em [[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/). |
| Gerenciar produtos e serviços | Em [[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/), os administradores podem: <ul><li>Criar, atualizar e remover usuários</li><li>Conceder acesso a soluções e serviços</li><li>Conceder permissões ao usuário</li></ul> |

Para facilitar a migração de usuários, pedimos a todos os [!DNL Audience Manager] administradores que façam a migração de suas contas de usuário para [Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html) o mais rápido possível, seguindo as etapas descritas neste artigo.

## O que os usuários precisam fazer {#what-to-do-users}

Como usuário do Audience Manager, tudo o que você precisa fazer é entrar em contato com o administrador [!DNL Audience Manager] e solicitar que ele crie uma nova conta de usuário para você em [!DNL Admin Console].

## O que os administradores precisam fazer {#what-to-do-admins}

Os administradores de Audience Manager devem seguir as etapas abaixo para migrar os usuários para [!DNL Admin Console].

1. Acesse [https://adminconsole.adobe.com](https://adminconsole.adobe.com) e faça logon usando seu Adobe ID ou Enterprise ID. Se você não tiver acesso ao [!DNL Admin Console], entre em contato com o Atendimento ao cliente ou seu consultor de Adobe.
2. Consulte o [!DNL Adobe Admin Console] [guia de ajuda](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html) para obter instruções detalhadas sobre como criar e gerenciar contas de usuário.
3. Crie novas contas de usuário para todos os usuários existentes do Audience Manager.
4. Informe seus usuários sobre as contas de usuário recém-criadas. Depois que os usuários forem migrados para [!DNL Admin Console], eles deverão parar de usar logons herdados.

## Considerações sobre migração de usuários {#considerations}

Os usuários e administradores devem ter em mente as seguintes considerações para a migração de usuários do Audience Manager:

* Assim que novas contas de usuário forem criadas no Admin Console, suas permissões existentes de suas contas de usuário herdadas serão automaticamente carregadas. Não há necessidade de os administradores atribuírem novas permissões em [!DNL Admin Console].
* Os administradores não precisam desativar contas de usuário herdadas. As contas de usuário antigas serão automaticamente mescladas nas migradas.
* As atualizações das permissões de usuário ainda serão gerenciadas de [!DNL Audience Manager]. O [!DNL Admin Console] abrange apenas o gerenciamento de usuários e grupos.