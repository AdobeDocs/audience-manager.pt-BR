---
description: A exclusão em massa permite remover vários segmentos, características, pastas, sinais derivados e destinos com uma única operação. Siga estas instruções para fazer uma solicitação de exclusão em massa.
seo-description: A exclusão em massa permite remover vários segmentos, características, pastas, sinais derivados e destinos com uma única operação. Siga estas instruções para fazer uma solicitação de exclusão em massa.
seo-title: Exclusão em massa
solution: Audience Manager
title: Exclusão em massa
uuid: 679 cde 46-09 fb -45 c 6-b 84 d -47 e 00 e 0 e 7 c 0 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Delete{#bulk-delete}

A exclusão em massa permite remover vários segmentos, características, pastas, sinais derivados e destinos com uma única operação. Siga estas instruções para fazer uma solicitação de exclusão em massa.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Essa ferramenta é fornecida para conveniência e apenas como cortesia. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [As permissões de grupo RBAC](../../features/administration/administration-overview.md) atribuídas na [!DNL Audience Manager] interface do usuário são respeitadas [!UICONTROL Bulk Management Tools].

>[!NOTE]
>
>Uma exclusão em massa para mapeamentos de destino falhará se houver segmentos mapeados para o destino. Remova seus segmentos desse destino na interface do usuário antes de tentar excluir destinos em massa. Além disso, as pastas de características e segmentos devem estar vazias antes de excluí-las.

To delete multiple items, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the create headers for the item you want to add.
2. Click the **[!UICONTROL Delete]** tab.
3. Cole os cabeçalhos de exclusão na primeira linha da planilha de atualização.
4. Cole ou digite as IDs dos objetos que deseja excluir na coluna abaixo do cabeçalho.
5. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

   The worksheet creates a [!UICONTROL Results] column. [!UICONTROL Results] A coluna retorna uma mensagem que indica se o item foi excluído ou uma mensagem de erro.
Antes de digitar os dados, sua planilha de atualização em massa deve ser semelhante ao seguinte:

![](assets/delete.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
