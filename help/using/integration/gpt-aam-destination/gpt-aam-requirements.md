---
description: Você pode enviar segmentos qualificados para o Google Ad Manager por meio de uma integração do lado do cliente ou do lado do servidor. Os requisitos e as informações relacionadas sobre os dois métodos estão listados abaixo.
seo-description: You can send qualified segments to Google Ad Manager either through a client-side or through a server-side integration. Requirements and related information about both methods are listed below.
seo-title: Requirements and Methods of Sending Segments to Google Ad Manager Using Google Publisher Tags (GPT)
solution: Audience Manager
title: Requisitos e métodos de envio de segmentos para o Google Ad Manager usando as Tags do Google Publisher (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third-party Integration
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Requisitos e métodos de envio de segmentos para o Google Ad Manager usando tags do Google Publisher ( GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Você pode enviar segmentos qualificados para o [!DNL Google Ad Manager] (antigo DFP) por meio de uma integração do cliente ou do servidor. Os requisitos e as informações relacionadas sobre os dois métodos estão listados abaixo.

## Integração do cliente {#client-side-integration}

Para uma integração no lado do cliente, é necessário configurar um destino [!DNL GPT] no Audience Manager. Considere os seguintes pontos quando quiser configurar [!DNL GPT] como um destino do Audience Manager:

* **Adicionar [!UICONTROL DIL]:** Implante o código [!UICONTROL Data Integration Library (DIL)] em todas as páginas que deseja direcionar. [!UICONTROL DIL] grava dados de segmento e IDs de usuário do Audience Manager em cookies que são usados por [!DNL GPT] para direcionamento.

* **Criar um [!UICONTROL Cookie Destination]:** [!DNL GPT] deve ser configurado como um destino baseado em cookie no Audience Manager.

* **Implementar código de verificação de cookie:** Adicione o método de API [!DNL GPT] `.setTargeting` ao nosso [código de verificação de cookie](../../integration/gpt-aam-destination/gpt-aam-modify-api.md) recomendado. Este código ajuda a evitar erros procurando cookies válidos do AAM antes que o método `.setTargeting` seja chamado.

* **Adicionar a Função `AamGpt`:** o código `AamGpt` captura dados de cookies do Audience Manager e os envia para [!DNL GPT]. Coloque o [Código Audience Manager das Tags do Google Publisher](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) na parte superior da página ou dentro do bloco de código `<head>`.

  >[!NOTE]
  >
  >A função `AamGpt` não é necessária se você usar seu próprio código para ler dados de cookies do Audience Manager.

* **Enviar logs de entrega para o Audience Manager:** Se desejar um relatório de entrega de segmento (opcional), forneça à Audience Manager um log diário que contenha dados de entrega no nível de impressão. Os dados podem estar em um formato bruto, mas cada registro deve conter o Audience Manager `UUID`. A Audience Manager pode recebê-los via [!DNL FTP].

### Somente os segmentos qualificados são enviados para GPT

A quantidade de dados passada para [!DNL GPT] depende de quantos segmentos um usuário específico se qualifica. Por exemplo, digamos que você configure 100 segmentos do Audience Manager. Se um visitante do site se qualificar para cinco deles, então apenas esses cinco segmentos serão enviados para [!DNL GPT] (não todos os 100).

>[!NOTE]
>
>Não há limites para o número de valores-chave que você pode enviar, mas a solicitação [!DNL Google] [!DNL URL] tem limites para o número de caracteres que ela pode aceitar. Consulte [Definição de direcionamento e tamanhos com GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712).

## Integração do lado do servidor {#server-side-integration}

Entre em contato com o consultor da Audience Manager ou com o Atendimento ao cliente se quiser configurar uma integração do lado do servidor com o [!DNL Google Ad Manager], usando o [!DNL GPT]. Você precisará fornecer a ID de rede e a ID de link de público-alvo da sua conta do [!DNL Google Ad Manager].

>[!IMPORTANT]
>
>Se suas páginas da Web estiverem executando a biblioteca [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]), você deverá usar a integração do lado do servidor com o Audience Manager. Se você estiver no [!DNL AMP] e tiver uma integração do lado do cliente com o [!DNL AMP], deverá migrar para a integração do lado do servidor. Entre em contato com seu consultor da Audience Manager ou com o Atendimento ao cliente para discutir a migração.

>[!MORELIKETHIS]
>
>* [Guia de Referência de API GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)
