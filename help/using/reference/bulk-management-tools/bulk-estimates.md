---
description: Uma estimativa em massa retorna os dados do tamanho do segmento com base nas regras do segmento. Siga estas instruções para fazer uma solicitação de estimativa em massa.
seo-description: Uma estimativa em massa retorna os dados do tamanho do segmento com base nas regras do segmento. Siga estas instruções para fazer uma solicitação de estimativa em massa.
seo-title: Estimativas em massa
solution: Audience Manager
title: Estimativas em massa
uuid: 63 b 2 f 06 a -8 ba 0-47 a 2-bd 0 b -8039 b 2 d 4 c 95 d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Estimates{#bulk-estimates}

Uma estimativa em massa retorna os dados do tamanho do segmento com base nas regras do segmento. Siga estas instruções para fazer uma solicitação de estimativa em massa.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Essa ferramenta é fornecida para conveniência e apenas como cortesia. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [As permissões de grupo RBAC](../../features/administration/administration-overview.md) atribuídas na [!DNL Audience Manager] interface do usuário são respeitadas [!UICONTROL Bulk Management Tools].

To make bulk updates, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the [!UICONTROL Estimate Segment Size] header.
1. Click the **[!UICONTROL Estimate]** tab.
1. Cole o cabeçalho da estimativa na primeira linha da planilha de estimativa.
1. Cole ou digite os dados que deseja alterar em uma coluna correspondente com base no rótulo do cabeçalho.
1. Na barra de ferramentas da planilha, clique no botão criar que corresponda ao item que está sendo atualizado.
This action opens the [!UICONTROL Account Information] dialog box.

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

This action creates a [!UICONTROL Response] column in the worksheet that contains estimated segment size data. Antes de digitar os dados, sua planilha de estimativa em massa deve ser semelhante ao seguinte:

![](assets/estimate.png)Se a sua atualização em massa retornar um erro ou falhar, consulte [Solução de problemas das ferramentas](../../reference/bulk-management-tools/bulk-troubleshooting.md)de gerenciamento em massa.

