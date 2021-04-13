---
description: Você pode enviar segmentos qualificados para o Google Ad Manager por meio de uma integração do lado do cliente (do lado do navegador) ou de uma integração do lado do servidor. Se você escolher a integração no lado do cliente, deve criar um destino baseado em cookies para as Tags do Google Publisher no Audience Manager.
seo-description: Você pode enviar segmentos qualificados para o Google Ad Manager por meio de uma integração do lado do cliente (do lado do navegador) ou de uma integração do lado do servidor. Se você escolher a integração no lado do cliente, deve criar um destino baseado em cookies para as Tags do Google Publisher no Audience Manager.
seo-title: Criar um destino com GPT
solution: Audience Manager
title: Criar um destino com GPT
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Integração de terceiros
exl-id: 26373826-de06-49e5-82fd-bb6588a73fb9
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 7%

---

# Criar um destino com GPT {#create-a-gpt-destination}

Você pode enviar segmentos qualificados para [!DNL Google Ad Manager] por meio de uma integração do lado do cliente (do lado do navegador) ou de uma integração do lado do servidor. Se você escolher a integração do lado do cliente, deverá criar um destino baseado em cookies para [!DNL Google Publisher Tags] no Audience Manager.

## Destinos 

No Audience Manager, um *`destination`* é qualquer outro sistema (servidor de anúncios, [!DNL DSP], rede de anúncios etc.) com o qual você deseja compartilhar dados. [!UICONTROL Destination Builder] O fornece as ferramentas que permitem criar e gerenciar esses processos de entrega de dados. Os recursos de destino do Audience Manager estão localizados em *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Para começar, clique em **[!UICONTROL Add New Destination]** e siga as etapas abaixo.

## Informações básicas

Para concluir a seção [!UICONTROL Basic Information]:

1. Nomeie o destino.
1. Selecione **[!UICONTROL "Cookie"]** na lista suspensa [!UICONTROL Type].
1. Clique em **[!UICONTROL Next]** e vá para as seções [!UICONTROL Configuration] e [!UICONTROL Segment Mappings].

## Configuração de cookie

Forneça o seguinte para concluir a seção [!UICONTROL Configuration] (outros campos são opcionais):

1. **Nome do cookie:** forneça um nome curto e descritivo para o cookie.
1. **Formato de dados:** Selecione a  **[!UICONTROL "Single Key"]** opção.
1. **Chave:** forneça um nome de chave.
1. **Serializar:** marque a  **[!UICONTROL Enable]** caixa de seleção.
1. **Delimitador em série:** use apenas vírgula.

## Mapeamentos de segmento

Para adicionar um segmento a um destino de cookie:

1. Localizar segmentos: A seção [!UICONTROL Segment Mappings] fornece duas ferramentas de pesquisa para ajudar a localizar segmentos. Para localizar um segmento:

   * Opção 1: Comece digitando um nome de segmento no campo de pesquisa. O campo é atualizado automaticamente com base no texto inserido. Clique em **[!UICONTROL Add]** depois de encontrar o segmento que deseja usar.
   * Opção 2: Clique em **[!UICONTROL Browse All Segments]** para abrir uma janela que permite procurar segmentos por nome ou local de armazenamento. Clique em **[!UICONTROL Add Selected Segments]** quando terminar.

1. **Adicionar mapeamentos:** no pop-up mapeamentos, insira a ID do segmento no campo mapeamentos e clique em  **[!UICONTROL Save]**.

1. Clique em **[!UICONTROL Done]**.
