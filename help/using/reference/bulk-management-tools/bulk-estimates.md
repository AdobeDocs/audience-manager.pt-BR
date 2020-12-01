---
description: Uma estimativa em massa retorna os dados de tamanho do segmento com base nas regras do segmento. Siga estas instruções para fazer uma solicitação de estimativa em massa.
seo-description: Uma estimativa em massa retorna os dados de tamanho do segmento com base nas regras do segmento. Siga estas instruções para fazer uma solicitação de estimativa em massa.
seo-title: Estimativas em massa
solution: Audience Manager
title: Estimativas em massa
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 3%

---


# Estimativas em massa{#bulk-estimates}

Uma estimativa em massa retorna os dados de tamanho do segmento com base nas regras do segmento. Siga estas instruções para fazer uma solicitação de estimativa em massa.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[As ](../../features/administration/administration-overview.md) permissões do grupo RBAC atribuídas na  [!DNL Audience Manager] interface do usuário são respeitadas no  [!UICONTROL Bulk Management Tools].

Para fazer atualizações em massa, abra a planilha [!UICONTROL Bulk Management Tools] e:

1. Clique na guia **[!UICONTROL Headers]** e copie o cabeçalho [!UICONTROL Estimate Segment Size].
2. Clique na guia **[!UICONTROL Estimate]**.
3. Cole o cabeçalho da estimativa na primeira linha da planilha da estimativa.
4. Cole ou digite os dados que deseja alterar em uma coluna correspondente com base no rótulo do cabeçalho.
5. Na barra de ferramentas da planilha, clique no botão criar que corresponde ao item que você está atualizando.
Esta ação abre a caixa de diálogo [!UICONTROL Account Information].
6. Forneça as [informações de logon necessárias](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) e clique em **[!UICONTROL Submit]**.

Essa ação cria uma coluna [!UICONTROL Response] na planilha que contém dados estimados do tamanho do segmento. Antes de inserir dados, sua planilha de estimativa em massa deve ser semelhante ao seguinte:

![](assets/estimate.png)
Se sua atualização em massa retornar um erro ou falhar, consulte  [Solução de problemas para ferramentas](../../reference/bulk-management-tools/bulk-troubleshooting.md) de gerenciamento em massa.

