---
description: A exclusão em massa permite remover vários segmentos, características, pastas, sinais derivados, fontes de dados, modelos e destinos com uma única operação. Siga estas instruções para fazer uma solicitação de exclusão em massa.
seo-description: A exclusão em massa permite remover vários segmentos, características, pastas, sinais derivados, fontes de dados, modelos e destinos com uma única operação. Siga estas instruções para fazer uma solicitação de exclusão em massa.
seo-title: Exclusão em massa
solution: Audience Manager
title: Exclusão em massa
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 2%

---


# Exclusão em massa{#bulk-delete}

A exclusão em massa permite remover vários segmentos, características, pastas, sinais derivados, fontes de dados, modelos e destinos com uma única operação. Siga estas instruções para fazer uma solicitação de exclusão em massa.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[As ](../../features/administration/administration-overview.md) permissões do grupo RBAC atribuídas na  [!DNL Audience Manager] interface do usuário são respeitadas no  [!UICONTROL Bulk Management Tools].

>[!NOTE]
>
>Uma exclusão em massa para mapeamentos de destino falhará se você tiver segmentos mapeados para o destino. Remova seus segmentos desse destino na interface do usuário antes de tentar excluir destinos em massa. Além disso, as pastas de características e segmentos devem estar vazias para que você possa excluí-las.

Para excluir vários itens, abra a planilha [!UICONTROL Bulk Management Tools] e:

1. Clique na guia **[!UICONTROL Headers]** e copie os cabeçalhos de criação para o item que você deseja adicionar.
2. Clique na guia **[!UICONTROL Delete]**.
3. Cole os cabeçalhos de exclusão na primeira linha da planilha de atualização.
4. Cole ou digite as IDs dos objetos que deseja excluir na coluna abaixo do cabeçalho.
5. Forneça as [informações de logon necessárias](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) e clique em **[!UICONTROL Submit]**.

   A planilha cria uma coluna [!UICONTROL Results]. A coluna [!UICONTROL Results] retorna uma mensagem que indica se o item foi excluído ou uma mensagem de erro.
Antes de inserir os dados, a planilha de atualização em massa deve ser semelhante ao seguinte:

![](assets/delete.png)

Se sua atualização em massa retornar um erro ou falhar, consulte [Solução de problemas para ferramentas de gerenciamento em massa](../../reference/bulk-management-tools/bulk-troubleshooting.md).
