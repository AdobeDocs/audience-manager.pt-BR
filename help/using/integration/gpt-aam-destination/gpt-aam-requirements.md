---
description: Você pode enviar segmentos qualificados para o DFP por meio de uma integração do lado do cliente ou do lado do servidor. Os requisitos e as informações relacionadas sobre ambos os métodos estão listados abaixo.
seo-description: Você pode enviar segmentos qualificados para o DFP por meio de uma integração do lado do cliente ou do lado do servidor. Os requisitos e as informações relacionadas sobre ambos os métodos estão listados abaixo.
seo-title: Requisitos e métodos de envio de segmentos para DFP usando Google Publisher Tags (GPT)
solution: Audience Manager
title: Requisitos e métodos de envio de segmentos para DFP usando Google Publisher Tags (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e67790b6
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Requisitos e métodos de envio de segmentos para DFP usando Google Publisher Tags (GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

É possível enviar segmentos qualificados para [!DNL DFP] o cliente por meio de uma integração do lado do servidor. Os requisitos e as informações relacionadas sobre ambos os métodos estão listados abaixo.

## Integração do cliente {#client-side-integration}

Para uma integração do cliente, é necessário configurar um [!DNL GPT] destino no Audience Manager. Considere os seguintes pontos quando quiser configurar [!DNL GPT] como um destino do Audience Manager:

* **[!UICONTROL DIL]Adicionar**: Implante o [!UICONTROL Data Integration Library (DIL)] código em todas as páginas que deseja direcionar. [!UICONTROL DIL] grava dados de segmento e IDs de usuário do Audience Manager em cookies que são usados [!DNL GPT] para direcionamento.

* **[!UICONTROL Cookie Destination]Criar um**: [!DNL GPT] deve ser configurado como um destino baseado em cookies no Audience Manager.

* **** Implementar código de verificação de cookie: Encapsule o método da [!DNL GPT] API em nosso código `.setTargeting` de verificação de [](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)cookie recomendado. Esse código ajuda a evitar erros procurando cookies AAM válidos antes de o `.setTargeting` método ser chamado.

* **`AamGpt`Adicione a** função: O `AamGpt` código captura dados de cookies do Audience Manager e os envia para [!DNL GPT]. Coloque o código do [Audience Manager para tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) do Google Publisher ( `AamGpt`) na parte superior da página ou dentro do bloco de `<head>` código.

   >[!NOTE]
   >
   >A `AamGpt` função não é necessária se você usar seu próprio código para ler os dados do cookie do Audience Manager.

* **** Enviar registros de entrega ao Audience Manager: Se desejar um relatório de entrega de segmento (opcional), forneça ao Audience Manager um registro diário que contenha dados de entrega em nível de impressão. Os dados podem estar em um formato bruto, mas cada registro deve conter o Audience Manager `UUID`. O Audience Manager pode coletar ou receber isso via [!DNL FTP].

### Somente segmentos qualificados são enviados para GPT

A quantidade de dados transmitida depende de quantos segmentos um usuário específico [!DNL GPT] se qualifica. Por exemplo, considere configurar 100 segmentos do Audience Manager. Se um visitante do site se qualificar para cinco deles, somente esses cinco segmentos serão enviados para [!DNL GPT] (não todos os 100).

>[!NOTE]
>
>Não há limites para o número de valores-chave que você pode enviar, mas a [!DNL Google] solicitação [!DNL URL] tem limites para o número de caracteres que pode aceitar. Consulte [Definição de metas e tamanhos com GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712).

## Integração do servidor {#server-side-integration}

Entre em contato com seu consultor do Audience Manager ou com o Atendimento ao cliente se desejar configurar uma integração do lado do servidor com [!DNL DFP]o, usando [!DNL GPT]. Será necessário fornecer a ID de rede da sua [!DNL DFP] conta e a ID do link de público-alvo.

>[!IMPORTANT]
>
>Se suas páginas da Web estiverem executando a biblioteca de páginas [de mídia](https://www.ampproject.org/) acelerada ([!DNL AMP]), você deverá usar a integração do servidor com o Audience Manager. Se você estiver ligado [!DNL AMP] e tiver uma integração do lado do cliente com [!DNL AMP], é necessário migrar para a integração do lado do servidor. Entre em contato com seu consultor do Audience Manager ou com o Atendimento ao cliente para discutir a migração.

>[!MORELIKETHIS]
>
>* [Guia de referência da API GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)

