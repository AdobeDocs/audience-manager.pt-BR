---
description: Informações sobre requisitos gerais, autenticação, parâmetros de consulta opcionais, urls de solicitação e outras referências.
seo-description: Informações sobre requisitos gerais, autenticação, parâmetros de consulta opcionais, urls de solicitação e outras referências.
seo-title: Introdução à REST apis
solution: Audience Manager
title: Introdução à REST apis
uuid: af 0 e 527 e -6 eec -449 c -9709-f 90 e 57 cd 188 d
translation-type: tm+mt
source-git-commit: 27800ce003a62733eece0d5de3b94737ed61133a

---


# Getting Started with REST APIs {#getting-started-with-rest-apis}

Informações sobre requisitos gerais, autenticação, parâmetros de consulta opcionais, urls de solicitação e outras referências.

<!-- c_rest_api_overview.xml -->

## API Requirements and Recommendations {#api-requirements-recommendations}

Things you must and should do when working with the Audience Manager [!DNL API]s.

<!-- aam-api-requirements.xml -->

Note the following when working with [Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#/) code:

* **Solicitar parâmetros:** Todos os parâmetros de solicitação são necessários, a menos que especificados caso contrário.
* **[!DNL JSON]tipo de conteúdo:** Especifique `content-type: application/json`*e* `accept: application/json` no código.

* **Solicitações e respostas:** Envie solicitações como um objeto formatado [!DNL JSON] corretamente. [!DNL Audience Manager] responde com [!DNL JSON] dados formatados. As respostas do servidor podem conter dados solicitados, um código de status ou ambos.

* **Acesso:** Seu [!DNL Audience Manager] consultor fornecerá uma ID de cliente e uma chave que permitem [!DNL API] fazer solicitações.

* **Documentação e amostras de código:** O texto em *itálico* representa uma variável que você fornece ou passa ao fazer ou receber [!DNL API] dados. Replace *italicised* text with your own code, parameters, or other required information.

## Recommendations: Create a Generic API User {#requirements}

We recommend you create a separate, technical user account for working with the Audience Manager [!DNL API]s. This is a generic account that is not tied to or associated with a specific user in your organization. This type of [!DNL API] user account helps you accomplish 2 things:

* Identify what service is calling the [!DNL API] (e.g., calls from your apps that use our [!DNL API]s or from other tools that make [!DNL API] requests).
* Provide uninterrupted access to the [!DNL API]s. An account tied to a specific person may be deleted when they leave your company. This will prevent you from working with the available [!DNL API] code. Uma conta genérica que não está vinculada a um determinado funcionário ajuda você a evitar esse problema.

As an example or use case for this type of account, let&#39;s say you want to change a lot of segments at once with the [Bulk Management Tools](../../reference/bulk-management-tools/bulk-management-intro.md). Well, to do this, your user account needs [!DNL API] access. Rather than add permissions to a specific user, create a non-specific, [!DNL API] user account that has the appropriate credentials, key, and secret to make [!DNL API] calls. This is also useful if you develop your own applications that use the Audience Manager [!DNL API]s.

Work with your Audience Manager consultant to set up a generic, [!DNL API]-only user account.

## OAuth Authentication {#oauth}

The Audience Manager [!UICONTROL REST API] follows [!DNL OAuth 2.0] standards for token authentication and renewal. The sections below describe how to authenticate and start working with the [!DNL API]s.

## Password Authentication Workflow {#password-authentication-workflow}

<!-- oath-authentication.xml -->

Password authentication secure access our [!DNL REST API]. The steps below outline the workflow for password authentication from a [!DNL JSON] client in your browser.

>[!TIP]
>
>Criptografar acesso e atualizar tokens se você os armazena em um banco de dados.

### Etapa 1: Acesso à API de solicitação

Entre em contato com o gerenciador de Soluções do parceiro. They will provide you with an [!DNL API] client ID and secret. The ID and secret authenticate you to the [!DNL API].

Note: If you&#39;d like to receive a refresh token, specify that when you request [!DNL API] access.

### Etapa 2: Solicitar o token

Pass in a token request with your preferred [!DNL JSON] client. Ao criar a solicitação:

* Use a `POST` method to call `https://api.demdex.com/oauth/token`.
* Converta a ID do cliente e o segredo em uma string codificada de base 64. Separe a ID e o segredo com um dois pontos durante o processo de conversão. For example, the credentials `testId : testSecret` convert to `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pass in the [!DNL HTTP] headers `Authorization:Basic <base-64 clientID:clientSecret>` and `Content-Type: application/x-www-form-urlencoded` . For example, your header could look like this: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Configure o corpo da solicitação da seguinte maneira:
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

### Etapa 3: Receber o token

[!DNL JSON] A resposta contém seu token de acesso. A resposta deve ser desta forma:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

`expires_in` A chave representa o número de segundos até que o token de acesso expire. Como prática recomendada, use tempos de expiração curtos para limitar a exposição se o token estiver exposto.

## Refresh Token {#refresh-token}

Refresh tokens renew [!DNL API] access after the original token expires. If requested, the response [!DNL JSON] in the password workflow includes a refresh token. Se você não receber um token atualizado, crie um novo por meio do processo de autenticação de senha.

Também é possível usar um token atualizado para gerar um novo token antes que o token de acesso existente expire.

If your access token has expired, you receive a `401 Status Code` and the following header in the response:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

The following steps outline the workflow for using a refresh token to create a new access token from a [!DNL JSON] client in your browser.

### Etapa 1: Solicitar o novo token

Pass in a refresh token request with your preferred [!DNL JSON] client. Ao criar a solicitação:

* Use a `POST` method to call `https://api.demdex.com/oauth/token`.
* Converta a ID do cliente e o segredo em uma string codificada de base 64. Separe a ID e o segredo com um dois pontos durante o processo de conversão. For example, the credentials `testId : testSecret` convert to `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pass in the HTTP headers `Authorization:Basic <base-64 clientID:clientSecret>` and `Content-Type: application/x-www-form-urlencoded`. For example, your header could look like this: <br/> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/> `Content-Type: application/x-www-form-urlencoded`
* In the request body, specify the `grant_type:refresh_token` and pass in the refresh token you received in your previous access request. The request should look like this: <br/> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

### Etapa 2: Receber o novo token

[!DNL JSON] A resposta contém seu novo token de acesso. A resposta deve ser desta forma:

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

## Authorization Code and Implicit Authentication {#authentication-code-implicit}

The Audience Manager [!UICONTROL REST API] supports authorization code and implicit authentication. To use these access methods, your users need to log in to `https://api.demdex.com/oauth/authorize` to get access and refresh tokens.

>[!MORE_ LIKE_ THIS]
>
>* [Oauth 2.0](https://oauth.net/2/)
>* [Oauth 2 simplificado](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)


## Make Authenticated API Requests {#authenticated-api-requests}

Requirements for calling [!DNL API] methods after you receive an authentication token.

<!-- c_oauth_call_methods.xml -->

To make calls against the available [!DNL API] methods:

* In the `HTTP` header, set `Authorization: Bearer <token>`.
* Call the required [!DNL API] method.

>[!MORE_ LIKE_ THIS]
>
>* [Autenticação oauth](../../api/rest-api-main/aam-api-getting-started.md#oauth)


## Optional API Query Parameters {#optional-api-query-parameters}

Defina os parâmetros opcionais disponíveis para métodos que retornam todas as propriedades de um objeto.

<!-- c_rest_api_optional.xml -->

You can use these optional parameters with [!DNL API] methods that return *all* properties for an object. Set these options in the request string when passing that query in to the [!DNL API].

| Parâmetro | Descrição |
|--- |--- |
| página | Retorna os resultados por número de página. A numeração é iniciada em 0. |
| Pagesize | Define o número de resultados da resposta retornados pela solicitação (10 é padrão). |
| Sortby | Sorts and returns results according to the specified [!DNL JSON] property. |
| decrescente | Os resultados e retornos resultam em ordem decrescente. Crescente é padrão. |
| pesquisa | Retorna os resultados com base na sequência especificada que você deseja usar como um parâmetro de pesquisa. Por exemplo, digamos que você queira encontrar resultados para todos os modelos com a palavra &quot;Teste&quot; em qualquer um dos campos de valor desse item. Your sample request could look like this:   `GET https://api.demdex.com/v1/models/?search=Test`.  Você pode pesquisar qualquer valor retornado por um método &quot;get all&quot;. |
| Folderid | Retorna todas as IDs para características dentro da pasta especificada. Não disponível para todos os métodos. |
| permissões | Retorna uma lista de segmentos com base na permissão especificada. LIDO é padrão. As permissões incluem:<ul><li>`READ` : Retorne e visualize informações sobre um segmento.</li><li>`WRITE` : Use `PUT` para atualizar um segmento.</li><li>`CREATE` : Use `POST` para criar um segmento.</li><li>`DELETE` : Excluir um segmento. Requer acesso a características subjacentes, se houver. Por exemplo, você precisará de direitos para excluir as características que pertencem a um segmento, se desejar removê-lo.</li></ul><br>Especifique várias permissões com pares de valor chave separados. For example, to return a list of segments with  `READ`  and  `WRITE`  permissions only, pass in  `"permissions":"READ"`, `"permissions":"WRITE"` . |
| Includepermissions | (Booliano) Defina como verdadeiro para retornar suas permissões para o segmento. O padrão é falso. |

### Uma nota sobre opções de página

When page information *is not* specified, the request returns plain [!DNL JSON] results in an array. If page information *is* specified, then the returned list is wrapped in a [!DNL JSON] object that contains information about the total result and current page. A solicitação de amostra usando as opções de página pode ser semelhante a:

```
GET https://api.demdex.com/v1/models/?page=1&pageSize=2&search=Test
```

## URLs de API {#api-urls}

[!DNL URLs] para solicitações, ambientes de armazenamento temporário e produção e versões.

<!-- r_rest_urls.xml -->

## Request URLs {#request-urls}

The following table lists the request URLs used to pass in [!DNL API] requests, by method.

| [!DNL API] Métodos | Solicitação [!DNL URL] |
|--- |--- |
| Modelagem algorítmica | `https://api.demdex.com/v1/models/` |
| Fonte de dados | `https://api.demdex.com/v1/datasources/` |
| Sinais derivados | `https://api.demdex.com/v1/signals/derived/` |
| Destinos | `https://api.demdex.com/v1/destinations/` |
| Domínios | `https://api.demdex.com/v1/partner-sites/` |
| Pastas | Traits:  `https://api.demdex.com/v1/folders/traits /`<br>Segments:  `https://api.demdex.com/v1/folders/segments /` |
| Esquema | `https://api.demdex.com/v1/schemas/` |
| Segmentos | `https://api.demdex.com/v1/segments/` |
| Características | `https://api.demdex.com/v1/traits/` |
| Tipos de características | `https://api.demdex.com/v1/customer-trait-types` |
| Taxonomia | `https://api.demdex.com/v1/taxonomies/0/` |

## Environments {#environments}

[!DNL Audience Manager][!DNL API]Os s fornecem acesso a diferentes ambientes de trabalho. Esses ambientes ajudam você a testar o código contra bancos de dados separados sem afetar os dados ao vivo e produção. The following table lists the available [!DNL API] environments and corresponding resource hostnames.

| Ambiente | Nome de host |
|---|---|
| **Produção** | `https://api.demdex.com/...` |
| **Beta** | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>O ambiente beta do Audience Manager é uma versão em menor escala e independente do ambiente de produção. Todos os dados que você deseja testar devem ser inseridos e coletados neste ambiente.

## Versões {#versions}

New versions of these [!DNL API]s are released on a regular schedule. A new release increments the [!DNL API] version number. The version number is referenced in the request URL as `v<version number>` as shown in the following example:

`https://<host>/v1/...`

## Response Codes Defined {#response-codes-defined}

`HTTP` códigos de status e texto de resposta retornados pelo Audience Manager [!UICONTROL REST API].

<!-- r_api_http_response_codes.xml -->

| ID do código de resposta | Texto de resposta | Definição |
|---|---|---|
| 200 | OK | A solicitação processada com sucesso. Retornará o conteúdo esperado ou os dados, se necessário. |
| 201 | Criado | O recurso foi criado. Returns for `PUT` and `POST` requests. |
| 204 | Sem conteúdo | O recurso foi excluído. O corpo da resposta ficará em branco. |
| 400 | Solicitação inválida | O servidor não entendeu a solicitação. Normalmente, devido à sintaxe malformada. Verifique sua solicitação e tente novamente. |
| 403 | Proibido | Você não tem acesso ao recurso. |
| 404 | Não encontrada | O recurso não foi encontrado para o caminho especificado. |
| 409 | Conflito | A solicitação não pôde ser concluída devido a um conflito com o estado do recurso. |
| 500 | Erro do servidor | O servidor encontrou um erro inesperado que impedia o cumprimento da solicitação. |