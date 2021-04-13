---
description: O Audience Manager e o serviço de identidade da Adobe Experience Platform fazem chamadas para e recebem dados do domínio demdex.net. Isso pode parecer que o Adobe está trabalhando com um domínio incomum de terceiros, mas não é o caso. Esta seção descreve os elementos em uma chamada demdex.net.
seo-description: O Audience Manager e o serviço de identidade da Adobe Experience Platform fazem chamadas para e recebem dados do domínio demdex.net. Isso pode parecer que o Adobe está trabalhando com um domínio incomum de terceiros, mas não é o caso. Esta seção descreve os elementos em uma chamada demdex.net.
seo-title: Compreender as chamadas ao domínio Demdex
solution: Audience Manager
title: Compreender as chamadas ao domínio Demdex
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: 'Referência '
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 15%

---

# Compreender as chamadas para o domínio [!DNL Demdex] {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] e  [!DNL Adobe Experience Platform Identity Service] faz chamadas para e recebe dados do  `demdex.net` domínio. Isso pode parecer que [!DNL Adobe] está funcionando com um domínio de terceiros incomum, mas não é o caso. Esta seção descreve os elementos em uma chamada `demdex.net`.

| Elemento de chamada | Descrição |
|---|---|
| `demdex.net` | Este é um domínio herdado controlado por [!DNL Adobe]. Ele reflete o nome original de pré-aquisição de [!DNL Audience Manager] ([!DNL Demdex]). [!DNL Adobe] adquirido [!DNL Demdex] em 2011 e reclassificou a empresa como [!DNL Audience Manager]. É difícil alterar esse domínio porque ele está profundamente entrelaçado com [!DNL Audience Manager], [!DNL Adobe Experience Cloud ID Service] e nossa base de usuários instalada. Você pode ver outros prefixos anexados a chamadas `demdex.net` herdadas (por exemplo, `dcs.demdex.net`, `fast.demdex.net`, etc.). Independentemente do prefixo, uma chamada para `something.demdex.net` é sempre uma chamada para [!DNL Adobe] e não para algum domínio desconhecido ou suspeito de terceiros. |
| `dpm` | [!DNL DPM] é uma abreviação de  [!DNL Data Provider Match]. Informa aos sistemas internos [!DNL Adobe] que uma chamada de [!DNL Audience Manager] ou [!DNL Adobe Experience Cloud ID Service] está transmitindo os dados do cliente para sincronização ou solicitando uma ID. Essa é a chamada `demdex.net` mais comum que você verá em [!DNL Audience Manager] ou [!DNL Adobe Experience Cloud ID Service]. <br><br>[!DNL DPM] noções básicas de chamada: <ul><li>[!DNL Audience Manager]: Uma  [!DNL DPM] chamada de  [!DNL Audience Manager] envia dados para o  [!DNL Data Collection Servers] e o  [!DNL Profile Cache Servers]. Consulte [Componentes da coleta de dados](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: Uma  [!DNL DPM] chamada do  [!DNL Adobe Experience Cloud ID Service] é uma solicitação de uma ID de visitante. Consulte [Cookies e o serviço de identidade da Adobe Experience Platform](https://docs.adobe.com/content/help/pt-BR/id-service/using/intro/cookies.html) e [Como o serviço de identidade da Adobe Experience Platform solicita e define IDs](https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html).</li></ul><br>Observação:  [!DNL Adobe Experience Cloud ID Service] Os clientes do podem alterar o  [!DNL DPM] prefixo no nome do domínio. Consulte [audienceManager Server e audienceManagerServerSecure](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Serviço de identidade da Adobe Experience Platform](https://docs.adobe.com/content/help/en/id-service/using/home.html)
>* [Cookies do Audience Manager](https://docs.adobe.com/content/help/pt-BR/core-services/interface/ec-cookies/cookies-am.html)

