---
description: Descreve os pares de valores-chave comuns no nível da plataforma que podem ser usados para direcionar usuários com variáveis relacionadas ao dispositivo em todas as propriedades da sua conta do Audience Manager.
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
>A Google atualizou a funcionalidade de [!DNL Google Chrome] e tudo [!DNL Chromium]navegadores baseados em para minimizar as informações coletadas pelo `User-Agent` cabeçalho.
>A partir de março de 2023, o Audience Manager oferecerá suporte a essas atualizações aproveitando [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en). Para continuar usando as informações de características fornecidas por meio da `User-Agent` cabeçalho, você deve usar [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) e ativar [Dicas de cliente do agente de usuário de alta criptografia](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=en).
>Estas atualizações não são suportadas pela [DIL](../../../using/dil/dil-overview.md), portanto, clientes do Audience Manager que usam [!DNL DIL] não poderá coletar informações de características por meio do `User-Agent` cabeçalho.

Descreve os pares de valores-chave comuns no nível da plataforma que podem ser usados para direcionar usuários com variáveis relacionadas ao dispositivo em todas as propriedades da sua conta do Audience Manager.

## Finalidade das variáveis no nível da plataforma {#platform-variables}

<!-- c_tb_device_targeting.xml -->

As variáveis de nível de plataforma permitem que você pegue os dados transmitidos de um site específico e os disponibilize para direcionamento em todas as propriedades em seu [!DNL Audience Manager] conta. Essas variáveis são formadas por [pares de valor-chave](../../reference/key-value-pairs-explained.md) com o prefixo `d_` conforme mostrado abaixo.

## Chaves de nível de plataforma definidas pelo Agente do usuário {#keys-user-agent}

O [!UICONTROL Data Collection Servers] extrair os valores dessas chaves do [cabeçalho do agente do usuário](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) em `HTTP` solicitações. Os valores representam informações no nível do dispositivo da variável [!UICONTROL Device Atlas] banco de dados. Os sinais na tabela abaixo estão disponíveis, como extraído do exemplo do agente do usuário. [Baixe uma lista das chaves mais comuns](assets/device_keys.csv), de acordo com [!UICONTROL Device Atlas] medidas.

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
>Mesmo que um ou mais sinais não possam ser recuperados do cabeçalho do agente do usuário, os outros sinais ainda serão passados para o [!UICONTROL Data Collection Servers].

>[!MORELIKETHIS]
>
>* [Requisitos de prefixo para variáveis-chave](../../features/traits/trait-variable-prefixes.md)

