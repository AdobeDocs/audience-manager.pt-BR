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
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 5%

---


# Índice de IDs em [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## Visão geral {#overview}

[!DNL Audience Manager] usa várias IDs para identificar e gerenciar os dados que você envia para ele. Consulte este artigo para obter a lista completa das [!DNL Audience Manager] IDs, juntamente com exemplos dos prefixos com os quais você deve usá-las.

## Prefixação de ID {#prefixing}

Embora você possa consultar a maioria dessas IDs por seus nomes independentes, a maioria delas deve ser usada com vários prefixos, ao transmitir dados por meio de chamadas [!DNL DCS]. Algumas dessas IDs são usadas por [!DNL Audience Manager] sem serem expostas aos usuários, enquanto outras também são visíveis na interface do usuário (UI).

Para entender os prefixos usados nos seguintes exemplos, consulte [Atributos suportados para chamadas de API DCS](../api/dcs-intro/dcs-api-reference/dcs-keys.md).

## [!DNL Audience Manager] Lista de IDs {#id-list}

| ID | Nome e descrição | Uso e exemplos | Local da interface do usuário |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID], também conhecido como  [!UICONTROL Device ID]. Uma ID de dispositivo numérica de 38 dígitos que [!DNL Audience Manager] associa a cada dispositivo com o qual ele interage. Pense nessa ID sempre que vir uma menção de usuários únicos na interface do usuário [!DNL Audience Manager]. O Audience Manager salva essa ID como [!DNL cookie] no domínio `demdex.net` de terceiros. | Em chamadas [!DNL DCS], `uuid` é precedido pelo prefixo `d_`. <br>Exemplo: `d_uuid = 07955261652886032950143702505894272138` | Você pode filtrar [!DNL traits] por [!UICONTROL Device ID] ao criar [Modelos semelhantes](../features/algorithmic-models/create-model.md) e [criar segmentos](../features/segments/segment-builder.md). Você também pode filtrar os resultados por [!UICONTROL Device ID] ao executar [Relatórios Gerais para Características](../reporting/general-reports.md) e [Relatórios de Tendência para Características](../reporting/trend-reports.md). |
| [!DNL ImsOrgId] | [!DNL Organization ID]. Essa é a ID que uma empresa recebe ao se inscrever em uma conta [!DNL Experience Cloud]. | `5DC5123F5245B1D20A490D46@AdobeOrg` | Não visível na interface do usuário [!DNL Audience Manager]. Para saber como encontrar sua empresa [!DNL Organization ID], leia [Localizar sua ID da organização](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |
| [!DNL PID] | [!DNL Partner ID]. [!DNL PID] é uma ID de empresa em [!DNL Audience Manager]. Audience Manager associa um [!DNL imsOrgId] a um [!DNL PID]. | `1352` | Não visível na interface do usuário [!DNL Audience Manager]. |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. A ID [!DNL Experience Cloud] ([!DNL ECID], abreviações herdadas [!DNL MID] ou [!DNL MCID]) é derivada matematicamente de [!DNL Organization ID] e [!DNL Audience Manager] [!UICONTROL Unique User ID]. Desde que essas IDs permaneçam constantes, gerar o [!DNL ECID] certo para um usuário específico é simplesmente um problema matemático. Com os mesmos [!DNL Organization ID] e [!DNL Audience Manager] [!DNL UUID] você obtém o mesmo valor [!DNL ECID] sempre. Você pode ler mais sobre [!DNL ECID] na documentação [Cookies e Experience Cloud ID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17). | `mid = 08382830887934830189014177072406221371` | Não visível na interface do usuário [!DNL Audience Manager]. |
| [!DNL SID] | [!UICONTROL Trait ID]. O [!UICONTROL Trait ID] identifica exclusivamente [!DNL traits] no ambiente [!DNL Audience Manager]. | Em chamadas [!DNL DCS], `SID` é precedido pelo prefixo `d_`. <br>Exemplo `d_sid=289983`. | Um [!UICONTROL Trait ID] é atribuído a cada [!DNL trait] e visível na interface do usuário, na página [Características](../features/traits/trait-details-page.md). |
| [!DNL SID] | [!UICONTROL Segment ID]. O [!UICONTROL Segment ID] identifica exclusivamente [!DNL segments] no ambiente [!DNL Audience Manager]. | Em chamadas [!DNL DCS], `SID` é precedido pelo prefixo `d_`. <br>Exemplo `d_sid=4798574`. | Um [!UICONTROL Segment ID] é atribuído a cada [!DNL segment] e visível na interface do usuário, na página [Segmentos](../features/segments/segment-summary-view.md). |
| [!DNL csegID] | [!DNL Legacy Segment ID]. Essa ID identifica exclusivamente segmentos no ambiente [!DNL Audience Manager]. | `741232` | Um [!UICONTROL Legacy Segment ID] é atribuído a cada segmento e visível na interface do usuário, na página [Segmentos](../features/segments/segment-summary-view.md). |
| [!DNL destID] | [!UICONTROL Destination ID]. O [!UICONTROL Destination ID] identifica exclusivamente [!DNL destinations] no ambiente [!DNL Audience Manager]. Uma ID é atribuída a cada [!DNL destination] na interface do usuário. | `2523` | Um [!UICONTROL Destination ID] é atribuído a cada [!DNL destination] e é visível na interface do usuário, na página [Destinos](../features/destinations/destinations-home.md). |
| [!DNL DPID] | [!UICONTROL Data Source ID] (também referido como  [!UICONTROL Data Provider ID]). [!UICONTROL Data Source ID] é uma namespace para IDs ou [!DNL traits]. Uma ID é atribuída a cada [!DNL data source] (provedor de dados) na interface do usuário. | Em chamadas [!DNL DCS], `dpid` é precedido pelo prefixo `d_`. <br>Exemplo: `d_dpid=39217`. | Um [!UICONTROL Data Provider ID] é atribuído a cada [!DNL data source] e visível na interface do usuário, na página [Fontes de Dados](../features/datasources-list-and-settings.md). |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID], também referido como  [!DNL CRM ID] ou  [!UICONTROL Cross-Device ID]. Uma ID de terceiros. Esta é a ID pela qual você identifica usuários finais em seu próprio sistema [!DNL CRM]. Você pode sincronizar [!DNL DPUUIDs] com [!DNL Audience Manager] [!DNL UUIDs] e pode sincronizar [!DNL DPUUIDs] de [!UICONTROL Data Sources] diferentes ([!DNL DPIDs]) no processo de sincronização de ID. | Em [!DNL DCS] chamadas, `dpuuid` é precedido pelo prefixo `d_`. <br> Exemplo `d_dpuuid=2132-3423vn-343fds-3432r`. | Você pode filtrar [!DNL traits] por [!UICONTROL Cross-Device ID] ao criar [Modelos semelhantes](../features/algorithmic-models/create-model.md) e [criar segmentos](../features/segments/segment-builder.md). Você também pode filtrar os resultados por [!UICONTROL Cross-Device ID] ao executar [Relatórios Gerais para Características](../reporting/general-reports.md) e [Relatórios de Tendência para Características](../reporting/trend-reports.md). |
| [!DNL CRM ID] | Consulte `DPUUID`. | Consulte `DPUUID`. | Consulte `DPUUID`. |
| [!DNL CID],  [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. Os pares de [!DNL CID] e [!DNL CID_IC] valor chave substituem [!DNL DPID] e [!DNL DPUUID]. Elas fornecem as mesmas funções que [!DNL DPID] e [!DNL DPUUID], mas são mais eficientes porque incluem a ID do provedor de dados e a ID do usuário (ou código de integração) em um único par de valores chave. | Em chamadas [!DNL DCS], essas IDs são precedidas pelo prefixo `d_`. <br>Exemplo: `d_cid_ic=39217_myIntegrationCode`. | Consulte `DPID` e `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. Uma ID única para cada dispositivo de hardware, a ser utilizada para fins de publicidade. Normalmente fornecido pelo fabricante do dispositivo ou do sistema operacional do dispositivo. | Consulte [IDs de dispositivo global](#global-device-ids). |  |

## [!DNL Global Device IDs] {#global-device-ids}

As IDs globais de dispositivo são IDs de publicidade de dispositivo, exclusivas para cada dispositivo, fornecidas pelo fabricante do dispositivo ou pelo sistema operacional. A tabela abaixo explica quais são essas IDs e qual seu formato. Para obter mais informações sobre as IDs de dispositivo global e como usá-las em [!DNL Audience Manager], leia [Fontes de Dados Globais](/help/using/features/global-data-sources.md).

| ID | [!DNL Global Data Source ID] | Nome e descrição | Exemplo |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 2015 | [!DNL Identifier for Advertisers] As IDs são identificadores de dispositivos móveis, fornecidos pelo fabricante do dispositivo. Essas IDs representam dispositivos que executam o sistema operacional [!DNL iOS]. | O formato consiste estritamente em 32 dígitos hexadecimais maiúsculos, exibidos em cinco grupos e separados por hífens, na forma 8-4-4-4-12, para um total de 36 caracteres.<br> Exemplo: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 2014 | [!DNL Google Advertising ID]s são identificadores de dispositivos móveis fornecidos pelos fabricantes de dispositivos Android. Essas IDs representam dispositivos que executam o sistema operacional [!DNL Android]. | O formato consiste estritamente em 32 dígitos hexadecimais minúsculos, exibidos em cinco grupos e separados por hífens, na forma 8-4-4-4-12, para um total de 36 caracteres. <br>Exemplo: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] representam dispositivos  [!DNL Roku] de transmissão. | O formato consiste estritamente em 32 dígitos hexadecimais minúsculos, exibidos em cinco grupos e separados por hífens, na forma 8-4-4-4-12, para um total de 36 caracteres. <br>Exemplo: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s são identificadores de dispositivo gerados por  [!DNL Windows 10] cada dispositivo, por usuário. | [!DNL MAID]s são formatados como strings alfanuméricas. |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] são identificadores de dispositivo fornecidos por TVs  [!DNL Samsung] inteligentes. | [!DNL Samsung] [!DNL TIFA] As IDs são formatadas como strings alfanuméricas. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Identificadores de dispositivo que representam dispositivos que executam o sistema operacional [!DNL Fire OS]. | O formato consiste estritamente em 32 dígitos hexadecimais minúsculos, exibidos em cinco grupos e separados por hífens, na forma 8-4-4-4-12, para um total de 36 caracteres. <br>Exemplo: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |