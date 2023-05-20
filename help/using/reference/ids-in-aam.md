---
description: Consulte este documento para obter a lista completa das IDs da Adobe Audience Manager.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuuid, uuid
seo-description: Refer to this document for the complete list of Adobe Audience Manager IDs.
seo-title: Index of IDs in Audience Manager
solution: Audience Manager
title: Índice de IDs no Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: Reference
exl-id: 1caf3c6a-ebfd-49f1-9ebd-d4604474c070
source-git-commit: e408c118870fb331c40758be8a7e6b38690aeb5f
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 5%

---

# Índice de IDs em [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## Visão geral {#overview}

[!DNL Audience Manager] O usa várias IDs para identificar e gerenciar os dados enviados para ele. Consulte este artigo para obter a lista completa de [!DNL Audience Manager] IDs, juntamente com exemplos dos prefixos que você deve usá-los com.

## Prefixo de ID {#prefixing}

Embora você possa consultar a maioria dessas IDs por seus nomes independentes, a maioria delas deve ser usada com vários prefixos ao transmitir dados pelo [!DNL DCS] chamadas. Algumas dessas IDs são usadas pelo [!DNL Audience Manager] sem ser exposto aos usuários, enquanto outros também ficam visíveis na interface do usuário (UI).

Para compreender os prefixos usados nos exemplos a seguir, consulte [Atributos compatíveis com chamadas de DCS API](../api/dcs-intro/dcs-api-reference/dcs-keys.md).

## [!DNL Audience Manager] Lista de IDs {#id-list}

| ID | Nome e descrição | Uso e exemplos | Local da interface do usuário |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID], também conhecido como [!UICONTROL Device ID]. Uma ID numérica de dispositivo de 38 dígitos que [!DNL Audience Manager] O está associado a cada dispositivo com o qual interage. Pense nessa ID sempre que vir uma menção de usuários únicos na variável [!DNL Audience Manager] IU. O Audience Manager salva essa ID como um [!DNL cookie] no `demdex.net` Domínio de terceiros. | Entrada [!DNL DCS] chamadas, `uuid` é precedido pelo `d_` prefixo. <br>Exemplo: `d_uuid = 07955261652886032950143702505894272138` | Você pode filtrar [!DNL traits] por [!UICONTROL Device ID] ao criar [Modelos Semelhantes](../features/algorithmic-models/create-model.md), e [criação de segmentos](../features/segments/segment-builder.md). Também é possível filtrar os resultados por [!UICONTROL Device ID] ao executar [Relatórios gerais para características](../reporting/general-reports.md) e [Relatórios de tendências para características](../reporting/trend-reports.md). |
| [!DNL ImsOrgId] | [!DNL Organization ID]. Esta é a ID que uma empresa recebe ao se cadastrar em uma [!DNL Experience Cloud] conta. | `5DC5123F5245B1D20A490D46@AdobeOrg` | Não visível no [!DNL Audience Manager] interface do usuário. Para saber como encontrar os recursos de sua empresa [!DNL Organization ID], ler [Encontrar a ID da organização](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |
| [!DNL PID] | [!DNL Partner ID]. A variável [!DNL PID] é a ID de uma empresa no [!DNL Audience Manager]. Audience Manager associa um [!DNL imsOrgId] para um [!DNL PID]. | `1352` | Não visível no [!DNL Audience Manager] interface do usuário. |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. A variável [!DNL Experience Cloud] ID ([!DNL ECID], abreviações herdadas [!DNL MID] ou [!DNL MCID]) é derivada matematicamente do seu [!DNL Organization ID] e a variável [!DNL Audience Manager] [!UICONTROL Unique User ID]. Contanto que essas IDs permaneçam constantes, a geração da ID [!DNL ECID] para um usuário específico é simplesmente um problema matemático. Com o mesmo [!DNL Organization ID] e [!DNL Audience Manager] [!DNL UUID] você tem o mesmo [!DNL ECID] sempre. Você pode ler mais sobre [!DNL ECID] no [Cookies e ID de Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) documentação. | `mid = 08382830887934830189014177072406221371` | Não visível no [!DNL Audience Manager] interface do usuário. |
| [!DNL SID] | [!UICONTROL Trait ID]. A variável [!UICONTROL Trait ID] identifica exclusivamente [!DNL traits] no [!DNL Audience Manager] ambiente. | Entrada [!DNL DCS] chamadas, `SID` é precedido pelo `d_` prefixo. <br>Exemplo `d_sid=289983`. | A [!UICONTROL Trait ID] é atribuído a cada [!DNL trait]e visível na interface do usuário, no [Características](../features/traits/trait-details-page.md) página. |
| [!DNL SID] | [!UICONTROL Segment ID]. A variável [!UICONTROL Segment ID] identifica exclusivamente [!DNL segments] no [!DNL Audience Manager] ambiente. | Entrada [!DNL DCS] chamadas, `SID` é precedido pelo `d_` prefixo. <br>Exemplo `d_sid=4798574`. | A [!UICONTROL Segment ID] é atribuído a cada [!DNL segment]e visível na interface do usuário, no [Segmentos](../features/segments/segment-summary-view.md) página. |
| [!DNL csegID] | [!DNL Legacy Segment ID]. Esta ID identifica segmentos exclusivamente na [!DNL Audience Manager] ambiente. | `741232` | A [!UICONTROL Legacy Segment ID] é atribuído a cada segmento e é visível na interface do usuário, no [Segmentos](../features/segments/segment-summary-view.md) página. |
| [!DNL destID] | [!UICONTROL Destination ID]. A variável [!UICONTROL Destination ID] identifica exclusivamente [!DNL destinations] no [!DNL Audience Manager] ambiente. Uma ID é atribuída a cada [!DNL destination] na interface do usuário. | `2523` | A [!UICONTROL Destination ID] é atribuído a cada [!DNL destination]e visível na interface do usuário, no [Destinos](../features/destinations/destinations-home.md) página. |
| [!DNL DPID] | [!UICONTROL Data Source ID] (também referido como [!UICONTROL Data Provider ID]). A variável [!UICONTROL Data Source ID] é um namespace para IDs ou [!DNL traits]. Uma ID é atribuída a cada [!DNL data source] (provedor de dados) na interface do usuário. | Entrada [!DNL DCS] chamadas, `dpid` é precedido pelo `d_` prefixo. <br>Exemplo: `d_dpid=39217`. | A [!UICONTROL Data Provider ID] é atribuído a cada [!DNL data source]e visível na interface do usuário, no [Fontes de dados](../features/datasources-list-and-settings.md) página. |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID], também referido como [!DNL CRM ID] ou [!UICONTROL Cross-Device ID]. Uma ID de terceiros. Essa é a ID pela qual você identifica os usuários finais na sua própria [!DNL CRM] sistema. Você pode sincronizar [!DNL DPUUIDs] com [!DNL Audience Manager] [!DNL UUIDs] e você pode sincronizar [!DNL DPUUIDs] do seu diferente [!UICONTROL Data Sources] ([!DNL DPIDs]) no processo de sincronização de ID. | Entrada [!DNL DCS] chamadas, `dpuuid` é precedido pelo `d_` prefixo. <br> Exemplo `d_dpuuid=2132-3423vn-343fds-3432r`. | Você pode filtrar [!DNL traits] por [!UICONTROL Cross-Device ID] ao criar [Modelos Semelhantes](../features/algorithmic-models/create-model.md), e [criação de segmentos](../features/segments/segment-builder.md). Também é possível filtrar os resultados por [!UICONTROL Cross-Device ID] ao executar [Relatórios gerais para características](../reporting/general-reports.md) e [Relatórios de tendências para características](../reporting/trend-reports.md). |
| [!DNL CRM ID] | Consulte `DPUUID`. | Consulte `DPUUID`. | Consulte `DPUUID`. |
| [!DNL CID], [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. A variável [!DNL CID] e [!DNL CID_IC] substituição de pares de valor-chave [!DNL DPID] e [!DNL DPUUID]. Elas fornecem as mesmas funções que a [!DNL DPID] e [!DNL DPUUID], mas são mais eficientes porque incluem a ID do provedor de dados e a ID do usuário (ou o código de integração) em um único par de valores chave. | Entrada [!DNL DCS] chamadas, essas IDs são precedidas pela variável `d_` prefixo. <br>Exemplo: `d_cid_ic=39217_myIntegrationCode`. | Consulte `DPID` e `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. Uma ID única para cada dispositivo de hardware, a ser utilizada para fins de publicidade. Normalmente fornecido pelo fabricante do dispositivo ou do sistema operacional do dispositivo. | Consulte [IDs de dispositivo global](#global-device-ids). |  |

## [!DNL Global Device IDs] {#global-device-ids}

As IDs de dispositivo globais são IDs de anúncio de dispositivo, exclusivas de cada dispositivo, fornecidas pelo fabricante do dispositivo ou pelo sistema operacional. A tabela abaixo explica quais são essas IDs e quais são os respectivos formatos. Para obter mais informações sobre IDs de dispositivos globais e como usá-las no [!DNL Audience Manager], ler [Fontes de dados globais](/help/using/features/global-data-sources.md).

| ID | [!DNL Global Data Source ID] | Nome e descrição | Exemplo |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] As IDs são identificadores de dispositivos móveis, fornecidos pelo fabricante do dispositivo. Essas IDs representam dispositivos que executam o [!DNL iOS] sistema operacional. | O formato consiste estritamente em 32 dígitos hexadecimais em maiúsculas, exibidos em cinco grupos e separados por hifens, na forma 8-4-4-4-12, para um total de 36 caracteres.<br> Exemplo: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s são identificadores de dispositivos móveis fornecidos pelos fabricantes de dispositivos Android. Essas IDs representam dispositivos que executam o [!DNL Android] sistema operacional. | O formato consiste estritamente em 32 dígitos hexadecimais minúsculos, exibidos em cinco grupos e separados por hifens, na forma 8-4-4-4-12, para um total de 36 caracteres. <br>Exemplo: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] representa [!DNL Roku] dispositivos de transmissão contínua. | O formato consiste estritamente em 32 dígitos hexadecimais minúsculos, exibidos em cinco grupos e separados por hifens, na forma 8-4-4-4-12, para um total de 36 caracteres. <br>Exemplo: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s são identificadores de dispositivos gerados por [!DNL Windows 10] por dispositivo e por usuário. | [!DNL MAID]s são formatados como cadeias de caracteres alfanuméricas. |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] são identificadores de dispositivos fornecidos por [!DNL Samsung] TVs inteligentes. | [!DNL Samsung] [!DNL TIFA] As IDs são formatadas como cadeias de caracteres alfanuméricas. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Identificadores de dispositivo que representam dispositivos que executam o [!DNL Fire OS] sistema operacional. | O formato consiste estritamente em 32 dígitos hexadecimais minúsculos, exibidos em cinco grupos e separados por hifens, na forma 8-4-4-4-12, para um total de 36 caracteres. <br>Exemplo: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |
| [!DNL LGUDID] | 1171485 | Identificadores de dispositivo que representam dispositivos que executam o [!DNL LG webOS] sistema operacional. | O formato consiste estritamente em 32 dígitos hexadecimais minúsculos, exibidos em cinco grupos e separados por hifens, na forma 8-4-4-4-12, para um total de 36 caracteres. <br>Exemplo: `095f142a-ace8-ac5d-b86a-92c8be18b197` |
| [!DNL Vizio IFA] | 1171489 | Identificadores de dispositivo que representam dispositivos que executam o sistema operacional Vizio Smart TV. | [!DNL Vizio IFA] As IDs são formatadas como cadeias de caracteres alfanuméricas. <br>Exemplo: `7XCBNROQJQPYW`. |
