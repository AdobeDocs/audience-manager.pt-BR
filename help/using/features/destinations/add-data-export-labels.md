---
description: Os Rótulos de exportação de dados funcionam com os Controles de exportação definidos em uma fonte de dados. Os rótulos de exportação de dados impedem que você adicione traços restritos a um segmento e envie dados de segmento para um destino. É possível definir vários rótulos de exportação para um cookie ou um destino de URL novo ou existente.
seo-description: Os Rótulos de exportação de dados funcionam com os Controles de exportação definidos em uma fonte de dados. Os rótulos de exportação de dados impedem que você adicione traços restritos a um segmento e envie dados de segmento para um destino. É possível definir vários rótulos de exportação para um cookie ou um destino de URL novo ou existente.
seo-title: Adicionar controles de exportação de dados para um destino
solution: Audience Manager
title: Adicionar controles de exportação de dados para um destino
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---



# Adicionar rótulos de exportação de dados a um destino {#add-data-export-labels}

[!DNL Data Export Labels] trabalhar com o [!DNL Export Controls] conjunto definido em uma fonte de dados. [!DNL Data Export Labels] impedir que você adicione traços restritos a um segmento e envie dados de segmento para um destino. É possível definir vários rótulos de exportação para um novo [!DNL cookie][!DNL URL] ou existente ou destino.

>[!NOTE]
>
>Para adicionar um rótulo de exportação, você precisa de permissões *de administrador ou* de privilégios suficientes para criar ou editar um destino.

<!-- t_export_labels.xml -->

Para adicionar rótulos de exportação a um destino:

1. Clique em **[!UICONTROL Audience Data]**:
   * Para novos destinos: Clique **[!UICONTROL Create New Destination]** em. Preencha a [!UICONTROL Basic Information] seção antes de selecionar um rótulo de exportação de dados. Consulte [Criar um destino de cookie](../../features/destinations/create-cookie-destination.md) ou [Criar um destino de URL](../../features/destinations/create-url-destination.md) para obter informações.
   * Para destinos existentes: Use [!DNL Search] a caixa para localizar o destino ou clique na lista e clique no nome de destino para abri-lo.
1. Selecione um [!DNL Data Export Label]. Deixe as caixas de seleção em branco se não quiser definir quaisquer restrições de exportação. Os rótulos de exportação incluem as seguintes opções:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >As restrições de exportação não funcionarão a menos que você defina um [controle de exportação correspondente](../../features/data-export-controls.md) em uma fonte de dados.
1. Clique em **[!UICONTROL Save]**.

>[!MORE_ LIKE_ THIS]
>
>* [Criar uma fonte de dados](../../features/manage-datasources.md#create-data-source)