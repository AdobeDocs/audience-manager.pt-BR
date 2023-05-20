---
description: Você pode enviar segmentos qualificados para o Google Ad Manager por meio de uma integração do lado do cliente (lado do navegador) ou uma integração do lado do servidor. Se você escolher a integração do lado do cliente, deverá criar um destino baseado em cookies para as Tags do Google Publisher no Audience Manager.
seo-description: You can send qualified segments to Google Ad Manager through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for Google Publisher Tags in Audience Manager.
seo-title: Create a GPT Destination
solution: Audience Manager
title: Criar um destino com GPT
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third-party Integration
exl-id: 26373826-de06-49e5-82fd-bb6588a73fb9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 6%

---

# Criar um destino com GPT {#create-a-gpt-destination}

Você pode enviar segmentos qualificados para o [!DNL Google Ad Manager] por meio de uma integração do lado do cliente (lado do navegador) ou do lado do servidor. Se você escolher a integração do lado do cliente, deverá criar um destino baseado em cookies para [!DNL Google Publisher Tags] em Audience Manager.

## Destinos 

No Audience Manager, um *`destination`* é qualquer outro sistema (servidor de anúncios, [!DNL DSP], rede de anúncios etc.) com o qual você deseja compartilhar dados. [!UICONTROL Destination Builder] O fornece as ferramentas que permitem criar e gerenciar esses processos de delivery de dados. Os recursos de destino do Audience Manager estão localizados em *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Para começar, clique em **[!UICONTROL Add New Destination]** e siga as etapas abaixo.

## Informações básicas

Para concluir o [!UICONTROL Basic Information] seção:

1. Nomeie o destino.
1. Selecionar **[!UICONTROL "Cookie"]** do [!UICONTROL Type] lista suspensa.
1. Clique em **[!UICONTROL Next]** e vá para a página [!UICONTROL Configuration] e [!UICONTROL Segment Mappings] seções.

## Configuração de cookie

Forneça o seguinte para concluir a [!UICONTROL Configuration] seção (outros campos são opcionais):

1. **Nome do cookie:** Forneça um nome curto e descritivo para o cookie.
1. **Formato de dados:** Selecione o **[!UICONTROL "Single Key"]** opção.
1. **Chave:** Forneça um nome de chave.
1. **Serializar:** Selecione o **[!UICONTROL Enable]** caixa de seleção
1. **Delimitador de série:** Use somente vírgula.

## Mapeamentos de segmentos

Para adicionar um segmento a um destino de cookie:

1. Localizar segmentos: a [!UICONTROL Segment Mappings] A seção fornece duas ferramentas de pesquisa para ajudar a localizar segmentos. Para localizar um segmento:

   * Opção 1: comece digitando um nome de segmento no campo de pesquisa. O campo é atualizado automaticamente com base no texto inserido. Clique em **[!UICONTROL Add]** depois de encontrar o segmento que deseja usar.
   * Opção 2: clique em **[!UICONTROL Browse All Segments]** para abrir uma janela que permite procurar segmentos por nome ou local de armazenamento. Clique em **[!UICONTROL Add Selected Segments]** quando terminar.

1. **Adicionar Mapeamentos:** No pop de mapeamentos, insira a ID do segmento no campo mapeamentos e clique em **[!UICONTROL Save]**.

1. Clique em **[!UICONTROL Done]**.
