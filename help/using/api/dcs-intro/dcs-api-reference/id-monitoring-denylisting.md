---
description: O DCS monitora as IDs que recebe e adiciona as que estão sendo enviadas em uma taxa excepcionalmente alta durante um curto período de tempo a uma lista de bloqueios.
keywords: id;monitoramento;dcs
seo-description: The DCS monitors the IDs it receives and adds those that are being sent at an unusually high rate over a short period of time to a deny list.
seo-title: ID Monitoring and Denylisting
solution: Audience Manager
title: Monitoramento e Incluir na lista de bloqueios de ID
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
exl-id: 8fd31b00-a822-4fd5-b6f5-7f20546da1d9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 0%

---

# Monitoramento e Incluir na lista de bloqueios de ID

O [!DNL DCS] monitora as IDs que recebe e adiciona as que estão sendo enviadas em uma taxa excepcionalmente alta durante um curto período de tempo a uma lista de bloqueios.

## Visão geral

Para proteger a infraestrutura do Audience Manager contra atividades mal-intencionadas, o [!DNL DCS] usa um algoritmo avançado para monitorar as IDs que recebe. Eles podem ser [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) ou [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Consulte [Índice de IDs no Audience Manager](../../../reference/ids-in-aam.md) para obter explicações detalhadas sobre as IDs com suporte no Audience Manager.

O [!DNL DCS] monitora a frequência com que recebe essas IDs para detectar possíveis atividades mal-intencionadas. Quando o [!DNL DCS] detecta uma quantidade excepcionalmente grande de [!DNL DCS] solicitações para qualquer ID em um curto período, essa ID é adicionada a uma lista de bloqueios.

## Códigos de erro

Você pode identificar IDs adicionadas a uma lista de bloqueios pelos códigos de erro recebidos do [!DNL DCS]. Os códigos de erro que você pode receber são:

* 303: ID do cliente bloqueada;
* 306: ID de dispositivo declarada bloqueada;
* 307: Operação de perfil bloqueada para ID.

Consulte [Códigos de erro, mensagens e exemplos de DCS](dcs-error-codes.md) para obter detalhes sobre os códigos de erro que você pode receber.

## Remoção de IDs do lista de bloqueios

As IDs que foram adicionadas às listas de bloqueios não devem ser usadas em solicitações futuras, pois resultarão em relatórios de dados incorretos. O [!DNL DCS] não oferece suporte à remoção de IDs do lista de bloqueios.

## Impacto na sincronização de ID

[!DNL DCS] chamadas podem incluir um ou vários tipos de IDs. Chamadas que contêm uma única ID são completamente ignoradas se essa ID for adicionada a uma lista de bloqueios e nenhuma sincronização de ID ocorrer nessa situação.

Incluir na lista de bloqueios Quando uma chamada com várias IDs também inclui uma ID reconhecida, o [!DNL DCS] ignora a ID negada e usa apenas as IDs restantes permitidas para sincronização.

## Causas e correções para o Incluir na lista de bloqueios de ID

A causa mais frequente de IDs adicionadas ao lista de bloqueios é a integração incorreta entre a infraestrutura do cliente e a Audience Manager. Incluir na lista de bloqueios Ao identificar uma ID do Audience Manager, revise detalhadamente suas integrações. Consulte **Guias de Implementação e Integração** para obter explicações detalhadas sobre como configurar o Audience Manager para funcionar com outras soluções da Experience Cloud ou sistemas externos.

Outra causa frequente da adição de IDs ao lista de bloqueios são bots de indexação (rastreadores da web), que geralmente causam aumentos no tráfego, fazendo com que as mesmas IDs sejam enviadas para o [!DNL DCS] várias vezes. Se você identificar bots de indexação como o motivo para a adição de IDs ao lista de bloqueios, deverá restringir o acesso de bot ao seu site.

Se tiver dificuldades para identificar problemas de integração, entre em contato com o Suporte ao cliente. Antes de abrir uma solicitação de suporte, mantenha o arquivo morto do `.har` `HTTP` do seu navegador pronto. Esse arquivo ajuda a equipe de suporte a identificar por que a ID foi adicionada a uma lista de bloqueios.
