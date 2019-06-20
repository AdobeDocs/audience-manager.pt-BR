---
description: Ao publicar segmentos no destino do parceiro por meio de uma integração de servidor a servidor em tempo real, o Audience Manager pode ser configurado para autenticação usando oauth 2.0 ao fazer as solicitações. Isso apresenta a capacidade de emitir solicitações autenticadas do Audience Manager para o terminal.
seo-description: Ao publicar segmentos no destino do parceiro por meio de uma integração de servidor a servidor em tempo real, o Audience Manager pode ser configurado para autenticação usando oauth 2.0 ao fazer as solicitações. Isso apresenta a capacidade de emitir solicitações autenticadas do Audience Manager para o terminal.
seo-title: Integração do oauth 2.0 para transferências de saída em tempo real
solution: Audience Manager
title: Integração do oauth 2.0 para transferências de saída em tempo real
uuid: a 39 e 370 c-b 3 bd -4 b 06-a 1 af -60 a 024 ee 7 ee 4
translation-type: tm+mt
source-git-commit: 1cc8afd25331528fd67922183b6550288b9939bc

---


# [!DNL OAuth 2.0] Integração para transferências de saída em tempo real{#oauth-integration-for-real-time-outbound-transfers}

When publishing segments to the partner destination via a realtime server-to-server integration, Audience Manager can be set up to authenticate using [!DNL OAuth 2.0] when making the requests. Isso apresenta a capacidade de emitir solicitações autenticadas do Audience Manager para o terminal.

## Authentication Flow {#auth-flow}

The [!DNL Adobe Audience Manager] [OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4) authentication implementation is based on the Client Credentials grant flow and follows these steps:

1. Você deve fornecer:
   * The [!DNL OAuth 2.0] endpoint that generates the authentication token.
   * As credenciais usadas para gerar um token.
1. An [!DNL Audience Manager] consultant sets up the [destination](../../../features/destinations/destinations.md) using the information you provided.
1. Once a segment is mapped to this destination, our real-time data transfer system, [IRIS](../../../reference/system-components/components-data-action.md#iris), makes a `POST` request to the token endpoint to exchange the credentials for a bearer token.
1. For each segment publishing request to the partner endpoint, [!UICONTROL IRIS] uses the bearer token to authenticate.

![](assets/oauth2-iris.png)

## Exigências {#auth-requirements}

As an [!DNL Audience Manager] partner, the following endpoints are needed to receive authenticated requests:

### Endpoint 1 usado pela íris para obter um token de atendimento

Esse terminal aceitará as credenciais fornecidas na etapa 1 e gerará um token de sinal que será usado em solicitações subsequentes.

* The endpoint must accept `HTTP POST` requests.
* The endpoint must accept and look at the [!DNL Authorization] header. The value for this header will be: `Basic <credentials_provided_by_partner>`.
* The endpoint must look at the [!DNL Content-type] header and validate that its value is `application/x-www-form-urlencoded ; charset=UTF-8`.
* The body of the request will be `grant_type=client_credentials`.

### Exemplo de solicitação feita pelo Audience Manager ao endpoint do parceiro para obter um token de portador

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

### Exemplo de resposta do endpoint do parceiro

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### Endpoint 2 usado pela íris para publicar segmentos usando o token do bearer

[!DNL Audience Manager] envia dados para esse endpoint em tempo próximo à medida que usuários se qualificam para segmentos. Além disso, esse método pode enviar lotes de dados offline ou integrados com frequência a cada 24 horas.

O token do bearer gerado pelo endpoint 1 é usado para emitir solicitações para esse endpoint. The [!DNL Audience Manager] real-time data transfer system, [IRIS](../../../reference/system-components/components-data-action.md#iris), constructs a normal HTTPS request and includes an Authorization header. The value for this header will be: Bearer `<bearer token from step 1>`.

### Exemplo de resposta do endpoint do parceiro

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
>Esta solicitação contém uma carga padrão (conteúdo de solicitação).

## Important Considerations {#considerations}

### Tokens são senhas

The credentials presented by the partner and the tokens obtained by [!DNL Audience Manager] when authenticating using the [!DNL OAuth 2.0] flow, are sensitive information and must not be shared with third parties.

### [!DNL SSL] é obrigatório

[!DNL SSL] deve ser usado para manter um processo de autenticação seguro. All requests, including the ones used to obtain and use the tokens must use `HTTPS` endpoints.