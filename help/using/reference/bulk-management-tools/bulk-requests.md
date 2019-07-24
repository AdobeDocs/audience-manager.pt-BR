---
description: Uma solicitação em massa retorna os dados que você pode usar com os diferentes cabeçalhos nas planilhas Atualizar, Criar, Estimativa e Excluir.
seo-description: Uma solicitação em massa retorna os dados que você pode usar com os diferentes cabeçalhos nas planilhas Atualizar, Criar, Estimativa e Excluir.
seo-title: Solicitações em massa
solution: Audience Manager
title: Solicitações em massa
uuid: 0192 d 26 a -4 cea -4 e 12-9 fea -388 b 92 b 382 f 1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Requests{#bulk-requests}

Uma solicitação em massa retorna os dados que você pode usar com os diferentes cabeçalhos nas planilhas Atualizar, Criar, Estimativa e Excluir.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Essa ferramenta é fornecida para conveniência e apenas como cortesia. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [As permissões de grupo RBAC](../../features/administration/administration-overview.md) atribuídas na [!DNL Audience Manager] interface do usuário são respeitadas [!UICONTROL Bulk Management Tools].

The [!UICONTROL Request] worksheet does not have its own set of column headers and you don't need to copy IDs to any of the columns. Em vez disso, retorna dados com base no botão de ação clicado na barra de ferramentas. Além disso, um recurso de relatório opcional retorna uma contagem de frequência para acionamentos de pixel e a contagem de usuários únicos por vários intervalos de tempo fixos.

To make bulk requests, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Request]** tab.
2. Na barra de ferramentas na parte superior da planilha, clique em um botão de solicitação correspondente aos dados com os quais você deseja trabalhar. Você pode solicitar:

   * IDs do provedor de dados
   * Sinais derivados
   * Mapeamentos de destino
   * Características baseadas em regras e no local
   * Segmentos
   * IDs de pastas e segmentos de características
   The [!DNL Audience Manager] API writes bulk data back to the [!UICONTROL Request] worksheet.

>[!NOTE]
>
>In your results, the `createTime` and `updateTime` columns return data in exponential notation. Os carimbos de data/hora subjacentes são registrados no horário UNIX UTC. Atualmente, a planilha não pode retornar carimbos de data/hora em um formato legível.

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
