---
description: Você pode enviar segmentos qualificados para DFP por meio de uma integração do lado do cliente (no navegador) ou uma integração do servidor. Se você escolher a integração do cliente, deverá criar um destino baseado em cookies para Tags do Google Publisher no Audience Manager.
seo-description: Você pode enviar segmentos qualificados para DFP por meio de uma integração do lado do cliente (no navegador) ou uma integração do servidor. Se você escolher a integração do cliente, deverá criar um destino baseado em cookies para Tags do Google Publisher no Audience Manager.
seo-title: Criar um destino GPT
solution: Audience Manager
title: Criar um destino GPT
uuid: e 3 bbf 327-a 7 e 0-48 da-bc 84-8 f 531 b 7 f 6750
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Create a GPT Destination {#create-a-gpt-destination}

You can send qualified segments to [!DNL DFP] through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for [!DNL Google Publisher Tags] in Audience Manager.

## Destinos

In Audience Manager, a *`destination`* is any other system (ad server, [!DNL DSP], ad network, etc.) que deseja compartilhar dados. [!UICONTROL Destination Builder] fornece as ferramentas que permitem criar e gerenciar esses processos de entrega de dados. Audience Manager destination features are located in *[!UICONTROL Audience Data] &gt; [!UICONTROL Destinations]*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

## Informações básicas

To complete the [!UICONTROL Basic Information] section:

1. Dê um nome ao destino.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Click **[!UICONTROL Next]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

## Configuração do cookie

Provide the following to complete the [!UICONTROL Configuration] section (other fields are optional):

1. **Nome do cookie:** Forneça um nome curto e descritivo para o seu cookie.
1. **Formato de dados:** Selecione a **[!UICONTROL "Single Key"]** opção.
1. **Chave:** Forneça um nome de chave.
1. **Serializar:** Marque a **[!UICONTROL Enable]** caixa de seleção.
1. **Delimitador de série:** Use apenas uma vírgula.

## Mapeamentos de segmento

Para adicionar um segmento a um destino de cookie:

1. Find segments: The [!UICONTROL Segment Mappings] section provides two search tools to help locate segments. Para encontrar um segmento:

   * Opção 1: Comece a digitar um nome de segmento no campo de pesquisa. O campo é atualizado automaticamente com base no texto inserido. Click **[!UICONTROL Add]** once you find the segment you want to use.
   * Option 2: Click **[!UICONTROL Browse All Segments]** to open a window that lets you browse for segments by name or storage location. Click **[!UICONTROL Add Selected Segments]** when done.

1. **Adicionar mapeamentos:** Nos pop-ups, insira a ID do segmento no campo de mapeamentos e clique **[!UICONTROL Save]** em.

1. Clique em **[!UICONTROL Done]**.