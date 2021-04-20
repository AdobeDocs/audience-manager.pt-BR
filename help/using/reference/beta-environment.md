---
description: O ambiente beta é para testar sua implementação de Audience Manager. As alterações feitas em beta não afetam os dados de produção. Entre em contato com o representante de soluções de parceiros do Audience Manager se estiver interessado em usar o ambiente beta.
keywords: sandbox
seo-description: O ambiente beta é para testar sua implementação de Audience Manager. As alterações feitas em beta não afetam os dados de produção. Entre em contato com o representante de soluções de parceiros do Audience Manager se estiver interessado em usar o ambiente beta.
seo-title: Ambiente beta
solution: Audience Manager
title: Ambiente beta
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
feature: Reference
exl-id: a6a5e1c2-29a2-40bf-972c-87fb8716a394
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 4%

---

# Ambiente beta {#beta-environment}

O ambiente beta é para testar sua implementação de Audience Manager. As alterações feitas em beta não afetam os dados de produção. Entre em contato com o representante de soluções de parceiros do Audience Manager se estiver interessado em usar o ambiente beta.

## Visão geral

O ambiente beta é uma réplica exata do ambiente de produção, sem recursos experimentais ou não lançados. Suas credenciais de logon do ambiente de produção são válidas no ambiente beta.

**Atualizar Programação**

O ambiente beta é atualizado no final de cada mês durante horários fora do horário de pico.

**Tráfego de saída**

O tráfego de saída não está habilitado para o ambiente beta.

<!-- 

Added re: AAM-30826.

 -->

## Endpoints



| Serviço | URL/Nome de host | Como obter acesso |
|--- |--- | --- |
| S3 | Entre em contato com o representante de soluções de parceiros do Audience Manager ou com o Atendimento ao cliente | Entre em contato com o representante de soluções de parceiros do Audience Manager ou com o Atendimento ao cliente para configurar um bucket do Amazon S3 para sua instância beta. Leia sobre as [vantagens de usar o Amazon S3](../reference/amazon-s3.md). |
| DCS | `https://dcs-beta.demdex.net/...` | Consulte [Acesso ao DCS no Ambiente Beta](../reference/beta-environment.md#access-dcs-beta-environment). |
| Interface do usuário | `https://bank-beta.demdex.com` | As credenciais do ambiente de produção são válidas para o ambiente beta. |
| API | `https://api-beta.demdex.com/...` | As credenciais do ambiente de produção são válidas para o ambiente beta. Recomendamos que você crie um usuário genérico da API, [consulte os detalhes](../api/rest-api-main/aam-api-getting-started.md#requirements). |

## Acessar o DCS no ambiente beta {#access-dcs-beta-environment}

1. Faça uma chamada DCS, usando o comando curl [](https://curl.haxx.se/docs/manpage.html). O Curl é uma ferramenta para transferir dados de ou para um servidor, usando um de vários protocolos compatíveis.

   Por exemplo:

   `curl -v https://dcs-beta.demdex.net/event`

1. Verifique se sua solicitação foi veiculada pelo DCS beta procurando por &quot;sandbox&quot; no cabeçalho de resposta do DCS.

   Por exemplo:

   ```
   curl -v http://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

<!--

1. Determine the load balancer's endpoint IP addresses.

   Run the `dig`  [command](https://en.wikipedia.org/wiki/Dig_(command)) to determine the IP address of the nearest load balancer. The `dig` command queries the Domain Name System and returns the name and IP addresses of the [!DNL Audience Manager] [!UICONTROL Data Collection Servers (DCS)].

   ```
   dig dcs-beta.demdex.net
   ...
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.87.15.51
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 50.16.150.8
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.2.228.100
   ```

2. Using one of the addresses in the above table, add a static DNS entry in the [!DNL /etc/hosts] file.

   On Windows, modify [!DNL c:\WINDOWS\system32\drivers\etc\hosts].

   For example:

   [!DNL 52.87.15.51 *`samplepartner`*.demdex.net]

   >[!NOTE]
   >
   >The addresses change occasionally, so you must keep your [!DNL /etc/hosts] file up to date.

   Additionally, if you need to set up ID synchronization, you must add a similar entry for [!DNL dpm.demdex.net.]

   [!DNL 52.87.15.51 dpm.demdex.net]. 

3. Make a DCS call, using the `curl` [command](https://curl.haxx.se/docs/manpage.html). Curl is a tool to transfer data from or to a server, using one of many supported protocols.

   For example:

   [!DNL https://<domain>/event?product=camera] 

4. Verify that your request was served by the beta DCS by looking for "sandbox" in the DCS response header.

   For example:

   ```
   curl -v https://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

   -->
