---
description: Descreve os pares de valores-chave comuns no nível da plataforma que podem ser usados para direcionar usuários com variáveis relacionadas ao dispositivo em todas as propriedades da sua conta do Audience Manager.
seo-description: Descreve os pares de valores-chave comuns no nível da plataforma que podem ser usados para direcionar usuários com variáveis relacionadas ao dispositivo em todas as propriedades da sua conta do Audience Manager.
seo-title: Direcionamento de dispositivo com chaves de nível de plataforma
solution: Audience Manager
title: Direcionamento de dispositivo com chaves de nível de plataforma
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: 'Características '
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 9%

---

# Direcionamento de dispositivo com chaves de nível de plataforma {#device-targeting-with-platform-level-keys}

Descreve os pares de valores-chave comuns no nível da plataforma que podem ser usados para direcionar usuários com variáveis relacionadas ao dispositivo em todas as propriedades da sua conta do Audience Manager.

## Propósito das variáveis no nível da plataforma {#platform-variables}

<!-- c_tb_device_targeting.xml -->

As variáveis de nível de plataforma permitem que você pegue os dados transmitidos de um site específico e os disponibilize para definição de metas em todas as propriedades da sua conta [!DNL Audience Manager]. Essas variáveis são formadas por [pares de valores chave](../../reference/key-value-pairs-explained.md) com a chave prefixada por `d_`, conforme mostrado abaixo.

## Chaves de nível de plataforma definidas pelo Agente do usuário {#keys-user-agent}

O [!UICONTROL Data Collection Servers] extrai os valores para essas chaves do [cabeçalho do agente do usuário](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) em solicitações `HTTP`. Os valores representam informações no nível do dispositivo do banco de dados [!UICONTROL Device Atlas]. Os sinais na tabela abaixo estão disponíveis, como extraído do exemplo do agente do usuário. [Baixe uma lista das chaves](assets/device_keys.csv) mais comuns, de acordo com  [!UICONTROL Device Atlas] as medições.

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

