---
description: Os Rótulos de exportação de dados funcionam com os Controles de exportação definidos em uma fonte de dados. Os rótulos de exportação de dados impedem que você adicione características restritas a um segmento e envie dados de segmento para um destino. Você pode definir vários rótulos de exportação para um cookie ou destino de URL novo ou existente.
seo-description: Os Rótulos de exportação de dados funcionam com os Controles de exportação definidos em uma fonte de dados. Os rótulos de exportação de dados impedem que você adicione características restritas a um segmento e envie dados de segmento para um destino. Você pode definir vários rótulos de exportação para um cookie ou destino de URL novo ou existente.
seo-title: Adicionar ou editar segmentos para destinos de servidor para servidor
solution: Audience Manager
title: Adicionar ou editar segmentos para destinos de servidor para servidor
feature: Noções básicas sobre o destino
exl-id: 20124779-e14b-4d17-be4b-9f17ee0dc19e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 8%

---

# Adicionar ou editar segmentos para destinos de servidor para servidor {#add-edit-segments}

Você só pode adicionar ou editar segmentos para um destino de servidor para servidor ([!DNL S2S]). Não é possível criar destinos [!DNL S2S] com [[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md). Entre em contato com seu consultor para configurar destinos [!DNL S2S]. Siga estas instruções para adicionar ou editar segmentos para um destino [!DNL S2S].

<!-- destination-s2s-edit.xml -->

Para adicionar ou editar mapeamentos de segmento para um destino [!DNL S2S]:

1. Vá para **[!UICONTROL Audience Data > Destinations]**. Selecione **Integrated Platforms > Device-Based** e localize o destino [!DNL S2S] com o qual deseja trabalhar.
2. Na coluna [!UICONTROL Action], clique no ícone de lápis para editar o destino.
   * Na caixa **[!UICONTROL Search and Add Segments]**, comece a digitar o nome de um segmento ou clique em **[!UICONTROL Browse All Segments]** para navegar em uma lista de segmentos disponíveis.
   * Clique em **[!UICONTROL Add Selected Segments]** quando encontrar o segmento que deseja usar. Adicionar um segmento abre a janela [!UICONTROL Edit Mapping].
   * Em [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Defina um valor para o par de valores  [chave ](../../features/destinations/key-value-pairs.md) usado por esse destino.
      * **[!UICONTROL Start Date]** e  **[!UICONTROL End Date]**: Escolha uma data inicial e final para o destino. Se a data final estiver em branco, o destino nunca expirará.
3. Clique em **[!UICONTROL Save]** e depois em **[!UICONTROL Done]**.
