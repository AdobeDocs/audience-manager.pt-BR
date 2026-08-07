---
description: Uma atualização em massa permite editar vários segmentos, características, modelos, fontes de dados e elementos de segmentos ou pastas de características em uma única operação. Siga estas instruções para fazer atualizações em massa.
keywords: baaam
seo-description: A bulk update lets you edit multiple segments, traits, models, data sources, and segment or trait folder elements in a single operation. Follow these instructions to make bulk updates.
seo-title: Bulk Updates
solution: Audience Manager
title: Atualizações em massa
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: BAAAM
exl-id: ef01c7d0-5af1-4db7-9859-1087c1fef684
TQID: https://experienceleague.adobe.com/fDSvlPqWTgaw-SszCIa5M2qxJcyfrewPaW03eVShhDw
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: c2c33729-f309-4bc2-92ba-87c475259df3id: d3dfac44-e20d-492d-a806-0f4a4a495901id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 271
ht-degree: 0%

---

# Atualizações em massa{#bulk-updates}

Uma atualização em massa permite editar vários segmentos, características, modelos, fontes de dados e elementos de segmentos ou pastas de características em uma única operação. Siga estas instruções para fazer atualizações em massa.

>[!IMPORTANT]
>
>As Ferramentas de gerenciamento em massa não são uma oferta oficialmente compatível com o Adobe. A solução de problemas e o suporte por meio do Atendimento ao cliente serão tratados caso a caso.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>As [permissões do grupo RBAC](../../features/administration/administration-overview.md) atribuídas na interface do usuário [!DNL Audience Manager] são honradas no [!UICONTROL Bulk Management Tools].

Para fazer atualizações em massa, abra a planilha [!UICONTROL Bulk Management Tools] e:

1. Clique na guia **[!UICONTROL Headers]** e copie os cabeçalhos de atualização para o item que deseja editar.
2. Clique na guia **[!UICONTROL Update]**.
3. Cole os cabeçalhos de atualização na primeira linha da planilha de atualização. Observe o seguinte:

   * Ao atualizar uma pasta, todos os cabeçalhos são obrigatórios.
   * Ao atualizar segmentos ou características, você só precisa da ID de segmento (SID) e do elemento de cabeçalho que precisa ser alterado. Excluir cabeçalhos não utilizados.

4. Cole ou digite os dados que deseja alterar em uma coluna correspondente com base no rótulo do cabeçalho.
5. Na barra de ferramentas da planilha, clique em um botão de atualização que corresponda ao item que você está atualizando.
Esta ação abre a caixa de diálogo [!UICONTROL Account Information].

6. Forneça as [informações de logon](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) necessárias e clique em **[!UICONTROL Submit]**.

   A planilha cria uma coluna [!UICONTROL Results]. A coluna [!UICONTROL Results] retorna a resposta JSON para uma operação bem-sucedida. Consulte as [REST APIs](../../api/rest-api-main/rest-api-main.md) para obter exemplos. Antes de inserir dados, sua planilha de atualização em massa deve ser semelhante ao seguinte:

![](assets/update.png)

Se a atualização em massa retornar um erro ou falhar, consulte [Solução de problemas das Ferramentas de Gerenciamento em Massa](../../reference/bulk-management-tools/bulk-troubleshooting.md).
