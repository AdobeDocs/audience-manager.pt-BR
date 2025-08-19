---
description: Uma solicitação em massa retorna dados que você pode usar com os diferentes cabeçalhos nas planilhas Atualizar, Criar, Estimar e Excluir.
seo-description: A bulk request returns data you can use with the different headers in the Update, Create, Estimate, and Delete worksheets.
seo-title: Bulk Requests
solution: Audience Manager
title: Solicitações em massa
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# Solicitações em massa{#bulk-requests}

Uma solicitação em massa retorna dados que você pode usar com os diferentes cabeçalhos nas planilhas Atualizar, Criar, Estimar e Excluir.

>[!IMPORTANT]
>
>As Ferramentas de gerenciamento em massa não são uma oferta oficialmente compatível com o Adobe. A solução de problemas e o suporte por meio do Atendimento ao cliente serão tratados caso a caso.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>As [permissões do grupo RBAC](../../features/administration/administration-overview.md) atribuídas na interface do usuário [!DNL Audience Manager] são honradas no [!UICONTROL Bulk Management Tools].

A planilha [!UICONTROL Request] não tem seu próprio conjunto de cabeçalhos de coluna e você não precisa copiar IDs para nenhuma das colunas. Em vez disso, ele retorna dados com base no botão de ação clicado na barra de ferramentas. E um recurso de relatório opcional retorna uma contagem de frequência para disparos de pixels e uma contagem de usuários exclusiva para vários intervalos de tempo fixos.

Para fazer solicitações em massa, abra a planilha [!UICONTROL Bulk Management Tools] e:

1. Clique na guia **[!UICONTROL Request]**.
2. Na barra de ferramentas na parte superior da planilha, clique em um botão de solicitação correspondente aos dados com os quais você deseja trabalhar. Você pode solicitar:

   * Modelos algorítmicos
   * Fontes de dados
   * Sinais derivados
   * Mapeamentos de destino
   * Características algorítmicas, baseadas em regras e integradas
   * Segmentos
   * IDs da pasta de características e segmentos

   A API [!DNL Audience Manager] grava dados em massa de volta na planilha [!UICONTROL Request].

>[!NOTE]
>
>Em seus resultados, as colunas `createTime` e `updateTime` retornam dados em notação exponencial. Os carimbos de data/hora subjacentes são registrados no horário UNIX UTC. Atualmente, a planilha não pode retornar carimbos de data/hora em um formato legível.

Se a atualização em massa retornar um erro ou falhar, consulte [Solução de problemas das Ferramentas de Gerenciamento em Massa](../../reference/bulk-management-tools/bulk-troubleshooting.md).
