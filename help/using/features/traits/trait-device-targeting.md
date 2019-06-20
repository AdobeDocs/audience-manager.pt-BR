---
description: Descreve os pares de valores de plataforma em nível de plataforma comuns que podem ser usados para direcionar usuários com variáveis relacionadas ao dispositivo em todas as propriedades na conta do Audience Manager.
seo-description: Descreve os pares de valores de plataforma em nível de plataforma comuns que podem ser usados para direcionar usuários com variáveis relacionadas ao dispositivo em todas as propriedades na conta do Audience Manager.
seo-title: Direcionamento de dispositivo com chaves de nível de plataforma
solution: Audience Manager
title: Direcionamento de dispositivo com chaves de nível de plataforma
uuid: bc 048 cc 5-3 df 1-49 bc-ac 78-0 ea 5 d 7 edd 9 cc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Device Targeting With Platform-level Keys {#device-targeting-with-platform-level-keys}

Descreve os pares de valores de plataforma em nível de plataforma comuns que podem ser usados para direcionar usuários com variáveis relacionadas ao dispositivo em todas as propriedades na conta do Audience Manager.

## Purpose of Platform-level Variables {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Platform-level variables let you take data passed in from a particular site and make it available for targeting across all the properties in your [!DNL Audience Manager] account. These variables are formed by [key-value pairs](../../reference/key-value-pairs-explained.md) with the key prefixed by `d_` as shown below.

## Platform-level Keys Defined by User Agent {#keys-user-agent}

[!UICONTROL Data Collection Servers] A extração dos valores para essas chaves do cabeçalho do agente [do usuário](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) em `HTTP` solicitações. The values represent device-level information from the [!UICONTROL Device Atlas] database. Os sinais na tabela abaixo estão disponíveis, como extraído do exemplo do agente do usuário. [Baixe uma lista das chaves](assets/device_keys.csv)mais comuns, de acordo com [!UICONTROL Device Atlas] as medidas.

| [!DNL Signal] | [!DNL Type] | [!DNL Example] |
|---|---|---|
| `d_device_vendor` | [!DNL VENDOR] | [!DNL apple] |
| `d_device_hardware_type` | [!DNL HARDWARE] | [!DNL mobile phone] |
| `d_device_os_version` | [!DNL OS VERSION] | [!DNL 5_0] |
| `d_device_os_name` | [!DNL OS NAME] | [!DNL ios] |
| `d_device_model` | [!DNL MODEL] | [!DNL iphone] |
| `d_device_marketing_name` | [!DNL MARKETING NAME] | [!DNL iphone] |
| `d_device_manufacturer` | [!DNL MANUFACTURER] | [!DNL apple] |

```
 Mozilla/5.0 (iPhone; CPU iPhone OS 5_0 like Mac OS X) AppleWebKit/534.46 (KHTML, like Gecko) Version/5.1 Mobile/9A334 Safari/7534.48.3
```

>[!NOTE]
>
>Even if one or more signals cannot be retrieved from the user agent header, the other signals will still be passed to the [!UICONTROL Data Collection Servers].

>[!MORE_ LIKE_ THIS]
>
>* [Requisitos de prefixo para variáveis principais](../../features/traits/trait-variable-prefixes.md)

