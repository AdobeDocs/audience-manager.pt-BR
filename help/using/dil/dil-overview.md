---
description: Uma visão geral do DIL e como ele funciona.
seo-description: Uma visão geral do DIL e como ele funciona.
seo-title: Como entender a Biblioteca de integração de dados (DIL)
keywords: 'dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, didil, dil, dil, dil, '
solution: Audience Manager
title: Como entender a Biblioteca de integração de dados (DIL)
uuid: 77 b 12 f 35-81 e 4-4639-ada 6-bf 982 f 27 b 36 e
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# Como entender a Biblioteca de integração de dados (DIL){#understanding-the-data-integration-library-dil}

Visão geral, introdução e métodos de código disponíveis na biblioteca de código DIL do Audience Manager.

>[!IMPORTANT]
>
>Starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. Depende do serviço de ID para acionar os destinos de Ids e de URL. Ocorre um erro se o serviço de ID estiver ausente, antigo ou não configurado.
>
>Recomendamos que você use o Adobe Launch para implementar e gerenciar suas bibliotecas do serviço de ID da Experience Cloud ID.

No entanto, você também pode baixar as versões mais recentes da Experience Cloud e da DIL de nossa página github. Consulte links de download abaixo:

* Baixar o [serviço da Experience Cloud ID](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Baixar [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Propósito da DIL {#purpose-dil}

[!UICONTROL DIL] é uma biblioteca de API. Você pode considerar como um corpo de código pessoal para [!DNL Adobe Audience Manager]. Não é necessário usar [!DNL Audience Manager], mas os métodos e funções [!UICONTROL DIL] fornecidas significam que você não precisa desenvolver seu próprio código para enviar dados. [!DNL Audience Manager] Além disso, [!UICONTROL DIL] é diferente da API fornecida pelo serviço [da Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/). Esse serviço é projetado para gerenciar a identidade do visitante em [!DNL Experience Cloud] diferentes soluções. Por outro lado, foi projetado [!UICONTROL DIL] para:

* Faça chamadas de evento e envie dados para o [Servidor](../reference/system-components/components-data-collection.md)de coleta de dados.
* Enviar dados para [destinos](../features/destinations/destinations.md).

## Obter e implementar o código DIL {#get-implement-dil-code}

[!UICONTROL DIL] está disponível para download **[aqui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Please note that starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. Depende do serviço de ID para acionar os destinos de Ids e de URL. Ocorre um erro se o serviço de ID estiver ausente, antigo ou não configurado.

Em vez de trabalhar [!UICONTROL DIL] e configurar [!DNL Audience Manager] manualmente, recomendamos que você use [o Adobe Launch](https://docs.adobelaunch.com/) em vez disso. [!DNL Adobe Launch] é a ferramenta de implementação recomendada, pois simplifica a implantação do código, disposição e gerenciamento de versão. Leia mais sobre a extensão [do Audience Manager](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) no Adobe Launch.

O Adobe Launch é sucessor do [Adobe Dynamic Tag Manager](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM]).

## Chamada de exemplo {#sample-code}

[!UICONTROL DIL] envia dados para [!DNL Audience Manager] uma chamada de evento. Uma chamada de evento é uma solicitação HTTP XML da sua página. Ele usa um `POST` método para enviar dados no corpo da solicitação.

| Elemento de chamada de evento | Descrição |
|--- |--- |
| URL | As chamadas de evento do DIL usam a seguinte sintaxe: `https://adobe.demdex.net/event?_ts =`*`UNIX UTC timestamp`* |
| Corpo | Como mostrado na amostra abaixo, o DIL envia dados como pares de valor chave. Caracteres de prefixos especiais identificam os pares de valores chave como Audience Manager ou variáveis de parceiros.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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