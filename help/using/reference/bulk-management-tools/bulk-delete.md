---
description: A exclusão em massa permite remover vários segmentos, características, pastas, sinais derivados, fontes de dados, modelos e destinos com uma única operação. Siga estas instruções para fazer uma solicitação de exclusão em massa.
seo-description: Bulk delete lets you remove multiple segments, traits, folders, derived signals, data sources, models, and destinations with a single operation. Follow these instructions to make a bulk delete request.
seo-title: Bulk Delete
solution: Audience Manager
title: Exclusão em massa
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
feature: BAAAM
exl-id: 3ff530dd-66d0-4dd3-a6e6-afe4a9cb5ba4
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 1%

---

# Exclusão em massa{#bulk-delete}

A exclusão em massa permite remover vários segmentos, características, pastas, sinais derivados, fontes de dados, modelos e destinos com uma única operação. Siga estas instruções para fazer uma solicitação de exclusão em massa.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[Permissões de grupo RBAC](../../features/administration/administration-overview.md) atribuído no [!DNL Audience Manager] A interface do usuário do é respeitada na [!UICONTROL Bulk Management Tools].

>[!NOTE]
>
>Uma exclusão em massa para mapeamentos de destino falhará se você tiver segmentos mapeados para o destino. Remova os segmentos desse destino na interface do usuário antes de tentar excluir destinos em massa. Além disso, as pastas de características e segmentos devem estar vazias para que você possa excluí-las.

Para excluir vários itens, abra o [!UICONTROL Bulk Management Tools] planilha e:

1. Clique em **[!UICONTROL Headers]** e copie os cabeçalhos de criação para o item que deseja adicionar.
2. Clique em **[!UICONTROL Delete]** guia.
3. Cole os cabeçalhos de exclusão na primeira linha da planilha de atualização.
4. Cole ou digite as IDs dos objetos que deseja excluir na coluna abaixo do cabeçalho.
5. Forneça os [informações de logon](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) e clique em **[!UICONTROL Submit]**.

   A planilha cria uma [!UICONTROL Results] coluna. A variável [!UICONTROL Results] A coluna retorna uma mensagem que indica se o item foi excluído ou uma mensagem de erro.
Antes de inserir dados, sua planilha de atualização em massa deve ser semelhante ao seguinte:

![](assets/delete.png)

Se a atualização em massa retornar um erro ou falhar, consulte [Solução de problemas para ferramentas de gerenciamento em massa](../../reference/bulk-management-tools/bulk-troubleshooting.md).
