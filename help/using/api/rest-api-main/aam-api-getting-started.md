---
description: Informações sobre requisitos gerais, autenticação, parâmetros opcionais de consulta, URLs de solicitação e outras referências.
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: Introdução às REST APIs
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 8bee593d0359f87f030840f87d70025dd5ea33ed
workflow-type: tm+mt
source-wordcount: '1910'
ht-degree: 3%

---

# Introdução ao [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Informações sobre requisitos gerais, autenticação, parâmetros de consulta opcionais, solicitação [!DNL URLs]e outras referências.

<!-- c_rest_api_overview.xml -->

## Requisitos da API e recomendações {#api-requirements-recommendations}

O que você deve e deve fazer ao trabalhar com a variável [!DNL Audience Manager] [!DNL API]s.

<!-- aam-api-requirements.xml -->

Observe o seguinte ao trabalhar com [API Audience Manager](https://bank.demdex.com/portal/swagger/index.html#/) código:

* **Parâmetros da solicitação:** todos os parâmetros de solicitação são necessários, a menos que especificado de outra forma.
* **Cabeçalhos de solicitação**: ao usar [Desenvolvedor de Adobe](https://www.adobe.io/) , você deve fornecer a variável `x-api-key` cabeçalho. Você pode obter seu [!DNL API] seguindo as instruções da [Integração de contas de serviço](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) página.
* **[!DNL JSON]tipo de conteúdo:** Especificar `content-type: application/json`  *e*  `accept: application/json` no seu código.
* **Solicitações e respostas:** Enviar solicitações como formatadas corretamente [!DNL JSON] objeto. [!DNL Audience Manager] responde com [!DNL JSON] dados formatados. As respostas do servidor podem conter dados solicitados, um código de status ou ambos.
* **Acesso:** Seu [!DNL Audience Manager] o consultor fornecerá a você uma ID do cliente e uma chave que permite [!DNL API] solicitações.
* **Documentação e amostras de código:** Texto em *itálico* representa uma variável fornecida ou transmitida ao criar ou receber [!DNL API] dados. Substituir *itálico* texto com seu próprio código, parâmetros ou outras informações necessárias.

## Autenticação {#authentication}

O [!DNL Audience Manager] [!DNL REST APIs] oferecem suporte para dois métodos de autenticação.

* [Autenticação JWT (Conta de Serviço)](#jwt) usar [Desenvolvedor de Adobe](https://www.adobe.io/). [!DNL Adobe Developer] é o ecossistema e a comunidade do Adobe. Inclui [APIs para todos os produtos Adobe](https://www.adobe.io/apis.html). Essa é a maneira recomendada de configurar e usar [!DNL Adobe] [!DNL APIs].
* [Autenticação OAuth (obsoleta)](#oauth). Embora esse método seja obsoleto, os clientes com [!DNL OAuth] as integrações podem continuar usando esse método.

>[!IMPORTANT]
>
>Dependendo do método de autenticação, é necessário ajustar a solicitação [!DNL URLs] em conformidade. Consulte a [Ambientes](#environments) para obter detalhes sobre os nomes de host que você deve usar.

## [!DNL JWT] ([!DNL Service Account]) Autenticação usando Adobe Developer {#jwt}

### Visão geral do desenvolvedor do Adobe {#adobeio}

[!DNL Adobe Developer] é o ecossistema e a comunidade do Adobe. Inclui [APIs para todos os produtos Adobe](https://www.adobe.io/apis.html).

Essa é a maneira recomendada de configurar e usar [!DNL Adobe] [!DNL APIs].

### Pré-requisitos {#prerequisites}

Antes de configurar [!DNL JWT] autenticação, certifique-se de ter acesso ao [Console do desenvolvedor do Adobe](https://console.adobe.io/) em [Desenvolvedor de Adobe](https://www.adobe.io/). Entre em contato com o administrador da organização para obter solicitações de acesso.

### Autenticação {#auth}

Siga as etapas abaixo para configurar [!DNL JWT (Service Account)] autenticação usando [!DNL Adobe Developer]:

1. Faça logon no [Console do desenvolvedor do Adobe](https://console.adobe.io/).
1. Siga as etapas em [Conexão da Conta de Serviço](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * Durante [Etapa 2: Adicionar uma API ao seu projeto usando a autenticação da conta de serviço](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), escolha o [!DNL Audience Manager] [!DNL API] opção.
1. Experimente a conexão fazendo a primeira [!DNL API] com base nas instruções de [Etapa 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Para configurar e trabalhar com a [!DNL Audience Manager] [!DNL REST APIs] de maneira automatizada, é possível gerar a variável [!DNL JWT] programaticamente. Consulte [Autenticação JWT (Conta de Serviço)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) para obter instruções detalhadas.

### Permissões RBAC de conta técnica

Se sua conta Audience Manager usar [Controle de acesso com base em função](../../features/administration/administration-overview.md), você deve criar uma conta de usuário técnica do Audience Manager e adicioná-la ao grupo RBAC do Audience Manager que fará as chamadas de API.

Siga as etapas abaixo para criar uma conta de usuário técnica e adicioná-la a um grupo RBAC:

1. Faça uma `GET` chamar para `https://aam.adobe.io/v1/users/self`. A chamada criará uma conta técnica de usuário que pode ser exibida na variável [!UICONTROL Admin Console]no [!UICONTROL Users] página.

   ![conta técnica](assets/technical-account.png)

1. Faça logon na sua conta do Audience Manager e [adicionar a conta técnica do usuário](../../features/administration/administration-overview.md#create-group) ao grupo de usuários que fará as chamadas de API.

## [!DNL OAuth] Autenticação (obsoleto) {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] autenticação e renovação de token via [!DNL OAuth 2.0] agora está obsoleta.
>
> Use [Autenticação JWT (Conta de Serviço)](#jwt-service-account-authentication-jwt) em vez disso.

O [!DNL Audience Manager] [!UICONTROL REST API] following [!DNL OAuth 2.0] padrões para autenticação e renovação de token. As seções abaixo descrevem como autenticar e começar a trabalhar com o [!DNL API]s.

### Criar um Genérico [!DNL API] Usuário {#requirements}

Recomendamos que você crie uma conta de usuário técnica e separada para trabalhar com a [!DNL Audience Manager] [!DNL API]s. Esta é uma conta genérica que não está vinculada ou associada a um usuário específico em sua organização. Esse tipo de [!DNL API] a conta de usuário ajuda você a realizar duas coisas:

* Identifique o serviço que está chamando a variável [!DNL API] (por exemplo, chamadas de seus aplicativos que usam nosso [!DNL API]ou de outras ferramentas [!DNL API] solicitações).
* Forneça acesso ininterrupto à [!DNL API]s. Uma conta vinculada a uma pessoa específica pode ser excluída ao sair da empresa. Isso impedirá que você trabalhe com os [!DNL API] código. Uma conta genérica não vinculada a um funcionário específico ajuda a evitar esse problema.

Como exemplo ou caso de uso para esse tipo de conta, digamos que você queira alterar muitos segmentos ao mesmo tempo com a variável [Ferramentas de gerenciamento em massa](../../reference/bulk-management-tools/bulk-management-intro.md). Para fazer isso, sua conta de usuário precisa [!DNL API] acesso. Em vez de adicionar permissões a um usuário específico, crie um [!DNL API] conta de usuário com credenciais, chave e segredo apropriados para fazer [!DNL API] chamadas . Isso também é útil se você desenvolver seus próprios aplicativos que usam o [!DNL Audience Manager] [!DNL API]s.

Trabalhe com seu [!DNL Audience Manager] consultor para configurar um genérico, [!DNL API]conta de usuário somente .

### Fluxo de trabalho de autenticação de senha {#password-authentication-workflow}

Autenticação de senha: acesso seguro à nossa [!DNL REST API]. As etapas abaixo destacam o fluxo de trabalho para autenticação de senha a partir de um [!DNL JSON] no seu navegador.

>[!TIP]
>
>Criptografe o acesso e atualize os tokens se você armazená-los em um banco de dados.

#### Etapa 1: Solicitação [!DNL API] Acesso

Entre em contato com o gerente de soluções de parceiros. Eles fornecerão uma [!DNL API] ID do cliente e segredo. A ID e o segredo o autenticam no [!DNL API].

Observação: Se quiser receber um token de atualização, especifique que quando solicitar [!DNL API] acesso.

#### Etapa 2: Solicitar o token

Envie uma solicitação de token com o seu [!DNL JSON] cliente. Ao criar a solicitação:

* Use um `POST` método para chamar `https://api.demdex.com/oauth/token`.
* Converta a ID do cliente e o segredo em uma string codificada em base 64. Separe a ID e o segredo com dois pontos durante o processo de conversão. Por exemplo, as credenciais `testId : testSecret` converter em `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Transmita o [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` e `Content-Type: application/x-www-form-urlencoded` . Por exemplo, o cabeçalho pode ter a seguinte aparência: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Configure o corpo da solicitação da seguinte maneira:
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Etapa 3: Receber o token

O [!DNL JSON] contém seu token de acesso. A resposta deve ser semelhante a esta:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

O `expires_in` representa o número de segundos até que o token de acesso expire. Como prática recomendada, use tempos de expiração curtos para limitar a exposição se o token for exposto.

### Atualizar Token {#refresh-token}

Renovar tokens [!DNL API] acesso após o token original expirar. Se solicitado, a resposta [!DNL JSON] no fluxo de trabalho da senha, inclui um token de atualização. Se você não receber um token de atualização, crie um novo por meio do processo de autenticação por senha.

Você também pode usar um token de atualização para gerar um novo token antes que o token de acesso existente expire.

Se o token de acesso tiver expirado, você receberá uma `401 Status Code` e o seguinte cabeçalho na resposta:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

As etapas a seguir descrevem o fluxo de trabalho para usar um token de atualização para criar um novo token de acesso a partir de um [!DNL JSON] no seu navegador.

#### Etapa 1: Solicitar o novo token

Envie uma solicitação de token de atualização com o seu [!DNL JSON] cliente. Ao criar a solicitação:

* Use um `POST` método para chamar `https://api.demdex.com/oauth/token`.
* Converta a ID do cliente e o segredo em uma string codificada em base 64. Separe a ID e o segredo com dois pontos durante o processo de conversão. Por exemplo, as credenciais `testId : testSecret` converter em `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Transmita os cabeçalhos HTTP `Authorization:Basic <base-64 clientID:clientSecret>` e `Content-Type: application/x-www-form-urlencoded`. Por exemplo, o cabeçalho pode ter a seguinte aparência: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* No corpo da solicitação, especifique o `grant_type:refresh_token` e transmitir o token de atualização recebido na solicitação de acesso anterior. A solicitação deve ter esta aparência: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Etapa 2: Receber o novo token

O [!DNL JSON] contém seu novo token de acesso. A resposta deve ser semelhante a esta:

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

O [!DNL Audience Manager] [!UICONTROL REST API] O suporta código de autorização e autenticação implícita. Para usar esses métodos de acesso, os usuários precisam fazer logon no para `https://api.demdex.com/oauth/authorize` para obter acesso e atualizar tokens.

## Tornar Autenticado [!DNL API] Solicitações {#authenticated-api-requests}

Requisitos para a chamada [!DNL API] métodos depois de receber um token de autenticação.

Para fazer chamadas em relação ao disponível [!DNL API] métodos:

* No `HTTP` cabeçalho, conjunto `Authorization: Bearer <token>`.
* Ao usar [Autenticação JWT (Conta de Serviço)](#jwt), é necessário fornecer a variável `x-api-key` , que será o mesmo que seu `client_id`. Você pode obter seu `client_id` do [Integração do desenvolvedor do Adobe](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) página.
* Chame o [!DNL API] método .

## Opcional [!DNL API] Parâmetros de consulta {#optional-api-query-parameters}

Defina os parâmetros opcionais disponíveis para métodos que retornam todas as propriedades de um objeto.

Você pode usar esses parâmetros opcionais com [!DNL API] métodos que retornam *all* propriedades de um objeto. Defina essas opções na cadeia de caracteres de solicitação ao passar essa consulta para o [!DNL API].

| Parâmetro | Descrição |
|--- |--- |
| `page` | Retorna os resultados por número de página. A numeração começa em 0. |
| `pageSize` | Define o número de resultados de resposta retornados pela solicitação (10 é o padrão). |
| `sortBy` | Classifica e retorna resultados de acordo com o especificado [!DNL JSON] propriedade. |
| `descending` | Classifica e retorna resultados em ordem decrescente. `ascending` é padrão. |
| `search` | Retorna resultados com base na string especificada que você deseja usar como parâmetro de pesquisa. Por exemplo, digamos que você queira encontrar resultados para todos os modelos que têm a palavra &quot;Teste&quot; em qualquer um dos campos de valor para esse item. Sua solicitação de amostra pode ter esta aparência:   `GET https://aam.adobe.io/v1/models/?search=Test`.  Você pode pesquisar qualquer valor retornado por um &quot;[!DNL get all]método &quot;. |
| `folderId` | Retorna todas as IDs para [!UICONTROL traits] dentro da pasta especificada. Não disponível para todos os métodos. |
| `permissions` | Retorna uma lista de segmentos com base na permissão especificada. `READ` é padrão. As permissões incluem:<ul><li>`READ` : Retornar e exibir informações sobre um segmento.</li><li>`WRITE` : Use  `PUT`  para atualizar um segmento.</li><li>`CREATE` : Use  `POST`  para criar um segmento.</li><li>`DELETE` : Excluir um segmento. Requer acesso às características subjacentes, se houver. Por exemplo, você precisará de direitos para excluir as características que pertencem a um segmento se desejar removê-lo.</li></ul><br>Especifique várias permissões com pares de valores chave separados. Por exemplo, para retornar uma lista de segmentos com  `READ`  e  `WRITE`  somente para permissões, transmitir  `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) Defina como `true` para retornar suas permissões para o segmento. O padrão é `false`. |

### Uma observação sobre as opções da página

Quando informações da página *não é* especificado, a solicitação retorna simples [!DNL JSON] resulta em uma matriz. Se informações da página *é* especificado, a lista retornada é encapsulada em uma [!DNL JSON] objeto que contém informações sobre o resultado total e a página atual. Sua solicitação de exemplo usando opções de página pode ser semelhante a esta:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] para solicitações, ambientes de preparo e produção e versões.

## Solicitação [!DNL URLs] {#request-urls}

A tabela a seguir lista a solicitação [!DNL URLs] usado para transmitir [!DNL API] solicitações, por método.

Dependendo do método de autenticação usado, é necessário ajustar a solicitação [!DNL URLs] de acordo com as tabelas abaixo.

### Solicitação [!DNL URLs] para [!DNL JWT] Autenticação {#request-urls-jwt}

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

### Solicitação [!DNL URLs] para [!DNL OAuth] Autenticação (obsoleto) {#request-urls-oauth}

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

O [!DNL Audience Manager] [!DNL API]Fornecem acesso a diferentes ambientes de trabalho. Esses ambientes ajudam a testar o código em bancos de dados separados sem afetar os dados de produção e ao vivo. A tabela a seguir lista os [!DNL API] e os nomes de host de recursos correspondentes.

Dependendo do método de autenticação usado, é necessário ajustar o ambiente [!DNL URLs] de acordo com a tabela abaixo.

| Ambiente | Nome do host para [!DNL JWT] autenticação | Nome do host para [!DNL OAuth] autenticação |
|---|---|---|
| **Produção** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>O [!DNL Audience Manager] o ambiente beta é uma versão independente e de menor escala do ambiente de produção. Todos os dados que você deseja testar devem ser inseridos e coletados neste ambiente.

## Versões {#versions}

Novas versões desses [!DNL API]s são libertadas regularmente. Uma nova versão aprimora o [!DNL API] número da versão. O número da versão é referenciado na solicitação [!DNL URL] as `v<version number>` como mostrado no exemplo a seguir:

`https://<host>/v1/...`

## Códigos de resposta definidos {#response-codes-defined}

`HTTP` códigos de status e texto de resposta retornados pela [!DNL Audience Manager] [!UICONTROL REST API].

| ID do código de resposta | Texto de resposta | Definição |
|---|---|---|
| `200` | `OK` | A solicitação foi processada com êxito. Retornará o conteúdo ou os dados esperados, se necessário. |
| `201` | `Created` | O recurso foi criado. Retorna para `PUT` e `POST` solicitações. |
| `204` | `No Content` | O recurso foi excluído. O corpo da resposta estará em branco. |
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

