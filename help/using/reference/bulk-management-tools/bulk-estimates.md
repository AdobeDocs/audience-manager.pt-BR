---
description: Uma estimativa em massa retorna os dados de tamanho do segmento com base nas regras do segmento. Siga estas instruções para fazer uma solicitação de estimativa em massa.
seo-description: Uma estimativa em massa retorna os dados de tamanho do segmento com base nas regras do segmento. Siga estas instruções para fazer uma solicitação de estimativa em massa.
seo-title: Estimativas em massa
solution: Audience Manager
title: Estimativas em massa
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Estimativas em massa{#bulk-estimates}

Uma estimativa em massa retorna os dados de tamanho do segmento com base nas regras do segmento. Siga estas instruções para fazer uma solicitação de estimativa em massa.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>Os [!UICONTROL Bulk Management Tools] não *são suportados por* [!DNL Audience Manager]. Esta ferramenta é fornecida apenas para conveniência e cortesia. Para alterações em massa, recomendamos que você trabalhe com as APIs [do](../../api/rest-api-main/aam-api-getting-started.md) Audience Manager. [As permissões](../../features/administration/administration-overview.md) de grupo RBAC atribuídas na [!DNL Audience Manager] interface do usuário são respeitadas na [!UICONTROL Bulk Management Tools].

Para fazer atualizações em massa, abra a [!UICONTROL Bulk Management Tools] planilha e:

1. Clique na **[!UICONTROL Headers]** guia e copie o [!UICONTROL Estimate Segment Size] cabeçalho.
1. Click the **[!UICONTROL Estimate]** tab.
1. Cole o cabeçalho da estimativa na primeira linha da planilha da estimativa.
1. Cole ou digite os dados que deseja alterar em uma coluna correspondente com base no rótulo do cabeçalho.
1. Na barra de ferramentas da planilha, clique no botão criar que corresponde ao item que você está atualizando.
Essa ação abre a caixa de [!UICONTROL Account Information] diálogo.

1. Forneça as informações [necessárias para o](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) logon e clique em **[!UICONTROL Submit]**.

Essa ação cria uma [!UICONTROL Response] coluna na planilha que contém dados estimados do tamanho do segmento. Antes de inserir dados, sua planilha de estimativa em massa deve ser semelhante ao seguinte:

![](assets/estimate.png)
Se sua atualização em massa retornar um erro ou falhar, consulte [Solução de problemas para ferramentas](../../reference/bulk-management-tools/bulk-troubleshooting.md)de gerenciamento em massa.

