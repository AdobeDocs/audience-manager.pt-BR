---
description: Continue aqui para obter informações sobre como solicitar uma resposta DCS em uma chamada /evento. Esta seção inclui um exemplo de resposta e definições para elementos de dados comuns em uma resposta.
seo-description: Continue aqui para obter informações sobre como solicitar uma resposta DCS em uma chamada /evento. Esta seção inclui um exemplo de resposta e definições para elementos de dados comuns em uma resposta.
seo-title: Receber dados do DCS
solution: Audience Manager
title: Receber dados do DCS
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 5%

---


# Receber dados do DCS {#receive-data-from-the-dcs}

Continue aqui para obter informações sobre como solicitar uma resposta [!DNL DCS] em uma chamada `/event`. Esta seção inclui um exemplo de resposta e definições para elementos de dados comuns em uma resposta.

Antes de revisar esse conteúdo, consulte [Enviar dados para o DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## Parâmetros de resposta do DCS: Uma revisão {#dcs-response-parameters}

Sua solicitação [!DNL DCS] deve incluir `d_rtbd=json` se você quiser receber uma resposta do [!DNL DCS]. O [!DNL DCS] não retornará dados se você omitir esse parâmetro. Uma chamada básica para [!DNL DCS] solicitar dados usa esta sintaxe:

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Resposta de exemplo {#sample-response}

Lembre-se de que da documentação [Enviar dados para o DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md), a empresa ficcional [!DNL Acme, Inc.] fez esta chamada:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Como esta chamada inclui o parâmetro de resposta necessário, o [!DNL DCS] devolveu o objeto [!DNL JSON] mostrado abaixo. O seu pode ser semelhante ou mais complexo.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Parâmetros de resposta {#response-parameters}

A tabela abaixo lista e define os parâmetros mais comuns que você pode ver em uma resposta do [!DNL DCS]. Isso se aplica a chamadas de evento ou outros query [!DNL DCS] [!DNL API] que retornam dados.

| Parâmetro | Descrição |
|--- |--- |
| `c` | Um URL que foi definido como [destino de URL](../../../features/destinations/create-url-destination.md). |
| `cn` | O nome ou ID definido no campo de nome do cookie de um [destino do cookie](../../../features/destinations/create-cookie-destination.md). |
| `cv` | Os valores enviados para o destino definido pelo parâmetro &quot;cn&quot;: nome do destino&quot;. |
| `dcs_region` | As [chamadas de DCS de servidor para servidor](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Este objeto contém informações para todos os destinos de URL configurados na interface do usuário. A lista desse objeto é dinâmica com base nas ações do usuário. |
| `dmn` | Este é o domínio especificado no campo Domínio do cookie para um destino de cookie. Consulte [Configurações opcionais para destinos de cookies](../../../features/destinations/cookie-destination-options.md).  Para integrações de Servidor a Servidor, recomendamos usar um domínio como `aam-api.com`. |
| `e` | O URL seguro que foi definido em um destino de URL. |
| `stuff` | Este objeto contém informações para todos os destinos de cookies. A lista desse objeto é dinâmica com base nas ações do usuário. |
| `tid` | ID de transação, que é uma ID exclusiva de 12 caracteres usada para fins de depuração. Cada chamada /evento para o DCS recebe uma marcação que pode ser referenciada em pesquisas de suporte para obter uma resposta melhor e mais rápida. |
| `ttl` | O valor do tempo de vida do cookie em dias. |
| `u` e `uuid` | ID de usuário exclusiva atribuída por Audience Manager. Isso é necessário se você estiver fazendo [chamadas DCS de servidor para servidor](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Tipo de destino, iFrame (`iframe`) ou imagem (`img`). |

>[!MORELIKETHIS]
>
>* [Prefixos e variáveis de valor-chave suportados pelo DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

