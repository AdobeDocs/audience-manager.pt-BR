---
description: Uma visão geral da DIL e como ela funciona.
seo-description: Uma visão geral da DIL e como ela funciona.
seo-title: Como entender a Biblioteca de integração de dados (DIL)
keywords: 'dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, l, '
solution: Audience Manager
title: Como entender a Biblioteca de integração de dados (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# Como entender a Biblioteca de integração de dados (DIL){#understanding-the-data-integration-library-dil}

Visão geral, introdução e métodos de código disponíveis na biblioteca de códigos DIL do Audience Manager.

>[!IMPORTANT]
>
>Starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. Ele depende do serviço de ID para acionar sincronizações de ID e destinos de URL. Ocorre um erro se o serviço de ID estiver ausente, antigo ou não configurado.
>
>Recomendamos que você use o Adobe Launch para implementar e gerenciar as bibliotecas do DIL e do Serviço da Experience Cloud ID.

No entanto, você também pode baixar as versões mais recentes da Experience Cloud e da DIL de nossa página do GitHub. Consulte os links de download abaixo:

* Baixar o serviço da [Experience Cloud ID](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Baixar [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Objetivo do DIL {#purpose-dil}

[!UICONTROL DIL] é uma biblioteca da API. Você pode pensar que é um corpo de código auxiliar para [!DNL Adobe Audience Manager]. Não é necessário usar [!DNL Audience Manager], mas os métodos e funções [!UICONTROL DIL] fornecem meios para que você não precise desenvolver seu próprio código para enviar dados [!DNL Audience Manager]. Além disso, [!UICONTROL DIL] é diferente da API fornecida pelo serviço [da](https://marketing.adobe.com/resources/help/en_US/mcvid/)Experience Cloud ID. Esse serviço foi projetado para gerenciar a identidade do visitante em diferentes [!DNL Experience Cloud] soluções. Por outro lado, [!UICONTROL DIL] foi concebido para:

* Efetuar chamadas de evento e enviar dados para o Servidor [de Coleta de](../reference/system-components/components-data-collection.md)Dados.
* Enviar dados para [destinos](../features/destinations/destinations.md).

## Obtenção e implementação do código DIL {#get-implement-dil-code}

[!UICONTROL DIL] o código está disponível para download **[aqui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Please note that starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. Ele depende do serviço de ID para acionar sincronizações de ID e destinos de URL. Ocorre um erro se o serviço de ID estiver ausente, antigo ou não configurado.

Em vez de trabalhar com [!UICONTROL DIL] e configurar [!DNL Audience Manager] manualmente, recomendamos que você use o [Adobe Launch](https://docs.adobelaunch.com/) . [!DNL Adobe Launch] é a ferramenta de implementação recomendada, pois simplifica a implantação de código, o posicionamento e o gerenciamento de versões. Leia mais sobre a extensão [do](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) Audience Manager no Adobe Launch.

O Adobe Launch é o sucessor do [Adobe Dynamic Tag Manager](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM]).

## Chamada de exemplo {#sample-code}

[!UICONTROL DIL] envia dados para [!DNL Audience Manager] uma chamada de evento. Uma chamada de evento é uma solicitação HTTP XML de sua página. Ele usa um `POST` método para enviar dados no corpo da solicitação.

| Elemento de chamada de evento | Descrição |
|--- |--- |
| URL | As chamadas de evento DIL usam a seguinte sintaxe: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Corpo | Como mostrado na amostra abaixo, o DIL transmite os dados como pares de valores chave. Caracteres de prefixo especiais identificam os pares de valores chave como Audience Manager ou variáveis de parceiro.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Consulte também:
* [Requisitos de prefixo para variáveis-chave](../features/traits/trait-variable-prefixes.md)
* [Atributos suportados para chamadas de API DCS](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Links relacionados

* [Casos de uso DIL e exemplos de código](/help/using/dil/dil-use-cases.md)
* [Métodos DIL de nível de classe](/help/using/dil/dil-class-overview/dil-start.md)
* [Métodos DIL de nível de instância](/help/using/dil/dil-instance-methods.md)
* [Módulos DIL](/help/using/dil/dil-modules.md)
* [Ferramentas DIL](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)