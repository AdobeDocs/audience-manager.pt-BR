---
description: O Audience Manager e o serviço de identificação do Adobe Experience Platform fazem chamadas e recebem dados do domínio demdex.net. Isso pode parecer que a Adobe está trabalhando com um domínio de terceiros incomum, mas não é o caso. Esta seção descreve os elementos em uma chamada demdex.net.
seo-description: O Audience Manager e o serviço de identificação do Adobe Experience Platform fazem chamadas e recebem dados do domínio demdex.net. Isso pode parecer que a Adobe está trabalhando com um domínio de terceiros incomum, mas não é o caso. Esta seção descreve os elementos em uma chamada demdex.net.
seo-title: Compreender as chamadas ao domínio Demdex
solution: Audience Manager
title: Compreender as chamadas ao domínio Demdex
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 14%

---


# Understanding Calls to the [!DNL Demdex] Domain {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] e faz chamadas e recebe dados do [!DNL Adobe Experience Platform Identity Service] `demdex.net` domínio. Isso pode parecer que [!DNL Adobe] está trabalhando com um domínio incomum de terceiros, mas não é assim. Esta seção descreve os elementos em uma `demdex.net` chamada.

| Elemento de chamada | Descrição |
|---|---|
| `demdex.net` | This is a legacy domain controlled by [!DNL Adobe]. Reflete o nome original de pré-aquisição de [!DNL Audience Manager] ([!DNL Demdex]). [!DNL Adobe] adquirido [!DNL Demdex] em 2011 e reclassificou a empresa como [!DNL Audience Manager]. É difícil alterar esse domínio porque ele está profundamente entrelaçado com [!DNL Audience Manager]o, o [!DNL Adobe Experience Cloud ID Service]e a nossa base de usuários instalada. Você pode ver outros prefixos anexados a `demdex.net` chamadas herdadas (por exemplo, `dcs.demdex.net`, `fast.demdex.net`etc.). Independentemente do prefixo, uma chamada para `something.demdex.net` é sempre uma chamada para [!DNL Adobe] e não para algum domínio de terceiros desconhecido ou suspeito. |
| `dpm` | [!DNL DPM] é uma abreviação para [!DNL Data Provider Match]. It tells internal, [!DNL Adobe] systems that a call from [!DNL Audience Manager] or the [!DNL Adobe Experience Cloud ID Service] is passing in customer data for synchronization or requesting an ID. Esta é a `demdex.net` chamada mais comum que você verá [!DNL Audience Manager] ou a [!DNL Adobe Experience Cloud ID Service]. <br><br>[!DNL DPM] noções básicas de chamada: <ul><li>[!DNL Audience Manager]: Uma [!DNL DPM] chamada de [!DNL Audience Manager] envia dados para o [!DNL Data Collection Servers] e [!DNL Profile Cache Servers]. Consulte [Componentes da coleta de dados](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: Uma [!DNL DPM] chamada do [!DNL Adobe Experience Cloud ID Service] é uma solicitação de uma ID de visitante. Consulte [Cookies e o Serviço](https://docs.adobe.com/content/help/pt-BR/id-service/using/intro/cookies.html) de identificação do Adobe Experience Platform e [Como o Serviço de identificação do Adobe Experience Platform solicita e define IDs](https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html).</li></ul><br>Observação: [!DNL Adobe Experience Cloud ID Service] os clientes podem alterar o [!DNL DPM] prefixo no nome do domínio. Consulte [audienceManager Server e audienceManagerServerSecure](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Serviço de identificação de Adobe Experience Platform](https://docs.adobe.com/content/help/en/id-service/using/home.html)
>* [Cookies do Audience Manager](https://docs.adobe.com/content/help/pt-BR/core-services/interface/ec-cookies/cookies-am.html)

