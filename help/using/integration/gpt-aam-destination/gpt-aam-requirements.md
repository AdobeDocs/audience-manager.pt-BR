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
source-wordcount: '481'
ht-degree: 0%

---

# Requisitos e métodos de envio de segmentos para o Google Ad Manager usando tags do Google Publisher ( GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Você pode enviar segmentos qualificados para o [!DNL Google Ad Manager] (antigo DFP) por meio de uma integração do lado do cliente ou do lado do servidor. Os requisitos e as informações relacionadas sobre os dois métodos estão listados abaixo.

## Integração do cliente {#client-side-integration}

Para uma integração no lado do cliente, é necessário configurar uma [!DNL GPT] destino em Audience Manager. Considere os pontos a seguir quando quiser configurar [!DNL GPT] como destino Audience Manager:

* **Adicionar [!UICONTROL DIL]:** Implantar [!UICONTROL Data Integration Library (DIL)] em todas as páginas que deseja direcionar. [!UICONTROL DIL] grava dados de segmento de Audience Manager e IDs de usuário em cookies que são usados pelo [!DNL GPT] para direcionamento.

* **Criar um [!UICONTROL Cookie Destination]:** [!DNL GPT] O deve ser configurado como um destino baseado em cookies no Audience Manager.

* **Implementar código de verificação de cookie:** Envolver o [!DNL GPT] `.setTargeting` Método de API em nosso recomendado [código de verificação de cookie](../../integration/gpt-aam-destination/gpt-aam-modify-api.md). Esse código ajuda a evitar erros, procurando cookies AAM válidos antes da variável `.setTargeting` é chamado.

* **Adicione o `AamGpt` Função:** A variável `AamGpt` O código captura dados de cookies Audience Manager e os envia para o [!DNL GPT]. Coloque o [Código Audience Manager para tags do Google Publisher](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`na parte superior da página ou dentro da `<head>` bloco de código.

   >[!NOTE]
   >
   >A variável `AamGpt` A função não é necessária se você usar seu próprio código para ler dados do cookie Audience Manager.

* **Enviar logs de entrega para o Audience Manager:** Se quiser um relatório de delivery de segmento (opcional), forneça ao Audience Manager um log diário que contenha dados de delivery no nível de impressão. Os dados podem estar em um formato bruto, mas cada registro deve conter o Audience Manager `UUID`. O Audience Manager pode recebê-los via [!DNL FTP].

### Somente os segmentos qualificados são enviados para GPT

A quantidade de dados transmitidos para o [!DNL GPT] depende de para quantos segmentos um usuário específico se qualifica. Por exemplo, digamos que você configure segmentos de 100 Audience Manager. Se um visitante do site se qualificar para cinco deles, então somente esses cinco segmentos serão enviados para o [!DNL GPT] (nem todos os 100).

>[!NOTE]
>
>Não há limites para o número de valores-chave que você pode enviar, mas a variável [!DNL Google] solicitação [!DNL URL] O tem limites para o número de caracteres que pode aceitar. Consulte [Definição do direcionamento e dos tamanhos com GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712).

## Integração do lado do servidor {#server-side-integration}

Entre em contato com o consultor do Audience Manager ou com o Atendimento ao cliente se quiser configurar uma integração do lado do servidor com o [!DNL Google Ad Manager], utilizando [!DNL GPT]. Você precisará fornecer seus [!DNL Google Ad Manager] ID de rede da conta e ID de link de público-alvo.

>[!IMPORTANT]
>
>Se suas páginas da Web estiverem executando o [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]), você deve usar a integração do lado do servidor com o Audience Manager. Se você estiver em [!DNL AMP] e ter uma integração do lado do cliente com o [!DNL AMP], você deve migrar para a integração do lado do servidor. Entre em contato com seu consultor do Audience Manager ou com o Atendimento ao cliente para discutir a migração.

>[!MORELIKETHIS]
>
>* [Guia de referência de API GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

