---
description: Consulte este documento para obter a lista completa das IDs do Adobe Audience Manager.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Consulte este documento para obter a lista completa das IDs do Adobe Audience Manager.
seo-title: Índice de IDs no Audience Manager
solution: Audience Manager
title: Índice de IDs no Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: f8916812a31513d3d8401a0598f37dae02a3fd02

---


# Índice de IDs no Audience Manager{#index-of-ids-in-audience-manager}

## Visão geral {#overview}

O Audience Manager usa várias IDs para identificar e gerenciar os dados enviados para ele. Consulte este artigo para obter a lista completa das IDs do Adobe Audience Manager, juntamente com exemplos dos prefixos com os quais você deve usá-las.

## Prefixação de ID {#prefixing}

Embora você possa consultar a maioria dessas IDs por seus nomes independentes, a maioria delas deve ser usada com vários prefixos ao transmitir dados por meio de chamadas DCS. Algumas dessas IDs são usadas pelo Audience Manager sem serem expostas aos usuários, enquanto outras também são visíveis na interface do usuário (UI).

Para entender os prefixos usados nos seguintes exemplos, consulte Atributos [suportados para chamadas de API DCS](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Lista de IDs do Audience Manager {#id-list}

| ID | Nome e descrição | Uso e exemplos | Localização da interface |
|---|---|---|---|
| [!DNL AAM UUID] | ID de usuário exclusiva do Audience Manager. Uma ID de dispositivo numérica de 38 dígitos associada pelo Audience Manager a cada dispositivo com o qual ele interage. Pense nessa ID sempre que vir uma menção de usuários únicos na interface do usuário do Audience Manager. O Audience Manager salva essa ID como um cookie no domínio de `demdex.net` terceiros. | Em [!DNL DCS] chamadas, `uuid` é precedido pelo `d_` prefixo. <br>Exemplo: `d_uuid = 07955261652886032950143702505894272138` | Não visível na interface do usuário do Audience Manager. |
| [!DNL ImsOrgId] | ID da organização. Essa é a ID que uma empresa fornece ao se inscrever em uma conta da Experience Cloud. | `5DC5123F5245B1D20A490D46@AdobeOrg` | Não visível na interface do usuário do Audience Manager. Para saber como encontrar a ID da empresa, leia [Localizar a ID](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)da empresa. |
| PID | ID do parceiro. O PID é uma ID da empresa no Audience Manager. O Audience Manager associa um [!DNL imsOrgId] a um [!DNL PID]. | `1352` | Não visível na interface do usuário do Audience Manager. |
| [!DNL ECID], [!DNL MID] | Experience Cloud ID. A Experience Cloud ID ([!DNL ECID], abreviações herdadas [!DNL MID] ou [!DNL MCID]) é derivada matematicamente da ID da empresa e da ID de usuário exclusiva do Audience Manager. As long as these IDs remain constant, generating the right [!DNL ECID] for a specific user is simply a math problem. With the same organization ID and Audience Manager [!DNL UUID] you get the same [!DNL ECID] value every time. Você pode ler mais sobre a ECID na documentação [Cookies e Experience Cloud ID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) . | `mid = 08382830887934830189014177072406221371` | Não visível na interface do usuário do Audience Manager. |
| [!DNL SID] | ID da característica. A ID de característica identifica exclusivamente características no ambiente do Audience Manager. | Em [!DNL DCS] chamadas, `SID` é precedido pelo `d_` prefixo. <br>Exemplo `d_sid=289983`. | Uma ID de característica é atribuída a cada característica e é visível na interface do usuário, na página [Características](../features/traits/trait-details-page.md) . |
| [!DNL SID] | ID do segmento. A ID do segmento identifica exclusivamente segmentos no ambiente do Audience Manager. | Em [!DNL DCS] chamadas, `SID` é precedido pelo `d_` prefixo. <br>Exemplo `d_sid=4798574`. | Uma ID de segmento é atribuída a cada segmento e é visível na interface do usuário, na página [Segmentos](../features/segments/segment-summary-view.md) . |
| [!DNL csegID] | ID do segmento herdado. Essa ID identifica exclusivamente segmentos no ambiente do Audience Manager. | `741232` | Uma ID de segmento herdada é atribuída a cada segmento e visível na interface do usuário, na página [Segmentos](../features/segments/segment-summary-view.md) . |
| [!DNL destID] | ID de destino. A ID de destino identifica exclusivamente os destinos no ambiente do Audience Manager. Uma ID é atribuída a cada destino na interface do usuário. | `2523` | Uma ID de destino é atribuída a cada destino e é visível na interface do usuário, na página [Destinos](../features/destinations/destinations-home.md) . |
| [!DNL DPID] | ID da fonte de dados (também chamada de ID do provedor de dados). A ID da fonte de dados é um namespace para IDs ou características. Uma ID é atribuída a cada fonte de dados (provedor de dados) na interface. | Em [!DNL DCS] chamadas, `dpid` é precedido pelo `d_` prefixo. <br>Exemplo: `d_dpid=39217`. | Uma ID do provedor de dados é atribuída a cada fonte de dados e é visível na interface do usuário, na página Fontes [de](../features/datasources-list-and-settings.md) dados. |
| [!DNL DPUUID] | ID de usuário único do provedor de dados (também chamada de [!DNL CRM ID]). Uma ID de terceiros. Essa é a ID pela qual você identifica usuários finais em seu próprio [!DNL CRM] sistema. Você pode sincronizar [!DNL DPUUIDs] com o Audience Manager [!DNL UUIDs] e pode sincronizar [!DNL DPUUIDs] a partir de diferentes Fontes de Dados ([!DNL DPIDs]) no processo de sincronização de ID. | Nas chamadas do DCS, `dpuuid` é precedido pelo `d_` prefixo. <br> Exemplo `d_dpuuid=2132-3423vn-343fds-3432r`. | Não visível na interface do usuário do Audience Manager. |
| [!DNL CRM ID] | Consulte `DPUUID`. | Consulte `DPUUID`. | Consulte `DPUUID`. |
| [!DNL CID], [!DNL CID_IC] | ID do cliente, Código de integração da ID do cliente. Os pares [!DNL CID] e de [!DNL CID_IC] valor chave substituem [!DNL DPID] e [!DNL DPUUID]. Eles fornecem as mesmas funções que o [!DNL DPID] e [!DNL DPUUID], mas são mais eficientes porque incluem a ID do provedor de dados e a ID do usuário (ou código de integração) em um único par de valores chave. | Em chamadas DCS, essas IDs são precedidas pelo `d_` prefixo. <br>Exemplo: `d_cid_ic=39217_myIntegrationCode`. | Consulte `DPID` e `DPUUID`. |
| [!DNL DAID] | ID de anúncio do dispositivo. Uma ID única para cada dispositivo de hardware, a ser utilizada para fins de publicidade. Normalmente fornecido pelo fabricante do dispositivo ou do sistema operacional do dispositivo. | Consulte IDs [de dispositivo](#global-device-ids)globais. |  |

## IDs de dispositivo globais {#global-device-ids}

As IDs globais de dispositivo são IDs de publicidade de dispositivo, exclusivas para cada dispositivo, fornecidas pelo fabricante do dispositivo ou pelo sistema operacional. A tabela abaixo explica quais são essas IDs e qual seu formato. Para obter mais informações sobre as IDs globais de dispositivos e como usá-las no Audience Manager, leia Fontes [de Dados](/help/using/features/global-data-sources.md)Globais.

| ID | ID da Fonte de Dados Global | Nome e descrição | Exemplo |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] As IDs são identificadores de dispositivos móveis, fornecidos pelo fabricante do dispositivo. Essas IDs representam dispositivos que executam o sistema operacional iOS. | O formato consiste estritamente em 32 dígitos hexadecimais maiúsculos, exibidos em cinco grupos e separados por hífens, na forma 8-4-4-4-12, para um total de 36 caracteres.<br> Exemplo: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s são identificadores de dispositivos móveis fornecidos pelos fabricantes de dispositivos Android. Essas IDs representam dispositivos que executam o sistema [!DNL Android] operacional. | O formato consiste estritamente em 32 dígitos hexadecimais minúsculos, exibidos em cinco grupos e separados por hífens, na forma 8-4-4-4-12, para um total de 36 caracteres. <br>Exemplo: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] representam dispositivos [!DNL Roku] de transmissão. | O formato consiste estritamente em 32 dígitos hexadecimais minúsculos, exibidos em cinco grupos e separados por hífens, na forma 8-4-4-4-12, para um total de 36 caracteres. <br>Exemplo: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s são identificadores de dispositivo gerados por [!DNL Windows 10] cada dispositivo, por usuário. | [!DNL MAID]s são formatados como strings alfanuméricas. |
| [!DNL DUID] | 404660 | [!DNL Samsung DUID]s são identificadores de dispositivos fornecidos por Smart TVs da Samsung. | As Samsung [!DNL DUID]s são formatadas como strings alfanuméricas. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Identificadores de dispositivos que representam dispositivos que executam o sistema [!DNL Fire OS] operacional. | O formato consiste estritamente em 32 dígitos hexadecimais minúsculos, exibidos em cinco grupos e separados por hífens, na forma 8-4-4-4-12, para um total de 36 caracteres. <br>Exemplo: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |

