---
description: Use Fontes de dados globais para importar IDs de publicidade de dispositivos.
seo-description: Use Fontes de dados globais para importar IDs de publicidade de dispositivos.
seo-title: Fontes de dados globais
solution: Audience Manager
title: Fontes de dados globais
feature: Data Sources
translation-type: tm+mt
source-git-commit: cb84f95d52c2e851cb0c016cb25f408f2d79d01b
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 6%

---


# Fontes de dados globais {#global-data-sources}

## Visão geral

As fontes globais de dados são acessíveis a todos os clientes do Audience Manager e contêm IDs de publicidade de dispositivos geradas por fabricantes de dispositivos, como [!DNL Apple], [!DNL Samsung], [!DNL Microsoft], [!DNL Roku] e [!DNL Android] fabricantes de dispositivos. Essas IDs são disponibilizadas pelos fabricantes para fins de publicidade. Os clientes do Audience Manager podem usar fontes de dados globais para sincronizar IDs de dispositivos e importar ou exportar dados marcados desses mapeamentos.

A tabela a seguir descreve as fontes de dados globais suportadas pelo Audience Manager.

| ID da fonte de dados | Descrição |
|---|---|
| 2014 | **[!DNL Google Advertising ID]** -  **[!DNL GAID]** As IDs representam dispositivos que executam o sistema  [!DNL Android] operacional. |
| 2015 | **[!DNL Apple ID For Advertising]** -  **[!DNL IDFA]** As IDs representam dispositivos que executam o sistema  [!DNL iOS] operacional. |
| 121963 | **[!DNL Roku ID for Advertising]** -  **[!DNL RIDA]** As IDs representam dispositivos  [!DNL Roku] de transmissão. |
| 389146 | **[!DNL Microsoft Advertising ID]** -  **[!DNL MAID]** As IDs representam os dispositivos que executam o sistema  [!DNL Windows 10] operacional. |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** -  **[!DNL TIFA]** As IDs representam TVs  [!DNL Samsung] inteligentes. |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]** representam dispositivos em execução  [!DNL Amazon Fire OS] |

## Importação de dados de fontes de dados globais

É possível importar IDs de dispositivo de fontes de dados globais por meio de [transferência de dados em tempo real](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md) e [transferência de dados em lote](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md).

>[!IMPORTANT]
>
>Ao enviar dados para o Audience Manager usando uma ID de dispositivo global, certifique-se de usar a fonte de dados correspondente para a ID do dispositivo em questão. Exemplo: para importar dados para [!DNL Apple IDFA], use a ID da fonte de dados 20915.

## Limitações

Em dispositivos que executam [!DNL iOS] e [!DNL Android] sistemas operacionais, somente aplicativos nativos podem recuperar e usar IDs de publicidade de dispositivos ([!UICONTROL DAID]s). As aplicações web em execução em navegadores móveis não têm acesso às IDs de publicidade do dispositivo.

## Validação da ID do dispositivo global

O Audience Manager valida as IDs de publicidade do dispositivo ([!UICONTROL DAID]) importadas pelos clientes, com base em seu formato, para garantir que elas correspondam ao formato padrão descrito pelos fabricantes do dispositivo. Consulte [Índice de IDs em Audience Manager](../reference/ids-in-aam.md) para obter um mapeamento detalhado das IDs de publicidade do dispositivo para fontes de dados globais e o formato adequado para cada ID. Verifique se você está importando IDs de dispositivo no formato correto, com base no tipo de dispositivo. O Audience Manager rejeita as IDs de dispositivo que não atendem ao formato correto e retorna uma mensagem de erro para indicar que a ID foi rejeitada.

* As mensagens de erro para transferências de dados em lote são descritas aqui: [Termos e Definições do Relatório de Estado de Integração](../reporting/onboarding-status-report.md#report-terms-conditions).
* As mensagens de erro para transferências de dados em tempo real são descritas aqui: [Códigos de erro, mensagens e exemplos](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md) do DCS.

## Política de expiração da ID do dispositivo

O Audience Manager descarta automaticamente as IDs de publicidade do dispositivo após 120 dias de inatividade, de modo semelhante a [AAM UUID](../faq/faq-privacy.md)s.

## Solicitação de novas fontes de dados globais

Para solicitar a adição de novas fontes de dados globais ao Audience Manager, entre em contato com a Adobe Consultoria ou com o Atendimento ao cliente do Adobe e forneça informações detalhadas sobre as fontes de dados necessárias:

* O nome da plataforma solicitada (por exemplo, [!UICONTROL Apple IDFA]);
* O nome da empresa/organização que gerencia a plataforma (por exemplo, [!UICONTROL Apple Inc.]);
* Links para as especificações técnicas da namespace de ID de anúncio do dispositivo (por exemplo, [Documentação do AdSupport](https://developer.apple.com/documentation/adsupport)).