---
description: Descreve os pares de valores principais comuns de nível de plataforma que você pode usar para públicos alvos usuários com variáveis relacionadas a dispositivos em todas as propriedades na sua conta do Audience Manager.
seo-description: Descreve os pares de valores principais comuns de nível de plataforma que você pode usar para públicos alvos usuários com variáveis relacionadas a dispositivos em todas as propriedades na sua conta do Audience Manager.
seo-title: Direcionamento de dispositivo com chaves de nível de plataforma
solution: Audience Manager
title: Direcionamento de dispositivo com chaves de nível de plataforma
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 9%

---


# Direcionamento de dispositivo com chaves de nível de plataforma {#device-targeting-with-platform-level-keys}

Descreve os pares de valores principais comuns de nível de plataforma que você pode usar para públicos alvos usuários com variáveis relacionadas a dispositivos em todas as propriedades na sua conta do Audience Manager.

## Objetivo das variáveis de nível Platform {#platform-variables}

<!-- c_tb_device_targeting.xml -->

As variáveis de nível Platform permitem que você capture os dados enviados de um site específico e os disponibilize para definição de metas em todas as propriedades da sua [!DNL Audience Manager] conta. Essas variáveis são formadas por pares [de valor](../../reference/key-value-pairs-explained.md) chave com o prefixo key `d_` , conforme mostrado abaixo.

## Teclas de nível Platform Definidas pelo Agente do Usuário {#keys-user-agent}

A [!UICONTROL Data Collection Servers] extrai os valores dessas chaves do cabeçalho [do agente do](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) usuário em `HTTP` solicitações. Os valores representam informações no nível do dispositivo do [!UICONTROL Device Atlas] banco de dados. Os sinais na tabela abaixo estão disponíveis, como extraídos do exemplo do agente do usuário. [Baixe uma lista das teclas](assets/device_keys.csv)mais comuns, de acordo com as [!UICONTROL Device Atlas] medidas.

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
>Mesmo que um ou mais sinais não possam ser recuperados do cabeçalho do agente do usuário, os outros sinais ainda serão transmitidos para o [!UICONTROL Data Collection Servers].

>[!MORELIKETHIS]
>
>* [Requisitos de prefixo para variáveis-chave](../../features/traits/trait-variable-prefixes.md)

