---
description: Uma visão geral do DIL e como ele funciona.
seo-description: Uma visão geral do DIL e como ele funciona.
seo-title: Como entender a Biblioteca de integração de dados (DIL)
solution: Audience Manager
title: Como entender a Biblioteca de integração de dados (DIL)
uuid: 77 b 12 f 35-81 e 4-4639-ada 6-bf 982 f 27 b 36 e
translation-type: tm+mt
source-git-commit: 8f2cbf8a31335762f03cad278114d9ab7c520763

---


# Understanding the Data Integration Library (DIL){#understanding-the-data-integration-library-dil}

Visão geral, introdução e métodos de código disponíveis na biblioteca de código DIL do Audience Manager.

>[!IMPORTANT]
>
>Starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. Depende do serviço de ID para acionar os destinos de Ids e de URL. Ocorre um erro se o serviço de ID estiver ausente, antigo ou não configurado.
>
>Recomendamos que você use o Adobe Launch para implementar e gerenciar suas bibliotecas do serviço de ID da Experience Cloud ID.

No entanto, você também pode baixar as versões mais recentes da Experience Cloud e da DIL de nossa página github. Consulte links de download abaixo:

* Download the [Experience Cloud ID Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Download [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Purpose of DIL {#purpose-dil}

[!UICONTROL DIL] é uma biblioteca de API. You can think it as a body of helper code for [!DNL Adobe Audience Manager]. It is not required to use [!DNL Audience Manager], but the methods and functions [!UICONTROL DIL] provides means you don&#39;t have to develop your own code to send data to [!DNL Audience Manager]. Also, [!UICONTROL DIL] is different than the API provided by the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/). That service is designed to manage visitor identity across different [!DNL Experience Cloud] solutions. By contrast, [!UICONTROL DIL] is designed to:

* Make event calls and send data to the [Data Collection Server](../reference/system-components/components-data-collection.md).
* Send data to [destinations](../features/destinations/destinations.md).

## Getting and Implementing DIL Code {#get-implement-dil-code}

[!UICONTROL DIL] está disponível para download **[aqui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Please note that starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. Depende do serviço de ID para acionar os destinos de Ids e de URL. Ocorre um erro se o serviço de ID estiver ausente, antigo ou não configurado.

Rather than work with [!UICONTROL DIL] and set up [!DNL Audience Manager] manually, we recommend that you use [Adobe Launch](https://docs.adobelaunch.com/) instead. [!DNL Adobe Launch] é a ferramenta de implementação recomendada, pois simplifica a implantação do código, disposição e gerenciamento de versão. Read more about the [Audience Manager extension](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) in Adobe Launch.

Adobe Launch is the successor to [Adobe Dynamic Tag Manager](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM]).

## Sample Call {#sample-code}

[!UICONTROL DIL] envia dados para [!DNL Audience Manager] uma chamada de evento. Uma chamada de evento é uma solicitação HTTP XML da sua página. It uses a `POST` method to send data in the body of the request.

| Elemento de chamada de evento | Descrição |
|--- |--- |
| URL | DIL event calls use the following syntax: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Corpo | Como mostrado na amostra abaixo, o DIL envia dados como pares de valor chave. Special prefix characters identify the key-value pairs as Audience Manager or partner variables.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Consulte também:
* [Requisitos de prefixo para variáveis principais](../features/traits/trait-variable-prefixes.md)
* [Atributos compatíveis para chamadas de API DCS](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Links relacionados

* [Casos de uso de DIL e amostras de código](/help/using/dil/dil-use-cases.md)
* [Métodos de DIL de nível de classe](/help/using/dil/dil-class-overview/dil-start.md)
* [Métodos de DIL de nível de instância](/help/using/dil/dil-instance-methods.md)
* [Módulos DIL](/help/using/dil/dil-modules.md)
* [Ferramentas DIL](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)