---
description: Você pode enviar segmentos qualificados para o DFP por meio de uma integração do lado do cliente (navegador) ou de uma integração do lado do servidor. Se você escolher a integração do cliente, deverá criar um destino baseado em cookies para as Tags do Google Publisher no Audience Manager.
seo-description: Você pode enviar segmentos qualificados para o DFP por meio de uma integração do lado do cliente (navegador) ou de uma integração do lado do servidor. Se você escolher a integração do cliente, deverá criar um destino baseado em cookies para as Tags do Google Publisher no Audience Manager.
seo-title: Criar um destino GPT
solution: Audience Manager
title: Criar um destino GPT
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 1%

---


# Criar um destino GPT {#create-a-gpt-destination}

Você pode enviar segmentos qualificados para [!DNL DFP] o cliente por meio de uma integração do lado do cliente (navegador) ou de uma integração do lado do servidor. Se você escolher a integração do lado do cliente, deverá criar um destino baseado em cookies para o [!DNL Google Publisher Tags] Audience Manager.

## Destinos 

No Audience Manager, um *`destination`* é qualquer outro sistema (servidor de anúncios, [!DNL DSP]rede de anúncios etc.) com os quais você deseja compartilhar dados. [!UICONTROL Destination Builder] fornece as ferramentas que permitem criar e gerenciar esses processos de delivery de dados. Os recursos de destino do Audience Manager estão localizados em *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Para começar, clique **[!UICONTROL Add New Destination]**e siga as etapas abaixo.

## Informações básicas

Para concluir a [!UICONTROL Basic Information] seção:

1. Nomeie o destino.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Clique **[!UICONTROL Next]** e vá para as seções [!UICONTROL Configuration] e [!UICONTROL Segment Mappings] .

## Configuração do cookie

Forneça o seguinte para concluir a [!UICONTROL Configuration] seção (outros campos são opcionais):

1. **Nome do cookie:** Forneça um nome curto e descritivo para seu cookie.
1. **Formato de dados:** Selecione a **[!UICONTROL "Single Key"]** opção.
1. **Chave:** Forneça um nome de chave.
1. **Serializar:** Marque a **[!UICONTROL Enable]** caixa de seleção.
1. **Delimitador serial:** Use apenas vírgula.

## Mapeamentos de segmentos

Para adicionar um segmento a um destino de cookie:

1. Localizar segmentos: A [!UICONTROL Segment Mappings] seção fornece duas ferramentas de pesquisa para ajudar a localizar segmentos. Para localizar um segmento:

   * Opção 1: Start que digita um nome de segmento no campo de pesquisa. O campo é atualizado automaticamente com base no texto inserido. Clique **[!UICONTROL Add]** quando encontrar o segmento que deseja usar.
   * Opção 2: Clique **[!UICONTROL Browse All Segments]** para abrir uma janela que permite procurar segmentos por nome ou local do armazenamento. Clique **[!UICONTROL Add Selected Segments]** quando concluído.

1. **Adicionar mapeamentos:** No pop-up de mapeamentos, insira a ID do segmento no campo de mapeamentos e clique em **[!UICONTROL Save]**.

1. Clique em **[!UICONTROL Done]**.