---
description: Audience Manager e o Adobe Experience Platform Identity Service fazem chamadas e recebem dados do domínio demdex.net. Isso pode parecer que o Adobe está trabalhando com um domínio incomum de terceiros, mas isso não é o caso. Esta seção descreve os elementos em uma chamada demdex.net.
seo-description: Audience Manager e o Adobe Experience Platform Identity Service fazem chamadas e recebem dados do domínio demdex.net. Isso pode parecer que o Adobe está trabalhando com um domínio incomum de terceiros, mas isso não é o caso. Esta seção descreve os elementos em uma chamada demdex.net.
seo-title: Compreender as chamadas ao domínio Demdex
solution: Audience Manager
title: Compreender as chamadas ao domínio Demdex
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 15%

---


# Noções Gerais das Chamadas ao Domínio [!DNL Demdex] {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] e  [!DNL Adobe Experience Platform Identity Service] faz chamadas e recebe dados do  `demdex.net` domínio. Isso pode parecer que [!DNL Adobe] está trabalhando com um domínio de terceiros incomum, mas não é o caso. Esta seção descreve os elementos em uma chamada `demdex.net`.

| Elemento de chamada | Descrição |
|---|---|
| `demdex.net` | Este é um domínio herdado controlado por [!DNL Adobe]. Ele reflete o nome original pré-aquisição de [!DNL Audience Manager] ([!DNL Demdex]). [!DNL Adobe] adquirido [!DNL Demdex] em 2011 e reclassificou a empresa como [!DNL Audience Manager]. É difícil alterar esse domínio porque ele está profundamente inserido com [!DNL Audience Manager], [!DNL Adobe Experience Cloud ID Service] e nossa base de usuários instalada. Você pode ver outros prefixos anexados às chamadas herdadas `demdex.net` (por exemplo, `dcs.demdex.net`, `fast.demdex.net`, etc.). Independentemente do prefixo, uma chamada para `something.demdex.net` é sempre uma chamada para [!DNL Adobe] e não para algum domínio de terceiros desconhecido ou suspeito. |
| `dpm` | [!DNL DPM] é uma abreviação para  [!DNL Data Provider Match]. Ele informa aos sistemas internos [!DNL Adobe] que uma chamada de [!DNL Audience Manager] ou [!DNL Adobe Experience Cloud ID Service] está transmitindo os dados do cliente para sincronização ou solicitando uma ID. Esta é a chamada mais comum `demdex.net` que você verá de [!DNL Audience Manager] ou [!DNL Adobe Experience Cloud ID Service]. <br><br>[!DNL DPM] noções básicas de chamada: <ul><li>[!DNL Audience Manager]: Uma  [!DNL DPM] chamada do  [!DNL Audience Manager] envia dados para o  [!DNL Data Collection Servers] e  [!DNL Profile Cache Servers]. Consulte [Componentes da coleta de dados](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: Uma  [!DNL DPM] chamada do  [!DNL Adobe Experience Cloud ID Service] é uma solicitação de ID de visitante. Consulte [Cookies e o Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/pt-BR/id-service/using/intro/cookies.html) e [Como o Adobe Experience Platform Identity Service solicita e define IDs](https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html).</li></ul><br>Observação:  [!DNL Adobe Experience Cloud ID Service] os clientes podem alterar o  [!DNL DPM] prefixo no nome do domínio. Consulte [audienceManager Server e audienceManagerServerSecure](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Serviço de identidade da Adobe Experience Platform](https://docs.adobe.com/content/help/en/id-service/using/home.html)
>* [Cookies do Audience Manager](https://docs.adobe.com/content/help/pt-BR/core-services/interface/ec-cookies/cookies-am.html)

