---
description: Uma solicitação em massa retorna dados que você pode usar com os diferentes cabeçalhos nas planilhas Atualizar, Criar, Estimar e Excluir.
seo-description: Uma solicitação em massa retorna dados que você pode usar com os diferentes cabeçalhos nas planilhas Atualizar, Criar, Estimar e Excluir.
seo-title: Solicitações em massa
solution: Audience Manager
title: Solicitações em massa
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Solicitações em massa{#bulk-requests}

Uma solicitação em massa retorna dados que você pode usar com os diferentes cabeçalhos nas planilhas Atualizar, Criar, Estimar e Excluir.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>Os [!UICONTROL Bulk Management Tools] não *são suportados por* [!DNL Audience Manager]. Esta ferramenta é fornecida apenas para conveniência e cortesia. Para alterações em massa, recomendamos que você trabalhe com as APIs [do](../../api/rest-api-main/aam-api-getting-started.md) Audience Manager. [As permissões](../../features/administration/administration-overview.md) de grupo RBAC atribuídas na [!DNL Audience Manager] interface do usuário são respeitadas na [!UICONTROL Bulk Management Tools].

A [!UICONTROL Request] planilha não tem seu próprio conjunto de cabeçalhos de coluna e você não precisa copiar IDs para nenhuma das colunas. Em vez disso, retorna dados com base no botão de ação que você clica na barra de ferramentas. Além disso, um recurso de relatório opcional retorna uma contagem de frequência para incêndios de pixels e contagem de usuários única para vários intervalos de tempo fixos.

Para fazer solicitações em massa, abra a [!UICONTROL Bulk Management Tools] planilha e:

1. Click the **[!UICONTROL Request]** tab.
2. Na barra de ferramentas na parte superior da planilha, clique em um botão de solicitação correspondente aos dados com os quais você deseja trabalhar. Você pode solicitar:

   * IDs do provedor de dados
   * Sinais derivados
   * Mapeamentos de destino
   * Características baseadas em regras e a bordo
   * Segmentos
   * IDs de pasta de características e segmentos
   A [!DNL Audience Manager] API grava dados em massa de volta à [!UICONTROL Request] planilha.

>[!NOTE]
>
>Em seus resultados, as colunas `createTime` e `updateTime` os dados retornam em notação exponencial. Os carimbos de data/hora subjacentes são registrados na hora UNIX UTC. Atualmente, a planilha não pode retornar carimbos de data/hora em um formato legível.

Se sua atualização em massa retornar um erro ou falhar, consulte [Solução de problemas para ferramentas](../../reference/bulk-management-tools/bulk-troubleshooting.md)de gerenciamento em massa.
