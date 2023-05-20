---
description: Descreve os pares de valores chave comuns em nível de plataforma que você pode usar para direcionar usuários com variáveis relacionadas ao dispositivo em todas as propriedades na sua conta Audience Manager.
seo-description: Describes the common platform-level key-value pairs you can use to target users with device-related variables across all properties in your Audience Manager account.
seo-title: Device Targeting With Platform-level Keys
solution: Audience Manager
title: Direcionamento de dispositivo com chaves de nível de plataforma
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
source-git-commit: b299783b993c5d4a1c7738eca82932c20f377ee7
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 5%

---

# Direcionamento de dispositivo com chaves de nível de plataforma {#device-targeting-with-platform-level-keys}

>[!WARNING]
>
>A Google atualizou a funcionalidade do [!DNL Google Chrome] e todos [!DNL Chromium]navegadores baseados em para minimizar as informações coletadas por meio do `User-Agent` cabeçalho.
>A partir de março de 2023, o Audience Manager oferecerá suporte a essas atualizações utilizando [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en). Para continuar usando as informações de características fornecidas por meio do `User-Agent` cabeçalho, você deve usar [SDK da Web](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) e habilitar [Dicas do cliente de usuário-agente de alta entropia](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=en).
>Estas atualizações não são suportadas pela [DIL](../../../using/dil/dil-overview.md), para que os clientes do Audience Manager que usam [!DNL DIL] O não poderá coletar informações de características por meio do `User-Agent` cabeçalho.

Descreve os pares de valores chave comuns em nível de plataforma que você pode usar para direcionar usuários com variáveis relacionadas ao dispositivo em todas as propriedades na sua conta Audience Manager.

## Finalidade das variáveis de nível de plataforma {#platform-variables}

<!-- c_tb_device_targeting.xml -->

As variáveis de nível de plataforma permitem pegar os dados transmitidos de um site específico e disponibilizá-los para direcionamento em todas as propriedades no [!DNL Audience Manager] conta. Essas variáveis são formadas por [pares de valor-chave](../../reference/key-value-pairs-explained.md) com a chave com o prefixo `d_` conforme mostrado abaixo.

## Chaves de nível de plataforma definidas pelo agente do usuário {#keys-user-agent}

A variável [!UICONTROL Data Collection Servers] extraia os valores dessas chaves da variável [cabeçalho do agente do usuário](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) in `HTTP` solicitações. Os valores representam informações de nível de dispositivo do [!UICONTROL Device Atlas] banco de dados. Os sinais na tabela abaixo estão disponíveis, conforme extraído do exemplo do agente do usuário. [Baixar uma lista das chaves mais comuns](assets/device_keys.csv), segundo [!UICONTROL Device Atlas] medições.

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
>Mesmo se um ou mais sinais não puderem ser recuperados do cabeçalho do agente do usuário, os outros sinais ainda serão passados para o [!UICONTROL Data Collection Servers].

>[!MORELIKETHIS]
>
>* [Requisitos de prefixo para variáveis-chave](../../features/traits/trait-variable-prefixes.md)

