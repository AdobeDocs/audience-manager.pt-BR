---
description: Você pode enviar segmentos qualificados para o Google Ad Manager por meio de uma integração do cliente ou do servidor. Os requisitos e as informações relacionadas sobre ambos os métodos estão listados abaixo.
seo-description: Você pode enviar segmentos qualificados para o Google Ad Manager por meio de uma integração do cliente ou do servidor. Os requisitos e as informações relacionadas sobre ambos os métodos estão listados abaixo.
seo-title: Requisitos e métodos de envio de segmentos ao Google Ad Manager usando Google Publisher Tags (GPT)
solution: Audience Manager
title: Requisitos e métodos de envio de segmentos ao Google Ad Manager usando Google Publisher Tags (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---


# Requisitos e métodos de envio de segmentos ao Google Ad Manager usando tags do Google Publisher (GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Você pode enviar segmentos qualificados para [!DNL Google Ad Manager] (antigo DFP) por meio de uma integração do cliente ou do servidor. Os requisitos e as informações relacionadas sobre ambos os métodos estão listados abaixo.

## Integração do lado do cliente {#client-side-integration}

Para uma integração do cliente, é necessário configurar um destino [!DNL GPT] no Audience Manager. Considere os seguintes pontos quando quiser configurar [!DNL GPT] como um destino de Audience Manager:

* **Adicionar  [!UICONTROL DIL]:** Implantar  [!UICONTROL Data Integration Library (DIL)] código em todas as páginas que você deseja público alvo. [!UICONTROL DIL] grava dados de segmento de Audience Manager e IDs de usuário em cookies que são usados  [!DNL GPT] para segmentação.

* **Criar um  [!UICONTROL Cookie Destination]:** [!DNL GPT] deve ser configurado como um destino baseado em cookie no Audience Manager.

* **Implemente o código de verificação de cookie:** vincule o método  [!DNL GPT] `.setTargeting` da API ao código [ de verificação de ](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)cookie recomendado. Este código ajuda a evitar erros procurando cookies AAM válidos antes que o método `.setTargeting` seja chamado.

* **Adicionar a  `AamGpt` função:** o  `AamGpt` código captura dados de cookies do Audience Manager e os envia para  [!DNL GPT]. Coloque o [Código de Audience Manager para Tags do Google Publisher](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) na parte superior da página ou dentro do bloco de código `<head>`.

   >[!NOTE]
   >
   >A função `AamGpt` não é necessária se você usar seu próprio código para ler dados de cookies de Audience Manager.

* **Enviar Logs do delivery Audience Manager:** se quiser um relatório de delivery de segmento (opcional), forneça ao Audience Manager um registro diário que contenha dados de delivery de nível de impressão. Os dados podem estar em um formato bruto, mas cada registro deve conter o Audience Manager `UUID`. O Audience Manager pode coletar ou receber esses itens por meio de [!DNL FTP].

### Somente segmentos qualificados são enviados para GPT

A quantidade de dados transmitida para [!DNL GPT] depende de quantos segmentos um usuário específico se qualifica. Por exemplo, considere configurar 100 segmentos de Audience Manager. Se um visitante de site se qualificar para cinco deles, então apenas esses cinco segmentos serão enviados para [!DNL GPT] (não todos os 100).

>[!NOTE]
>
>Não há limites para o número de valores-chave que você pode enviar, mas a solicitação [!DNL Google] [!DNL URL] tem limites para o número de caracteres que pode aceitar. Consulte [Definição de metas e tamanhos com GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712).

## Integração do servidor {#server-side-integration}

Fale com seu consultor de Audience Manager ou com o Atendimento ao cliente se quiser configurar uma integração do lado do servidor com [!DNL Google Ad Manager], usando [!DNL GPT]. Você precisará fornecer a ID de rede da sua conta [!DNL Google Ad Manager] e a ID do link de Audiência.

>[!IMPORTANT]
>
>Se suas páginas da Web estiverem executando a biblioteca [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]), você deverá usar a integração do lado do servidor com o Audience Manager. Se você estiver em [!DNL AMP] e tiver uma integração do lado do cliente com [!DNL AMP], é necessário migrar para a integração do lado do servidor. Entre em contato com seu consultor de Audience Manager ou com o Atendimento ao cliente para discutir a migração.

>[!MORELIKETHIS]
>
>* [Guia de referência da API GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

