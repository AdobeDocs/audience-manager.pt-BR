---
description: Uma estimativa em massa retorna dados de tamanho de segmento com base em regras de segmento. Siga estas instruções para fazer uma solicitação de estimativa em massa.
seo-description: A bulk estimate returns segment size data based on segment rules. Follow these instructions to make a bulk estimate request.
seo-title: Bulk Estimates
solution: Audience Manager
title: Estimativas em massa
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 2%

---

# Estimativas em massa{#bulk-estimates}

Uma estimativa em massa retorna dados de tamanho de segmento com base em regras de segmento. Siga estas instruções para fazer uma solicitação de estimativa em massa.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[Permissões de grupo RBAC](../../features/administration/administration-overview.md) atribuído no [!DNL Audience Manager] A interface do usuário do é respeitada na [!UICONTROL Bulk Management Tools].

Para fazer atualizações em massa, abra o [!UICONTROL Bulk Management Tools] planilha e:

1. Clique em **[!UICONTROL Headers]** e copie a guia [!UICONTROL Estimate Segment Size] cabeçalho.
2. Clique em **[!UICONTROL Estimate]** guia.
3. Cole o cabeçalho da estimativa na primeira linha da planilha da estimativa.
4. Cole ou digite os dados que deseja alterar em uma coluna correspondente com base no rótulo do cabeçalho.
5. Na barra de ferramentas da planilha, clique no botão Criar que corresponda ao item que você está atualizando.
Essa ação abre a variável [!UICONTROL Account Information] caixa de diálogo.
6. Forneça os [informações de logon](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) e clique em **[!UICONTROL Submit]**.

Essa ação cria uma [!UICONTROL Response] na planilha que contém os dados de tamanho estimado do segmento. Antes de inserir dados, sua planilha de estimativa em massa deve ser semelhante ao seguinte:

![](assets/estimate.png)
Se a atualização em massa retornar um erro ou falhar, consulte [Solução de problemas para ferramentas de gerenciamento em massa](../../reference/bulk-management-tools/bulk-troubleshooting.md).
