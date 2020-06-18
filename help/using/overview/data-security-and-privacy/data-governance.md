---
description: Este documento explica como os dados do cliente são controlados no Audience Manager.
seo-description: Este documento explica como os dados do cliente são governados no Audience Manager.
seo-title: Controle de dados
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent, obfuscation, governance
title: Controle de dados
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 1%

---


# Controle de dados

## Visão geral {#overview}

O Data Governance no Audience Manager refere-se ao ciclo de vida dos dados do cliente no Audience Manager e abrange a [coleta e ofuscação de endereços](data-governance.md#collecting-ip-addresses)IP, retenção [de](data-governance.md#data-retention)dados e transferências [de dados](data-governance.md#data-transfers)transfronteiras.

## Coletando Endereços IP e Ofuscação de Endereço IP {#collecting-ip-addresses}

The [!DNL IP] address of a visitor to a customer’s website is transmitted to an Adobe [!DNL Data Processing Center] ([!DNL DPC]) where the [!DNL IP] address may be stored. Depending on the network configuration for the visitor, the [!DNL IP] address may not necessarily represent the [!DNL IP] address of the visitor’s computer. For example, the [!DNL IP] address could be the external [!DNL IP] address of a Network Address Translation (NAT) firewall, [!DNL HTTP] proxy, or Internet gateway.

**Metodologia de ofuscação de IP:** Seguindo os princípios de &quot;Privacidade por design&quot;, o Adobe Audience Manager permite que os clientes habilitem a [!DNL IP] ofuscação da interface do usuário, tanto globalmente em todas as regiões geográficas quanto para países específicos. Quando você habilita essa configuração, o último octeto (a última parte) do [!DNL IP] endereço é imediatamente descartado quando o [!DNL IP] endereço é ingerido no Audience Manager. O Audience Manager descarta essa parte do [!DNL IP] endereço antes do processamento (inclusive antes de qualquer pesquisa geográfica ou registro opcional do [!DNL IP] endereço). Por exemplo:

* Antes: `255.255.255.255`
* Depois: `255.255.255.0`

>[!NOTE]
>
>Consulte Ofuscação [de endereço](../../features/administration/ip-obfuscation.md) IP para saber como ativar a ofuscação de [!DNL IP] endereço na interface do usuário do Audience Manager.

Assista ao vídeo abaixo para entender como a ofuscação de [!DNL IP] endereços funciona no Audience Manager.

>[!VIDEO](https://video.tv.adobe.com/v/27218/)

**Segmentação geográfica:** Se você ativar a ofuscação de [!DNL IP] endereço, os octeto restantes do [!DNL IP] endereço ainda poderão ser usados para a segmentação geográfica e relatórios no Audience Manager. Se você não ativar a ofuscação de [!DNL IP] endereço, o Audience Manager usará o [!DNL IP] endereço completo. Você pode usar o recurso Segmentação geográfica que permite identificar um [!DNL IP] local por área geográfica em ambos os casos, mas com uma pequena perda de precisão quando a [!DNL IP] ofuscação está sendo usada. Obtaining city-level information will likely be significantly impacted by the obfuscation of the [!DNL IP] address. A obtenção de informações sobre a região e o nível do país só deve ser ligeiramente afetada. Os dados de Segmentação geográfica são granulares somente no nível da cidade ou no nível do código postal, e não no nível individual. Leia mais sobre a [geolocalização](../../features/traits/trait-geotarget-keys.md) e como configurar características com variáveis geográficas.

## Retenção de dados no Audience Manager {#data-retention}

A aplicação de políticas apropriadas, seguras e oportunas de retenção de dados aos seus dados é uma parte importante do cumprimento das regras de privacidade dos dados. Os clientes do Audience Manager têm a capacidade de definir períodos de retenção personalizados em características e segmentos definindo o TTL (tempo de vida) necessário. Consulte Perguntas frequentes sobre [retenção de](../../faq/faq-privacy.md) dados para obter mais detalhes sobre os períodos de retenção.

## Transferências de dados transfronteiras {#data-transfers}

Quando a Audience Manager transfere dados pessoais de Clientes para além das fronteiras nacionais, a Audience Manager faz isso em conformidade com a legislação aplicável. Visite o Centro [de privacidade da](https://www.adobe.com/privacy/eudatatransfers.html) Adobe para saber mais.