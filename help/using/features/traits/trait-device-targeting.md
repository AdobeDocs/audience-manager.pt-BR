---
description: Descreve os pares de valores chave comuns em nível de plataforma que você pode usar para direcionar usuários com variáveis relacionadas ao dispositivo em todas as propriedades na sua conta do Audience Manager.
seo-description: Describes the common platform-level key-value pairs you can use to target users with device-related variables across all properties in your Audience Manager account.
seo-title: Device Targeting With Platform-level Keys
solution: Audience Manager
title: Direcionamento de dispositivo com chaves de nível de plataforma
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
source-git-commit: b299783b993c5d4a1c7738eca82932c20f377ee7
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 1%

---

# Direcionamento de dispositivo com chaves de nível de plataforma {#device-targeting-with-platform-level-keys}

>[!WARNING]
>
>A Google atualizou a funcionalidade de [!DNL Google Chrome] e de todos os navegadores baseados em [!DNL Chromium] para minimizar as informações coletadas por meio do cabeçalho `User-Agent`.
>&#x200B;>A partir de março de 2023, o Audience Manager oferecerá suporte a essas atualizações aproveitando o [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en). Para continuar usando as informações de características fornecidas pelo cabeçalho `User-Agent`, você deve usar o [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) e habilitar as [Client Hints de Agente do Usuário de Alta Entropia](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=en).
>&#x200B;>Não há suporte para estas atualizações no [DIL](../../../using/dil/dil-overview.md), portanto, os clientes do Audience Manager que usam o [!DNL DIL] não poderão coletar informações de características por meio do cabeçalho `User-Agent`.

Descreve os pares de valores chave comuns em nível de plataforma que você pode usar para direcionar usuários com variáveis relacionadas ao dispositivo em todas as propriedades na sua conta do Audience Manager.

## Finalidade das variáveis de nível de plataforma {#platform-variables}

<!-- c_tb_device_targeting.xml -->

As variáveis de nível de plataforma permitem que você obtenha dados transmitidos de um site específico e os disponibilize para direcionamento em todas as propriedades da sua conta do [!DNL Audience Manager]. Essas variáveis são formadas por [pares de valores chave](../../reference/key-value-pairs-explained.md) com a chave prefixada por `d_`, como mostrado abaixo.

## Chaves de nível de plataforma definidas pelo agente do usuário {#keys-user-agent}

O [!UICONTROL Data Collection Servers] extrai os valores dessas chaves do [cabeçalho do agente do usuário](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) em `HTTP` solicitações. Os valores representam informações de nível de dispositivo do banco de dados [!UICONTROL Device Atlas]. Os sinais na tabela abaixo estão disponíveis, conforme extraído do exemplo do agente do usuário. [Baixe uma lista das chaves mais comuns](assets/device_keys.csv), de acordo com as [!UICONTROL Device Atlas] medidas.

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
