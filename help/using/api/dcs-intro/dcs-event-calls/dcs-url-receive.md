---
description: Continue aqui para obter informações sobre como solicitar uma resposta do DCS em uma chamada /event. Esta seção inclui um exemplo de resposta e definições para elementos de dados comuns em uma resposta.
seo-description: Continue aqui para obter informações sobre como solicitar uma resposta do DCS em uma chamada /event. Esta seção inclui um exemplo de resposta e definições para elementos de dados comuns em uma resposta.
seo-title: Receber dados do DCS
solution: Audience Manager
title: Receber dados do DCS
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
exl-id: c6a87e5a-63cc-44d7-b6f0-ac8ee845fd00
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 5%

---

# Receber dados do DCS {#receive-data-from-the-dcs}

Continue aqui para obter informações sobre como solicitar uma resposta [!DNL DCS] em uma chamada `/event`. Esta seção inclui um exemplo de resposta e definições para elementos de dados comuns em uma resposta.

Antes de revisar esse conteúdo, consulte [Enviar dados para o DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## Parâmetros de resposta DCS: Uma revisão {#dcs-response-parameters}

Sua solicitação [!DNL DCS] deve incluir `d_rtbd=json` se você quiser receber uma resposta do [!DNL DCS]. O [!DNL DCS] não retornará dados se você omitir esse parâmetro. Uma chamada básica para o [!DNL DCS] para solicitar dados usa esta sintaxe:

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Resposta de exemplo {#sample-response}

Lembre-se de que da documentação [Enviar dados para o DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md), a empresa ficcional [!DNL Acme, Inc.] fez esta chamada:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Como essa chamada inclui o parâmetro de resposta necessário, o [!DNL DCS] enviou de volta o objeto [!DNL JSON] mostrado abaixo. O seu pode ser semelhante ou mais complexo.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Parâmetros de resposta {#response-parameters}

A tabela abaixo lista e define os parâmetros mais comuns que você pode ver em uma resposta do [!DNL DCS]. Isso se aplica a chamadas de evento ou outras [!DNL DCS] [!DNL API] consultas que retornam dados.

| Parâmetro | Descrição |
|--- |--- |
| `c` | Um URL que foi definido como [URL destination](../../../features/destinations/create-url-destination.md). |
| `cn` | O nome ou ID definido no campo de nome do cookie de um [destino do cookie](../../../features/destinations/create-cookie-destination.md). |
| `cv` | Os valores enviados para o destino definido pelo parâmetro &quot;cn&quot;: &quot;nome do destino&quot;. |
| `dcs_region` | O [DCS de servidor para servidor chama](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Esse objeto contém informações para todos os destinos de URL que estão configurados na interface do usuário do . A lista deste objeto é dinâmica com base nas ações do usuário. |
| `dmn` | Este é o domínio especificado no campo Domínio de cookie para um destino de cookie. Consulte [Configurações opcionais para destinos de cookies](../../../features/destinations/cookie-destination-options.md).  Para integrações de servidor a servidor, recomendamos usar um domínio como `aam-api.com`. |
| `e` | O URL seguro que foi definido em um destino de URL. |
| `stuff` | Esse objeto contém informações para todos os destinos de Cookie. A lista deste objeto é dinâmica com base nas ações do usuário. |
| `tid` | ID da transação, que é uma ID exclusiva de 12 caracteres usada para fins de depuração. Cada chamada /event para o DCS recebe uma marcação que pode ser referenciada em pesquisas de suporte para obter uma resposta melhor e mais rápida. |
| `ttl` | O valor do tempo de vida do cookie em dias. |
| `u` e `uuid` | ID de usuário exclusiva atribuída pelo Audience Manager. Isso é necessário se você estiver fazendo [chamadas DCS de servidor para servidor](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Tipo de destino, iFrame (`iframe`) ou imagem (`img`). |

>[!MORELIKETHIS]
>
>* [Prefixos e variáveis de valor-chave compatíveis com o DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

