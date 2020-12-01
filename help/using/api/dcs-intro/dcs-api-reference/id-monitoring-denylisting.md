---
description: O DCS monitora as IDs que recebe e adiciona aquelas que estão sendo enviadas a uma taxa excepcionalmente alta durante um curto período de tempo para uma lista de bloqueios.
keywords: id;monitoring;dcs
seo-description: O DCS monitora as IDs que recebe e adiciona aquelas que estão sendo enviadas a uma taxa excepcionalmente alta durante um curto período de tempo para uma lista de bloqueios.
seo-title: Monitoramento e Incluir na lista de bloqueios de ID
solution: Audience Manager
title: Monitoramento e Incluir na lista de bloqueios de ID
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# Monitoramento e Incluir na lista de bloqueios de ID

O [!DNL DCS] monitora as IDs recebidas e adiciona as que estão sendo enviadas a uma taxa excepcionalmente alta em um curto período de tempo para uma lista de bloqueios.

## Visão geral

Para proteger a infraestrutura do Audience Manager contra atividades mal-intencionadas, o [!DNL DCS] usa um algoritmo avançado para monitorar as IDs recebidas. Podem ser [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) ou [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Consulte [Índice de IDs em Audience Manager](../../../reference/ids-in-aam.md) para obter explicações detalhadas das IDs suportadas pelo Audience Manager.

O [!DNL DCS] monitora a frequência com que recebe essas IDs para detectar possíveis atividades mal-intencionadas. Quando [!DNL DCS] detecta uma quantidade invulgarmente grande de solicitações [!DNL DCS] para uma determinada ID em um curto período de tempo, essa ID é adicionada a uma lista de bloqueios.

## Códigos de erro

Você pode identificar IDs adicionadas a uma lista de bloqueios pelos códigos de erro recebidos de [!DNL DCS]. Os códigos de erro que você pode receber são:

* 303: ID do cliente bloqueado;
* 306: ID de dispositivo declarada bloqueada;
* 307: Operação de perfil bloqueada para ID.

Consulte [Códigos de erro, mensagens e exemplos](dcs-error-codes.md) do DCS para obter detalhes sobre os códigos de erro que você pode receber.

## Remoção de IDs do lista de bloqueios

As IDs que foram adicionadas ao lista de bloqueios não devem ser usadas em solicitações futuras, pois resultarão em relatórios de dados incorreto. O [!DNL DCS] não suporta a remoção de IDs do lista de bloqueios.

## Impacto na sincronização de ID

[!DNL DCS] as chamadas podem incluir um ou vários tipos de IDs. As chamadas que contêm uma única ID serão completamente desconsideradas se essa ID for adicionada a uma lista de bloqueios, e nenhuma sincronização de ID ocorrerá nessa situação.

Quando uma chamada de ID múltipla também inclui uma ID incluir na lista de bloqueios, [!DNL DCS] ignora a ID negada e usa apenas as IDs restantes permitidas para sincronização.

## Causas e correções para Incluir na lista de bloqueios de ID

A causa mais frequente de IDs adicionadas ao lista de bloqueios é a integração incorreta entre a infraestrutura do cliente e o Audience Manager. Ao identificar uma ID incluir na lista de bloqueios, verifique se as integrações de Audience Manager. Consulte **Guias de implementação e integração** para obter explicações detalhadas sobre como você deve configurar o Audience Manager para trabalhar com outras soluções de Experience Cloud ou sistemas externos.

Outra causa frequente de IDs adicionadas ao lista de bloqueios são bots de indexação (rastreadores da Web), que geralmente causam aumento no tráfego, resultando no envio das mesmas IDs para [!DNL DCS] várias vezes. Se você identificar bots de indexação como o motivo para IDs serem adicionadas ao lista de bloqueios, deverá restringir o acesso do bot ao seu site.

Se você tiver dificuldades para identificar problemas de integração, não hesite em entrar em contato com o Suporte ao cliente. Antes de abrir uma solicitação de suporte, certifique-se de manter o arquivo `.har` `HTTP` do seu navegador pronto. Esse arquivo ajuda a equipe de suporte a identificar por que a ID foi adicionada a uma lista de bloqueios.