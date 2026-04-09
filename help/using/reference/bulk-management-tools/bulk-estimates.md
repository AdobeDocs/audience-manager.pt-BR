---
description: Uma estimativa em massa retorna dados de tamanho de segmento com base em regras de segmento. Siga estas instruções para fazer uma solicitação de estimativa em massa.
seo-description: A bulk estimate returns segment size data based on segment rules. Follow these instructions to make a bulk estimate request.
seo-title: Bulk Estimates
solution: Audience Manager
title: Estimativas em massa
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
TQID: https://experienceleague.adobe.com/FDD4gSg00I8p4sRqxE9sEpO5dSkGEXpH3hUD6h5CAtI
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: d3dfac44-e20d-492d-a806-0f4a4a495901id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 199
ht-degree: 0%

---

# Estimativas em massa{#bulk-estimates}

Uma estimativa em massa retorna dados de tamanho de segmento com base em regras de segmento. Siga estas instruções para fazer uma solicitação de estimativa em massa.

>[!IMPORTANT]
>
>As Ferramentas de gerenciamento em massa não são uma oferta oficialmente compatível com o Adobe. A solução de problemas e o suporte por meio do Atendimento ao cliente serão tratados caso a caso.

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
