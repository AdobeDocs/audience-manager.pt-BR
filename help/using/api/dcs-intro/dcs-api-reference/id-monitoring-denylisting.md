---
description: O DCS monitora as IDs recebidas e adiciona aquelas que estão sendo enviadas em uma taxa excepcionalmente alta durante um curto período para uma lista de bloqueios.
keywords: id; monitoramento; dcs
seo-description: O DCS monitora as IDs recebidas e adiciona aquelas que estão sendo enviadas em uma taxa excepcionalmente alta durante um curto período para uma lista de bloqueios.
seo-title: Monitoramento de ID e Incluir na lista de bloqueios
solution: Audience Manager
title: Monitoramento de ID e Incluir na lista de bloqueios
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
exl-id: 8fd31b00-a822-4fd5-b6f5-7f20546da1d9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 0%

---

# Monitoramento de ID e Incluir na lista de bloqueios

O [!DNL DCS] monitora as IDs recebidas e adiciona aquelas que estão sendo enviadas em uma taxa excepcionalmente alta durante um curto período para uma lista de bloqueios.

## Visão geral

Para proteger a infraestrutura do Audience Manager contra atividades mal-intencionadas, o [!DNL DCS] usa um algoritmo avançado para monitorar as IDs que recebe. Eles podem ser [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) ou [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Consulte [Índice de IDs no Audience Manager](../../../reference/ids-in-aam.md) para obter explicações detalhadas sobre as IDs suportadas pelo Audience Manager.

O [!DNL DCS] monitora a frequência com que recebe essas IDs para detectar possíveis atividades mal-intencionadas. Quando o [!DNL DCS] detecta uma quantidade invulgarmente grande de solicitações [!DNL DCS] para qualquer ID em um curto período de tempo, essa ID é adicionada a uma lista de bloqueios.

## Códigos de erro

Você pode identificar IDs adicionadas a uma lista de bloqueios pelos códigos de erro recebidos do [!DNL DCS]. Os códigos de erro que você pode receber são:

* 303: ID do cliente bloqueado;
* 306: ID de dispositivo declarada bloqueada;
* 307: Operação de perfil bloqueada para ID.

Consulte [Códigos de erro DCS, mensagens e exemplos](dcs-error-codes.md) para obter detalhes sobre os códigos de erro que você pode receber.

## Remover IDs do lista de bloqueios

As IDs que foram adicionadas ao lista de bloqueios não devem ser usadas em solicitações futuras, pois resultarão em relatórios de dados incorretos. O [!DNL DCS] não suporta a remoção de IDs do lista de bloqueios.

## Impacto na sincronização de ID

[!DNL DCS] As chamadas podem incluir um ou vários tipos de IDs. As chamadas contendo uma única ID são completamente desconsideradas, se essa ID for adicionada a uma lista de bloqueios, e nenhuma sincronização de ID ocorre nessa situação.

Quando uma chamada de várias IDs também inclui uma ID incluir na lista de bloqueios, o [!DNL DCS] ignora a ID negada e usa apenas as IDs restantes e permitidas para sincronização.

## Causas e correções para o Incluir na lista de bloqueios de ID

A causa mais frequente de IDs adicionadas ao lista de bloqueios é a integração incorreta entre a infraestrutura do cliente e o Audience Manager. Ao identificar uma ID incluir na lista de bloqueios, verifique se as integrações do Audience Manager estão totalmente revisadas. Consulte **Guias de implementação e integração** para obter explicações detalhadas sobre como você deve configurar o Audience Manager para trabalhar com outras soluções Experience Cloud ou sistemas externos.

Outra causa frequente de IDs adicionadas às listas de bloqueios são bots de indexação (rastreadores da Web), que geralmente causam aumento no tráfego, resultando no envio das mesmas IDs para o [!DNL DCS] várias vezes. Se você identificar bots de indexação como o motivo para as IDs serem adicionadas ao lista de bloqueios, deverá restringir o acesso de bot ao seu site.

Se você tiver dificuldade em identificar problemas de integração, não hesite em entrar em contato com o Suporte ao cliente. Antes de abrir uma solicitação de suporte, mantenha o arquivo `.har` `HTTP` do seu navegador pronto. Esse arquivo ajuda a equipe de suporte a identificar por que a ID foi adicionada a uma lista de bloqueios.
