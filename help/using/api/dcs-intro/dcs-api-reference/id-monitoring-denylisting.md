---
description: O DCS monitora as IDs recebidas e adiciona aquelas que estão sendo enviadas a uma taxa excepcionalmente alta durante um curto período de tempo para uma lista de negação.
keywords: id;monitoring;dcs
seo-description: O DCS monitora as IDs recebidas e adiciona aquelas que estão sendo enviadas a uma taxa excepcionalmente alta durante um curto período de tempo para uma lista de negação.
seo-title: Monitoramento de ID e lista de negação
solution: Audience Manager
title: Monitoramento de ID e lista de negação
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# Monitoramento de ID e lista de negação

O [!DNL DCS] monitora as IDs recebidas e adiciona aquelas que estão sendo enviadas a uma taxa excepcionalmente alta em um curto período de tempo para uma lista de negação.

## Visão geral

Para proteger a infraestrutura do Audience Manager contra atividades mal-intencionadas, o [!DNL DCS] usa um algoritmo avançado para monitorar as IDs recebidas. Podem ser [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) ou [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Consulte [Índice de IDs no Audience Manager](../../../reference/ids-in-aam.md) para obter explicações detalhadas das IDs suportadas pelo Audience Manager.

O [!DNL DCS] monitora a frequência com que recebe essas IDs para detectar possíveis atividades maliciosas. Quando o [!DNL DCS] detecta uma quantidade invulgarmente grande de [!DNL DCS] solicitações para determinada ID em um curto período de tempo, essa ID é adicionada a uma lista de negação.

## Códigos de erro

É possível identificar IDs adicionadas a uma lista de negação pelos códigos de erro recebidos do [!DNL DCS]. Os códigos de erro que você pode receber são:

* 303: ID do cliente bloqueado;
* 306: ID de dispositivo declarada bloqueada;
* 307: Operação de perfil bloqueada para ID.

Consulte Códigos de erro, mensagens e exemplos [do](dcs-error-codes.md) DCS para obter detalhes sobre os códigos de erro que você pode receber.

## Remoção de IDs de listas de negação

As IDs que foram adicionadas às listas de negação não devem ser usadas em solicitações futuras, pois resultarão em relatórios de dados incorreto. O [!DNL DCS] não suporta a remoção de IDs de listas de negação.

## Impacto na sincronização de ID

[!DNL DCS] as chamadas podem incluir um ou vários tipos de IDs. As chamadas que contêm uma única ID serão completamente desconsideradas se essa ID for adicionada a uma lista de negação e nenhuma sincronização de ID ocorrerá nessa situação.

Quando uma chamada de ID múltipla também inclui uma ID deslistada, a ID [!DNL DCS] ignora a ID negada e usa somente as IDs restantes permitidas para sincronização.

## Causas e correções para a lista de negação de ID

A causa mais frequente de IDs adicionadas às listas de negação é a integração incorreta entre a infraestrutura do cliente e o Audience Manager. Ao identificar uma ID deslistada, verifique se as integrações de Audience Manager estão totalmente revisadas. Consulte Guias **de** implementação e integração para obter explicações detalhadas sobre como configurar o Audience Manager para trabalhar com outras soluções de Experience Cloud ou sistemas externos.

Outra causa frequente de IDs adicionadas às listas de negação são bots de indexação (rastreadores da Web), que geralmente causam aumento no tráfego, resultando no envio das mesmas IDs para as [!DNL DCS] várias vezes. Se você identificar bots de indexação como o motivo para IDs serem adicionadas às listas de negação, deverá restringir o acesso do robô ao seu site.

Se você tiver dificuldades para identificar problemas de integração, não hesite em entrar em contato com o Suporte ao cliente. Antes de abrir uma solicitação de suporte, certifique-se de manter o `.har` arquivo `HTTP` do navegador pronto. Este arquivo ajuda a equipe de suporte a identificar por que a ID foi adicionada a uma lista de negação.