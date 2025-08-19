---
description: Rótulos de exportação de dados funcionam com os Controles de exportação que você define em uma fonte de dados. Os rótulos de exportação de dados impedem que você adicione características restritas a um segmento e envie dados de segmento para um destino. É possível definir vários rótulos de exportação para um cookie novo ou existente ou um destino de URL.
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add Data Export Controls to a Destination
solution: Audience Manager
title: Adicionar controles de exportação de dados a um destino
feature: Data Export Controls
exl-id: 12cfd2cc-b343-4dd1-a188-acbfc5cd25a2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 2%

---

# Adicionar rótulos de exportação de dados a um destino {#add-data-export-labels}

[!DNL Data Export Labels] trabalhe com o [!DNL Export Controls] que você definiu em uma fonte de dados. [!DNL Data Export Labels] impede que você adicione características restritas a um segmento e envie dados de segmento para um destino. Você pode definir vários rótulos de exportação para um destino [!DNL cookie] ou [!DNL URL] novo ou existente.

>[!NOTE]
>
>Para adicionar um rótulo de exportação, você precisa de permissões de administrador *ou* privilégios suficientes para criar ou editar um destino.

<!-- t_export_labels.xml -->

Para adicionar rótulos de exportação a um destino:

1. Clique em **[!UICONTROL Audience Data]**:
   * Para novos destinos: Clique em **[!UICONTROL Create New Destination]**. Conclua a seção [!UICONTROL Basic Information] antes de selecionar um rótulo de exportação de dados. Consulte [Criar um Destino de Cookie](../../features/destinations/create-cookie-destination.md) ou [Criar um Destino de URL](../../features/destinations/create-url-destination.md) para obter informações.
   * Para destinos existentes: Use a caixa [!DNL Search] para encontrar seu destino ou percorrer a lista e clique no nome do destino para abri-lo.
1. Selecione um [!DNL Data Export Label]. Deixe as caixas de seleção em branco se não quiser definir restrições de exportação. Os rótulos de exportação incluem as seguintes opções:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Restrições de exportação não funcionarão a menos que você defina um [controle de exportação correspondente](../../features/data-export-controls.md) em uma fonte de dados.
1. Clique em **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Criar uma fonte de dados](../../features/manage-datasources.md#create-data-source)
