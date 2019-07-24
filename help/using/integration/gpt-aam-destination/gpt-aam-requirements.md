---
description: É possível enviar segmentos qualificados para DFP por meio de um cliente ou por meio de uma integração com o servidor. Os requisitos e informações relacionadas sobre os dois métodos estão listados abaixo.
seo-description: É possível enviar segmentos qualificados para DFP por meio de um cliente ou por meio de uma integração com o servidor. Os requisitos e informações relacionadas sobre os dois métodos estão listados abaixo.
seo-title: Requisitos e métodos de envio de segmentos para DFP usando Google Publisher Tags (GPT)
solution: Audience Manager
title: Requisitos e métodos de envio de segmentos para DFP usando Google Publisher Tags (GPT)
uuid: 4 b 2 ea 81 c -29 bb -42 d 3-9d d 3-1 d 8 e 677790 b 6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Requisitos e métodos de envio de segmentos para DFP usando Google Publisher Tags (GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

You can send qualified segments to [!DNL DFP] either through a client-side or through a server-side integration. Os requisitos e informações relacionadas sobre os dois métodos estão listados abaixo.

## Client-Side Integration {#client-side-integration}

For a client-side integration, you need to set up a [!DNL GPT] destination in Audience Manager. Consider the following points when you want to set up [!DNL GPT] as an Audience Manager destination:

* **Adicionar[!UICONTROL DIL]:** Implante [!UICONTROL Data Integration Library (DIL)] o código em todas as páginas que deseja definir como meta. [!UICONTROL DIL] grava os dados de segmento e as IDs do usuário do Audience Manager a cookies que são usados [!DNL GPT] para direcionamento.

* **Criar a[!UICONTROL Cookie Destination]:**[!DNL GPT] deve ser configurado como um destino baseado em cookies no Audience Manager.

* **Implementar código de verificação de cookies:** Encapsule o [!DNL GPT]`.setTargeting` método da API em nosso código de verificação de [cookie recomendado](../../integration/gpt-aam-destination/gpt-aam-modify-api.md). This code helps prevent errors by looking for valid AAM cookies before the `.setTargeting` method gets invoked.

* **Adicione`AamGpt`a função:** `AamGpt` O código captura dados dos cookies do Audience Manager e a envia [!DNL GPT]para. Place the [Audience Manager Code for Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) at the top of the page or inside the `<head>` code block.

   >[!NOTE]
   >
   >The `AamGpt` function is not required if you use your own code to read Audience Manager cookie data.

* **Enviar logs de entrega para o Audience Manager:** Se desejar um relatório de entrega de segmento (opcional), forneça ao Audience Manager um log diário que contenha dados de entrega de nível de impressão. The data can be in a raw format, but each record must contain the Audience Manager `UUID`. Audience Manager can pick up or receive these via [!DNL FTP].

### Somente os segmentos qualificados são enviados para GPT

The amount of data passed in to [!DNL GPT] depends on how many segments a particular user qualifies for. Por exemplo, digamos que você configure os segmentos Audience 00 do Audience Manager. If a site visitor qualifies for five of them, then only those five segments get sent to [!DNL GPT] (not all 100).

>[!NOTE]
>
>There are no limits to the number of key-values you can send, but the [!DNL Google] request [!DNL URL] does have limits to the number of characters it can accept. See [Setting targeting and sizes with GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712).

## Server-Side Integration {#server-side-integration}

Talk to your Audience Manager consultant or Customer Care if you want to set up a server-side integration with [!DNL DFP], using [!DNL GPT]. You'll need to provide your [!DNL DFP] account Network ID and Audience Link ID.

>[!IMPORTANT]
>
>If your web pages are running the [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]) library, you must use the server-side integration with Audience Manager. If you are on [!DNL AMP] and have a client-side integration with [!DNL AMP], you must migrate to the server-side integration. Entre em contato com o consultor do Audience Manager ou com o Atendimento ao cliente para discutir a migração.

>[!MORE_ LIKE_ THIS]
>
>* [Guia de referência de API de GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)

