---
description: Uma solicitação em massa retorna dados que você pode usar com os diferentes cabeçalhos nas planilhas Atualizar, Criar, Estimar e Excluir.
seo-description: Uma solicitação em massa retorna dados que você pode usar com os diferentes cabeçalhos nas planilhas Atualizar, Criar, Estimar e Excluir.
seo-title: Solicitações em massa
solution: Audience Manager
title: Solicitações em massa
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 2%

---


# Solicitações em massa{#bulk-requests}

Uma solicitação em massa retorna dados que você pode usar com os diferentes cabeçalhos nas planilhas Atualizar, Criar, Estimar e Excluir.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[As permissões](../../features/administration/administration-overview.md) de grupo RBAC atribuídas na [!DNL Audience Manager] interface do usuário são respeitadas na [!UICONTROL Bulk Management Tools].

A [!UICONTROL Request] planilha não tem seu próprio conjunto de cabeçalhos de coluna e você não precisa copiar IDs para nenhuma das colunas. Em vez disso, retorna dados com base no botão de ação que você clica na barra de ferramentas. Além disso, um recurso de relatórios opcional retorna uma contagem de frequência para disparos de pixels e contagem de usuários única para vários intervalos de tempo fixos.

Para fazer solicitações em massa, abra a [!UICONTROL Bulk Management Tools] planilha e:

1. Click the **[!UICONTROL Request]** tab.
2. Na barra de ferramentas na parte superior da planilha, clique em um botão de solicitação correspondente aos dados com os quais você deseja trabalhar. Você pode solicitar:

   * Modelos algorítmicos
   * Fontes de dados
   * Sinais derivados
   * Mapeamentos de destino
   * Características algorítmicas, baseadas em regras e a bordo
   * Segmentos 
   * IDs de pasta de características e segmentos

   A [!DNL Audience Manager] API grava dados em massa de volta à [!UICONTROL Request] planilha.

>[!NOTE]
>
>Em seus resultados, as colunas `createTime` e `updateTime` os dados retornam em notação exponencial. Os carimbos de data/hora subjacentes são registrados na hora UNIX UTC. Atualmente, a planilha não pode retornar carimbos de data/hora em um formato legível.

Se sua atualização em massa retornar um erro ou falhar, consulte [Solução de problemas para ferramentas](../../reference/bulk-management-tools/bulk-troubleshooting.md)de gerenciamento em massa.
