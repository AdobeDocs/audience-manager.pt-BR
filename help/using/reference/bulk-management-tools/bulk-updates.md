---
description: Uma atualização em massa permite editar vários segmentos, características, modelos, fontes de dados e elementos de segmentos ou pastas de características em uma única operação. Siga estas instruções para fazer atualizações em massa.
keywords: baaam
seo-description: Uma atualização em massa permite editar vários segmentos, características, modelos, fontes de dados e elementos de segmentos ou pastas de características em uma única operação. Siga estas instruções para fazer atualizações em massa.
seo-title: Atualizações em massa
solution: Audience Manager
title: Atualizações em massa
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: BAAAM
exl-id: ef01c7d0-5af1-4db7-9859-1087c1fef684
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 2%

---

# Atualizações em massa{#bulk-updates}

Uma atualização em massa permite editar vários segmentos, características, modelos, fontes de dados e elementos de segmentos ou pastas de características em uma única operação. Siga estas instruções para fazer atualizações em massa.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[As ](../../features/administration/administration-overview.md) permissões do grupo RBAC atribuídas na  [!DNL Audience Manager] interface do usuário são honradas no  [!UICONTROL Bulk Management Tools].

Para fazer atualizações em massa, abra a planilha [!UICONTROL Bulk Management Tools] e:

1. Clique na guia **[!UICONTROL Headers]** e copie os cabeçalhos de atualização do item que deseja editar.
2. Clique na guia **[!UICONTROL Update]**.
3. Cole os cabeçalhos de atualização na primeira linha da planilha de atualização. Observe o seguinte:

   * Ao atualizar uma pasta, todos os cabeçalhos são necessários.
   * Ao atualizar segmentos ou características, você só precisa da ID de segmento (SID) e do elemento de cabeçalho que precisa ser alterado. Exclua cabeçalhos não utilizados.

4. Cole ou digite os dados que deseja alterar em uma coluna correspondente com base no rótulo do cabeçalho.
5. Na barra de ferramentas da planilha, clique em um botão de atualização que corresponda ao        item que você está atualizando.
Essa ação abre a caixa de diálogo [!UICONTROL Account Information].

6. Forneça as [informações necessárias sobre o logon](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) e clique em **[!UICONTROL Submit]**.

   A planilha cria uma coluna [!UICONTROL Results]. A coluna [!UICONTROL Results] retorna a resposta JSON para uma operação bem-sucedida. Consulte as [REST APIs](../../api/rest-api-main/rest-api-main.md) para obter exemplos. Antes de inserir dados, sua planilha de atualização em massa deve ser semelhante ao seguinte:

![](assets/update.png)

Se a atualização em massa retornar um erro ou falhar, consulte [Solução de problemas para Ferramentas de gerenciamento em massa](../../reference/bulk-management-tools/bulk-troubleshooting.md).
