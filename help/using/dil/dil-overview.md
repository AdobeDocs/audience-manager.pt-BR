---
description: Uma visão geral da DIL e como ela funciona.
seo-description: Uma visão geral da DIL e como ela funciona.
seo-title: Como entender a DIL (Data Integration Library, biblioteca de integração de dados)
keywords: dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil,
solution: Audience Manager
title: Como entender a DIL (Data Integration Library, biblioteca de integração de dados)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 18%

---


# Como entender a [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

Visão geral, introdução e métodos de código disponíveis na biblioteca de [!DNL Audience Manager DIL] códigos.

>[!IMPORTANT]
>
>A partir da versão 8.0 (lançada em agosto de 2018), [!UICONTROL DIL] há uma forte dependência do [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/pt-BR/id-service/using/home.html), versão 3.3 ou superior. Ele depende do [!DNL ID Service] acionamento de sincronizações de ID e destinos de URL. Ocorre um erro se o [!DNL ID Service] estiver ausente, antigo ou não configurado.
>
>Recomendamos que você use [!DNL Adobe Experience Platform Launch] para implementar e gerenciar suas [!DNL DIL] bibliotecas e [!DNL Adobe Experience Platform Identity Service] bibliotecas.

No entanto, você também pode baixar o Experience Cloud e [!DNL DIL] as versões mais recentes de nossa página do GitHub. Consulte os links de download abaixo:

* Download the [Adobe Experience Platform Identity Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Baixar [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Objetivo do DIL {#purpose-dil}

[!UICONTROL DIL] é uma biblioteca de APIs. Você pode pensar que é um corpo de código auxiliar para [!DNL Adobe Audience Manager]. Não é necessário usar [!DNL Audience Manager], mas os métodos e funções [!UICONTROL DIL] fornecem meios para que você não precise desenvolver seu próprio código para enviar dados [!DNL Audience Manager]. Além disso, [!UICONTROL DIL] é diferente da API fornecida pelo Serviço [de identidade do](https://docs.adobe.com/content/help/en/id-service/using/home.html)Adobe Experience Platform. Esse serviço foi projetado para gerenciar a identidade do visitante em diferentes [!DNL Experience Cloud] soluções. Por outro lado, [!UICONTROL DIL] foi concebido para:

* Efetuar chamadas de evento e enviar dados para o Servidor [de Coleta de](../reference/system-components/components-data-collection.md)Dados.
* Enviar dados para [destinos](../features/destinations/destinations.md).

## Obtenção e implementação do código DIL {#get-implement-dil-code}

[!UICONTROL DIL] o código está disponível para download **[aqui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Observe que, a partir da versão 8.0 (lançada em agosto de 2018),[!UICONTROL DIL]há uma forte dependência do Serviço[de identificação do](https://docs.adobe.com/content/help/en/id-service/using/home.html)Adobe Experience Platform, versão 3.3 ou superior. Ele depende do[!DNL ID Service]acionamento de sincronizações de ID e[!DNL URL destinations]. Ocorre um erro se o[!DNL ID Service]estiver ausente, antigo ou não configurado.

Em vez de trabalhar com [!UICONTROL DIL] e configurar [!DNL Audience Manager] manualmente, recomendamos que você use [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) . [!DNL Adobe Experience Platform Launch] é a ferramenta de implementação recomendada, pois simplifica a implantação de código, o posicionamento e o gerenciamento de versões. Leia mais sobre a extensão [do](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) Audience Manager em [!DNL Adobe Experience Platform Launch].

[!DNL Adobe Experience Platform Launch] é o sucessor do [Adobe Dynamic Tag Manager](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html) ([!DNL DTM]).

## Chamada de exemplo {#sample-code}

[!UICONTROL DIL] envia dados para [!DNL Audience Manager] uma chamada de evento. Uma chamada de evento é uma solicitação HTTP XML de sua página. Ele usa um `POST` método para enviar dados no corpo da solicitação.

| Elemento de chamada do Evento | Descrição |
|--- |--- |
| URL | As chamadas de evento DIL usam a seguinte sintaxe: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Corpo | Como mostrado na amostra abaixo, o DIL transmite os dados como pares de valores chave. Caracteres de prefixo especiais identificam os pares de valor chave como variáveis de Audience Manager ou de parceiro.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Consulte também:
* [Requisitos de prefixo para variáveis-chave](../features/traits/trait-variable-prefixes.md)
* [Atributos compatíveis com chamadas de DCS API](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Links relacionados

* [Casos de uso da DIL e exemplos de código](/help/using/dil/dil-use-cases.md)
* [Métodos da DIL em nível de classe ](/help/using/dil/dil-class-overview/dil-start.md)
* [Métodos da DIL em nível de instância](/help/using/dil/dil-instance-methods.md)
* [Módulos da DIL](/help/using/dil/dil-modules.md)
* [Ferramentas da DIL](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)