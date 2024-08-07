---
description: Use as Fontes de dados globais para importar IDs de anúncios de dispositivos.
seo-description: Use Global Data Sources to import device advertising IDs.
seo-title: Global Data Sources
solution: Audience Manager
title: Fontes de dados globais
feature: Data Sources
exl-id: ef137f89-1e1a-4cc0-8864-8a84162581c1
source-git-commit: 77daa5bd6545914f65e3e0f19b12c750535244e8
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 4%

---

# Fontes de dados globais {#global-data-sources}

## Visão geral

As fontes de dados globais são acessíveis a todos os clientes do Audience Manager e contêm IDs de anúncios de dispositivos geradas por fabricantes de dispositivos como [!DNL Apple], [!DNL Samsung], [!DNL Microsoft], [!DNL Roku] e [!DNL Android]. Essas IDs são disponibilizadas pelos fabricantes para fins de publicidade. Os clientes do Audience Manager podem usar fontes de dados globais para sincronizar IDs de dispositivos e importar ou exportar dados extraídos desses mapeamentos.

A tabela a seguir descreve as fontes de dados globais suportadas pelo Audience Manager.

| ID do Source de dados | Descrição |
|---|---|
| 20914 | **[!DNL Google Advertising ID]** - **[!DNL GAID]** IDs representam dispositivos que executam o sistema operacional [!DNL Android]. |
| 20915 | **[!DNL Apple ID For Advertising]** - **[!DNL IDFA]** IDs representam dispositivos que executam o sistema operacional [!DNL iOS]. |
| 121963 | **[!DNL Roku ID for Advertising]** - **[!DNL RIDA]** IDs representam [!DNL Roku] dispositivos de streaming. |
| 389146 | **[!DNL Microsoft Advertising ID]** - **[!DNL MAID]** IDs representam dispositivos executando o sistema operacional [!DNL Windows 10]. |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** - **[!DNL TIFA]** IDs representam [!DNL Samsung] TVs inteligentes. |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]** representam dispositivos executando [!DNL Amazon Fire OS] |
| 1171485 | **[!DNL LG webOS TV ID]** - **[!DNL LGUDID]** representam dispositivos que executam o sistema operacional [!DNL LG webOS]. |
| 1171489 | **[!DNL Vizio ID for Advertising]** - **[!DNL IFA]** representam dispositivos que executam os sistemas operacionais Vizio smart TV. |

## Importação de Dados de Origens de Dados Globais

Você pode importar IDs de dispositivo de fontes de dados globais por meio de [transferência de dados em tempo real](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md) e [transferência de dados em lote](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md).

>[!IMPORTANT]
>
>Ao enviar dados para o Audience Manager usando uma ID de dispositivo global, certifique-se de usar a fonte de dados correspondente para a ID de dispositivo em questão. Exemplo: para importar dados de [!DNL Apple IDFA], use a ID de fonte de dados 20915.

## Limitações

Em dispositivos que executam os sistemas operacionais [!DNL iOS] e [!DNL Android], somente aplicativos nativos podem recuperar e usar IDs de anúncio de dispositivo ([!UICONTROL DAID]s). Os aplicativos web executados em navegadores móveis não têm acesso às IDs de publicidade do dispositivo.

## Validação global da ID do dispositivo

O Audience Manager valida as IDs de publicidade de dispositivos ([!UICONTROL DAID]) importadas por clientes, com base em seus formatos, para garantir que correspondam ao formato padrão determinado pelos fabricantes. Consulte o [Índice de IDs no Audience Manager](../reference/ids-in-aam.md) para obter um mapeamento detalhado de IDs de anúncios de dispositivos para fontes de dados globais e o formato adequado para cada ID. Verifique se você está importando IDs de dispositivo no formato correto, com base no tipo de dispositivo. O Audience Manager rejeita IDs de dispositivo que não atendem ao formato correto e retorna uma mensagem de erro para indicar que a ID foi rejeitada.

* As mensagens de erro para transferências de dados em lote estão descritas aqui: [Termos e definições do relatório de status onboard](../reporting/onboarding-status-report.md#report-terms-conditions).
* As mensagens de erro para transferências de dados em tempo real estão descritas aqui: [Códigos de erro DCS, mensagens e exemplos](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).

## Política de Expiração de ID de Dispositivo

O Audience Manager descarta automaticamente as IDs de publicidade do dispositivo após 120 dias de inatividade, de modo semelhante à [UUID de AAM](../faq/faq-privacy.md)s.

## Solicitação de novas fontes de dados globais

Para solicitar que novas fontes de dados globais sejam adicionadas ao Audience Manager, entre em contato com o Atendimento ao cliente da Adobe Consulting ou do Adobe e forneça informações detalhadas sobre as fontes de dados necessárias:

* O nome da plataforma solicitada (por exemplo, [!UICONTROL Apple IDFA]);
* O nome da empresa/organização que gerencia a plataforma (por exemplo, [!UICONTROL Apple Inc.]);
* Links para as especificações técnicas do namespace de ID de anúncio do dispositivo (por exemplo, [Documentação de AdSupport](https://developer.apple.com/documentation/adsupport)).
