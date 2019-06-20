---
description: O DCS monitora as IDs que recebe e lista negra aquelas que estão sendo enviadas em uma taxa excepcionalmente alta durante um curto período.
keywords: id; monitoramento; lista negra; dcs
seo-description: O DCS monitora as IDs que recebe e lista negra aquelas que estão sendo enviadas em uma taxa excepcionalmente alta durante um curto período.
seo-title: Monitoramento de ID e lista negra
solution: Audience Manager
title: Monitoramento de ID e lista negra
uuid: 498 e 0316-cf 1 b -43 e 9-88 ba -338 ee 0 daf 225
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# Monitoramento de ID e lista negra

[!UICONTROL DCS] Os monitores são recebidos e lista negra os que estão sendo enviados em uma taxa excepcionalmente alta durante um curto período de tempo.

## Visão geral

To protect the Audience Manager infrastructure against malicious activity, the [!UICONTROL DCS] uses an advanced algorithm to monitor the IDs it receives. These can be [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s), or [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). See [Index of IDs in Audience Manager](../../../reference/ids-in-aam.md) for detailed explanations of the IDs supported by Audience Manager.

The [!UICONTROL DCS] monitors the frequency at which it receives these IDs to detect potential malicious activity. When the [!UICONTROL DCS] detects an unusually large amount of [!UICONTROL DCS] requests for any given ID in a short amount of time, that ID is blacklisted.

## Códigos de erro

You can identify blacklisted IDs by the error codes received from the [!UICONTROL DCS]. Os códigos de erro que você receber são:

* : 03: ID do cliente bloqueada;
* : 06: ID de dispositivo declarada bloqueada;
* : 07: Operação de perfil bloqueada para ID.

See [DCS Error Codes, Messages, and Examples](dcs-error-codes.md) for details on the error codes that you may receive.

## Lista negra

IDs proibidas não devem ser usadas em solicitações futuras, uma vez que elas geram relatórios de dados incorretos. The [!UICONTROL DCS] does not support un-blacklisting of IDs.

## Impacto na sincronização da ID

[!UICONTROL DCS] podem incluir um ou vários tipos de IDs. As chamadas que contêm uma única ID são completamente desconsideradas se a ID estiver na lista negra e não houver uma sincronização de ID nessa situação.

When a multiple ID call also includes a blacklisted ID, the [!UICONTROL DCS] disregards the blacklisted ID and only uses the remaining, non-blacklisted IDs for synchronization.

## Causas e correções para a lista negra da ID

A causa mais frequente das IDs na lista negra é a integração incorreta entre a infraestrutura do cliente e o Audience Manager. Ao identificar uma ID da lista negra, verifique completamente as integrações do Audience Manager. See **Implementation and Integration Guides** for detailed explanations of how you should configure Audience Manager to work with other Experience Cloud solutions or external systems.

Another frequent cause of blacklisted IDs are indexing bots (web crawlers), which generally cause increases in traffic, leading to the same IDs being sent to the [!UICONTROL DCS] multiple times. Se você identificar bots de indexação como o motivo para a lista negra da ID, você deve restringir o acesso do robô ao seu site.

Se você tiver um tempo difícil identificar problemas de integração, não hesite em entrar em contato com o Suporte ao cliente. Prior to opening a support request, make sure to keep the `.har` `HTTP` archive of your browser ready. Este arquivamento ajuda a equipe de suporte a identificar por que a lista de negação de ID ocorreu.