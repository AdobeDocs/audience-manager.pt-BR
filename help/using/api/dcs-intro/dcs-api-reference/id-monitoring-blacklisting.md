---
description: O DCS monitora as IDs que recebe e faz a lista negra das que estão sendo enviadas a uma taxa excepcionalmente alta em um curto período de tempo.
keywords: id;monitoramento;lista negra;dcs
seo-description: O DCS monitora as IDs que recebe e faz a lista negra das que estão sendo enviadas a uma taxa excepcionalmente alta em um curto período de tempo.
seo-title: Monitoramento de ID e lista negra
solution: Audience Manager
title: Monitoramento de ID e lista negra
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# Monitoramento de ID e lista negra

O [!UICONTROL DCS] monitora as IDs recebidas e faz a lista negra das que estão sendo enviadas a uma taxa excepcionalmente alta em um curto período de tempo.

## Visão geral

Para proteger a infraestrutura do Audience Manager contra atividades mal-intencionadas, o [!UICONTROL DCS] usa um algoritmo avançado para monitorar as IDs recebidas. Podem ser [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) ou [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Consulte [Índice de IDs no Audience Manager](../../../reference/ids-in-aam.md) para obter explicações detalhadas das IDs suportadas pelo Audience Manager.

O [!UICONTROL DCS] monitora a frequência com que recebe essas IDs para detectar possíveis atividades mal-intencionadas. Quando o [!UICONTROL DCS] detecta uma quantidade invulgarmente grande de [!UICONTROL DCS] solicitações para determinada ID em um curto período de tempo, essa ID é bloqueada.

## Códigos de erro

É possível identificar as IDs proibidas pelos códigos de erro recebidos do [!UICONTROL DCS]. Os códigos de erro que você pode receber são:

* 303: ID do cliente bloqueado;
* 306: ID de dispositivo declarada bloqueada;
* 307: Operação de perfil bloqueada para ID.

Consulte Códigos de erro, mensagens e exemplos [do](dcs-error-codes.md) DCS para obter detalhes sobre os códigos de erro que você pode receber.

## Lista não negra

As IDs da lista negra não devem ser usadas em solicitações futuras, já que levarão a relatórios de dados incorretos. O [!UICONTROL DCS] não oferece suporte para a remoção da lista negra de IDs.

## Impacto na sincronização de ID

[!UICONTROL DCS] as chamadas podem incluir um ou vários tipos de IDs. As chamadas que contêm uma única ID serão completamente desconsideradas se essa ID estiver na lista negra e nenhuma sincronização de ID ocorrerá nessa situação.

Quando uma chamada de ID múltipla também inclui uma ID da lista negra, a ID [!UICONTROL DCS] ignora a lista negra e usa somente as IDs restantes não proibidas para sincronização.

## Causas e correções para a lista negra de ID

A causa mais frequente das IDs que estão sendo proibidas é a integração incorreta entre a infraestrutura do cliente e o Audience Manager. Ao identificar uma ID da lista negra, certifique-se de revisar detalhadamente suas integrações do Audience Manager. Consulte Guias **de** implementação e integração para obter explicações detalhadas sobre como você deve configurar o Audience Manager para trabalhar com outras soluções da Experience Cloud ou sistemas externos.

Outra causa frequente de IDs proibidas são os bots de indexação (rastreadores da Web), que geralmente causam aumento no tráfego, resultando no envio das mesmas IDs para [!UICONTROL DCS] várias vezes. Se você identificar os bots de indexação como o motivo da lista negra de ID, deverá restringir o acesso do bot ao seu site.

Se você tiver dificuldades para identificar problemas de integração, não hesite em entrar em contato com o Suporte ao cliente. Antes de abrir uma solicitação de suporte, certifique-se de manter o `.har` arquivo `HTTP` do navegador pronto. Esse arquivo ajuda a equipe de suporte a identificar por que a lista negra de ID ocorreu.