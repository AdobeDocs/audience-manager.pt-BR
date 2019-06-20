---
description: A criação em massa permite que você construa várias fontes de dados, sinais derivados, segmentos, características e outros itens com uma única operação. Siga estas instruções para criar uma solicitação de criação em massa.
seo-description: A criação em massa permite que você construa várias fontes de dados, sinais derivados, segmentos, características e outros itens com uma única operação. Siga estas instruções para criar uma solicitação de criação em massa.
seo-title: Criar em massa
solution: Audience Manager
title: Criar em massa
uuid: 1 e 09 bcfa -783 e -4 e 9 b -9 ead -147 f 8 d 1381 c 8
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Create{#bulk-create}

A criação em massa permite que você construa várias fontes de dados, sinais derivados, segmentos, características e outros itens com uma única operação. Siga estas instruções para criar uma solicitação de criação em massa.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Essa ferramenta é fornecida para conveniência e apenas como cortesia. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [As permissões de grupo RBAC](../../features/administration/administration-overview.md) atribuídas na [!DNL Audience Manager] interface do usuário são respeitadas [!UICONTROL Bulk Management Tools].

>[!CAUTION]
>
>Não misture tipos de objetos em uma solicitação de criação em massa. Os cabeçalhos de cada objeto são exclusivos e não podem ser combinados. Limpe a planilha e faça uma solicitação separada para itens diferentes.

To create objects in bulk, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the create headers for the item you want to add.
1. Click the **[!UICONTROL Create]** tab.
1. Cole os cabeçalhos de criação na primeira linha da planilha de atualização.
1. Cole ou digite os dados que deseja alterar em uma coluna correspondente com base no rótulo do cabeçalho.
1. Na barra de ferramentas da planilha, clique no botão criar que corresponda ao item que está sendo atualizado.
This action opens the [!UICONTROL Account Information] dialog box.

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

The worksheet creates a [!UICONTROL Results] column. The [!UICONTROL Results] column returns the JSON response for a successful operation. See the [REST APIs](../../api/rest-api-main/rest-api-main.md) for examples. Antes de digitar dados, sua planilha de criação em massa deve ser semelhante ao exemplo a seguir. Observe que todas as diferentes opções de criação não são mostradas aqui. Isso é incluído para ajudá-lo a entender a aparência de uma planilha concluída.

![](assets/cretetraits.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
