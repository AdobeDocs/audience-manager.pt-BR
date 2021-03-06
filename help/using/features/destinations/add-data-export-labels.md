---
description: Os Rótulos de exportação de dados funcionam com os Controles de exportação definidos em uma fonte de dados. Os rótulos de exportação de dados impedem que você adicione características restritas a um segmento e envie dados de segmento para um destino. Você pode definir vários rótulos de exportação para um cookie ou destino de URL novo ou existente.
seo-description: Os Rótulos de exportação de dados funcionam com os Controles de exportação definidos em uma fonte de dados. Os rótulos de exportação de dados impedem que você adicione características restritas a um segmento e envie dados de segmento para um destino. Você pode definir vários rótulos de exportação para um cookie ou destino de URL novo ou existente.
seo-title: Adicionar controles de exportação de dados a um destino
solution: Audience Manager
title: Adicionar controles de exportação de dados a um destino
feature: Controles da exportação de dados
exl-id: 12cfd2cc-b343-4dd1-a188-acbfc5cd25a2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 8%

---

# Adicionar rótulos de exportação de dados a um destino {#add-data-export-labels}

[!DNL Data Export Labels] trabalhe com o  [!DNL Export Controls] que você definir em uma fonte de dados. [!DNL Data Export Labels] impedir que você adicione características restritas a um segmento e envie dados de segmento para um destino. Você pode definir vários rótulos de exportação para um destino novo ou existente [!DNL cookie] ou [!DNL URL].

>[!NOTE]
>
>Para adicionar um rótulo de exportação, você precisa de permissões de administrador *ou* privilégios suficientes para criar ou editar um destino.

<!-- t_export_labels.xml -->

Para adicionar rótulos de exportação a um destino:

1. Clique em **[!UICONTROL Audience Data]**:
   * Para novos destinos: Clique em **[!UICONTROL Create New Destination]**. Complete a seção [!UICONTROL Basic Information] antes de selecionar um rótulo de exportação de dados. Consulte [Criar um destino de cookie](../../features/destinations/create-cookie-destination.md) ou [Criar um destino de URL](../../features/destinations/create-url-destination.md) para obter informações.
   * Para destinos existentes: Use a caixa [!DNL Search] para localizar seu destino ou role pela lista e clique no nome do destino para abri-lo.
1. Selecione um [!DNL Data Export Label]. Deixe as caixas de seleção em branco caso não deseje definir restrições de exportação. Os rótulos de exportação incluem as seguintes opções:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**

   >[!IMPORTANT]
   >
   >As restrições de exportação não funcionarão a menos que você defina um [controle de exportação correspondente](../../features/data-export-controls.md) em uma fonte de dados.
1. Clique em **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Criar uma fonte de dados](../../features/manage-datasources.md#create-data-source)

