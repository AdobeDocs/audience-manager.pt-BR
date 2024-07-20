---
description: Rótulos de exportação de dados funcionam com os Controles de exportação que você define em uma fonte de dados. Os rótulos de exportação de dados impedem que você adicione características restritas a um segmento e envie dados de segmento para um destino. É possível definir vários rótulos de exportação para um cookie novo ou existente ou um destino de URL.
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add or Edit Segments for Server-to-Server Destinations
solution: Audience Manager
title: Adicionar ou editar segmentos para destinos de servidor para servidor
feature: Destination Basics
exl-id: 20124779-e14b-4d17-be4b-9f17ee0dc19e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---

# Adicionar ou editar segmentos para destinos de servidor para servidor {#add-edit-segments}

Você só pode adicionar ou editar segmentos para um destino de servidor para servidor ([!DNL S2S]). Você não pode criar [!DNL S2S] destinos com [[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md). Contate seu consultor para configurar os destinos do [!DNL S2S]. Siga estas instruções para adicionar ou editar segmentos para um destino [!DNL S2S].

<!-- destination-s2s-edit.xml -->

Para adicionar ou editar mapeamentos de segmentos para um destino [!DNL S2S]:

1. Ir para **[!UICONTROL Audience Data > Destinations]**. Selecione **Plataformas Integradas > Baseadas em Dispositivo** e localize o destino [!DNL S2S] com o qual você deseja trabalhar.
2. Na coluna [!UICONTROL Action], clique no ícone de lápis para editar o destino.
   * Na caixa **[!UICONTROL Search and Add Segments]**, comece digitando o nome de um segmento ou clique em **[!UICONTROL Browse All Segments]** para procurar uma lista de segmentos disponíveis.
   * Clique em **[!UICONTROL Add Selected Segments]** quando encontrar o segmento que deseja usar. Adicionar um segmento abre a janela [!UICONTROL Edit Mapping].
   * Em [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Defina um valor para o [par de valores-chave](../../features/destinations/key-value-pairs.md) usado por este destino.
      * **[!UICONTROL Start Date]** e **[!UICONTROL End Date]**: escolha uma data de início e término para o destino. Se a data final estiver em branco, o destino nunca expirará.
3. Clique em **[!UICONTROL Save]** e em **[!UICONTROL Done]**.
