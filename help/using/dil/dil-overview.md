---
description: Uma visão geral do DIL e como ele funciona.
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: dil
solution: Audience Manager
title: Noções básicas sobre o Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 1%

---

# Compreender o [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

>[!WARNING]
>
>A partir de julho de 2023, a Adobe descontinuou o desenvolvimento do [!DNL Data Integration Library (DIL)] e da extensão [!DNL DIL].
>
>Os clientes existentes podem continuar usando a implementação [!DNL DIL]. Entretanto, a Adobe não desenvolverá [!DNL DIL] além deste ponto. Os clientes são incentivados a avaliar o [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=pt-BR) para sua estratégia de coleta de dados de longo prazo.
>
>Os clientes que desejam implementar novas integrações de coleta de dados após julho de 2023 devem usar o [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=pt-BR).

Visão geral, introdução e métodos de código disponíveis na biblioteca de códigos [!DNL Audience Manager DIL].

>[!IMPORTANT]
>
>A partir da versão 8.0 (lançada em agosto de 2018), o [!UICONTROL DIL] tem uma dependência forte no [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR), versão 3.3 ou superior. Ele depende do [!DNL ID Service] para acionar sincronizações de ID e destinos de URL. Ocorre um erro se o [!DNL ID Service] estiver ausente, antigo ou não configurado.
>
>Recomendamos que você use o [!DNL Adobe Experience Platform Tags] para implementar e gerenciar as bibliotecas do [!DNL DIL] e do [!DNL Adobe Experience Platform Identity Service].

No entanto, você também pode baixar as versões mais recentes do Experience Cloud e do [!DNL DIL] da nossa página do GitHub. Consulte os links de download abaixo:

* Baixe o [Adobe Experience Platform Identity Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Baixar [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Finalidade do DIL {#purpose-dil}

[!UICONTROL DIL] é uma biblioteca de API. Você pode considerá-lo um corpo de código auxiliar para [!DNL Adobe Audience Manager]. Não é necessário usar [!DNL Audience Manager], mas os métodos e funções que [!UICONTROL DIL] fornece significam que você não precisa desenvolver seu próprio código para enviar dados para [!DNL Audience Manager]. Além disso, [!UICONTROL DIL] é diferente da API fornecida pelo [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR). Esse serviço foi criado para gerenciar a identidade do visitante em diferentes soluções do [!DNL Experience Cloud]. Por outro lado, o [!UICONTROL DIL] foi criado para:

* Efetue chamadas de evento e envie dados para o [Servidor de Coleta de Dados](../reference/system-components/components-data-collection.md).
* Enviar dados para [destinos](../features/destinations/destinations.md).

## Obtenção e implementação do código DIL {#get-implement-dil-code}

O código [!UICONTROL DIL] está disponível para download **[aqui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Observe que a partir da versão 8.0 (lançada em agosto de 2018), o [!UICONTROL DIL] tem uma forte dependência do [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR), versão 3.3 ou superior. Ele depende do [!DNL ID Service] para acionar sincronizações de ID e [!DNL URL destinations]. Ocorre um erro se o [!DNL ID Service] estiver ausente, antigo ou não configurado.

Em vez de trabalhar com [!UICONTROL DIL] e configurar [!DNL Audience Manager] manualmente, recomendamos que você use [Marcas do Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=pt-BR). [!DNL Adobe Experience Platform Tags] é a ferramenta de implementação recomendada porque simplifica a implantação de código, o posicionamento e o gerenciamento de versão. Leia mais sobre a [extensão do Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html?lang=pt-BR) em [!DNL Adobe Experience Platform Tags].

## Exemplo de chamada {#sample-code}

[!UICONTROL DIL] envia dados a [!DNL Audience Manager] em uma chamada de evento. Uma chamada de evento é uma solicitação XML HTTP da página. Ele usa um método `POST` para enviar dados no corpo da solicitação.

| Elemento de chamada de evento | Descrição |
|--- |--- |
| URL | As chamadas de evento do DIL usam a seguinte sintaxe: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Corpo | Como mostrado na amostra abaixo, o DIL transmite os dados como pares de valores chave. Caracteres de prefixo especiais identificam os pares de valores chave como variáveis Audience Manager ou de parceiros.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Consulte também:
* [Requisitos de prefixo para variáveis-chave](../features/traits/trait-variable-prefixes.md)
* [Atributos compatíveis com chamadas de DCS API](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Links relacionados

* [Casos de uso da DIL e exemplos de código](/help/using/dil/dil-use-cases.md)
* [Métodos do DIL em nível de classe](/help/using/dil/dil-class-overview/dil-start.md)
* [Métodos do DIL em nível de instância](/help/using/dil/dil-instance-methods.md)
* [Módulos do DIL](/help/using/dil/dil-modules.md)
* [Ferramentas do DIL](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)
