---
description: A criação em massa permite construir várias fontes de dados, sinais derivados, segmentos, características e outros itens com uma única operação. Siga estas instruções para fazer uma solicitação de criação em massa.
seo-description: Bulk create lets you construct multiple data sources, derived signals, segments, traits, and other items with a single operation. Follow these instructions to make a bulk creation request.
seo-title: Bulk Create
solution: Audience Manager
title: Criação em massa
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 1%

---

# Criação em massa{#bulk-create}

A criação em massa permite construir várias fontes de dados, sinais derivados, segmentos, características e outros itens com uma única operação. Siga estas instruções para fazer uma solicitação de criação em massa.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[Permissões de grupo RBAC](../../features/administration/administration-overview.md) atribuído no [!DNL Audience Manager] A interface do usuário do é respeitada na [!UICONTROL Bulk Management Tools].

>[!CAUTION]
>
>Não misture tipos de objeto em uma solicitação de criação em massa. Os cabeçalhos de cada objeto são exclusivos e não podem ser combinados. Limpe a planilha e faça uma solicitação separada para itens diferentes.

Para criar objetos em massa, abra a variável [!UICONTROL Bulk Management Tools] planilha e:

1. Clique em **[!UICONTROL Headers]** e copie os cabeçalhos de criação para o item que deseja adicionar.
2. Clique em **[!UICONTROL Create]** guia.
3. Cole os cabeçalhos de criação na primeira linha da planilha de atualização.
4. Cole ou digite os dados que deseja alterar em uma coluna correspondente com base no rótulo do cabeçalho.
5. Na barra de ferramentas da planilha, clique no botão Criar que corresponda ao item que você está atualizando.
Essa ação abre a variável [!UICONTROL Account Information] caixa de diálogo.
6. Forneça os [informações de logon](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) e clique em **[!UICONTROL Submit]**.

A planilha cria uma [!UICONTROL Results] coluna. A variável [!UICONTROL Results] A coluna retorna a resposta JSON para uma operação bem-sucedida. Consulte a [REST APIs](../../api/rest-api-main/rest-api-main.md) para obter exemplos. Antes de inserir dados, sua planilha de criação em massa deve ser semelhante ao exemplo a seguir. Observe que todas as diferentes opções de criação não são mostradas aqui. Isso é incluído para ajudá-lo a entender como uma planilha concluída pode ser.

![](assets/cretetraits.png)

Se a atualização em massa retornar um erro ou falhar, consulte [Solução de problemas para ferramentas de gerenciamento em massa](../../reference/bulk-management-tools/bulk-troubleshooting.md).
