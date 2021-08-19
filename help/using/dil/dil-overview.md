---
description: Uma visão geral do DIL e como ele funciona.
seo-description: Uma visão geral do DIL e como ele funciona.
seo-title: Como entender a DIL (Data Integration Library, biblioteca de integração de dados)
keywords: 'dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, l, '
solution: Audience Manager
title: Como entender a DIL (Data Integration Library, biblioteca de integração de dados)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: Implementação de DIL
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 12%

---

# Noções básicas sobre o [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

Visão geral, introdução e métodos de código disponíveis na biblioteca de códigos [!DNL Audience Manager DIL].

>[!IMPORTANT]
>
>A partir da versão 8.0 (lançada em agosto de 2018), [!UICONTROL DIL] tem uma forte dependência no [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html), versão 3.3 ou superior. Ele depende do [!DNL ID Service] para acionar sincronizações de ID e destinos de URL. Ocorre um erro se o [!DNL ID Service] estiver ausente, antigo ou não estiver configurado.
>
>Recomendamos que você use [!DNL Adobe Experience Platform Launch] para implementar e gerenciar suas bibliotecas [!DNL DIL] e [!DNL Adobe Experience Platform Identity Service].

No entanto, você também pode baixar as versões mais recentes do Experience Cloud e [!DNL DIL] de nossa página do GitHub. Consulte os links de download abaixo:

* Baixe o [Adobe Experience Platform Identity Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Baixar [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Objetivo do DIL {#purpose-dil}

[!UICONTROL DIL] é uma biblioteca de API. Você pode considerá-lo um corpo de código auxiliar para [!DNL Adobe Audience Manager]. Não é necessário usar [!DNL Audience Manager], mas os métodos e as funções [!UICONTROL DIL] fornecidos significam que você não precisa desenvolver seu próprio código para enviar dados para [!DNL Audience Manager]. Além disso, [!UICONTROL DIL] é diferente da API fornecida pelo [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). Esse serviço foi projetado para gerenciar a identidade do visitante em diferentes [!DNL Experience Cloud] soluções. Por outro lado, [!UICONTROL DIL] foi projetado para:

* Efetuar chamadas de evento e enviar dados para o [Servidor de Coleta de Dados](../reference/system-components/components-data-collection.md).
* Envie dados para [destinos](../features/destinations/destinations.md).

## Obter e implementar o código DIL {#get-implement-dil-code}

[!UICONTROL DIL] O código está disponível para download  **[aqui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Observe que a partir da versão 8.0 (lançada em agosto de 2018), [!UICONTROL DIL] tem uma forte dependência no [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html), versão 3.3 ou superior. Ele depende do [!DNL ID Service] para acionar sincronizações de ID e [!DNL URL destinations]. Ocorre um erro se o [!DNL ID Service] estiver ausente, antigo ou não estiver configurado.

Em vez de trabalhar com [!UICONTROL DIL] e configurar [!DNL Audience Manager] manualmente, recomendamos que você use [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html). [!DNL Adobe Experience Platform Launch] O é a ferramenta de implementação recomendada porque simplifica a implantação de código, o posicionamento e o gerenciamento de versão. Leia mais sobre a [extensão do Audience Manager](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html) em [!DNL Adobe Experience Platform Launch].

## Exemplo de chamada {#sample-code}

[!UICONTROL DIL] envia dados para o  [!DNL Audience Manager] em uma chamada de evento. Uma chamada de evento é uma solicitação HTTP XML da sua página. Ele usa um método `POST` para enviar dados no corpo da solicitação.

| Elemento de chamada de evento | Descrição |
|--- |--- |
| URL | As chamadas de evento DIL usam a seguinte sintaxe: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Corpo | Como mostrado na amostra abaixo, o DIL transmite os dados como pares de valores chave. Caracteres de prefixo especiais identificam os pares de valor chave como variáveis Audience Manager ou de parceiro.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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
