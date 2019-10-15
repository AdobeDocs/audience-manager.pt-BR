---
description: Uma atualização em massa permite editar vários segmentos, características, modelos, fontes de dados e elementos de pastas de segmento ou característica em uma única operação. Siga estas instruções para fazer atualizações em massa.
keywords: baaam
seo-description: Uma atualização em massa permite editar vários segmentos, características, modelos, fontes de dados e elementos de pastas de segmento ou característica em uma única operação. Siga estas instruções para fazer atualizações em massa.
seo-title: Atualizações em massa
solution: Audience Manager
title: Atualizações em massa
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
translation-type: tm+mt
source-git-commit: 30d4cec4502a2cf8b217816ea4ae62eb1b22f641

---


# Atualizações em massa{#bulk-updates}

Uma atualização em massa permite editar vários segmentos, características, modelos, fontes de dados e elementos de pastas de segmento ou característica em uma única operação. Siga estas instruções para fazer atualizações em massa.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>Os [!UICONTROL Bulk Management Tools] não *são suportados por* [!DNL Audience Manager]. Esta ferramenta é fornecida apenas para conveniência e cortesia. Para alterações em massa, recomendamos que você trabalhe com as APIs [do](../../api/rest-api-main/aam-api-getting-started.md) Audience Manager. [As permissões](../../features/administration/administration-overview.md) de grupo RBAC atribuídas na [!DNL Audience Manager] interface do usuário são respeitadas na [!UICONTROL Bulk Management Tools].

Para fazer atualizações em massa, abra a [!UICONTROL Bulk Management Tools] planilha e:

1. Clique na **[!UICONTROL Headers]** guia e copie os cabeçalhos de atualização do item que você deseja editar.
1. Click the **[!UICONTROL Update]** tab.
1. Cole os cabeçalhos de atualização na primeira linha da planilha de atualização. Observe o seguinte:

   * Ao atualizar uma pasta, todos os cabeçalhos são necessários.
   * Ao atualizar segmentos ou características, você só precisa da ID do segmento (SID) e do elemento do cabeçalho que precisa ser alterado. Exclua cabeçalhos não utilizados.

1. Cole ou digite os dados que deseja alterar em uma coluna correspondente com base no rótulo do cabeçalho.
1. Na barra de ferramentas da planilha, clique em um botão de atualização que corresponda ao item que você está atualizando.
Essa ação abre a caixa de [!UICONTROL Account Information] diálogo.

1. Forneça as informações [necessárias para o](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) logon e clique em **[!UICONTROL Submit]**.

   A planilha cria uma [!UICONTROL Results] coluna. A [!UICONTROL Results] coluna retorna a resposta JSON para uma operação bem-sucedida. Consulte as APIs [](../../api/rest-api-main/rest-api-main.md) REST para obter exemplos. Antes de inserir dados, a planilha de atualização em massa deve ser semelhante ao seguinte:

![](assets/update.png)

Se sua atualização em massa retornar um erro ou falhar, consulte [Solução de problemas para ferramentas](../../reference/bulk-management-tools/bulk-troubleshooting.md)de gerenciamento em massa.
