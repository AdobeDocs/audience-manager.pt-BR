---
description: Uma estimativa em massa retorna dados de tamanho de segmento com base em regras de segmento. Siga estas instruções para fazer uma solicitação de estimativa em massa.
seo-description: A bulk estimate returns segment size data based on segment rules. Follow these instructions to make a bulk estimate request.
seo-title: Bulk Estimates
solution: Audience Manager
title: Estimativas em massa
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---

# Estimativas em massa{#bulk-estimates}

Uma estimativa em massa retorna dados de tamanho de segmento com base em regras de segmento. Siga estas instruções para fazer uma solicitação de estimativa em massa.

>[!IMPORTANT]
>
>As Ferramentas de gerenciamento em massa não são uma oferta de Adobe oficialmente compatível. A solução de problemas e o suporte por meio do Atendimento ao cliente serão tratados caso a caso.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>As [permissões do grupo RBAC](../../features/administration/administration-overview.md) atribuídas na interface do usuário [!DNL Audience Manager] são honradas no [!UICONTROL Bulk Management Tools].

Para fazer atualizações em massa, abra a planilha [!UICONTROL Bulk Management Tools] e:

1. Clique na guia **[!UICONTROL Headers]** e copie o cabeçalho [!UICONTROL Estimate Segment Size].
2. Clique na guia **[!UICONTROL Estimate]**.
3. Cole o cabeçalho da estimativa na primeira linha da planilha da estimativa.
4. Cole ou digite os dados que deseja alterar em uma coluna correspondente com base no rótulo do cabeçalho.
5. Na barra de ferramentas da planilha, clique no botão Criar que corresponda ao item que você está atualizando.
Esta ação abre a caixa de diálogo [!UICONTROL Account Information].
6. Forneça as [informações de logon](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) necessárias e clique em **[!UICONTROL Submit]**.

Esta ação cria uma coluna [!UICONTROL Response] na planilha que contém os dados de tamanho estimado do segmento. Antes de inserir dados, sua planilha de estimativa em massa deve ser semelhante ao seguinte:

![](assets/estimate.png)
Se a atualização em massa retornar um erro ou falhar, consulte [Solução de problemas das Ferramentas de Gerenciamento em Massa](../../reference/bulk-management-tools/bulk-troubleshooting.md).
