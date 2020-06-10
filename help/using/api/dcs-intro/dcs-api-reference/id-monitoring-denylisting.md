---
description: O DCS monitora as IDs que recebe e adiciona aquelas que estão sendo enviadas a uma taxa excepcionalmente alta durante um curto período de tempo para uma lista de negação.
keywords: id;monitoring;dcs
seo-description: O DCS monitora as IDs que recebe e adiciona aquelas que estão sendo enviadas a uma taxa excepcionalmente alta durante um curto período de tempo para uma lista de negação.
seo-title: Monitoramento de ID e lista de negação
solution: Audience Manager
title: Monitoramento de ID e lista de negação
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 92751df14777335744db69bfb0c9b7b2f9088785
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# Monitoramento de ID e lista de negação

O [!UICONTROL DCS] monitora as IDs recebidas e adiciona aquelas que estão sendo enviadas a uma taxa excepcionalmente alta durante um curto período de tempo para uma lista de negação.

## Visão geral

Para proteger a infraestrutura do Gerenciador de Audiências contra atividades mal-intencionadas, o [!UICONTROL DCS] usa um algoritmo avançado para monitorar as IDs recebidas. Podem ser [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) ou [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Consulte [Índice de IDs no Gerenciador](../../../reference/ids-in-aam.md) de Audiências para obter explicações detalhadas das IDs suportadas pelo Gerenciador de Audiências.

O [!UICONTROL DCS] monitora a frequência com que recebe essas IDs para detectar possíveis atividades maliciosas. Quando o [!UICONTROL DCS] detecta uma quantidade invulgarmente grande de [!UICONTROL DCS] solicitações para uma determinada ID em um curto período de tempo, essa ID é adicionada a uma lista de negação.

## Códigos de erro

É possível identificar IDs adicionadas a uma lista de negação pelos códigos de erro recebidos do [!UICONTROL DCS]. Os códigos de erro que você pode receber são:

* 303: ID do cliente bloqueado;
* 306: ID de dispositivo declarada bloqueada;
* 307: Operação de perfil bloqueada para ID.

Consulte Códigos de erro, mensagens e exemplos [do](dcs-error-codes.md) DCS para obter detalhes sobre os códigos de erro que você pode receber.

## Remoção de IDs de listas de negação

As IDs que foram adicionadas para negar listas não devem ser usadas em solicitações futuras, pois resultarão em relatórios de dados incorreto. O [!UICONTROL DCS] não suporta a remoção de IDs de listas de negação.

## Impacto na sincronização de ID

[!UICONTROL DCS] as chamadas podem incluir um ou vários tipos de IDs. As chamadas que contêm uma única ID serão completamente desconsideradas se essa ID for adicionada a uma lista de negação, e nenhuma sincronização de ID ocorrerá nessa situação.

Quando uma chamada de ID múltipla também inclui uma ID deslistada, a ID [!UICONTROL DCS] ignora a ID negada e usa somente as IDs restantes permitidas para sincronização.

## Causas e correções para a lista de negação de ID

A causa mais frequente de IDs adicionadas para negar listas é a integração incorreta entre a infraestrutura do cliente e o Gerenciador de Audiências. Ao identificar uma ID deslistada, verifique se as integrações do Gerenciador de Audiências foram analisadas detalhadamente. Consulte Guias **de** implementação e integração para obter explicações detalhadas sobre como você deve configurar o Audiência Manager para trabalhar com outras soluções da Experience Cloud ou sistemas externos.

Outra causa frequente de IDs sendo adicionadas para negar listas são bots de indexação (rastreadores da Web), que geralmente causam aumento no tráfego, resultando no envio das mesmas IDs para [!UICONTROL DCS] várias vezes. Se você identificar bots de indexação como o motivo para IDs serem adicionadas para negar listas, deverá restringir o acesso do robô ao seu site.

Se você tiver dificuldades para identificar problemas de integração, não hesite em entrar em contato com o Suporte ao cliente. Antes de abrir uma solicitação de suporte, certifique-se de manter o `.har` arquivo `HTTP` do navegador pronto. Esse arquivo ajuda a equipe de suporte a identificar por que a ID foi adicionada a uma lista de negação.