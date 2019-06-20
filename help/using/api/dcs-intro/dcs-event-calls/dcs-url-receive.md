---
description: Continue aqui para obter informações sobre como solicitar uma resposta do DCS em uma chamada /event. Esta seção inclui um exemplo de resposta e definições para elementos comuns de dados em uma resposta.
seo-description: Continue aqui para obter informações sobre como solicitar uma resposta do DCS em uma chamada /event. Esta seção inclui um exemplo de resposta e definições para elementos comuns de dados em uma resposta.
seo-title: Receber dados do DCS
solution: Audience Manager
title: Receber dados do DCS
uuid: fbb 77197-8530-48 a 8-b 708-d 785 f 7214494
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Receive Data From the DCS {#receive-data-from-the-dcs}

Continue here for information about how to request a [!UICONTROL DCS] response in a `/event` call. Esta seção inclui um exemplo de resposta e definições para elementos comuns de dados em uma resposta.

Before reviewing this content, see [Send Data to the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## DCS Response Parameters: A Review {#dcs-response-parameters}

Your [!UICONTROL DCS] request must include `d_rtbd=json` if you want to receive a response from the [!UICONTROL DCS]. The [!UICONTROL DCS] will not return data if you omit this parameter. A basic call to the [!UICONTROL DCS] to request data uses this syntax:

<pre><code>https://domain alias.demdex.net/event<i></i>?<i>key 1</i>= <i>val 1</i>, &amp;<i>key 2</i>= <i>val 2</i>&amp; d_ dst = 1 &amp; d_ rtbd = json &amp; d_ cb =<i>callback</i></code>
</pre>

## Resposta de exemplo {#sample-response}

Recall that from the [Send Data to the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) documentation, the fictional company [!DNL Acme, Inc.] made this call:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

As this call includes the required response parameter, the [!UICONTROL DCS] sent back the [!DNL JSON] object shown below. Pode ser semelhante ou mais complexo.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Parâmetros de resposta {#response-parameters}

The table below lists and defines the more common parameters you may see in a response from the [!UICONTROL DCS]. This applies to event calls or other [!UICONTROL DCS] [!DNL API] queries that return data.

| Parâmetro | Descrição |
|--- |--- |
| `c` | A URL that has been set as a [URL destination](../../../features/destinations/manage-destinations.md#configure-url-destination). |
| `cn` | The name or ID set in the cookie name field of a [cookie destination](../../../features/destinations/manage-destinations.md#create-cookie-destination). |
| `cv` | Os valores enviados para o destino definido pelo &quot;cn&quot;: parâmetro &quot;destinatno nome&quot;. |
| `dcs_region` | The [server-to-server DCS calls](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Esse objeto contém informações para todos os destinos de URL configurados na interface do usuário. A lista desse objeto é dinâmica com base nas ações do usuário. |
| `dmn` | Esse é o domínio especificado no campo Domínio do cookie para um destino de cookie. See [Optional Settings for Cookie Destinations](../../../features/destinations/manage-destinations.md#optional-settings-cookies).  For  Server to Server integrations we recommend using a domain like `aam-api.com`. |
| `e` | O URL seguro que foi definido em um destino de URL. |
| `stuff` | Esse objeto contém informações para todos os destinos de cookies. A lista desse objeto é dinâmica com base nas ações do usuário. |
| `tid` | ID de transação, que é uma ID única de 12 caracteres usada para depuração. Cada chamada /event ao DCS recebe uma tid que você pode referenciar em pesquisas de suporte para obter uma resposta melhor e mais rápida. |
| `ttl` | O valor de tempo para live do cookie em dias. |
| `u` e `uuid` | ID de usuário exclusiva atribuída pelo Audience Manager. This is required if you&#39;re making [server-to-server DCS calls](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Destination type,  iFrame (`iframe`) or image (`img`). |

>[!MORE_ LIKE_ THIS]
>
>* [Prefixos de valores chave e variáveis suportadas pelo DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

