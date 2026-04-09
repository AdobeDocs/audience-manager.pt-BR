---
description: Uma solicitação em massa retorna dados que você pode usar com os diferentes cabeçalhos nas planilhas Atualizar, Criar, Estimar e Excluir.
seo-description: A bulk request returns data you can use with the different headers in the Update, Create, Estimate, and Delete worksheets.
seo-title: Bulk Requests
solution: Audience Manager
title: Solicitações em massa
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
TQID: https://experienceleague.adobe.com/9VACsTAdf5nqwXAeQCqA7ME7M1sTOwt-eW-fyVdE-Ag
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2:
  - id: a49258d4-867f-4130-b875-d72c001bdf6c
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 253
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
