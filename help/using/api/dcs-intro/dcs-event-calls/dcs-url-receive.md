---
description: Continue aqui para obter informações sobre como solicitar uma resposta do DCS em uma chamada /event. Esta seção inclui um exemplo de resposta e definições de elementos de dados comuns em uma resposta.
seo-description: Continue here for information about how to request a DCS response in a /event call. This section includes a response example and definitions for common data elements in a response.
seo-title: Receive Data From the DCS
solution: Audience Manager
title: Receber dados do DCS
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
exl-id: c6a87e5a-63cc-44d7-b6f0-ac8ee845fd00
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 1%

---

# Receber dados do DCS {#receive-data-from-the-dcs}

Continue aqui para obter informações sobre como solicitar uma resposta do [!DNL DCS] em uma chamada do `/event`. Esta seção inclui um exemplo de resposta e definições de elementos de dados comuns em uma resposta.

Antes de revisar este conteúdo, consulte [Enviar Dados para o DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## Parâmetros de resposta do DCS: uma revisão {#dcs-response-parameters}

Sua solicitação [!DNL DCS] deve incluir `d_rtbd=json` se você deseja receber uma resposta de [!DNL DCS]. O [!DNL DCS] não retornará dados se você omitir esse parâmetro. Uma chamada básica para [!DNL DCS] para solicitar dados usa esta sintaxe:

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Resposta de exemplo {#sample-response}

Lembre-se que, na documentação [Enviar Dados para o DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md), a empresa fictícia [!DNL Acme, Inc.] fez esta chamada:

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

A tabela abaixo lista e define os parâmetros mais comuns que você pode ver em uma resposta do [!DNL DCS]. Isso se aplica a chamadas de evento ou outras consultas [!DNL DCS] [!DNL API] que retornam dados.

| Parâmetro | Descrição |
|--- |--- |
| `c` | Uma URL que foi definida como um [destino de URL](../../../features/destinations/create-url-destination.md). |
| `cn` | O nome ou a ID definida no campo de nome do cookie de um [destino de cookie](../../../features/destinations/create-cookie-destination.md). |
| `cv` | Os valores enviados para o destino definido pelo parâmetro &quot;cn&quot;:&quot; destination name&quot;. |
| `dcs_region` | As [chamadas DCS de servidor para servidor](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Esse objeto contém informações para todos os destinos de URL configurados na interface do. A lista deste objeto é dinâmica com base nas ações do usuário. |
| `dmn` | Esse é o domínio especificado no campo Domínio do cookie para um destino de cookie. Consulte [Configurações Opcionais para Destinos de Cookies](../../../features/destinations/cookie-destination-options.md).  Para integrações Servidor a Servidor, recomendamos usar um domínio como o `aam-api.com`. |
| `e` | O URL seguro que foi definido em um destino de URL. |
| `stuff` | Este objeto contém informações para todos os destinos de Cookie. A lista deste objeto é dinâmica com base nas ações do usuário. |
| `tid` | A ID de transação, que é uma ID exclusiva de 12 caracteres usada para fins de depuração. Cada chamada /event para o DCS recebe uma tid que pode ser referenciada em consultas de suporte para obter uma resposta melhor e mais rápida. |
| `ttl` | O valor do tempo de vida útil do cookie em dias. |
| `u` e `uuid` | ID de usuário exclusiva atribuída pela Audience Manager. Isso é necessário se você estiver fazendo [chamadas de DCS de servidor para servidor](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Tipo de destino, iFrame (`iframe`) ou imagem (`img`). |

>[!MORELIKETHIS]
>
>* [Prefixos e Variáveis de Valor-Chave com Suporte do DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
