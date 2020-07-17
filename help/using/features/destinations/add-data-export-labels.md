---
description: Rótulos de exportação de dados funcionam com os Controles de exportação definidos em uma fonte de dados. Rótulos de exportação de dados impedem que você adicione características restritas a um segmento e envie dados de segmento para um destino. Você pode definir vários rótulos de exportação para um cookie ou destino de URL novo ou existente.
seo-description: Rótulos de exportação de dados funcionam com os Controles de exportação definidos em uma fonte de dados. Rótulos de exportação de dados impedem que você adicione características restritas a um segmento e envie dados de segmento para um destino. Você pode definir vários rótulos de exportação para um cookie ou destino de URL novo ou existente.
seo-title: Adicionar controles de exportação de dados a um destino
solution: Audience Manager
title: Adicionar controles de exportação de dados a um destino
feature: Data Export Controls
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 7%

---



# Add Data Export Labels to a Destination {#add-data-export-labels}

[!DNL Data Export Labels] trabalhe com a fonte de dados [!DNL Export Controls] definida. [!DNL Data Export Labels] impedir que você adicione características restritas a um segmento e envie dados de segmento para um destino. É possível definir vários rótulos de exportação para um destino novo ou existente [!DNL cookie] ou [!DNL URL] .

>[!NOTE]
>
>Para adicionar um rótulo de exportação, você precisa de permissões de administrador *ou* privilégios suficientes para criar ou editar um destino.

<!-- t_export_labels.xml -->

Para adicionar rótulos de exportação a um destino:

1. Clique em **[!UICONTROL Audience Data]**:
   * Para novos destinos: Clique em **[!UICONTROL Create New Destination]**. Preencha a [!UICONTROL Basic Information] seção antes de selecionar um rótulo de exportação de dados. Consulte [Criar um destino](../../features/destinations/create-cookie-destination.md) de cookie ou [Criar um destino](../../features/destinations/create-url-destination.md) de URL para obter informações.
   * Para destinos existentes: Use a [!DNL Search] caixa para localizar o destino ou percorra a lista e clique no nome de destino para abri-la.
1. Selecione um [!DNL Data Export Label]. Deixe as caixas de seleção em branco se não quiser definir restrições de exportação. Os rótulos de exportação incluem as seguintes opções:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**

   >[!IMPORTANT]
   >
   >As restrições de exportação não funcionarão a menos que você defina um controle [de exportação](../../features/data-export-controls.md) correspondente em uma fonte de dados.
1. Clique em **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Criar uma fonte de dados](../../features/manage-datasources.md#create-data-source)