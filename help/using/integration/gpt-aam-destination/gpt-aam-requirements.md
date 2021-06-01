---
description: Você pode enviar segmentos qualificados para o Google Ad Manager por meio de uma integração do lado do cliente ou do lado do servidor. Os requisitos e informações relacionadas sobre ambos os métodos estão listados abaixo.
seo-description: Você pode enviar segmentos qualificados para o Google Ad Manager por meio de uma integração do lado do cliente ou do lado do servidor. Os requisitos e informações relacionadas sobre ambos os métodos estão listados abaixo.
seo-title: Requisitos e métodos de envio de segmentos para o Google Ad Manager usando Google Publisher Tags (GPT)
solution: Audience Manager
title: Requisitos e métodos de envio de segmentos para o Google Ad Manager usando Google Publisher Tags (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Integração de terceiros
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# Requisitos e métodos de envio de segmentos para o Google Ad Manager usando Google Publisher Tags (GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Você pode enviar segmentos qualificados para [!DNL Google Ad Manager] (antigo DFP) por meio de uma integração do lado do cliente ou por meio de uma integração do lado do servidor. Os requisitos e informações relacionadas sobre ambos os métodos estão listados abaixo.

## Integração do lado do cliente {#client-side-integration}

Para uma integração do lado do cliente, você precisa configurar um destino [!DNL GPT] no Audience Manager. Considere os seguintes pontos quando deseja configurar [!DNL GPT] como um destino de Audience Manager:

* **Adicionar  [!UICONTROL DIL]:** implante o  [!UICONTROL Data Integration Library (DIL)] código em todas as páginas que deseja direcionar. [!UICONTROL DIL] grava dados de segmento do Audience Manager e IDs de usuário em cookies que são usados pelo  [!DNL GPT] para direcionamento.

* **Criar um  [!UICONTROL Cookie Destination]:** [!DNL GPT] deve ser configurado como um destino baseado em cookies no Audience Manager.

* **Implemente o código de verificação de cookie:** Encapsule o método da  [!DNL GPT] `.setTargeting` API em nosso código de verificação de  [cookie recomendado](../../integration/gpt-aam-destination/gpt-aam-modify-api.md). Este código ajuda a evitar erros, procurando cookies de AAM válidos antes de o método `.setTargeting` ser chamado.

* **Adicionar a  `AamGpt` função:** o  `AamGpt` código captura dados de cookies do Audience Manager e os envia para o  [!DNL GPT]. Coloque o [Audience Manager Code for Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) na parte superior da página ou dentro do bloco de código `<head>`.

   >[!NOTE]
   >
   >A função `AamGpt` não é necessária se você usar seu próprio código para ler dados de cookie de Audience Manager.

* **Enviar logs de delivery para o Audience Manager:** se quiser um relatório de delivery de segmento (opcional), forneça ao Audience Manager um log diário que contenha dados de delivery de nível de impressão. Os dados podem estar em um formato bruto, mas cada registro deve conter o Audience Manager `UUID`. O Audience Manager pode coletá-los ou recebê-los via [!DNL FTP].

### Somente os segmentos qualificados são enviados para GPT

A quantidade de dados transmitidos para [!DNL GPT] depende de quantos segmentos um usuário específico se qualifica. Por exemplo, digamos que você tenha configurado 100 segmentos de Audience Manager. Se um visitante do site se qualificar para cinco deles, então apenas esses cinco segmentos serão enviados para [!DNL GPT] (não todos os 100).

>[!NOTE]
>
>Não há limites para o número de valores-chave que você pode enviar, mas a solicitação [!DNL Google] [!DNL URL] tem limites para o número de caracteres que pode aceitar. Consulte [Definir o direcionamento e os tamanhos com GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712).

## Integração do lado do servidor {#server-side-integration}

Fale com seu consultor do Audience Manager ou com o Atendimento ao cliente se desejar configurar uma integração do lado do servidor com [!DNL Google Ad Manager], usando [!DNL GPT]. Você precisará fornecer sua [!DNL Google Ad Manager] ID de rede da conta e ID do link de público-alvo.

>[!IMPORTANT]
>
>Se as páginas da Web estiverem executando a biblioteca [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]), você deverá usar a integração do lado do servidor com o Audience Manager. Se você estiver em [!DNL AMP] e tiver uma integração do lado do cliente com [!DNL AMP], migre para a integração do lado do servidor. Entre em contato com o consultor do Audience Manager ou com o Atendimento ao cliente para discutir a migração.

>[!MORELIKETHIS]
>
>* [Guia de referência da API GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

