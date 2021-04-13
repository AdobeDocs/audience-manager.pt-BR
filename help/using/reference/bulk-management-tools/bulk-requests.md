---
description: Uma solicitação em massa retorna dados que você pode usar com os diferentes cabeçalhos nas planilhas de Atualização, Criação, Estimativa e Exclusão.
seo-description: Uma solicitação em massa retorna dados que você pode usar com os diferentes cabeçalhos nas planilhas de Atualização, Criação, Estimativa e Exclusão.
seo-title: Solicitações em massa
solution: Audience Manager
title: Solicitações em massa
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 3%

---

# Solicitações em massa{#bulk-requests}

Uma solicitação em massa retorna dados que você pode usar com os diferentes cabeçalhos nas planilhas de Atualização, Criação, Estimativa e Exclusão.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[As ](../../features/administration/administration-overview.md) permissões do grupo RBAC atribuídas na  [!DNL Audience Manager] interface do usuário são honradas no  [!UICONTROL Bulk Management Tools].

A planilha [!UICONTROL Request] não tem seu próprio conjunto de cabeçalhos de coluna e você não precisa copiar IDs para nenhuma das colunas. Em vez disso, retorna dados com base no botão de ação que você clicou na barra de ferramentas. Além disso, um recurso opcional de relatório retorna uma contagem de frequência para incêndios de pixels e uma contagem de usuários exclusiva para vários intervalos de tempo fixos.

Para fazer solicitações em massa, abra a planilha [!UICONTROL Bulk Management Tools] e:

1. Clique na guia **[!UICONTROL Request]**.
2. Na barra de ferramentas, na parte superior da planilha, clique em um botão de solicitação correspondente aos dados com os quais deseja trabalhar. Você pode solicitar:

   * Modelos algorítmicos
   * Fontes de dados
   * Sinais derivados
   * Mapeamentos de destino
   * Características algorítmicas, baseadas em regras e integradas
   * Segmentos 
   * IDs de pasta de características e segmentos

   A API [!DNL Audience Manager] grava dados em massa de volta na planilha [!UICONTROL Request].

>[!NOTE]
>
>Nos resultados, as colunas `createTime` e `updateTime` retornam dados em notação exponencial. Os carimbos de data/hora subjacentes são registrados na hora UNIX UTC. Atualmente, a planilha não pode retornar carimbos de data/hora em um formato legível.

Se a atualização em massa retornar um erro ou falhar, consulte [Solução de problemas para Ferramentas de gerenciamento em massa](../../reference/bulk-management-tools/bulk-troubleshooting.md).
