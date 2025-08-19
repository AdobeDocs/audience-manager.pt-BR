---
description: Informações sobre requisitos gerais, autenticação, parâmetros opcionais de consulta, URLs de solicitação e outras referências.
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: Introdução às REST APIs
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 622664170f2a76039bcf2333bde43ce9e60b6af2
workflow-type: tm+mt
source-wordcount: '2563'
ht-degree: 1%

---

# Introdução ao [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Informações sobre requisitos gerais, autenticação, parâmetros de consulta opcionais, solicitação [!DNL URLs] e outras referências.

## Requisitos da API e recomendações {#api-requirements-recommendations}

Observe o seguinte ao trabalhar com o código [API Audience Manager](https://bank.demdex.com/portal/swagger/index.html#/):

* **Parâmetros de solicitação:** todos os parâmetros de solicitação são necessários, a menos que especificado de outra forma.
* **Solicitar cabeçalhos**: ao usar tokens do [Adobe Developer](https://www.adobe.io/), você deve fornecer o cabeçalho `x-api-key`. Para obter a chave [!DNL API], siga as instruções na página [Integração de Conta de Serviço](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
* **[!DNL JSON]tipo de conteúdo:** Especifique `content-type: application/json` *e* `accept: application/json` no seu código.
* **Solicitações e respostas:** envia solicitações como um objeto [!DNL JSON] formatado corretamente. [!DNL Audience Manager] responde com [!DNL JSON] dados formatados. As respostas do servidor podem conter dados solicitados, um código de status ou ambos.
* **Acesso:** O consultor do [!DNL Audience Manager] fornecerá a você uma ID de cliente e uma chave que permitem fazer solicitações do [!DNL API].
* **Documentação e exemplos de código:** O texto em *itálico* representa uma variável que você fornece ou transmite ao criar ou receber dados [!DNL API]. Substitua o texto *em itálico* pelo seu próprio código, parâmetros ou outras informações necessárias.

## Autenticação {#authentication}

O [!DNL Audience Manager] [!DNL REST APIs] dá suporte a três métodos de autenticação.

* [!BADGE Recomendado]{type=positive} [Autenticação de Servidor para Servidor OAuth](#oauth-adobe-developer) usando o [console do desenvolvedor do Adobe](https://www.adobe.io/). [!DNL Adobe Developer] é o ecossistema de desenvolvedores e a comunidade da Adobe. Ele inclui [APIs para todos os produtos da Adobe](https://developer.adobe.com/apis/). Esta é a maneira recomendada de configurar e usar o [!DNL Adobe] [!DNL APIs]. Leia mais sobre [Autenticação de servidor para servidor OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/) na documentação do desenvolvedor do Adobe.
* [!BADGE Desaprovado]{type=negative} [Autenticação JWT (Conta de Serviço)](#jwt) usando o [console de desenvolvedor do Adobe](https://www.adobe.io/). [!DNL Adobe Developer] é o ecossistema de desenvolvedores e a comunidade da Adobe. Ele inclui [APIs para todos os produtos da Adobe](https://developer.adobe.com/apis/).
* [!BADGE Obsoleto]{type=negative} [Autenticação OAuth herdada](#oauth-deprecated). Enquanto esse método estiver obsoleto, os clientes com integrações existentes do [!DNL OAuth] podem continuar usando esse método.

>[!IMPORTANT]
>
>Dependendo do seu método de autenticação, você precisa ajustar sua solicitação [!DNL URLs] de acordo. Consulte a seção [Ambientes](#environments) para obter detalhes sobre os nomes de host que você deve usar.

## Autenticação de servidor para servidor OAuth usando Adobe Developer {#oauth-adobe-developer}

Esta seção aborda como coletar as credenciais necessárias para autenticar chamadas de API do Audience Manager, conforme descrito no fluxograma abaixo. Você pode coletar a maioria das credenciais necessárias na configuração inicial única. No entanto, o token de acesso deve ser atualizado a cada 24 horas.

![Diagrama de fluxo de autenticação do Audience Manager.](/help/using/api/rest-api-main/assets/aam-authentication-flow.png)

### Visão geral do Adobe Developer {#developer-overview}

[!DNL Adobe Developer] é o ecossistema de desenvolvedores e a comunidade da Adobe. Ele inclui [APIs para todos os produtos da Adobe](https://developer.adobe.com/apis).

Esta é a maneira recomendada de configurar e usar o [!DNL Adobe] [!DNL APIs].

### Pré-requisitos {#prerequisites-server-to-server}

Antes de configurar a autenticação do [!DNL OAuth Server-to-Server], verifique se você tem acesso ao [Adobe Developer Console](https://developer.adobe.com/console/home) no [Adobe Developer](https://developer.adobe.com/). Entre em contato com o administrador da organização para obter solicitações de acesso.

### Autenticação {#oauth}

Siga as etapas abaixo para configurar a autenticação do [!DNL OAuth Server-to-Server] usando o [!DNL Adobe Developer]:

1. Faça logon no [Adobe Developer Console](https://developer.adobe.com/console/home).
1. Siga as etapas no [guia de implementação de credenciais de servidor para servidor do OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/).
   * Durante a [Etapa 2: adicionar uma API ao seu projeto usando a autenticação de Conta de Serviço](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), escolha a opção [!DNL Audience Manager] [!DNL API].
1. Experimente a conexão fazendo sua primeira chamada do [!DNL API] com base nas instruções da [Etapa 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Para configurar e trabalhar com o [!DNL Audience Manager] [!DNL REST APIs] de forma automatizada, você pode girar os segredos do cliente de forma programática. Consulte [a documentação do desenvolvedor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#rotating-client-secrets-programmatically) para obter instruções detalhadas.

### Adicionar a API do Audience Manager a um projeto {#add-aam-api-to-project}

Vá para [Adobe Developer Console](https://www.adobe.com/go/devs_console_ui) e entre com sua Adobe ID. Em seguida, siga as etapas descritas no tutorial sobre [criação de um projeto vazio](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty/) na documentação do Adobe Developer Console.

Depois de criar um novo projeto, selecione **[!UICONTROL Add API]** na tela **[!UICONTROL Project Overview]**.

>[!TIP]
>
>Se você tiver sido provisionado para várias organizações, use o seletor de organizações no canto superior direito da interface para garantir que está na organização necessária.

![Tela do Developer Console com a opção Adicionar API realçada.](/help/using/api/rest-api-main/assets/add-api.png)

A tela **[!UICONTROL Add an API]** é exibida. Selecione o ícone de produto do Adobe Experience Cloud e escolha **[!UICONTROL Audience Manager API]** antes de selecionar **[!UICONTROL Next]**.

![Selecionar API do Audience Manager.](/help/using/api/rest-api-main/assets/audience-manager-api.png)

>[!TIP]
>
>Selecione a opção **[!UICONTROL View docs]** para navegar em uma janela de navegador separada para a [documentação de referência da API do Audience Manager](https://bank.demdex.com/portal/swagger/index.html#) completa.

### Selecione o tipo de autenticação de servidor para servidor OAuth {#select-oauth-server-to-server}

Em seguida, selecione o tipo de autenticação para gerar tokens de acesso e acessar a API do Audience Manager.

>[!IMPORTANT]
>
>Selecione o método **[!UICONTROL OAuth Server-to-Server]**, pois esse será o único método com suporte dali em diante. O método **[!UICONTROL Service Account (JWT)]** está obsoleto. Embora as integrações que usam o método de autenticação JWT continuem a funcionar até 1º de janeiro de 2025, a Adobe recomenda que você migre as integrações existentes para o novo método servidor para servidor OAuth antes dessa data.

![Selecione o método de autenticação OAuth.](/help/using/api/rest-api-main/assets/select-oauth-authentication-method.png)

### Selecione os perfis de produto para sua integração {#select-product-profiles}

Na tela **[!UICONTROL Configure API]**, selecione os perfis de produto desejados. A conta de serviço da sua integração terá acesso aos recursos detalhados por meio dos perfis de produto selecionados aqui.

![Selecione perfis de produto para sua integração.](/help/using/api/rest-api-main/assets/select-product-profiles.png)

Selecione **[!UICONTROL Save configured API]** quando estiver pronto.

### Coletar credenciais {#gather-credentials}

Depois que a API for adicionada ao projeto, a página **[!UICONTROL Audience Manager API]** do projeto exibirá as seguintes credenciais, necessárias em todas as chamadas para as APIs do Audience Manager:

![Informações de integração após adicionar uma API no Developer Console.](/help/using/api/rest-api-main/assets/api-integration-information.png)

* `{API_KEY}` ([!UICONTROL Client ID])
* `{ORG_ID}` ([!UICONTROL Organization ID])

## Gerar um token de acesso {#generate-access-token}

A próxima etapa é gerar uma credencial `{ACCESS_TOKEN}` para uso em chamadas de API do Audience Manager. Diferentemente dos valores de `{API_KEY}` e `{ORG_ID}`, um novo token deve ser gerado a cada 24 horas para continuar usando as APIs do Audience Manager. Selecione **[!UICONTROL Generate access token]**, conforme mostrado abaixo.

![Mostrar como gerar um token de acesso](/help/using/api/rest-api-main/assets/generate-acces-token.gif)

## Testar uma chamada de API {#test-api-call}

Depois de obter o token do portador de autenticação, execute uma chamada de API para testar se agora é possível acessar as APIs do Audience Manager.

1. Navegue até a [documentação de referência da API](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_).
2. Selecione **[!UICONTROL Authorize]** e cole o token de acesso obtido na etapa [gerar token de acesso](#generate-access-token).

   ![Autorizar chamadas de API](/help/using/api/rest-api-main/assets/authorize-api-calls.gif)

3. Execute uma chamada GET para o ponto de extremidade da API `/datasources` para recuperar uma lista de todas as fontes de dados disponíveis globalmente, conforme indicado na [documentação de referência da API](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_). Selecione **[!UICONTROL Try it out]**, seguido por **[!UICONTROL Execute]**, como mostrado abaixo.

   ![Executar chamadas de API](/help/using/api/rest-api-main/assets/perform-api-calls.gif)


>[!BEGINSHADEBOX]

>[!BEGINTABS]

>[!TAB Solicitação de API]

```shell
curl -X 'GET' \
  'https://api.demdex.com/v1/datasources/' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer your-access-token'
```


>[!TAB Resposta da API em caso de uso do token de portador correto]


Ao usar um token de acesso funcional, o endpoint da API retorna uma resposta 200, juntamente com um corpo de resposta que inclui todas as fontes de dados globais às quais sua organização tem acesso.

```json
[
  {
    "pid": 1794,
    "name": "testdatasource1",
    "description": "Test data source",
    "status": "ACTIVE",
    "integrationCode": "test_ds1",
    "dataExportRestrictions": [],
    "updateTime": 1595340792000,
    "crUID": 0,
    "upUID": 15910,
    "linkNamespace": false,
    "type": "GENERAL",
    "subIdType": "CROSS_DEVICE_PERSON",
    "inboundS2S": true,
    "outboundS2S": true,
    "useAudienceManagerVisitorID": false,
    "allowDataSharing": true,
    "masterDataSourceIdProvider": true,
    "uniqueTraitIntegrationCodes": false,
    "uniqueSegmentIntegrationCodes": false,
    "marketingCloudVisitorIdVersion": 0,
    "idType": "CROSS_DEVICE",
    "samplingEndTime": 1596550392825,
    "allowDeviceGraphSharing": false,
    "supportsAuthenticatedProfile": true,
    "deviceGraph": false,
    "authenticatedProfileName": "testdatasource1",
    "deviceGraphName": "",
    "customNamespaceId": 29769,
    "customNamespaceCode": "silviu_ds1",
    "customerProfileDataRetention": 62208000,
    "samplingStartTime": 1595340792825,
    "dataSourceId": 29769,
    "containerIds": [],
    "samplingEnabled": false
  },
  {
    "pid": 1794,
    "name": "AAM Test Company Audiences",
    "description": "Automatically generated trait data source",
    "status": "ACTIVE",
    "integrationCode": "adobe-provided",
    "dataExportRestrictions": [
      "PII"
    ],

    [...]
```

>[!ENDTABS]

>[!ENDSHADEBOX]

## [!BADGE Desaprovado]{type=negative} [!DNL JWT] ([!DNL Service Account]) Autenticação usando Adobe Developer {#jwt}

+++ Exibir informações sobre o método [!DNL JWT] ([!DNL Service Account]) obsoleto de obtenção de tokens de autenticação.

### Visão geral do Adobe Developer {#adobeio}

[!DNL Adobe Developer] é o ecossistema de desenvolvedores e a comunidade da Adobe. Ele inclui [APIs para todos os produtos da Adobe](https://www.adobe.io/apis.html).

Esta é a maneira recomendada de configurar e usar o [!DNL Adobe] [!DNL APIs].

### Pré-requisitos {#prerequisites}

Antes de configurar a autenticação do [!DNL JWT], verifique se você tem acesso ao [Adobe Developer Console](https://console.adobe.io/) no [Adobe Developer](https://www.adobe.io/). Entre em contato com o administrador da organização para obter solicitações de acesso.

### Autenticação {#auth}

Siga as etapas abaixo para configurar a autenticação do [!DNL JWT (Service Account)] usando o [!DNL Adobe Developer]:

1. Faça logon no [Adobe Developer Console](https://console.adobe.io/).
1. Siga as etapas em [Conexão com a Conta de Serviço](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * Durante a [Etapa 2: adicionar uma API ao seu projeto usando a autenticação de Conta de Serviço](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), escolha a opção [!DNL Audience Manager] [!DNL API].
1. Experimente a conexão fazendo sua primeira chamada do [!DNL API] com base nas instruções da [Etapa 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Para configurar e trabalhar com o [!DNL Audience Manager] [!DNL REST APIs] de forma automatizada, você pode gerar o [!DNL JWT] de forma programática. Consulte [Autenticação de JWT (Conta de Serviço)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) para obter instruções detalhadas.

### Permissões RBAC da conta técnica

Se sua conta do Audience Manager usar o [Controle de acesso com base em função](../../features/administration/administration-overview.md), você deverá criar uma conta de usuário técnico do Audience Manager e adicioná-la ao grupo Audience Manager RBAC que fará as chamadas de API.

Siga as etapas abaixo para criar uma conta de usuário técnico e adicioná-la a um grupo RBAC:

1. Fazer uma chamada `GET` para `https://aam.adobe.io/v1/users/self`. A chamada criará uma conta de usuário técnico que você poderá ver no [!UICONTROL Admin Console], na página [!UICONTROL Users].

   ![conta técnica](assets/technical-account.png)

1. Faça logon em sua conta do Audience Manager e [adicione a conta de usuário técnico](../../features/administration/administration-overview.md#create-group) ao grupo de usuários que fará as chamadas de API.

+++

## [!BADGE Obsoleto]{type=negative} [!DNL OAuth] Autenticação (Obsoleto) {#oauth-deprecated}

+++ Visualize informações sobre o método de autenticação [!DNL OAuth] herdado obsoleto de obtenção de tokens de autenticação.

>[!WARNING]
> A autenticação e renovação do token [!DNL Audience Manager] [!UICONTROL REST API] via [!DNL OAuth 2.0] foi descontinuada.
>
> Em vez disso, use a [Autenticação JWT (Conta de Serviço)](#jwt-service-account-authentication-jwt).

O [!DNL Audience Manager] [!UICONTROL REST API] segue os [!DNL OAuth 2.0] padrões de autenticação e renovação de token. As seções abaixo descrevem como autenticar e começar a trabalhar com o [!DNL API]s.

### Criar um usuário [!DNL API] genérico {#requirements}

Recomendamos que você crie uma conta de usuário técnico separada para trabalhar com o [!DNL Audience Manager] [!DNL API]s. É uma conta genérica que não está vinculada a um usuário específico na organização nem associada a ele. Este tipo de conta de usuário do [!DNL API] ajuda você a realizar duas coisas:

* Identifique qual serviço está chamando o [!DNL API] (por exemplo, chamadas de seus aplicativos que usam nosso [!DNL API]s ou de outras ferramentas que fazem [!DNL API] solicitações).
* Forneça acesso ininterrupto ao [!DNL API]s. Uma conta vinculada a uma pessoa específica pode ser excluída ao ela sair da empresa. Isso impedirá que você trabalhe com o código [!DNL API] disponível. Uma conta genérica que não está vinculada a um funcionário específico ajuda a evitar esse problema.

Como exemplo ou caso de uso para esse tipo de conta, suponhamos que você queira alterar muitos segmentos ao mesmo tempo com as [Ferramentas de gerenciamento em massa](../../reference/bulk-management-tools/bulk-management-intro.md). Para fazer isso, sua conta de usuário precisa de acesso [!DNL API]. Em vez de adicionar permissões a um usuário específico, crie uma conta de usuário [!DNL API] não específica que tenha as credenciais, a chave e o segredo apropriados para fazer chamadas [!DNL API]. Isso também é útil se você desenvolver seus próprios aplicativos que usam o [!DNL Audience Manager] [!DNL API]s.

Trabalhe com o consultor do [!DNL Audience Manager] para configurar uma conta de usuário genérica, somente para [!DNL API].

### Fluxo de trabalho de autenticação de senha {#password-authentication-workflow}

Autenticação de senha acesso seguro nosso [!DNL REST API]. As etapas abaixo descrevem o fluxo de trabalho para autenticação de senha de um cliente do [!DNL JSON] em seu navegador.

>[!TIP]
>
>Criptografe tokens de acesso e atualização se você armazená-los em um banco de dados.

#### Etapa 1: solicitar acesso de [!DNL API]

Entre em contato com seu gerente de soluções de parceiros. Eles fornecerão a você uma ID de cliente e um segredo do [!DNL API]. A ID e o segredo autenticam você no [!DNL API].

Observação: se quiser receber um token de atualização, especifique-o ao solicitar acesso de [!DNL API].

#### Etapa 2: solicitar o token

Transmita uma solicitação de token com o cliente [!DNL JSON] de sua preferência. Ao criar a solicitação:

* Use um método `POST` para chamar `https://api.demdex.com/oauth/token`.
* Converta a ID do cliente e o segredo em uma sequência de caracteres codificada na base 64. Separe a ID e o segredo com dois pontos durante o processo de conversão. Por exemplo, as credenciais `testId : testSecret` são convertidas em `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Passar no [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` e `Content-Type: application/x-www-form-urlencoded` . Por exemplo, seu cabeçalho pode ter esta aparência: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Configure o corpo da solicitação da seguinte maneira:
  <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Etapa 3: Receber o token

A resposta [!DNL JSON] contém seu token de acesso. A resposta deve ser semelhante a:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

A chave `expires_in` representa o número de segundos até o token de acesso expirar. Como prática recomendada, use tempos de expiração curtos para limitar a exposição se o token for exposto.

### Atualizar token {#refresh-token}

Atualizar tokens renova o acesso [!DNL API] depois que o token original expirar. Se solicitado, a resposta [!DNL JSON] no fluxo de trabalho de senha inclui um token de atualização. Se você não receber um token de atualização, crie um novo por meio do processo de autenticação de senha.

Você também pode usar um token de atualização para gerar um novo token antes que o token de acesso existente expire.

Se o token de acesso tiver expirado, você receberá um `401 Status Code` e o seguinte cabeçalho na resposta:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

As etapas a seguir descrevem o fluxo de trabalho para usar um token de atualização para criar um novo token de acesso a partir de um cliente [!DNL JSON] em seu navegador.

#### Etapa 1: solicitar o novo token

Transmita uma solicitação de token de atualização com seu cliente [!DNL JSON] preferido. Ao criar a solicitação:

* Use um método `POST` para chamar `https://api.demdex.com/oauth/token`.
* Converta a ID do cliente e o segredo em uma sequência de caracteres codificada na base 64. Separe a ID e o segredo com dois pontos durante o processo de conversão. Por exemplo, as credenciais `testId : testSecret` são convertidas em `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Passar nos cabeçalhos HTTP `Authorization:Basic <base-64 clientID:clientSecret>` e `Content-Type: application/x-www-form-urlencoded`. Por exemplo, seu cabeçalho pode ter esta aparência: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* No corpo da solicitação, especifique o `grant_type:refresh_token` e transmita o token de atualização recebido na solicitação de acesso anterior. A solicitação deve ter esta aparência: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Etapa 2: receber o novo token

A resposta [!DNL JSON] contém seu novo token de acesso. A resposta deve ser semelhante a:

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

O [!DNL Audience Manager] [!UICONTROL REST API] dá suporte ao código de autorização e à autenticação implícita. Para usar esses métodos de acesso, seus usuários precisam fazer logon no `https://api.demdex.com/oauth/authorize` para obter acesso e atualizar tokens.

+++

## Fazer Solicitações [!DNL API] Autenticadas {#authenticated-api-requests}

Requisitos para chamar métodos [!DNL API] depois que você receber um token de autenticação.

Para fazer chamadas com os métodos [!DNL API] disponíveis:

* No cabeçalho `HTTP`, defina `Authorization: Bearer <token>`.
* Ao usar a [Autenticação JWT (Conta de Serviço)](#jwt), é necessário fornecer o cabeçalho `x-api-key`, que será o mesmo que o `client_id`. Você pode obter o seu `client_id` da página [integração com o Adobe Developer](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
* Chame o método [!DNL API] necessário.

## Parâmetros de Consulta [!DNL API] Opcionais {#optional-api-query-parameters}

Defina os parâmetros opcionais disponíveis para métodos que retornam todas as propriedades de um objeto.

Você pode usar esses parâmetros opcionais com métodos [!DNL API] que retornam *todas* as propriedades de um objeto. Defina essas opções na cadeia de caracteres de solicitação ao passar essa consulta para o [!DNL API].

| Parâmetro | Descrição |
|--- |--- |
| `page` | Retorna resultados por número de página. A numeração começa em 0. |
| `pageSize` | Define o número de resultados de resposta retornados pela solicitação (10 é o padrão). |
| `sortBy` | Classifica e retorna resultados de acordo com a propriedade [!DNL JSON] especificada. |
| `descending` | Classifica e retorna resultados em ordem decrescente. `ascending` é o padrão. |
| `search` | Retorna resultados com base na cadeia de caracteres especificada que você deseja usar como parâmetro de pesquisa. Por exemplo, digamos que você queira encontrar resultados para todos os modelos que têm a palavra &quot;Teste&quot; em qualquer um dos campos de valor para esse item. Seu exemplo de solicitação pode ser semelhante a:   `GET https://aam.adobe.io/v1/models/?search=Test`.  Você pode pesquisar qualquer valor retornado por um método &quot;[!DNL get all]&quot;. |
| `folderId` | Retorna todas as IDs de [!UICONTROL traits] dentro da pasta especificada. Não disponível para todos os métodos. |
| `permissions` | Retorna uma lista de segmentos com base na permissão especificada. `READ` é o padrão. As permissões incluem:<ul><li>`READ` : Retornar e exibir informações sobre um segmento.</li><li>`WRITE` : Use `PUT` para atualizar um segmento.</li><li>`CREATE` : Use `POST` para criar um segmento.</li><li>`DELETE` : Excluir um segmento. Requer acesso a características subjacentes, se houver. Por exemplo, você precisará de direitos para excluir as características que pertencem a um segmento se desejar removê-lo.</li></ul><br>Especifique várias permissões com pares de valores chave separados. Por exemplo, para retornar uma lista de segmentos com permissões `READ` e `WRITE` somente, passe em `"permissions":"READ"`, `"permissions":"WRITE"`. |
| `includePermissions` | ([!DNL Boolean]) Defina como `true` para retornar suas permissões para o segmento. O padrão é `false`. |

{style="table-layout:auto"}

### Uma Observação Sobre As Opções De Página

Quando as informações de página *não são* especificadas, a solicitação retorna resultados [!DNL JSON] simples em uma matriz. Se as informações da página *forem* especificadas, a lista retornada será encapsulada em um objeto [!DNL JSON] que contém informações sobre o resultado total e a página atual. O exemplo de solicitação usando opções de página pode ser semelhante a:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] para solicitações, ambientes de preparo e produção e versões.

## Solicitação [!DNL URLs] {#request-urls}

A tabela a seguir lista a solicitação [!DNL URLs] usada para passar em [!DNL API] solicitações, por método.

Dependendo do método de autenticação usado, é necessário ajustar sua solicitação [!DNL URLs] de acordo com as tabelas abaixo.

### Solicitação [!DNL URLs] para a [!BADGE Recomendada]{type=positive} de Servidor para Servidor OAuth e a [!BADGE Desaprovada]{type=negative} Autenticação [!DNL JWT] por meio do Adobe Developer {#request-urls-jwt}

| [!DNL API] Métodos | Solicitação [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | Características: `https://aam.adobe.io/v1/folders/traits /`<br>Segmentos: `https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

{style="table-layout:auto"}

### Solicitar [!DNL URLs] para a [!BADGE Autenticação ]{type=negative} herdada[!DNL OAuth] obsoleta {#request-urls-oauth}

| [!DNL API] Métodos | Solicitação [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | Características: `https://api.demdex.com/v1/folders/traits /`<br>Segmentos: `https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

{style="table-layout:auto"}

## Ambientes {#environments}

O [!DNL Audience Manager] [!DNL API]s fornece acesso a diferentes ambientes de trabalho. Esses ambientes ajudam a testar o código em bancos de dados separados, sem afetar os dados de produção em tempo real. A tabela a seguir lista os ambientes [!DNL API] disponíveis e os nomes de host de recursos correspondentes.

Dependendo do método de autenticação usado, é necessário ajustar o ambiente [!DNL URLs] de acordo com a tabela abaixo.

| Ambiente | Nome do host para autenticação [!DNL JWT] | Nome do host para autenticação [!DNL OAuth] |
|---|---|---|
| **Produção** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>O ambiente beta do [!DNL Audience Manager] é uma versão independente de menor escala do ambiente de produção. Todos os dados que você deseja testar devem ser inseridos e coletados neste ambiente.

## Versões {#versions}

Novas versões desses [!DNL API]s são lançadas regularmente. Uma nova versão incrementa o número de versão [!DNL API]. O número da versão é referenciado na solicitação [!DNL URL] como `v<version number>`, conforme mostrado no exemplo a seguir:

`https://<host>/v1/...`

## Códigos de resposta definidos {#response-codes-defined}

`HTTP` códigos de status e texto de resposta retornados por [!DNL Audience Manager] [!UICONTROL REST API].

| ID do código de resposta | Texto da resposta | Definição |
|---|---|---|
| `200` | `OK` | A solicitação foi processada com sucesso. Retornará o conteúdo ou os dados esperados, se necessário. |
| `201` | `Created` | O recurso foi criado Retorna para solicitações de `PUT` e `POST`. |
| `204` | `No Content` | O recurso foi excluído. O corpo da resposta ficará em branco. |
| `400` | `Bad Request` | O servidor não entendeu a solicitação. Geralmente devido a sintaxe malformada. Verifique sua solicitação e tente novamente. |
| `403` | `Forbidden` | Você não tem acesso ao recurso. |
| `404` | `Not Found` | O recurso não foi encontrado para o caminho especificado. |
| `409` | `Conflict` | A solicitação não pôde ser concluída devido a um conflito com o estado do recurso. |
| `500` | `Server Error` | O servidor encontrou um erro inesperado que o impediu de atender à solicitação. |

>[!MORELIKETHIS]
>
>* [Autenticação JWT (Conta de Serviço)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [Autenticação OAuth](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 simplificado](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)
