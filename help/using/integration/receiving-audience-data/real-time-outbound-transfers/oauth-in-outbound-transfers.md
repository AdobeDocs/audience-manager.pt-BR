---
description: Ao publicar segmentos no destino do parceiro por meio de uma integração de servidor para servidor em tempo real, o Audience Manager pode ser configurado para autenticação usando o OAuth 2.0 ao fazer as solicitações. Isso apresenta a capacidade de emitir solicitações autenticadas do Audience Manager para o terminal.
seo-description: Ao publicar segmentos no destino do parceiro por meio de uma integração de servidor para servidor em tempo real, o Audience Manager pode ser configurado para autenticação usando o OAuth 2.0 ao fazer as solicitações. Isso apresenta a capacidade de emitir solicitações autenticadas do Audience Manager para o terminal.
seo-title: Integração do OAuth 2.0 para transferências de saída em tempo real
solution: Audience Manager
title: Integração do OAuth 2.0 para transferências de saída em tempo real
uuid: a39e370c-b3bd-4b06-a1af-60a024ee7ee4
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 2%

---


# [!DNL OAuth 2.0] Integração para transferências de saída em tempo real{#oauth-integration-for-real-time-outbound-transfers}

Ao publicar segmentos no destino do parceiro por meio de uma integração de servidor para servidor em tempo real, o Audience Manager pode ser configurado para autenticação usando [!DNL OAuth 2.0] ao fazer as solicitações. Isso apresenta a capacidade de emitir solicitações autenticadas do Audience Manager para o terminal.

## Fluxo de autenticação {#auth-flow}

A implementação de autenticação [!DNL Adobe Audience Manager] [OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4) baseia-se no fluxo de concessão de Credenciais do Cliente e segue estas etapas:

1. Você deve nos fornecer:
   * O terminal [!DNL OAuth 2.0] que gera o token de autenticação.
   * As credenciais usadas para gerar um token.
1. Um consultor [!DNL Audience Manager] configura [destino](../../../features/destinations/destinations.md) usando as informações fornecidas.
1. Quando um segmento é mapeado para esse destino, nosso sistema de transferência de dados em tempo real, [IRIS](../../../reference/system-components/components-data-action.md#iris), faz uma solicitação `POST` ao ponto final do token para trocar as credenciais por um token do portador.
1. Para cada solicitação de publicação de segmento ao terminal do parceiro, [!UICONTROL IRIS] usa o token do portador para autenticação.

![](assets/oauth2-iris.png)

## Requisitos {#auth-requirements}

Como parceiro [!DNL Audience Manager], os seguintes pontos finais são necessários para receber solicitações autenticadas:

### Ponto de extremidade 1 usado pelo IRIS para obter um token do portador

Esse terminal aceitará as credenciais fornecidas na etapa 1 e gerará um token de portador que será usado em solicitações subsequentes.

* O ponto de extremidade deve aceitar solicitações `HTTP POST`.
* O ponto de extremidade deve aceitar e observar o cabeçalho [!DNL Authorization]. O valor deste cabeçalho será: `Basic <credentials_provided_by_partner>`.
* O ponto de extremidade deve observar o cabeçalho [!DNL Content-type] e validar se seu valor é `application/x-www-form-urlencoded ; charset=UTF-8`.
* O corpo da solicitação será `grant_type=client_credentials`.

### Exemplo de solicitação feita pelo Audience Manager para o ponto de extremidade do parceiro para obter um token do portador

```
POST /oauth2/token HTTP/1.1
Host: api.partner.com
User-Agent: Adobe Audience Manager Iris
Authorization: Basic zq2LOO1CcYGrODS5nXiNHpEz97eCpVHAoMF8pAgCntXAzxp5uRV7DTAE2qtPLjhMQwrEX3O6MHV4S
Content-Type: application/x-www-form-urlencoded;charset=UTF-8
Content-Length: 29
Accept-Encoding: gzip
  
grant_type=client_credentials
```

### Exemplo de resposta do ponto de extremidade do parceiro

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### Ponto de extremidade 2 usado pelo IRIS para publicar segmentos usando o token do portador

[!DNL Audience Manager] envia dados para esse terminal em tempo quase real, à medida que os usuários se qualificam para segmentos. Além disso, esse método pode enviar lotes de dados offline ou integrados com uma frequência de até 24 horas.

O token do portador gerado pelo ponto de extremidade 1 é usado para emitir solicitações para esse ponto de extremidade. O [!DNL Audience Manager] sistema de transferência de dados em tempo real, [IRIS](../../../reference/system-components/components-data-action.md#iris), constrói uma solicitação HTTPS normal e inclui um cabeçalho de Autorização. O valor deste cabeçalho será: Portador `<bearer token from step 1>`.

### Exemplo de resposta do ponto de extremidade do parceiro

```
GET /segments/aam HTTP/1.1
Host: api.partner.com
User-Agent: Adobe Audience Manager Iris
Authorization: Bearer glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY
Content-Type: application/json
Accept-Encoding: gzip
   
{
"ProcessTime": "Wed Jul 27 16:17:42 UTC 2016",
"User_DPID": "12345",
"Client_ID": "74323",
"AAM_Destination_Id": "423",
"User_count": "2",
"Users": [{
   "AAM_UUID": "19393572368547369350319949416899715727",
   "DataPartner_UUID": "4250948725049857",
   "Segments": [{
            "Segment_ID": "14356",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         }
      ]
   }]
}
```

>[!NOTE]
>
>Essa solicitação contém uma carga padrão (conteúdo da solicitação).

## Considerações importantes {#considerations}

### Tokens são senhas

As credenciais apresentadas pelo parceiro e os tokens obtidos por [!DNL Audience Manager] ao autenticar usando o fluxo [!DNL OAuth 2.0] são informações confidenciais e não devem ser compartilhados com terceiros.

### [!DNL SSL] é obrigatório

[!DNL SSL] deve ser usada para manter um processo de autenticação seguro. Todas as solicitações, incluindo as usadas para obter e usar os tokens, devem usar os pontos finais `HTTPS`.