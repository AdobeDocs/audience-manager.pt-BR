---
description: Continue aqui para obter informações sobre como solicitar uma resposta do DCS em uma chamada /event. Esta seção inclui um exemplo de resposta e definições para elementos comuns de dados em uma resposta.
seo-description: Continue aqui para obter informações sobre como solicitar uma resposta do DCS em uma chamada /event. Esta seção inclui um exemplo de resposta e definições para elementos comuns de dados em uma resposta.
seo-title: Receber dados do DCS
solution: Audience Manager
title: Receber dados do DCS
uuid: fbb 77197-8530-48 a 8-b 708-d 785 f 7214494
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Receber dados do DCS {#receive-data-from-the-dcs}

Continue aqui para obter informações sobre como solicitar [!UICONTROL DCS] uma resposta em uma `/event` chamada. Esta seção inclui um exemplo de resposta e definições para elementos comuns de dados em uma resposta.

Antes de revisar este conteúdo, consulte [Enviar dados para o DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## Parâmetros de resposta do DCS: Uma revisão {#dcs-response-parameters}

Sua [!UICONTROL DCS] solicitação deve incluir `d_rtbd=json` se você quiser receber uma resposta do [!UICONTROL DCS]. Os [!UICONTROL DCS] dados não retornarão se você omitir esse parâmetro. Uma chamada básica para a [!UICONTROL DCS] solicitação de dados usa essa sintaxe:

<pre><code>https://domain alias.demdex.net/event<i></i>?<i>key 1</i>= <i>val 1</i>, &amp;<i>key 2</i>= <i>val 2</i>&amp; d_ dst = 1 &amp; d_ rtbd = json &amp; d_ cb =<i>callback</i></code>
</pre>

## Resposta de exemplo {#sample-response}

Lembre-se de que a empresa fictícia fez essa chamada de [Enviar dados para a](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) [!DNL Acme, Inc.] documentação do DCS:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Como essa chamada inclui o parâmetro de resposta obrigatório, o [!UICONTROL DCS] retornado de volta o [!DNL JSON] objeto mostrado abaixo. Pode ser semelhante ou mais complexo.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Parâmetros de resposta {#response-parameters}

A tabela abaixo lista e define os parâmetros mais comuns que podem ser vistos em uma resposta do [!UICONTROL DCS]. Isso se aplica a chamadas de evento ou a outras [!UICONTROL DCS][!DNL API] consultas que retornam dados.

| Parâmetro | Descrição |
|--- |--- |
| `c` | Um URL que foi definido como um destino [de URL](../../../features/destinations/create-url-destination.md). |
| `cn` | O nome ou ID definido no campo nome do cookie de um [destino](../../../features/destinations/create-cookie-destination.md)de cookie. |
| `cv` | Os valores enviados para o destino definido pelo "cn": parâmetro "destinatno nome". |
| `dcs_region` | As chamadas do servidor de [servidor para servidor](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Esse objeto contém informações para todos os destinos de URL configurados na interface do usuário. A lista desse objeto é dinâmica com base nas ações do usuário. |
| `dmn` | Esse é o domínio especificado no campo Domínio do cookie para um destino de cookie. Consulte [Configurações opcionais para destinos de cookies](../../../features/destinations/cookie-destination-options.md). Para integrações do servidor nas integrações do servidor, recomendamos usar um domínio como `aam-api.com`. |
| `e` | O URL seguro que foi definido em um destino de URL. |
| `stuff` | Esse objeto contém informações para todos os destinos de cookies. A lista desse objeto é dinâmica com base nas ações do usuário. |
| `tid` | ID de transação, que é uma ID única de 12 caracteres usada para depuração. Cada chamada /event ao DCS recebe uma tid que você pode referenciar em pesquisas de suporte para obter uma resposta melhor e mais rápida. |
| `ttl` | O valor de tempo para live do cookie em dias. |
| `u` e `uuid` | ID de usuário exclusiva atribuída pelo Audience Manager. Isso é necessário se você estiver fazendo [chamadas DCS de servidor para servidor](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Tipo de destino, iframe (`iframe`) ou image (`img`). |

>[!MORE_ LIKE_ THIS]
>
>* [Prefixos de valores chave e variáveis suportadas pelo DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

