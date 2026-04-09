---
description: O ambiente beta é usado para testar a implementação do Audience Manager. As alterações feitas na versão beta não afetam os dados de produção. Entre em contato com o representante de soluções de parceiros da Audience Manager se estiver interessado em usar o ambiente beta.
keywords: sandbox
seo-description: The beta environment is for testing your Audience Manager implementation. Changes made in beta do not affect production data. Contact your Audience Manager Partner Solutions representative if you're interested in using the beta environment.
seo-title: Beta Environment
solution: Audience Manager
title: Ambiente do Beta
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
feature: Reference
exl-id: a6a5e1c2-29a2-40bf-972c-87fb8716a394
TQID: https://experienceleague.adobe.com/zz0F-QZ2QIVdVkGO5T9LoX4R8T12ivdz-pQ3Iv-DLao
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2:
  - id: d8f681b8-67cc-42dc-85c5-a0977528a942
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 362
ht-degree: 2%

---

# Ambiente do Beta {#beta-environment}

O ambiente beta é usado para testar a implementação do Audience Manager. As alterações feitas na versão beta não afetam os dados de produção. Entre em contato com o representante de soluções de parceiros da Audience Manager se estiver interessado em usar o ambiente beta.

## Visão geral

A funcionalidade no ambiente beta é uma réplica exata do ambiente de produção, sem recursos experimentais ou não lançados. Suas credenciais de logon do ambiente de produção são válidas no ambiente beta.

**Atualizar Calendário**

O ambiente beta é atualizado no final de cada mês fora do horário de pico.

>[!IMPORTANT]
>
>Observe que os dados do cliente ([sinais, características e segmentos](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html?lang=pt-BR)) não são sincronizados entre os ambientes de produção e beta.

## Tráfego de entrada

O ambiente beta oferece suporte ao tráfego de entrada somente para fins de validação de nome de arquivo e sintaxe de conteúdo. Como não há mapeamento de ID ocorrendo no ambiente beta, os clientes não verão populações de segmentos.

Consequentemente, a página [!UICONTROL Onboarding Status] sempre relatará [!UICONTROL No matching AAM ID] na assimilação de arquivos no ambiente beta.

Recomendamos que todos os clientes executem qualquer teste de entrada em seus ambientes de produção.

## Tráfego de saída

O tráfego de saída não está ativado para o ambiente beta.

## Endpoints

| Serviço | URL/Nome do host | Como obter acesso |
|--- |--- | --- |
| S3 | Entre em contato com seu representante de soluções de parceiros da Audience Manager ou com o Atendimento ao cliente | Entre em contato com seu representante de soluções de parceiros da Audience Manager ou com o Atendimento ao cliente para configurar um bucket do Amazon S3 para sua instância beta. Leia sobre as [vantagens de usar o Amazon S3](../reference/amazon-s3.md). |
| DCS | `https://dcs-beta.demdex.net/...` | Consulte [Acessando o DCS no Ambiente Beta](../reference/beta-environment.md#access-dcs-beta-environment). |
| Interface do usuário | `https://bank-beta.demdex.com` | Suas credenciais de ambiente de produção são válidas para o ambiente beta. |
| API | `https://api-beta.demdex.com/...` | Suas credenciais de ambiente de produção são válidas para o ambiente beta. Recomendamos que você crie um usuário de API genérico, [veja os detalhes](../api/rest-api-main/aam-api-getting-started.md#requirements). |

## Acesso ao DCS no ambiente do Beta {#access-dcs-beta-environment}

1. Fazer uma chamada DCS, usando o curl [command](https://curl.haxx.se/docs/manpage.html). O Curl é uma ferramenta para transferir dados de ou para um servidor, usando um dos vários protocolos compatíveis.

   Por exemplo:

   `curl -v https://dcs-beta.demdex.net/event`

1. Verifique se sua solicitação foi atendida pelo DCS beta procurando por &quot;sandbox&quot; no cabeçalho de resposta do DCS.

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
