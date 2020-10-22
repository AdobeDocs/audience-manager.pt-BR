---
description: Este documento aborda os aspectos técnicos relacionados à conformidade com as regulamentações de privacidade de dados do Audience Manager.
seo-description: Este documento aborda os aspectos técnicos relacionados à conformidade com as regulamentações de privacidade de dados do Audience Manager.
seo-title: Solicitações de privacidade de dados
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: Solicitações de privacidade de dados
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 231d8e537cf5b4f29b1c4f284fe1b3ffe6d187a9
workflow-type: tm+mt
source-wordcount: '1477'
ht-degree: 65%

---


# Solicitações de privacidade de dados {#data-privacy-requests}

## Visão geral {#overview}

This document provides an overview of managing individual data privacy and opt-out requests that you can send to [!DNL Audience Manager] through the [Privacy Service UI](https://privacyui.cloud.adobe.io/) and the **[!DNL Privacy Service API]**.

These tools allow you to send consumer data privacy requests made under [!DNL GDPR] and [!DNL CCPA].

Antes de ler este artigo, recomendamos consultar o [Glossário do GDPR](../data-security-and-privacy/aam-gdpr-glossary.md) e o [Glossário da CCPA](aam-ccpa-glossary.md) para entender melhor a terminologia usada aqui.

You can submit individual requests to access and delete consumer data from [!DNL Audience Manager], in two ways:

* Por meio da [Interface do usuário do Privacy Service](https://privacyui.cloud.adobe.io/). Consulte a documentação [aqui](https://docs.adobe.com/content/help/pt-BR/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Por meio da **[!DNL Privacy Service API]**. Consulte a documentação [aqui](https://docs.adobe.com/content/help/pt-BR/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)[!DNL API] e a referência da [aqui](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

When sending individual data privacy requests, you can submit any [!DNL Audience Manager] identifiers (IDs), as described in the **[Audience Manager Identifiers](data-privacy-ids.md)** section, along with their respective namespace IDs (data source IDs).

O [Privacy Service](https://docs.adobe.com/content/help/pt-BR/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md) oferece suporte a dois tipos de solicitações: acesso aos dados e solicitações de exclusão de dados.

## Solicitações de acesso a dados {#access-data}

You can send individual data access requests through the [Privacy Service UI](https://privacyui.cloud.adobe.io) (documentation [here](https://docs.adobe.com/content/help/pt-BR/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) or by calling the Privacy Service API (documentation [here](https://docs.adobe.com/content/help/pt-BR/experience-platform/privacy/home.html) and [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

A [Interface do usuário do Privacy Service](https://privacyui.cloud.adobe.io/) permite criar novas solicitações de trabalho usando o [!UICONTROL Request Builder] ou fazendo upload de um arquivo [!DNL JSON].

Para ver a aparência de um arquivo válido [!DNL JSON], é possível [ baixar uma amostra de JSON](../data-security-and-privacy/assets/access_request.json).

Compreendemos o seu compromisso de atender às suas solicitações de privacidade de dados dentro do período definido pela legislação.

## Solicitações de exclusão de dados {#delete-data}

You can send data deletion requests through the [Privacy Service UI](https://privacyui.cloud.adobe.io) (documentation [here](https://docs.adobe.com/content/help/pt-BR/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) or by calling the Privacy Service API (documentation [here](https://docs.adobe.com/content/help/pt-BR/experience-platform/privacy/home.html) and [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

A [Interface do usuário do Privacy Service](https://privacyui.cloud.adobe.io/) permite criar novas solicitações de trabalho usando o [!UICONTROL Request Builder] ou fazendo upload de um arquivo [!DNL JSON].

Para ver a aparência de um arquivo válido [!DNL JSON], é possível [ baixar uma amostra de JSON](../data-security-and-privacy/assets/access_request.json).

A Adobe entende seu compromisso de atender às solicitações de privacidade dos clientes em 30 dias. For that reason, [!DNL Adobe] is committed to processing your data deletion request as soon as possible.

In response to your consumer data deletion requests, [!DNL Audience Manager] deletes traits and segments associated with the [!DNL Audience Manager] identifier included in the request. Additionally, the respective [!DNL Audience Manager] identifiers for the individual opted out of further data collection by [!DNL Audience Manager] and the respective ID mappings will be removed.

Ao enviar IDs declaradas, como IDs do [!DNL CRM] entre dispositivos ou IDs de , em solicitações de privacidade de dados, o executará a exclusão necessária em todos os dispositivos vinculados (até 100 dispositivos por ID declarada).[!DNL cookie][!DNL Audience Manager]

[!DNL Audience Manager]O tentará notificar os parceiros de ativação sobre solicitações de exclusão enviando informações de cancelamento de segmentos para os titulares dos dados que solicitam a exclusão de determinados dados. No entanto, alguns parceiros de ativação:

1. Cannot support unsegment (or remove segment) requests from [!DNL Audience Manager] and/or
2. Are not able to receive updates from [!DNL Audience Manager] with a frequency of less than 30 days. In those cases, [!DNL Audience Manager] customers are not able to send delete requests to activation partners in an automated way through [!DNL Audience Manager].

Nesses casos, não é possível enviar solicitações de exclusão para parceiros de ativação de forma automatizada pelo [!DNL Audience Manager].

Baixe nossa [Planilha do Excel para parceiros](assets/AAM-Partners-October2019.xlsx) para ver quais parceiros de ativação do oferecem suporte ao cancelamento de segmentos.[!DNL Audience Manager]

## Solicitações de recusa {#opt-out-requests}

[!DNL Audience Manager] apoia as normas do setor em matéria de gestão de opções. Leia para obter informações completas sobre os tipos de recusa compatíveis com o [!DNL Audience Manager].

Enquanto as solicitações de acesso e exclusão de dados são tratadas pelo [Privacy Service](https://docs.adobe.com/content/help/pt-BR/experience-platform/privacy/home.html), as solicitações de recusa são feitas por meio da [!DNL DCS API]. Read on to learn what the opt-out [!DNL API] calls should look like.

### Solicitações globais de recusa

The global opt-out represents an opt-out across [!DNL Audience Manager] and other [!DNL Adobe Experience Cloud] solutions for all brands. A tabela abaixo lista os métodos usados para a recusa global:

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recusar para </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>A página <a href="https://www.adobe.com/br/privacy/opt-out.html#customeruse" format="http" scope="external"> Suas escolhas de privacidade </a> fornece recursos de 1 clique que permitem que os usuários finais controlem e excluam a coleta de dados pelas soluções de publicidade da Adobe Experience Cloud (incluindo o Audience Manager). Especificamente, consulte a seção <a href="https://www.adobe.com/br/privacy/opt-out.html#customeruse" format="http" scope="external">Cliente comercial </a> da página Opções de privacidade. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chamadas de API diretas para o Audience Manager </p> </td> 
   <td colname="col2"> <p>Seus usuários podem recusar a coleta de dados por todas as marcas do Audience manager fazendo uma chamada para a API DCS abaixo e incluindo a <a href="../../reference/ids-in-aam.md"> ID de usuário do Audience Manager</a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Como resultado, definiremos os cookies <code>demdex=NOTARGET</code> e <code>dextp=NOTARGET</code> para a ID de usuário do Audience Manager enviada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dispositivos móveis </p> </td> 
   <td colname="col2"> <p>Consulte as configurações de recusa e privacidade para: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://docs.adobe.com/content/help/pt-BR/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external"> Dispositivos Android </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://docs.adobe.com/content/help/pt-BR/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external"> Dispositivos iOS </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Seus usuários finais também podem recusar a coleta global de dados ao acessar os sites de nossos parceiros padrão do setor.

* [The Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Seguindo as solicitações de recusa descritas acima:

* [!DNL Audience Manager]O interromperá toda a coleta de dados, segmentação ou ativação, desde que o usuário não limpe os cookies do navegador.
* Os dados históricos são removidos do perfil do usuário após 120 dias.

### Recusa em nível de parceiro com chamadas de ID declaradas

The partner-level opt-out allows you to opt-out your users from data collection by specific [!DNL Audience Manager] partners. You can send partner-level opt-out requests for cross-device IDs, including [!DNL CRM] IDs and hashed email addresses.

Seguindo uma recusa em nível de parceiro com uma chamada de ID declarada:

* A [ID de CRM](../../reference/ids-in-aam.md) recusa a coleta de dados;
* A última ID de dispositivo ([ID de usuário exclusiva do Audience Manager](../../reference/ids-in-aam.md)) vinculada à [ID de CRM](../../reference/ids-in-aam.md) recusa a coleta de dados.
* [!DNL Audience Manager]O cessará toda a coleta, segmentação ou ativação de dados a partir de agora para a ID de e a última ID de dispositivo vinculada à ID de ;[!DNL CRM][!DNL CRM]
* [!DNL Audience Manager] cancela a segmentação da ID [!DNL CRM] de opção e da ID do último dispositivo de todos os segmentos;
* [!UICONTROL Destination] os parceiros recebem a solicitação de cancelamento de segmento para a [!DNL CRM] ID e a ID do último dispositivo. O cancelamento de segmentos funciona para destinos [em tempo real](data-privacy-requests.md#aam-partners-with-unsegmentation) e em lote.
* Nenhum dado histórico é excluído.

When [!DNL Audience Manager] receives a partner-level opt-out request, the [!DNL JSON] returned by the [!DNL DCS] contains the [error code 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), with the message [!UICONTROL "Encountered opt out tag"], instead of the [!DNL Audience Manager] user ID.

Você pode fazer uma solicitação de recusa de ID declarada com os pares de valor-chave `d_cid` e `d_cid_ic`. Os parâmetros herdados como `d_dpid` e `d_dpuuid` ainda funcionam, mas são considerados obsoletos. Consulte [CID substitui DPID e DPUUID](../../reference/cid.md). Nos exemplos, *itálico* indica um espaço reservado para variável.

#### Recusar com [!DNL CID] e [!DNL CID_IC]

Para obter uma descrição e sintaxe, consulte [Variáveis e sintaxe de URL para IDs declaradas](../../features/declared-ids.md#variables-and-syntax).

| Recusa de uso | Amostra de código |
|--- |--- |
| Uma ID de provedor de dados e ID de usuário. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Um código de integração e ID de usuário. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Vários pares `d_cid` e `d_cid_ic` valores chave. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Recusa em nível de parceiro com chamadas de ID de dispositivo

The partner-level opt-out allows you to opt-out your users from data collection by specific [!DNL Audience Manager] partners. Você pode recusar a coleta de dados em uma determinada ID de dispositivo para uma marca fazendo as seguintes chamadas para a [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| Recusa de uso | Amostra de código |
|--- |--- |
| An [!DNL Audience Manager] [!DNL Unique User ID] (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Uma [!DNL Experience Cloud] ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Leia mais sobre `uuid`, `mid` e `imsOrgId` no [Índice de IDs no Audience Manager](/help/using/reference/ids-in-aam.md).

Seguindo uma opção de recusa em nível de parceiro com uma chamada de ID de dispositivo:

* A ID do dispositivo recusa a coleta de dados.
* [!DNL Audience Manager]O encerrará toda a coleta de dados, segmentação ou ativação para o parceiro a partir da ID do dispositivo.
* [!DNL Audience Manager] dessegmenta a ID do dispositivo de todos os segmentos;
* Os parceiros de destino recebem a solicitação de cancelamento de segmentos para a ID do dispositivo. O cancelamento de segmentos funciona para destinos [em tempo real](data-privacy-requests.md#aam-partners-with-unsegmentation) e em lote.
* Nenhum dado histórico é excluído.

## [!DNL Audience Manager] Parceiros Com Recursos De Dessegmentação {#aam-partners-with-unsegmentation}

In order to help you automate your consumer data privacy requests, [!DNL Audience Manager] will attempt to notify activation partners about deletion requests from Data Subjects by sending them unsegment (or remove segment) information.

Entretanto, alguns de nossos parceiros e ativação:

1. Cannot support unsegment requests from [!DNL Audience Manager] and/or
2. Are not able to receive updates from [!DNL Audience Manager] more frequently than once in 30 days.

Nesses casos, não é possível enviar solicitações de exclusão para parceiros de ativação de forma automatizada pelo [!DNL Audience Manager].

Consulte a [lista de destinos com base em dispositivos](/help/using/features/destinations/device-based-destinations-list.md) para ver quais parceiros de ativação do oferecem suporte ao cancelamento de segmentos.[!DNL Audience Manager]

## Solicitações de correção de dados {#correction}

Given that [!DNL Audience Manager] is not the source of the data, there is a limited role for data correction in [!DNL Audience Manager]. The correction could mean that the consumer has requested to either be disqualified from an incorrect [!UICONTROL trait]/[!UICONTROL segment] or qualified to the desired [!UICONTROL trait]/[!UICONTROL segment].

[!DNL Audience Manager] os clientes podem optar por capturar os sinais/características/segmentos relevantes em relação aos perfis do usuário e enviar essas informações por meio da ingestão [de dados](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) offline para [!DNL Audience Manager]. Please note that the user will continue to get qualified to the original [!UICONTROL trait] and [!UICONTROL segments] if they repeat their behavior.
