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
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---

# Atualizações em massa{#bulk-updates}

Uma atualização em massa permite editar vários segmentos, características, modelos, fontes de dados e elementos de segmentos ou pastas de características em uma única operação. Siga estas instruções para fazer atualizações em massa.

>[!IMPORTANT]
>
>As Ferramentas de gerenciamento em massa não são uma oferta de Adobe oficialmente compatível. A solução de problemas e o suporte por meio do Atendimento ao cliente serão tratados caso a caso.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[Permissões de grupo RBAC](../../features/administration/administration-overview.md) atribuído no [!DNL Audience Manager] A interface do usuário do é respeitada na [!UICONTROL Bulk Management Tools].

Para fazer atualizações em massa, abra o [!UICONTROL Bulk Management Tools] planilha e:

1. Clique em **[!UICONTROL Headers]** e copie os cabeçalhos de atualização do item que deseja editar.
2. Clique em **[!UICONTROL Update]** guia.
3. Cole os cabeçalhos de atualização na primeira linha da planilha de atualização. Observe o seguinte:

   * Ao atualizar uma pasta, todos os cabeçalhos são obrigatórios.
   * Ao atualizar segmentos ou características, você só precisa da ID de segmento (SID) e do elemento de cabeçalho que precisa ser alterado. Excluir cabeçalhos não utilizados.

4. Cole ou digite os dados que deseja alterar em uma coluna correspondente com base no rótulo do cabeçalho.
5. Na barra de ferramentas da planilha, clique em um botão de atualização que corresponda ao item que você está atualizando.
Essa ação abre a variável [!UICONTROL Account Information] caixa de diálogo.

6. Forneça os [informações de logon](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) e clique em **[!UICONTROL Submit]**.

   A planilha cria uma [!UICONTROL Results] coluna. A variável [!UICONTROL Results] A coluna retorna a resposta JSON para uma operação bem-sucedida. Consulte a [REST APIs](../../api/rest-api-main/rest-api-main.md) para obter exemplos. Antes de inserir dados, sua planilha de atualização em massa deve ser semelhante ao seguinte:

![](assets/update.png)

Se a atualização em massa retornar um erro ou falhar, consulte [Solução de problemas para ferramentas de gerenciamento em massa](../../reference/bulk-management-tools/bulk-troubleshooting.md).
