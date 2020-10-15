---
description: Informações sobre requisitos gerais, autenticação, parâmetros opcionais de consulta, URLs de solicitação e outras referências.
seo-description: Informações sobre requisitos gerais, autenticação, parâmetros opcionais de consulta, URLs de solicitação e outras referências.
seo-title: Introdução às REST APIs
solution: Audience Manager
title: Introdução às REST APIs
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
translation-type: tm+mt
source-git-commit: f7b9c30f120b24f9294afa4aa6727ce8c4236acf
workflow-type: tm+mt
source-wordcount: '1860'
ht-degree: 4%

---


# Getting Started with [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Information about general requirements, authentication, optional query parameters, request [!DNL URLs], and other references.

<!-- c_rest_api_overview.xml -->

## Requisitos da API e recomendações {#api-requirements-recommendations}

As coisas que você deve e deve fazer ao trabalhar com os [!DNL Audience Manager] [!DNL API]EUA.

<!-- aam-api-requirements.xml -->

Observe o seguinte ao trabalhar com o código da API [](https://bank.demdex.com/portal/swagger/index.html#/) Audience Manager:

* **Parâmetros de solicitação:** todos os parâmetros de solicitação são obrigatórios, a menos que especificado de outra forma.
* **Cabeçalhos** de solicitação: ao usar tokens de E/S [de](https://www.adobe.io/) Adobe, você deve fornecer o `x-api-key` cabeçalho. Você pode obter sua [!DNL API] chave seguindo as instruções na página Integração [da conta de](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) serviço.
* **[!DNL JSON]tipo de conteúdo:** Especifique `content-type: application/json` e *especifique* `accept: application/json` no seu código.
* **Solicitações e respostas:** Envie solicitações como um [!DNL JSON] objeto formatado corretamente. [!DNL Audience Manager] responde com dados [!DNL JSON] formatados. As respostas do servidor podem conter dados solicitados, um código de status ou ambos.
* **Acesso:** Seu [!DNL Audience Manager] consultor fornecerá uma ID de cliente e uma chave que permite fazer [!DNL API] solicitações.
* **Documentação e amostras de código:** O texto em *itálico* representa uma variável fornecida ou transmitida ao criar ou receber [!DNL API] dados. Substitua o texto *em itálico* por seu próprio código, parâmetros ou outras informações necessárias.

## Autenticação {#authentication}

O [!DNL Audience Manager] [!DNL REST APIs] suporta dois métodos de autenticação.

* [Autenticação](#jwt) JWT (Conta de serviço) usando E/S [Adobe](https://www.adobe.io/). [!DNL Adobe I/O] é o ecossistema e a comunidade do Adobe. Ele inclui as ferramentas do desenvolvedor de E/S do [Adobe, APIs](https://www.adobe.io/apis/experienceplatform.html) e [APIs para todos os produtos](https://www.adobe.io/apis.html)do Adobe. Essa é a maneira recomendada de configurar e usar [!DNL Adobe][!DNL APIs].
* [Autenticação OAuth (obsoleta)](#oauth). Embora esse método esteja obsoleto, os clientes com [!DNL OAuth] integrações existentes podem continuar usando esse método.

>[!IMPORTANT]
>
>Dependendo do método de autenticação, é necessário ajustar a solicitação [!DNL URLs] de acordo. Consulte a seção [Ambientes](#environments) para obter detalhes sobre os nomes de host que você deve usar.

## [!DNL JWT] ([!DNL Service Account]) Autenticação usando E/S de Adobe {#jwt}

### Visão geral de E/S de Adobe {#adobeio}

[!DNL Adobe I/O] é o ecossistema e a comunidade do Adobe. Ele inclui as ferramentas do desenvolvedor de E/S do [Adobe, APIs](https://www.adobe.io/apis/experienceplatform.html) e [APIs para todos os produtos](https://www.adobe.io/apis.html)do Adobe.

Essa é a maneira recomendada de configurar e usar [!DNL Adobe][!DNL APIs].

### Pré-requisitos {#prerequisites}

Antes de configurar a [!DNL JWT] autenticação, verifique se você tem acesso ao [Adobe Developer Console](https://console.adobe.io/) em E/S [do](https://www.adobe.io/)Adobe. Entre em contato com o administrador da organização para obter informações sobre solicitações de acesso.

### Autenticação

Siga as etapas abaixo para configurar a [!DNL JWT (Service Account)] autenticação usando [!DNL Adobe I/O]:

1. Faça logon no [Adobe Developer Console](https://console.adobe.io/).
1. Siga as etapas em [Service Account Connection (Conexão](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)de conta de serviço).
   * Durante a [Etapa 2: Adicione uma API ao seu projeto usando a autenticação](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)da Conta de serviço, escolha a [!DNL Audience Manager] opção [!DNL API] .
1. Experimente a conexão fazendo sua primeira [!DNL API] chamada com base nas instruções da [Etapa 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Para configurar e trabalhar com o [!DNL Audience Manager] de maneira automatizada, é possível gerar o [!DNL REST APIs] [!DNL JWT] programa. Consulte Autenticação [](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) JWT (Conta de serviço) para obter instruções detalhadas.

## [!DNL OAuth] Autenticação (obsoleto) {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] a autenticação e a renovação do token via agora [!DNL OAuth 2.0] está obsoleta.
>
> Em vez disso, use a Autenticação [](#jwt-service-account-authentication-jwt) JWT (Conta de Serviço).

Os [!DNL Audience Manager] seguintes [!UICONTROL REST API] [!DNL OAuth 2.0] padrões para autenticação e renovação de token. As seções abaixo descrevem como autenticar e start trabalhando com os [!DNL API]s.

### Criar um [!DNL API] usuário genérico {#requirements}

Recomendamos que você crie uma conta de usuário técnica e separada para trabalhar com os [!DNL Audience Manager] [!DNL API]s. Esta é uma conta genérica que não está vinculada ou associada a um usuário específico em sua organização. Este tipo de conta de [!DNL API] usuário ajuda você a realizar duas coisas:

* Identifique o serviço que está chamando o [!DNL API] (por exemplo, chamadas de seus aplicativos que usam nossos [!DNL API]s ou de outras ferramentas que fazem [!DNL API] solicitações).
* Fornecer acesso ininterrupto aos [!DNL API]s. Uma conta vinculada a uma pessoa específica pode ser excluída quando ela deixar sua empresa. Isso impedirá que você trabalhe com o [!DNL API] código disponível. Uma conta genérica que não está vinculada a um determinado funcionário ajuda a evitar esse problema.

Como exemplo ou caso de uso para esse tipo de conta, digamos que você queira alterar muitos segmentos de uma só vez com as Ferramentas [de Gerenciamento em](../../reference/bulk-management-tools/bulk-management-intro.md)massa. Bem, para fazer isso, sua conta de usuário precisa de [!DNL API] acesso. Em vez de adicionar permissões a um usuário específico, crie uma conta de usuário não específica, [!DNL API] que tenha as credenciais, a chave e o segredo apropriados para fazer [!DNL API] chamadas. Isso também é útil se você desenvolver seus próprios aplicativos que usam os [!DNL Audience Manager] [!DNL API]s.

Entre em contato com seu [!DNL Audience Manager] consultor para configurar uma conta de usuário genérica e [!DNL API]exclusiva.

### Fluxo de trabalho da autenticação de senha {#password-authentication-workflow}

Autenticação de senha, acesso seguro a nossa [!DNL REST API]senha. As etapas abaixo descrevem o fluxo de trabalho para autenticação por senha de um [!DNL JSON] cliente em seu navegador.

>[!TIP]
>
>Criptografe o acesso e atualize os tokens se você armazená-los em um banco de dados.

#### Etapa 1: Solicitar [!DNL API] acesso

Entre em contato com seu gerente de soluções de parceiros. Eles fornecerão uma ID de [!DNL API] cliente e um segredo. A ID e o segredo autenticam você no [!DNL API].

Observação: Se você quiser receber um token de atualização, especifique-o ao solicitar [!DNL API] acesso.

#### Etapa 2: Solicite o token

Transmita uma solicitação de token com seu [!DNL JSON] cliente preferencial. Quando você cria a solicitação:

* Use um `POST` método para chamar `https://api.demdex.com/oauth/token`.
* Converta a ID do cliente e o segredo em uma string codificada em base 64. Separe a ID e o segredo com dois pontos durante o processo de conversão. Por exemplo, as credenciais são `testId : testSecret` convertidas em `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Passe para dentro [!DNL HTTP] [!DNL headers] e `Authorization:Basic <base-64 clientID:clientSecret>` `Content-Type: application/x-www-form-urlencoded` . Por exemplo, seu cabeçalho pode ser semelhante a: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Configure o corpo da solicitação da seguinte maneira:
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Etapa 3: Receber o token

A [!DNL JSON] resposta contém seu token de acesso. A resposta deve ser parecida com esta:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

A `expires_in` chave representa o número de segundos até que o token de acesso expire. Como prática recomendada, use tempos de expiração curtos para limitar a exposição se o token for exposto.

### Atualizar token {#refresh-token}

Atualizar tokens renovam o [!DNL API] acesso após o token original expirar. Se solicitado, a resposta [!DNL JSON] no fluxo de trabalho de senha inclui um token de atualização. Se você não receber um token de atualização, crie um novo pelo processo de autenticação de senha.

Você também pode usar um token de atualização para gerar um novo token antes que o token de acesso existente expire.

Se o token de acesso tiver expirado, você receberá um cabeçalho `401 Status Code` e o seguinte na resposta:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

As etapas a seguir descrevem o fluxo de trabalho para usar um token de atualização para criar um novo token de acesso a partir de um [!DNL JSON] cliente em seu navegador.

#### Etapa 1: Solicitar o novo token

Passe uma solicitação de token de atualização com o seu [!DNL JSON] cliente preferencial. Quando você cria a solicitação:

* Use um `POST` método para chamar `https://api.demdex.com/oauth/token`.
* Converta a ID do cliente e o segredo em uma string codificada em base 64. Separe a ID e o segredo com dois pontos durante o processo de conversão. Por exemplo, as credenciais são `testId : testSecret` convertidas em `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Transmita os cabeçalhos HTTP `Authorization:Basic <base-64 clientID:clientSecret>` e `Content-Type: application/x-www-form-urlencoded`. Por exemplo, seu cabeçalho pode ser semelhante a: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* No corpo da solicitação, especifique o token de atualização `grant_type:refresh_token` e passe-o na solicitação de acesso anterior. A solicitação deve ser parecida com esta: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Etapa 2: Receber o novo token

A [!DNL JSON] resposta contém seu novo token de acesso. A resposta deve ser parecida com esta:

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

### Código de autorização e autenticação implícita {#authentication-code-implicit}

O [!DNL Audience Manager] [!UICONTROL REST API] oferece suporte ao código de autorização e à autenticação implícita. Para usar esses métodos de acesso, os usuários precisam fazer logon para obter acesso e atualizar tokens `https://api.demdex.com/oauth/authorize` para que possam acessá-los.

## Fazer [!DNL API] solicitações autenticadas {#authenticated-api-requests}

Requisitos para chamar [!DNL API] métodos depois de receber um token de autenticação.

Para efetuar chamadas em relação aos [!DNL API] métodos disponíveis:

* No `HTTP` cabeçalho, defina `Authorization: Bearer <token>`.
* Ao usar a Autenticação [](#jwt)JWT (Conta de serviço), é necessário fornecer o `x-api-key` cabeçalho, que será o mesmo de sua `client_id`. Você pode obter o seu `client_id` da página de integração [de E/S do](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) Adobe.
* Chame o [!DNL API] método necessário.

## Parâmetros de [!DNL API] Query opcionais {#optional-api-query-parameters}

Defina os parâmetros opcionais disponíveis para métodos que retornam todas as propriedades de um objeto.

Você pode usar esses parâmetros opcionais com [!DNL API] métodos que retornam *todas* as propriedades de um objeto. Defina essas opções na string de solicitação ao passar esse query para o [!DNL API].

| Parâmetro | Descrição |
|--- |--- |
| `page` | Retorna os resultados por número de página. Numerando start em 0. |
| `pageSize` | Define o número de resultados de resposta retornados pela solicitação (10 é padrão). |
| `sortBy` | Classifica e retorna os resultados de acordo com a [!DNL JSON] propriedade especificada. |
| `descending` | Classifica e retorna os resultados em ordem decrescente. `ascending` é padrão. |
| `search` | Retorna os resultados com base na string especificada que você deseja usar como parâmetro de pesquisa. Por exemplo, digamos que você queira encontrar resultados para todos os modelos que têm a palavra &quot;Teste&quot; em qualquer um dos campos de valor desse item. Sua solicitação de amostra pode ser semelhante a:   `GET https://aam.adobe.io/v1/models/?search=Test`.  Você pode pesquisar qualquer valor retornado por um método &quot;[!DNL get all]&quot;. |
| `folderId` | Retorna todas as IDs para [!UICONTROL traits] dentro da pasta especificada. Não disponível para todos os métodos. |
| `permissions` | Retorna uma lista de segmentos com base na permissão especificada. `READ` é padrão. As permissões incluem:<ul><li>`READ` : Informações de retorno e visualização sobre um segmento.</li><li>`WRITE` : Use `PUT` para atualizar um segmento.</li><li>`CREATE` : Use `POST` para criar um segmento.</li><li>`DELETE` : Excluir um segmento. Requer acesso às características subjacentes, se houver. Por exemplo, você precisará de direitos para excluir as características que pertencem a um segmento se desejar removê-lo.</li></ul><br>Especifique várias permissões com pares separados de valores chave. Por exemplo, para retornar uma lista de segmentos somente com `READ` e `WRITE` permissões, passe `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) Defina como `true` retornar suas permissões para o segmento. O padrão é `false`. |

### Uma observação sobre as opções da página

Quando as informações da página não *são especificadas, a solicitação retorna* [!DNL JSON] resultados simples em uma matriz. Se as informações da página *forem* especificadas, a lista retornada será encapsulada em um [!DNL JSON] objeto que contém informações sobre o resultado total e a página atual. Sua solicitação de amostra usando opções de página pode ser semelhante a esta:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] para solicitações, ambientes de preparo e produção e versões.

## Solicitação [!DNL URLs] {#request-urls}

A tabela a seguir lista a solicitação usada para passar [!DNL URLs] [!DNL API] solicitações, por método.

Dependendo do método de autenticação usado, é necessário ajustar sua solicitação de [!DNL URLs] acordo com as tabelas abaixo.

### Solicitação [!DNL URLs] de [!DNL JWT] autenticação {#request-urls-jwt}

| [!DNL API] Métodos | Solicitação [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | Características:  `https://aam.adobe.io/v1/folders/traits /`<br>Segmentos:  `https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

### Solicitação [!DNL URLs] de [!DNL OAuth] autenticação (obsoleto) {#request-urls-oauth}

| [!DNL API] Métodos | Solicitação [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | Características:  `https://api.demdex.com/v1/folders/traits /`<br>Segmentos:  `https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

## Ambientes {#environments}

Os [!DNL Audience Manager] [!DNL API]s fornecem acesso a diferentes ambientes de trabalho. Esses ambientes ajudam você a testar o código em bancos de dados separados sem afetar os dados de produção ao vivo. A tabela a seguir lista os [!DNL API] ambientes disponíveis e os nomes dos hosts de recursos correspondentes.

Dependendo do método de autenticação usado, é necessário ajustar o ambiente de acordo [!DNL URLs] com a tabela abaixo.

| Ambiente | Nome do host para [!DNL JWT] autenticação | Nome do host para [!DNL OAuth] autenticação |
|---|---|---|
| **Produção** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>O ambiente [!DNL Audience Manager] beta é uma versão independente e de menor escala do ambiente de produção. Todos os dados que você deseja testar devem ser inseridos e coletados neste ambiente.

## Versões {#versions}

Novas versões desses [!DNL API]s são lançadas regularmente. Uma nova versão incrementa o número da [!DNL API] versão. O número da versão é referenciado na solicitação [!DNL URL] como mostrado `v<version number>` no exemplo a seguir:

`https://<host>/v1/...`

## Códigos de resposta definidos {#response-codes-defined}

`HTTP` códigos de status e texto de resposta retornados pelo [!DNL Audience Manager][!UICONTROL REST API].

| ID do código de resposta | Texto de resposta | Definição |
|---|---|---|
| `200` | `OK` | A solicitação foi processada com êxito. Retornará o conteúdo ou os dados esperados, se necessário. |
| `201` | `Created` | O recurso foi criado. Retorna para `PUT` e `POST` solicitações. |
| `204` | `No Content` | O recurso foi excluído. O corpo da resposta ficará em branco. |
| `400` | `Bad Request` | O servidor não entendeu a solicitação. Geralmente devido a sintaxe malformada. Verifique sua solicitação e tente novamente. |
| `403` | `Forbidden` | Você não tem acesso ao recurso. |
| `404` | `Not Found` | Não foi possível localizar o recurso para o caminho especificado. |
| `409` | `Conflict` | Não foi possível concluir a solicitação devido a um conflito com o estado do recurso. |
| `500` | `Server Error` | O servidor encontrou um erro inesperado que o impedia de atender à solicitação. |

>[!MORELIKETHIS]
>
>* [Autenticação JWT (Conta de Serviço)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [Autenticação OAuth](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 simplificado](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

