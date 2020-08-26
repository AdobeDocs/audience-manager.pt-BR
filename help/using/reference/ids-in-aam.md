---
description: Consulte este documento para obter a lista completa das Adobe Audience Manager IDs.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Consulte este documento para obter a lista completa das Adobe Audience Manager IDs.
seo-title: Índice de IDs no Audience Manager
solution: Audience Manager
title: Índice de IDs no Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: reference
translation-type: tm+mt
source-git-commit: b8b848ad04d1ec07c12e57d94e4f3c6e672dc102
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 5%

---


# Index of IDs in [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## Visão geral {#overview}

[!DNL Audience Manager] usa várias IDs para identificar e gerenciar os dados que você envia para ele. Consulte este artigo para obter a lista completa de [!DNL Audience Manager] IDs, juntamente com exemplos dos prefixos com os quais você deve usá-las.

## Prefixação de ID {#prefixing}

Embora você possa consultar a maioria dessas IDs por seus nomes independentes, a maioria delas deve ser usada com vários prefixos, ao transmitir dados por meio de [!DNL DCS] chamadas. Algumas dessas IDs são usadas sem [!DNL Audience Manager] serem expostas aos usuários, enquanto outras também são visíveis na interface do usuário.

Para entender os prefixos usados nos exemplos a seguir, consulte Atributos [suportados para chamadas](../api/dcs-intro/dcs-api-reference/dcs-keys.md)de API DCS.

## [!DNL Audience Manager] Lista de IDs {#id-list}

| ID | Nome e descrição | Uso e exemplos | Local da interface do usuário |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID], também conhecido como [!UICONTROL Device ID]. Uma ID de dispositivo numérica de 38 dígitos que [!DNL Audience Manager] se associa a cada dispositivo com o qual ele interage. Considere essa ID sempre que vir uma menção de usuários únicos na [!DNL Audience Manager] interface do usuário. O Audience Manager salva essa ID como um domínio [!DNL cookie] de `demdex.net` terceiros. | Em [!DNL DCS] chamadas, `uuid` é precedido pelo `d_` prefixo. <br>Exemplo: `d_uuid = 07955261652886032950143702505894272138` | Você pode filtrar [!DNL traits] ao [!UICONTROL Device ID] criar modelos [semelhantes e](../features/algorithmic-models/create-model.md)criar segmentos [](../features/segments/segment-builder.md). Você também pode filtrar os resultados [!UICONTROL Device ID] ao executar Relatórios [Gerais para Características](../reporting/general-reports.md) e Relatórios de [Tendência para Características](../reporting/trend-reports.md). |
| [!DNL ImsOrgId] | [!DNL Organization ID]. Essa é a ID que uma empresa recebe ao se inscrever em uma [!DNL Experience Cloud] conta. | `5DC5123F5245B1D20A490D46@AdobeOrg` | Não visível na interface do [!DNL Audience Manager] usuário. Para saber como encontrar sua empresa [!DNL Organization ID], leia [Localizar sua ID](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)de organização. |
| [!DNL PID] | [!DNL Partner ID]. O [!DNL PID] é um ID de empresa em [!DNL Audience Manager]. Audience Manager associa um [!DNL imsOrgId] a um [!DNL PID]. | `1352` | Não visível na interface do [!DNL Audience Manager] usuário. |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. A [!DNL Experience Cloud] ID ([!DNL ECID], abreviações herdadas [!DNL MID] ou [!DNL MCID]) é derivada matematicamente de seu [!DNL Organization ID] e do [!DNL Audience Manager] [!UICONTROL Unique User ID]. As long as these IDs remain constant, generating the right [!DNL ECID] for a specific user is simply a math problem. Com o mesmo [!DNL Organization ID] e [!DNL Audience Manager] você recebe o mesmo [!DNL UUID] [!DNL ECID] valor toda vez. Você pode ler mais sobre o [!DNL ECID] na documentação [Cookies e Experience Cloud ID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) . | `mid = 08382830887934830189014177072406221371` | Não visível na interface do [!DNL Audience Manager] usuário. |
| [!DNL SID] | [!UICONTROL Trait ID]. A identificação [!UICONTROL Trait ID] é única [!DNL traits] no [!DNL Audience Manager] ambiente. | Em [!DNL DCS] chamadas, `SID` é precedido pelo `d_` prefixo. <br>Exemplo `d_sid=289983`. | Um [!UICONTROL Trait ID] é atribuído a cada um [!DNL trait]e visível na interface do usuário, na página [Características](../features/traits/trait-details-page.md) . |
| [!DNL SID] | [!UICONTROL Segment ID]. A identificação [!UICONTROL Segment ID] é única [!DNL segments] no [!DNL Audience Manager] ambiente. | Em [!DNL DCS] chamadas, `SID` é precedido pelo `d_` prefixo. <br>Exemplo `d_sid=4798574`. | Um [!UICONTROL Segment ID] é atribuído a cada um [!DNL segment]e visível na interface do usuário, na página [Segmentos](../features/segments/segment-summary-view.md) . |
| [!DNL csegID] | [!DNL Legacy Segment ID]. Essa ID identifica exclusivamente os segmentos no [!DNL Audience Manager] ambiente. | `741232` | Um [!UICONTROL Legacy Segment ID] é atribuído a cada segmento e visível na interface do usuário, na página [Segmentos](../features/segments/segment-summary-view.md) . |
| [!DNL destID] | [!UICONTROL Destination ID]. A identificação [!UICONTROL Destination ID] é única [!DNL destinations] no [!DNL Audience Manager] ambiente. Uma ID é atribuída a cada um [!DNL destination] na interface do usuário. | `2523` | Um [!UICONTROL Destination ID] é atribuído a cada um [!DNL destination]e visível na interface do usuário, na página [Destinos](../features/destinations/destinations-home.md) . |
| [!DNL DPID] | [!UICONTROL Data Source ID] (também referido como [!UICONTROL Data Provider ID]). A namespace [!UICONTROL Data Source ID] é para IDs ou [!DNL traits]. Uma ID é atribuída a cada [!DNL data source] (provedor de dados) na interface do usuário. | Em [!DNL DCS] chamadas, `dpid` é precedido pelo `d_` prefixo. <br>Exemplo: `d_dpid=39217`. | Um [!UICONTROL Data Provider ID] é atribuído a cada um [!DNL data source]e visível na interface do usuário, na página Fontes [de](../features/datasources-list-and-settings.md) dados. |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID], também referido como [!DNL CRM ID] ou [!UICONTROL Cross-Device ID]. Uma ID de terceiros. Essa é a ID pela qual você identifica usuários finais em seu próprio [!DNL CRM] sistema. É possível sincronizar [!DNL DPUUIDs] com [!DNL Audience Manager] e sincronizar [!DNL UUIDs] de diferentes [!DNL DPUUIDs] ( [!UICONTROL Data Sources][!DNL DPIDs]) no processo de sincronização de ID. | Em [!DNL DCS] chamadas, `dpuuid` é precedido pelo `d_` prefixo. <br> Exemplo `d_dpuuid=2132-3423vn-343fds-3432r`. | Você pode filtrar [!DNL traits] ao [!UICONTROL Cross-Device ID] criar modelos [semelhantes e](../features/algorithmic-models/create-model.md)criar segmentos [](../features/segments/segment-builder.md). Você também pode filtrar os resultados [!UICONTROL Cross-Device ID] ao executar Relatórios [Gerais para Características](../reporting/general-reports.md) e Relatórios de [Tendência para Características](../reporting/trend-reports.md). |
| [!DNL CRM ID] | Consulte `DPUUID`. | Consulte `DPUUID`. | Consulte `DPUUID`. |
| [!DNL CID], [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. Os pares [!DNL CID] e de [!DNL CID_IC] valor chave substituem [!DNL DPID] e [!DNL DPUUID]. Eles fornecem as mesmas funções que o [!DNL DPID] e [!DNL DPUUID], mas são mais eficientes porque incluem a ID do provedor de dados e a ID do usuário (ou código de integração) em um único par de valores chave. | Em [!DNL DCS] chamadas, essas IDs são precedidas pelo `d_` prefixo. <br>Exemplo: `d_cid_ic=39217_myIntegrationCode`. | Consulte `DPID` e `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. Uma ID única para cada dispositivo de hardware, a ser utilizada para fins de publicidade. Normalmente fornecido pelo fabricante do dispositivo ou do sistema operacional do dispositivo. | Consulte IDs [de dispositivo](#global-device-ids)globais. |  |

## [!DNL Global Device IDs] {#global-device-ids}

As IDs globais de dispositivo são IDs de publicidade de dispositivo, exclusivas para cada dispositivo, fornecidas pelo fabricante do dispositivo ou pelo sistema operacional. A tabela abaixo explica quais são essas IDs e qual seu formato. Para obter mais informações sobre as IDs globais de dispositivos e como usá-las em [!DNL Audience Manager], leia Fontes [de Dados](/help/using/features/global-data-sources.md)Globais.

| ID | [!DNL Global Data Source ID] | Nome e descrição | Exemplo |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] As IDs são identificadores de dispositivos móveis, fornecidos pelo fabricante do dispositivo. Essas IDs representam dispositivos que executam o sistema [!DNL iOS] operacional. | O formato consiste estritamente em 32 dígitos hexadecimais maiúsculos, exibidos em cinco grupos e separados por hífens, na forma 8-4-4-4-12, para um total de 36 caracteres.<br> Exemplo: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s são identificadores de dispositivos móveis fornecidos pelos fabricantes de dispositivos Android. Essas IDs representam dispositivos que executam o sistema [!DNL Android] operacional. | O formato consiste estritamente em 32 dígitos hexadecimais minúsculos, exibidos em cinco grupos e separados por hífens, na forma 8-4-4-4-12, para um total de 36 caracteres. <br>Exemplo: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] representam dispositivos [!DNL Roku] de transmissão. | O formato consiste estritamente em 32 dígitos hexadecimais minúsculos, exibidos em cinco grupos e separados por hífens, na forma 8-4-4-4-12, para um total de 36 caracteres. <br>Exemplo: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s são identificadores de dispositivo gerados por [!DNL Windows 10] cada dispositivo, por usuário. | [!DNL MAID]s são formatados como strings alfanuméricas. |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] são identificadores de dispositivo fornecidos por [!DNL Samsung] Smart TVs. | [!DNL Samsung] [!DNL TIFA] As IDs são formatadas como strings alfanuméricas. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Identificadores de dispositivos que representam dispositivos que executam o sistema [!DNL Fire OS] operacional. | O formato consiste estritamente em 32 dígitos hexadecimais minúsculos, exibidos em cinco grupos e separados por hífens, na forma 8-4-4-4-12, para um total de 36 caracteres. <br>Exemplo: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |