---
description: Rótulos de exportação de dados funcionam com os Controles de exportação definidos em uma fonte de dados. Rótulos de exportação de dados impedem que você adicione características restritas a um segmento e envie dados de segmento para um destino. Você pode definir vários rótulos de exportação para um cookie ou destino de URL novo ou existente.
seo-description: Rótulos de exportação de dados funcionam com os Controles de exportação definidos em uma fonte de dados. Rótulos de exportação de dados impedem que você adicione características restritas a um segmento e envie dados de segmento para um destino. Você pode definir vários rótulos de exportação para um cookie ou destino de URL novo ou existente.
seo-title: Adicionar ou editar segmentos para destinos de servidor para servidor
solution: Audience Manager
title: Adicionar ou editar segmentos para destinos de servidor para servidor
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 8%

---


# Adicionar ou editar segmentos para destinos de servidor para servidor {#add-edit-segments}

Você só pode adicionar ou editar segmentos para um destino de servidor para servidor ([!DNL S2S]). Não é possível criar [!DNL S2S] destinos com o [!UICONTROL [Destination Builder](/help/using/features/destinations/destination-builder.md)]. Entre em contato com seu consultor para configurar [!DNL S2S] destinos. Siga estas instruções para adicionar ou editar segmentos para um [!DNL S2S] destino.

<!-- destination-s2s-edit.xml -->

Para adicionar ou editar mapeamentos de segmentos para um [!DNL S2S] destino:

1. Vá para **[!UICONTROL Audience Data > Destinations]**. Selecione Plataformas **integradas > Baseadas** em dispositivo e localize o [!DNL S2S] destino com o qual você deseja trabalhar.
2. Na [!UICONTROL Action] coluna, clique no ícone de lápis para editar o destino.
   * Na **[!UICONTROL Search and Add Segments]** caixa, start que digita o nome de um segmento ou clique em **[!UICONTROL Browse All Segments]** navegar em uma lista de segmentos disponíveis.
   * Clique **[!UICONTROL Add Selected Segments]** quando encontrar o segmento que deseja usar. Adicionar um segmento abre a [!UICONTROL Edit Mapping] janela.
   * Em [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Defina um valor para o par [de valor-](../../features/destinations/key-value-pairs.md) chave usado por este destino.
      * **[!UICONTROL Start Date]** e **[!UICONTROL End Date]**: Escolha um start e uma data de término para o destino. Se a data final estiver em branco, o destino nunca expirará.
3. Clique em **[!UICONTROL Save]** e em **[!UICONTROL Done]**.