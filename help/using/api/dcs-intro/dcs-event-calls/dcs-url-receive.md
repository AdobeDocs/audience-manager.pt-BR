---
description: Continue aqui para obter informações sobre como solicitar uma resposta DCS em uma chamada /event. Esta seção inclui um exemplo de resposta e definições para elementos de dados comuns em uma resposta.
seo-description: Continue aqui para obter informações sobre como solicitar uma resposta DCS em uma chamada /event. Esta seção inclui um exemplo de resposta e definições para elementos de dados comuns em uma resposta.
seo-title: Receber dados do DCS
solution: Audience Manager
title: Receber dados do DCS
uuid: fbb77197-8530-48a8-b708-d785f7214494
translation-type: tm+mt
source-git-commit: bc2a9364b771436fe0191f9d69a8c291563f9229

---


# Receber dados do DCS {#receive-data-from-the-dcs}

Continue aqui para obter informações sobre como solicitar uma [!UICONTROL DCS] resposta em uma `/event` chamada. Esta seção inclui um exemplo de resposta e definições para elementos de dados comuns em uma resposta.

Antes de revisar esse conteúdo, consulte [Enviar dados para o DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## Parâmetros de resposta do DCS: Uma revisão {#dcs-response-parameters}

Sua [!UICONTROL DCS] solicitação deve incluir `d_rtbd=json` se você deseja receber uma resposta do [!UICONTROL DCS]. Os dados não [!UICONTROL DCS] retornarão se você omitir esse parâmetro. Uma chamada básica para solicitar dados usa [!UICONTROL DCS] esta sintaxe:

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Resposta de exemplo {#sample-response}

Lembre-se de que da documentação [Enviar dados para o DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) , a empresa ficcional [!DNL Acme, Inc.] fez esta chamada:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Como essa chamada inclui o parâmetro de resposta necessário, o [!UICONTROL DCS] enviou de volta o [!DNL JSON] objeto mostrado abaixo. O seu pode ser semelhante ou mais complexo.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Parâmetros de resposta {#response-parameters}

A tabela abaixo lista e define os parâmetros mais comuns que você pode ver em uma resposta do [!UICONTROL DCS]. Isso se aplica a chamadas de evento ou outras [!UICONTROL DCS] [!DNL API] consultas que retornam dados.

| Parâmetro | Descrição |
|--- |--- |
| `c` | Um URL que foi definido como um destino [de](../../../features/destinations/create-url-destination.md)URL. |
| `cn` | O nome ou ID definido no campo de nome do cookie de um destino [de](../../../features/destinations/create-cookie-destination.md)cookie. |
| `cv` | Os valores enviados para o destino definido pelo parâmetro "cn": nome do destino". |
| `dcs_region` | As chamadas [DCS](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)servidor a servidor. |
| `dests` | Este objeto contém informações para todos os destinos de URL configurados na interface do usuário. A lista desse objeto é dinâmica com base nas ações do usuário. |
| `dmn` | Este é o domínio especificado no campo Domínio do cookie para um destino de cookie. Consulte Configurações [opcionais para destinos](../../../features/destinations/cookie-destination-options.md)de cookies.  Para integrações de Servidor a Servidor, recomendamos usar um domínio como `aam-api.com`. |
| `e` | O URL seguro que foi definido em um destino de URL. |
| `stuff` | Este objeto contém informações para todos os destinos de cookies. A lista desse objeto é dinâmica com base nas ações do usuário. |
| `tid` | ID de transação, que é uma ID exclusiva de 12 caracteres usada para fins de depuração. Cada /chamada de evento para o DCS recebe uma marcação que pode ser referenciada em pesquisas de suporte para obter uma resposta melhor e mais rápida. |
| `ttl` | O valor do tempo de vida do cookie em dias. |
| `u` e `uuid` | ID de usuário exclusiva atribuída pelo Audience Manager. Isso é necessário se você estiver realizando chamadas [](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)DCS de servidor para servidor. |
| `y` | Tipo de destino, iFrame (`iframe`) ou imagem (`img`). |

>[!MORE_LIKE_THIS]
>
>* [Prefixos e variáveis de valor-chave suportados pelo DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

