---
description: Informações sobre requisitos gerais, autenticação, parâmetros opcionais de consulta, URLs de solicitação e outras referências.
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: Introdução às REST APIs
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 95182160b37bb15df4867bbacd06d8d75c971fa3
workflow-type: tm+mt
source-wordcount: '1942'
ht-degree: 3%

---

# Introdução a [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Informações sobre requisitos gerais, autenticação, parâmetros de consulta opcionais, solicitação [!DNL URLs] e outras referências.

<!-- c_rest_api_overview.xml -->

## Requisitos da API e recomendações {#api-requirements-recommendations}

O que você deve e deve fazer ao trabalhar com o [!DNL Audience Manager] [!DNL API]s.

<!-- aam-api-requirements.xml -->

Observe o seguinte ao trabalhar com o código [API do Audience Manager](https://bank.demdex.com/portal/swagger/index.html#/):

* **Parâmetros da solicitação:** todos os parâmetros da solicitação são obrigatórios, a menos que especificado de outra forma.
* **Cabeçalhos** de solicitação: ao usar o  [Adobe I/](https://www.adobe.io/) Otokens, você deve fornecer o  `x-api-key` cabeçalho . Você pode obter sua chave [!DNL API] seguindo as instruções na página [Integração da conta de serviço](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
* **[!DNL JSON]tipo de conteúdo:** especifique  `content-type: application/json`  **  `accept: application/json` e no seu código.
* **Solicitações e respostas:** envia solicitações como um  [!DNL JSON] objeto formatado corretamente. [!DNL Audience Manager] responde com dados  [!DNL JSON] formatados. As respostas do servidor podem conter dados solicitados, um código de status ou ambos.
* **Acesso:** seu  [!DNL Audience Manager] consultor fornecerá uma ID de cliente e uma chave que permitem fazer  [!DNL API] solicitações.
* **Documentação e exemplos de código:** o texto em  ** itálico representa uma variável que você fornece ou transmite ao criar ou receber  [!DNL API] dados. Substitua o texto *em itálico* por seu próprio código, parâmetros ou outras informações necessárias.

## Autenticação {#authentication}

O [!DNL Audience Manager] [!DNL REST APIs] suporta dois métodos de autenticação.

* [Autenticação JWT (Conta de Serviço) ](#jwt) usando  [Adobe I/O](https://www.adobe.io/). [!DNL Adobe I/O] é o ecossistema e a comunidade do Adobe. Ele inclui as ferramentas do desenvolvedor [Adobe I/O e as APIs](https://www.adobe.io/apis/experienceplatform.html) e [APIs para todos os produtos Adobe](https://www.adobe.io/apis.html). Esta é a maneira recomendada de configurar e usar [!DNL Adobe] [!DNL APIs].
* [Autenticação OAuth (obsoleta)](#oauth). Embora esse método seja obsoleto, os clientes com integrações [!DNL OAuth] existentes podem continuar usando esse método.

>[!IMPORTANT]
>
>Dependendo do seu método de autenticação, você precisa ajustar sua solicitação [!DNL URLs] de acordo. Consulte a seção [Ambientes](#environments) para obter detalhes sobre os nomes de host que você deve usar.

## [!DNL JWT] ([!DNL Service Account]) Autenticação usando Adobe I/O {#jwt}

### Visão geral do Adobe I/O {#adobeio}

[!DNL Adobe I/O] é o ecossistema e a comunidade do Adobe. Ele inclui as ferramentas do desenvolvedor [Adobe I/O e as APIs](https://www.adobe.io/apis/experienceplatform.html) e [APIs para todos os produtos Adobe](https://www.adobe.io/apis.html).

Esta é a maneira recomendada de configurar e usar [!DNL Adobe] [!DNL APIs].

### Pré-requisitos {#prerequisites}

Antes de configurar a autenticação [!DNL JWT], verifique se você tem acesso ao [Console do Desenvolvedor do Adobe](https://console.adobe.io/) em [Adobe I/O](https://www.adobe.io/). Entre em contato com o administrador da organização para obter solicitações de acesso.

### Autenticação {#auth}

Siga as etapas abaixo para configurar a autenticação [!DNL JWT (Service Account)] usando [!DNL Adobe I/O]:

1. Faça logon no [Console do desenvolvedor do Adobe](https://console.adobe.io/).
1. Siga as etapas em [Conexão da Conta de Serviço](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * Durante [Etapa 2: Adicione uma API ao seu projeto usando a autenticação da conta de serviço](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), escolha a opção [!DNL Audience Manager] [!DNL API].
1. Experimente a conexão fazendo sua primeira chamada [!DNL API] com base nas instruções de [Etapa 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Para configurar e trabalhar com o [!DNL Audience Manager] [!DNL REST APIs] de maneira automatizada, você pode gerar o [!DNL JWT] programaticamente. Consulte [Autenticação JWT (Conta de Serviço)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) para obter instruções detalhadas.

### Permissões RBAC de conta técnica

Se sua conta do Audience Manager usar [Controle de acesso com base em função](../../features/administration/administration-overview.md), você deverá criar uma conta de usuário técnica do Audience Manager e adicioná-la ao grupo RBAC do Audience Manager que fará as chamadas de API.

Siga as etapas abaixo para criar uma conta de usuário técnica e adicioná-la a um grupo RBAC:

1. Faça uma chamada `GET` para `https://aam.adobe.io/v1/users/self`. A chamada criará uma conta técnica de usuário que você pode ver no [!UICONTROL Admin Console], na página [!UICONTROL Users].

   ![conta técnica](assets/technical-account.png)

1. Faça logon em sua conta do Audience Manager e [adicione a conta técnica de usuário](../../features/administration/administration-overview.md#create-group) ao grupo de usuários que fará as chamadas de API.

## [!DNL OAuth] Autenticação (obsoleto) {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] a autenticação e a renovação de token por meio do agora  [!DNL OAuth 2.0] está obsoleta.
>
> Em vez disso, use a [JWT (Conta de Serviço) Authentication](#jwt-service-account-authentication-jwt).

O [!DNL Audience Manager] [!UICONTROL REST API] segue os padrões [!DNL OAuth 2.0] para autenticação e renovação de token. As seções abaixo descrevem como autenticar e começar a trabalhar com os [!DNL API]s.

### Criar um Usuário Genérico [!DNL API] {#requirements}

Recomendamos que você crie uma conta de usuário técnica e separada para trabalhar com os [!DNL Audience Manager] [!DNL API]s. Esta é uma conta genérica que não está vinculada ou associada a um usuário específico em sua organização. Esse tipo de [!DNL API] conta de usuário ajuda você a realizar duas coisas:

* Identifique qual serviço está chamando o [!DNL API] (por exemplo, chamadas de seus aplicativos que usam nossos [!DNL API]s ou de outras ferramentas que fazem solicitações de [!DNL API]).
* Forneça acesso ininterrupto aos [!DNL API]s. Uma conta vinculada a uma pessoa específica pode ser excluída ao sair da empresa. Isso impedirá que você trabalhe com o código [!DNL API] disponível. Uma conta genérica não vinculada a um funcionário específico ajuda a evitar esse problema.

Como exemplo ou caso de uso para esse tipo de conta, digamos que você queira alterar muitos segmentos ao mesmo tempo com as [Ferramentas de gerenciamento em massa](../../reference/bulk-management-tools/bulk-management-intro.md). Bem, para fazer isso, sua conta de usuário precisa de [!DNL API] acesso. Em vez de adicionar permissões a um usuário específico, crie uma conta de usuário [!DNL API] não específica que tenha as credenciais, a chave e o segredo apropriados para fazer chamadas [!DNL API]. Isso também é útil se você desenvolver seus próprios aplicativos que usam o [!DNL Audience Manager] [!DNL API]s.

Trabalhe com seu consultor [!DNL Audience Manager] para configurar uma conta de usuário genérica, [!DNL API] somente.

### Fluxo de trabalho de autenticação de senha {#password-authentication-workflow}

A autenticação de senha protege o acesso em [!DNL REST API]. As etapas abaixo descrevem o fluxo de trabalho para autenticação de senha de um cliente [!DNL JSON] em seu navegador.

>[!TIP]
>
>Criptografe o acesso e atualize os tokens se você armazená-los em um banco de dados.

#### Etapa 1: Solicitar acesso [!DNL API]

Entre em contato com o gerente de soluções de parceiros. Eles fornecerão uma [!DNL API] ID do cliente e um segredo. A ID e o segredo autenticam você no [!DNL API].

Observação: Se quiser receber um token de atualização, especifique que ao solicitar acesso a [!DNL API].

#### Etapa 2: Solicitar o token

Transmita uma solicitação de token com seu cliente preferido [!DNL JSON]. Ao criar a solicitação:

* Use um método `POST` para chamar `https://api.demdex.com/oauth/token`.
* Converta a ID do cliente e o segredo em uma string codificada em base 64. Separe a ID e o segredo com dois pontos durante o processo de conversão. Por exemplo, as credenciais `testId : testSecret` são convertidas em `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Transmita [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` e `Content-Type: application/x-www-form-urlencoded` . Por exemplo, o cabeçalho pode ter a seguinte aparência: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Configure o corpo da solicitação da seguinte maneira:
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Etapa 3: Receber o token

A resposta [!DNL JSON] contém o token de acesso. A resposta deve ser semelhante a esta:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

A chave `expires_in` representa o número de segundos até que o token de acesso expire. Como prática recomendada, use tempos de expiração curtos para limitar a exposição se o token for exposto.

### Atualizar Token {#refresh-token}

Atualize os tokens para renovar o acesso [!DNL API] após o token original expirar. Se solicitado, a resposta [!DNL JSON] no workflow de senha inclui um token de atualização. Se você não receber um token de atualização, crie um novo por meio do processo de autenticação por senha.

Você também pode usar um token de atualização para gerar um novo token antes que o token de acesso existente expire.

Se o token de acesso tiver expirado, você receberá um `401 Status Code` e o seguinte cabeçalho na resposta:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

As etapas a seguir descrevem o fluxo de trabalho para usar um token de atualização para criar um novo token de acesso de um cliente [!DNL JSON] em seu navegador.

#### Etapa 1: Solicitar o novo token

Passe uma solicitação de token de atualização com o cliente preferido [!DNL JSON]. Ao criar a solicitação:

* Use um método `POST` para chamar `https://api.demdex.com/oauth/token`.
* Converta a ID do cliente e o segredo em uma string codificada em base 64. Separe a ID e o segredo com dois pontos durante o processo de conversão. Por exemplo, as credenciais `testId : testSecret` são convertidas em `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Transmita os cabeçalhos HTTP `Authorization:Basic <base-64 clientID:clientSecret>` e `Content-Type: application/x-www-form-urlencoded`. Por exemplo, o cabeçalho pode ter a seguinte aparência: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* No corpo da solicitação, especifique o `grant_type:refresh_token` e passe o token de atualização recebido em sua solicitação de acesso anterior. A solicitação deve ter esta aparência: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Etapa 2: Receber o novo token

A resposta [!DNL JSON] contém seu novo token de acesso. A resposta deve ser semelhante a esta:

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

O [!DNL Audience Manager] [!UICONTROL REST API] suporta código de autorização e autenticação implícita. Para usar esses métodos de acesso, os usuários precisam fazer logon em `https://api.demdex.com/oauth/authorize` para obter acesso e atualizar tokens.

## Fazer solicitações autenticadas [!DNL API] {#authenticated-api-requests}

Requisitos para chamar os métodos [!DNL API] após receber um token de autenticação.

Para fazer chamadas em relação aos métodos [!DNL API] disponíveis:

* No cabeçalho `HTTP`, defina `Authorization: Bearer <token>`.
* Ao usar a [Autenticação JWT (Conta de Serviço)](#jwt), é necessário fornecer o cabeçalho `x-api-key`, que será o mesmo que seu `client_id`. Você pode obter seu `client_id` da página [Adobe I/O integration](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
* Chame o método [!DNL API] necessário.

## Parâmetros de consulta [!DNL API] opcionais {#optional-api-query-parameters}

Defina os parâmetros opcionais disponíveis para métodos que retornam todas as propriedades de um objeto.

Você pode usar esses parâmetros opcionais com métodos [!DNL API] que retornam *todas* propriedades para um objeto. Defina essas opções na cadeia de caracteres de solicitação ao passar essa consulta para [!DNL API].

| Parâmetro | Descrição |
|--- |--- |
| `page` | Retorna os resultados por número de página. A numeração começa em 0. |
| `pageSize` | Define o número de resultados de resposta retornados pela solicitação (10 é o padrão). |
| `sortBy` | Classifica e retorna resultados de acordo com a propriedade [!DNL JSON] especificada. |
| `descending` | Classifica e retorna resultados em ordem decrescente. `ascending` é padrão. |
| `search` | Retorna resultados com base na string especificada que você deseja usar como parâmetro de pesquisa. Por exemplo, digamos que você queira encontrar resultados para todos os modelos que têm a palavra &quot;Teste&quot; em qualquer um dos campos de valor para esse item. Sua solicitação de amostra pode ter esta aparência:   `GET https://aam.adobe.io/v1/models/?search=Test`.  Você pode pesquisar qualquer valor retornado por um método &quot;[!DNL get all]&quot;. |
| `folderId` | Retorna todas as IDs para [!UICONTROL traits] dentro da pasta especificada. Não disponível para todos os métodos. |
| `permissions` | Retorna uma lista de segmentos com base na permissão especificada. `READ` é padrão. As permissões incluem:<ul><li>`READ` : Retornar e exibir informações sobre um segmento.</li><li>`WRITE` : Use   `PUT`  para atualizar um segmento.</li><li>`CREATE` : Use   `POST`  para criar um segmento.</li><li>`DELETE` : Excluir um segmento. Requer acesso às características subjacentes, se houver. Por exemplo, você precisará de direitos para excluir as características que pertencem a um segmento se desejar removê-lo.</li></ul><br>Especifique várias permissões com pares de valores chave separados. Por exemplo, para retornar uma lista de segmentos com permissões `READ` e `WRITE` somente, passe `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) Defina como `true` para retornar suas permissões para o segmento. O padrão é `false`. |

### Uma observação sobre as opções da página

Quando as informações de página *não são* especificadas, a solicitação retorna simples [!DNL JSON] resulta em uma matriz. Se as informações de página *forem* especificadas, a lista retornada será encapsulada em um objeto [!DNL JSON] que contém informações sobre o resultado total e a página atual. Sua solicitação de exemplo usando opções de página pode ser semelhante a esta:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] para solicitações, ambientes de preparo e produção e versões.

## Solicitação [!DNL URLs] {#request-urls}

A tabela a seguir lista a solicitação [!DNL URLs] usada para transmitir solicitações [!DNL API], por método.

Dependendo do método de autenticação usado, é necessário ajustar a solicitação [!DNL URLs] de acordo com as tabelas abaixo.

### Solicite [!DNL URLs] a autenticação [!DNL JWT] {#request-urls-jwt}

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

### Solicitação [!DNL URLs] para autenticação [!DNL OAuth] (obsoleto) {#request-urls-oauth}

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

Os [!DNL Audience Manager] [!DNL API]s fornecem acesso a diferentes ambientes de trabalho. Esses ambientes ajudam a testar o código em bancos de dados separados sem afetar os dados de produção e ao vivo. A tabela a seguir lista os ambientes [!DNL API] disponíveis e os nomes de host de recursos correspondentes.

Dependendo do método de autenticação usado, é necessário ajustar o ambiente [!DNL URLs] de acordo com a tabela abaixo.

| Ambiente | Nome do host para autenticação [!DNL JWT] | Nome do host para autenticação [!DNL OAuth] |
|---|---|---|
| **Produção** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>O [!DNL Audience Manager] ambiente beta é uma versão independente e de menor escala do ambiente de produção. Todos os dados que você deseja testar devem ser inseridos e coletados neste ambiente.

## Versões {#versions}

Novas versões desses [!DNL API]s são lançadas regularmente. Uma nova versão incrementa o número da versão [!DNL API]. O número da versão é referenciado na solicitação [!DNL URL] como `v<version number>`, como mostrado no exemplo a seguir:

`https://<host>/v1/...`

## Códigos de resposta definidos {#response-codes-defined}

`HTTP` códigos de status e texto de resposta retornados pelo  [!DNL Audience Manager] [!UICONTROL REST API].

| ID do código de resposta | Texto de resposta | Definição |
|---|---|---|
| `200` | `OK` | A solicitação foi processada com êxito. Retornará o conteúdo ou os dados esperados, se necessário. |
| `201` | `Created` | O recurso foi criado. Retorna para solicitações `PUT` e `POST`. |
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

