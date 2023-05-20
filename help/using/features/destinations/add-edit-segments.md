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
ht-degree: 7%

---

# Adicionar ou editar segmentos para destinos de servidor para servidor {#add-edit-segments}

Você só pode adicionar ou editar segmentos de um servidor para servidor ([!DNL S2S]) destino. Não é possível criar [!DNL S2S] destinos com [[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md). Entre em contato com seu consultor para configurar [!DNL S2S] destinos. Siga estas instruções para adicionar ou editar segmentos para um [!DNL S2S] destino.

<!-- destination-s2s-edit.xml -->

Para adicionar ou editar mapeamentos de segmentos para um [!DNL S2S] destino:

1. Ir para **[!UICONTROL Audience Data > Destinations]**. Selecionar **Plataformas integradas > Baseado em dispositivo** e localize o [!DNL S2S] destino com o qual você deseja trabalhar.
2. No [!UICONTROL Action] clique no ícone de lápis para editar o destino.
   * No **[!UICONTROL Search and Add Segments]** digite o nome de um segmento ou clique em **[!UICONTROL Browse All Segments]** procure uma lista de segmentos disponíveis.
   * Clique em **[!UICONTROL Add Selected Segments]** quando você encontra o segmento que deseja usar. A adição de um segmento abre a [!UICONTROL Edit Mapping] janela.
   * Em [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Defina um valor para a variável [par de valor-chave](../../features/destinations/key-value-pairs.md) usado por este destino.
      * **[!UICONTROL Start Date]** e **[!UICONTROL End Date]**: escolha uma data de início e término para o destino. Se a data final estiver em branco, o destino nunca expirará.
3. Clique em **[!UICONTROL Save]** e clique em **[!UICONTROL Done]**.
