---
description: Uma atualização em massa permite editar vários segmentos, características e elementos de pastas de segmento ou característica em uma única operação. Siga estas instruções para fazer atualizações em massa.
keywords: baaam
seo-description: Uma atualização em massa permite editar vários segmentos, características e elementos de pastas de segmento ou característica em uma única operação. Siga estas instruções para fazer atualizações em massa.
seo-title: Atualizações em massa
solution: Audience Manager
title: Atualizações em massa
uuid: 22 f 1 badd-a 274-4 d 3 e -9957-a 24 bf 8 c 1 d 0 dc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Updates{#bulk-updates}

Uma atualização em massa permite editar vários segmentos, características e elementos de pastas de segmento ou característica em uma única operação. Siga estas instruções para fazer atualizações em massa.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Essa ferramenta é fornecida para conveniência e apenas como cortesia. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [As permissões de grupo RBAC](../../features/administration/administration-overview.md) atribuídas na [!DNL Audience Manager] interface do usuário são respeitadas [!UICONTROL Bulk Management Tools].

To make bulk updates, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the update headers for the item you want to edit.
1. Click the **[!UICONTROL Update]** tab.
1. Cole os cabeçalhos de atualização na primeira linha da planilha de atualização. Observe o seguinte:

   * Ao atualizar uma pasta, todos os cabeçalhos são obrigatórios.
   * Ao atualizar segmentos ou características, você precisa apenas da ID do segmento (SID) e do elemento de cabeçalho que precisa ser alterado. Excluir cabeçalhos não utilizados.

1. Cole ou digite os dados que deseja alterar em uma coluna correspondente com base no rótulo do cabeçalho.
1. Na barra de ferramentas da planilha, clique em um botão de atualização que corresponda ao item que está sendo atualizado.
This action opens the [!UICONTROL Account Information] dialog box.

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

   The worksheet creates a [!UICONTROL Results] column. The [!UICONTROL Results] column returns the JSON response for a successful operation. See the [REST APIs](../../api/rest-api-main/rest-api-main.md) for examples. Antes de digitar os dados, sua planilha de atualização em massa deve ser semelhante ao seguinte:

![](assets/update.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
