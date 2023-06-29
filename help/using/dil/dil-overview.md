---
description: Uma visão geral do DIL e como ele funciona.
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: dil
solution: Audience Manager
title: Como entender a DIL (Data Integration Library, biblioteca de integração de dados)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: fcf13cf39f688f8aafd2b1020ddfe4583d67e14f
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 10%

---

# Compreender o [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

>[!WARNING]
>
>A partir de julho de 2023, a Adobe interrompeu o desenvolvimento do [!DNL Data Integration Library (DIL)] e a variável [!DNL DIL] extensão.
><br>
>Os clientes existentes podem continuar usando seus [!DNL DIL] execução. No entanto, o Adobe não estará em desenvolvimento [!DNL DIL] além deste ponto. Os clientes são incentivados a avaliar [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) para a sua estratégia de recolha de dados a longo prazo.
><br>
>Os clientes que desejam implementar novas integrações de coleta de dados após julho de 2023 devem usar [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) em vez disso.

Visão geral, introdução e métodos de código disponíveis no [!DNL Audience Manager DIL] biblioteca de códigos.

>[!IMPORTANT]
>
>A partir da versão 8.0 (lançada em agosto de 2018), [!UICONTROL DIL] tem uma forte dependência do [Serviço de identidade da Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html), versão 3.3 ou superior. Baseia-se no [!DNL ID Service] para acionar sincronizações de ID e destinos de URL. Ocorre um erro se a variável [!DNL ID Service] está ausente, antigo ou não está configurado.
>
>Recomendamos que você use [!DNL Adobe Experience Platform Tags] para implementar e gerenciar o seu [!DNL DIL] e [!DNL Adobe Experience Platform Identity Service] bibliotecas.

No entanto, você também pode baixar o Experience Cloud mais recente e [!DNL DIL] versões da nossa página do GitHub. Consulte os links de download abaixo:

* Baixe o [Serviço de identidade da Adobe Experience Platform](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Baixar [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Finalidade do DIL {#purpose-dil}

[!UICONTROL DIL] é uma biblioteca de API. Você pode considerá-lo um corpo de código auxiliar para [!DNL Adobe Audience Manager]. Não é necessário usar [!DNL Audience Manager], mas os métodos e as funções [!UICONTROL DIL] O fornece significa que você não precisa desenvolver seu próprio código para enviar dados para [!DNL Audience Manager]. Além disso, [!UICONTROL DIL] é diferente da API fornecida pela variável [Serviço de identidade da Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html). Esse serviço foi projetado para gerenciar a identidade do visitante em diferentes [!DNL Experience Cloud] soluções. Em contrapartida, [!UICONTROL DIL] O foi projetado para:

* Efetue chamadas de evento e envie dados para o [Servidor de coleta de dados](../reference/system-components/components-data-collection.md).
* Enviar dados para [destinos](../features/destinations/destinations.md).

## Obter e implementar o código DIL {#get-implement-dil-code}

[!UICONTROL DIL] o código está disponível para download **[aqui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Observe que, a partir da versão 8.0 (lançada em agosto de 2018), [!UICONTROL DIL] tem uma forte dependência do [Serviço de identidade da Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html), versão 3.3 ou superior. Baseia-se no [!DNL ID Service] para acionar sincronizações de ID e [!DNL URL destinations]. Ocorre um erro se a variável [!DNL ID Service] está ausente, antigo ou não está configurado.

Em vez de trabalhar com [!UICONTROL DIL] e configurar [!DNL Audience Manager] manualmente, recomendamos usar [Tags do Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) em vez disso. [!DNL Adobe Experience Platform Tags] O é a ferramenta de implementação recomendada porque simplifica a implantação do código, a inserção e o gerenciamento de versão. Leia mais sobre o [extensão do Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) in [!DNL Adobe Experience Platform Tags].

## Exemplo de chamada {#sample-code}

[!UICONTROL DIL] envia dados para [!DNL Audience Manager] em uma chamada de evento. Uma chamada de evento é uma solicitação XML HTTP da página. Ele usa um `POST` método para enviar dados no corpo da solicitação.

| Elemento de chamada de evento | Descrição |
|--- |--- |
| URL | As chamadas de evento DIL usam a seguinte sintaxe: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Corpo | Como mostrado na amostra abaixo, o DIL transmite os dados como pares de valores chave. Caracteres de prefixo especiais identificam os pares de valores chave como variáveis Audience Manager ou de parceiro.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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
