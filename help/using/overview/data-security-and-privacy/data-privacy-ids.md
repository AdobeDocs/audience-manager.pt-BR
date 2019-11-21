---
description: Este documento aborda os tipos de IDs do Audience Manager que você pode usar em solicitações de privacidade de dados.
seo-description: Este documento aborda os tipos de IDs do Audience Manager que você pode usar em solicitações de privacidade de dados.
seo-title: Identificadores (IDs) do Audience Manager
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, AAM ID
title: Identificadores (IDs) do Audience Manager
translation-type: tm+mt
source-git-commit: 30352749e926d5730e9cc8beef3936c9ed6d2986

---


# Identificadores (IDs) do Audience Manager {#aam-ids}

Ao enviar solicitações [de privacidade de](data-privacy-requests.md) dados ao Adobe Audience Manager, você deve incluir um dos identificadores (IDs) listados abaixo. Você pode encontrar mais informações sobre os formatos de ID em nosso [Índice de IDs](../../reference/ids-in-aam.md)do Audience Manager.

## ID de usuário exclusiva do Adobe Audience Manager

* **ID de usuário**: `aam_uuid`
* **Definição**:ID de usuário exclusiva do Adobe Audience Manager
* **ID** do namespace: 0

**Exemplo de JSON**:

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

>[!NOTE]
>
>You can also use the [!DNL CORE] namespace.

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

## Adobe Experience Cloud ID

* **ID de usuário**: `mid`
* **Definição**: [!DNL Adobe Experience Cloud ID], anteriormente conhecido como [!DNL Visitor ID] ou [!DNL Marketing Cloud ID]
* **ID** do namespace: 4

>[!NOTE]
>
>You can also use the [!DNL ECID] namespace. Veja o segundo [!DNL JSON] exemplo.

**Exemplo de JSON**:

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

## Customer ID

**ID de usuário**: `cid`

**Definição**: ID do cliente, como um cookie definido para visitantes anônimos do site ou uma [!DNL CRM] ID de um sistema offline ou um nome de usuário com hash.

**ID** do namespace: Específico do cliente. Localize-o na sua instância do Audience Manager.

**Exemplo de JSON**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"1234567",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-1234567"
      },
      {
        "namespace": "1234567",
        "type": "namespaceId",
        "value": "another-unique-user-id-for-datasource-1234567"
      },
      {
        "namespace":"54321",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-54321"
      }
    ]
  }
```

## ID de anúncio móvel

**ID de usuário**: `d_cid`

**Definição**: IDs de anúncios móveis.

**ID de namespace**:

* [!DNL IDFA:] 20915
* [!DNL GAID:] 20914

Consulte Fontes [de dados](../../features/global-data-sources.md) globais para obter mais detalhes.

>[!IMPORTANT]
>
> Se estiver usando o Mobile [!DNL SDK], você também deverá enviar a Experience Cloud ID (`MID`) juntamente com as IDs de publicidade móvel para obter respostas completas de Acesso e Excluir.

**Exemplo de JSON**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"20914",
        "type": "namespaceId",
        "value": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2"
      },
      {
        "namespace":"20915",
        "type": "namespaceId",
        "value": "AEBE52E7-03EE-455A-B3C4-E57283966239"
      }
    ]
  }
]
```

## Código de integração

**ID de usuário**: `d_cid_ic`

**Definição**: Um código de integração para a fonte de dados. Isso pode ser usado em vez da ID da fonte de dados / ID do namespace na [!DNL API] solicitação para [!DNL Adobe Experience Cloud Privacy Core Service].

**ID** do namespace: Não aplicável

**Exemplo de JSON**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "loyaltyCard",
        "type": "integrationCode",
        "value": "272023537812"
      },
      {
        "namespace":"offlineCampaign",
        "type": "integrationCode",
        "value": "9546673332"
      }
    ]
  }
]
```
