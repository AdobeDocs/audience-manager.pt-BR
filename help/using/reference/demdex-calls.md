---
description: O Audience Manager e o Serviço de identidade da Adobe Experience Platform fazem chamadas para e recebem dados do domínio demdex.net. Pode parecer que o Adobe está trabalhando com um domínio incomum de terceiros, mas não é o caso. Esta seção descreve os elementos em uma chamada demdex.net.
seo-description: Audience Manager and the Adobe Experience Platform Identity Service make calls to and receive data from the demdex.net domain. This may seem like Adobe is working with an unusual third-party domain, but this is not the case. This section describes the elements in a demdex.net call.
seo-title: Understanding Calls to the Demdex Domain
solution: Audience Manager
title: Compreender as chamadas ao domínio Demdex
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: Reference
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 8%

---

# Compreender as chamadas para o [!DNL Demdex] Domínio {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] e a variável [!DNL Adobe Experience Platform Identity Service] fazer chamadas para e receber dados do `demdex.net` domínio. Isso pode parecer como [!DNL Adobe] O está trabalhando com um domínio incomum de terceiros, mas não é o caso. Esta seção descreve os elementos em uma `demdex.net` chame.

| Elemento de chamada | Descrição |
|---|---|
| `demdex.net` | Este é um domínio herdado controlado por [!DNL Adobe]. Ele reflete o nome original de pré-aquisição de [!DNL Audience Manager] ([!DNL Demdex]). [!DNL Adobe] adquirido [!DNL Demdex] em 2011 e reclassificou a empresa como [!DNL Audience Manager]. É difícil alterar este domínio porque está profundamente entrelaçado com [!DNL Audience Manager], o [!DNL Adobe Experience Cloud ID Service]e nossa base de usuários instalada. Você pode ver outros prefixos anexados a legados `demdex.net` chamadas (por exemplo, `dcs.demdex.net`, `fast.demdex.net`, etc.). Independentemente do prefixo, uma chamada para `something.demdex.net` é sempre uma chamada para [!DNL Adobe] e não a algum domínio de terceiros desconhecido ou suspeito. |
| `dpm` | [!DNL DPM] é uma abreviação de [!DNL Data Provider Match]. Informa as variáveis internas, [!DNL Adobe] sistemas que fazem uma chamada de [!DNL Audience Manager] ou o [!DNL Adobe Experience Cloud ID Service] O está transmitindo os dados do cliente para sincronização ou solicitando uma ID. Este é o mais comum `demdex.net` chamada que você verá de [!DNL Audience Manager] ou o [!DNL Adobe Experience Cloud ID Service]. <br><br>[!DNL DPM] noções básicas de chamada: <ul><li>[!DNL Audience Manager]: A [!DNL DPM] chamar de [!DNL Audience Manager] envia dados para o [!DNL Data Collection Servers] e [!DNL Profile Cache Servers]. Consulte [Componentes da coleta de dados](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: A [!DNL DPM] chame do [!DNL Adobe Experience Cloud ID Service] é uma solicitação de ID de visitante. Consulte [Cookies e o serviço de identidade da Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) e [Como o serviço de identidade da Adobe Experience Platform solicita e define IDs](https://experienceleague.adobe.com/docs/id-service/using/intro/id-request.html).</li></ul><br>Nota: [!DNL Adobe Experience Cloud ID Service] os clientes podem alterar o [!DNL DPM] no nome de domínio. Consulte [audienceManager Server e audienceManagerServerSecure](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Serviço de identidade da Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html)
>* [Cookies do Audience Manager](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html)

