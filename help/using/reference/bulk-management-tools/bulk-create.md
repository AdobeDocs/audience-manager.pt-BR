---
description: A criação em massa permite construir várias fontes de dados, sinais derivados, segmentos, características e outros itens com uma única operação. Siga estas instruções para fazer uma solicitação de criação em massa.
seo-description: A criação em massa permite construir várias fontes de dados, sinais derivados, segmentos, características e outros itens com uma única operação. Siga estas instruções para fazer uma solicitação de criação em massa.
seo-title: Criação em massa
solution: Audience Manager
title: Criação em massa
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---

# Criação em massa{#bulk-create}

A criação em massa permite construir várias fontes de dados, sinais derivados, segmentos, características e outros itens com uma única operação. Siga estas instruções para fazer uma solicitação de criação em massa.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[As ](../../features/administration/administration-overview.md) permissões do grupo RBAC atribuídas na  [!DNL Audience Manager] interface do usuário são honradas no  [!UICONTROL Bulk Management Tools].

>[!CAUTION]
>
>Não misture tipos de objetos em uma solicitação de criação em massa. Os cabeçalhos de cada objeto são exclusivos e não podem ser combinados. Limpe a planilha e faça uma solicitação separada para itens diferentes.

Para criar objetos em massa, abra a planilha [!UICONTROL Bulk Management Tools] e:

1. Clique na guia **[!UICONTROL Headers]** e copie os cabeçalhos de criação para o item que deseja adicionar.
2. Clique na guia **[!UICONTROL Create]**.
3. Cole os cabeçalhos de criação na primeira linha da planilha de atualização.
4. Cole ou digite os dados que deseja alterar em uma coluna correspondente com base no rótulo do cabeçalho.
5. Na barra de ferramentas da planilha, clique no botão criar que corresponda ao item que você está atualizando.
Essa ação abre a caixa de diálogo [!UICONTROL Account Information].
6. Forneça as [informações necessárias sobre o logon](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) e clique em **[!UICONTROL Submit]**.

A planilha cria uma coluna [!UICONTROL Results]. A coluna [!UICONTROL Results] retorna a resposta JSON para uma operação bem-sucedida. Consulte as [REST APIs](../../api/rest-api-main/rest-api-main.md) para obter exemplos. Antes de inserir dados, sua planilha de criação em massa deve ser semelhante ao seguinte exemplo. Observe que todas as diferentes opções de criação não são mostradas aqui. Isso é incluído para ajudar você a entender como uma planilha concluída pode ser.

![](assets/cretetraits.png)

Se a atualização em massa retornar um erro ou falhar, consulte [Solução de problemas para Ferramentas de gerenciamento em massa](../../reference/bulk-management-tools/bulk-troubleshooting.md).
