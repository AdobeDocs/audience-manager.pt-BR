---
description: Este documento aborda os tipos de IDs do Audience Manager que você pode usar em solicitações de privacidade de dados.
seo-description: Este documento aborda os tipos de IDs do Audience Manager que você pode usar em solicitações de privacidade de dados.
seo-title: Identificadores do Audience Manager (IDs)
solution: Audience Manager
keywords: Interface do usuário do GDPR, API do GDPR, CCPA, privacidade, AAM ID
title: Identificadores do Audience Manager (IDs)
feature: Data Governance & Privacy
exl-id: 5f18ed0a-c875-4596-a4d1-f9a7fe871d1b
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 95%

---

# Identificadores do Audience Manager (IDs) {#aam-ids}

Ao enviar [solicitações de privacidade de dados](data-privacy-requests.md) para o Adobe Audience Manager, você deve incluir um dos identificadores (IDs) listados abaixo. Você pode encontrar mais informações sobre os formatos de ID em nosso [Índice de IDs do Audience Manager](../../reference/ids-in-aam.md).

## ID de usuário exclusiva do Adobe Audience Manager

* **ID de usuário**: `aam_uuid`
* **Definição**: ID de usuário exclusiva do Adobe Audience Manager
* **ID de namespace**: 0

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
>Você também pode usar o namespace [!DNL CORE].

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
* **Definição**: [!DNL Adobe Experience Cloud ID], anteriormente conhecida como [!DNL Visitor ID] ou [!DNL Marketing Cloud ID]
* **ID de namespace**: 4

>[!NOTE]
>
>Você também pode usar o namespace [!DNL ECID]. Veja o segundo exemplo de [!DNL JSON].

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

**Definição**: ID do cliente, como um cookie definido para visitantes anônimos do site ou uma ID de [!DNL CRM] de um sistema offline ou nome de usuário com hash.

**ID de namespace**: específico do cliente. Localize-o na sua instância do Audience Manager.

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

Consulte [Fontes de dados globais](../../features/global-data-sources.md) para obter mais detalhes.

>[!IMPORTANT]
>
> Se estiver usando o [!DNL SDK] móvel, você também deverá enviar a Experience Cloud ID (`MID`) juntamente com as IDs de publicidade móvel para obter respostas completas de Acesso e Exclusão.

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

**Definição**: um código de integração para a fonte de dados. Ele pode ser usado em vez da ID da fonte de dados/ID de namespace na solicitação de [!DNL API] para o [!DNL Adobe Experience Cloud Privacy Core Service].

**ID de namespace**: não aplicável

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
