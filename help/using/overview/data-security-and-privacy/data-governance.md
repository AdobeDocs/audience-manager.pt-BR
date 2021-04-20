---
description: Este documento explica como os dados do cliente são controlados no Audience Manager.
seo-description: Este documento explica como os dados do cliente são controlados no Audience Manager.
seo-title: Controle de dados
solution: Audience Manager
keywords: Interface do usuário do GDPR, API do GDPR, CCPA, privacidade, consentimento, ofuscação, governança
title: Controle de dados
feature: Data Governance & Privacy
exl-id: 52aeca00-73f2-4525-9e11-34a472ec45c6
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 94%

---

# Controle de dados

## Visão geral {#overview}

O controle de dados no Audience Manager refere-se ao ciclo de vida dos dados de seus clientes no Audience Manager e abrange [Coleta e ofuscação de endereços IP](data-governance.md#collecting-ip-addresses), [Retenção de dados](data-governance.md#data-retention) e [Transferências de dados entre fronteiras](data-governance.md#data-transfers).

## Coleta e ofuscação de endereço IP {#collecting-ip-addresses}

O endereço [!DNL IP] de um visitante do site de um cliente é transmitido a um [!DNL Data Processing Center] ([!DNL DPC]) da Adobe, onde o endereço [!DNL IP] pode ser armazenado. Dependendo da configuração de rede do visitante, o endereço [!DNL IP] não representa necessariamente o endereço [!DNL IP] do computador dele. Por exemplo, o endereço [!DNL IP] pode ser o endereço [!DNL IP] externo de um firewall NAT (Network Address Translation, tradução de endereço de rede), proxy [!DNL HTTP] ou gateway de Internet.

**Metodologia de ofuscação de IP:** seguindo os princípios de &quot;Privacidade por design&quot;, o Adobe Audience Manager permite que os clientes habilitem a ofuscação de [!DNL IP] da interface do usuário, globalmente em todas as áreas geográficas ou em países específicos. Ao habilitar essa configuração, o último octeto (a última parte) do endereço [!DNL IP] é imediatamente descartado quando o endereço [!DNL IP] é assimilado no Audience Manager. O Audience Manager descarta essa parte do endereço [!DNL IP] antes do processamento (incluindo antes de qualquer pesquisa geográfica ou registro opcional do endereço [!DNL IP]). Por exemplo:

* Antes: `255.255.255.255`
* Depois: `255.255.255.0`

>[!NOTE]
>
>Consulte [Ofuscação de endereço IP](../../features/administration/ip-obfuscation.md) para saber como ativar a ofuscação de endereço [!DNL IP] na interface do usuário do Audience Manager.

Assista ao vídeo abaixo para entender como a ofuscação de endereços [!DNL IP] funciona no Audience Manager.

>[!VIDEO](https://video.tv.adobe.com/v/27218/)

**Segmentação geográfica:** se você ativar a ofuscação de endereço [!DNL IP], os octetos restantes do endereço [!DNL IP] ainda poderão ser usados para a segmentação geográfica e em relatórios no Audience Manager. Se você não ativar a ofuscação de endereço [!DNL IP], o Audience Manager usará o endereço [!DNL IP] completo. Você pode usar o recurso Segmentação geográfica que permite identificar um local [!DNL IP] por área geográfica em ambos os casos, mas com uma pequena perda de precisão quando a ofuscação de [!DNL IP] está sendo usada. A obtenção de informações do nível da cidade provavelmente será muito afeta pela ofuscação do endereço [!DNL IP]. A obtenção de informações do nível da região e do país será pouco afetada. Os dados de segmentação geográfica são granulares somente no nível da cidade ou no nível de código postal, e não no nível individual. Leia mais sobre [geolocalização](../../features/traits/trait-geotarget-keys.md) e como configurar características com variáveis geográficas.

## Retenção de dados no Audience Manager {#data-retention}

A aplicação de políticas apropriadas, seguras e oportunas de retenção de dados é uma parte importante do cumprimento das regras de privacidade dos dados. Os clientes do Audience Manager podem definir períodos de retenção personalizados em características e segmentos definindo o TTL (tempo de vida útil) necessário. Consulte [Perguntas frequentes sobre retenção de dados](../../faq/faq-privacy.md) para obter mais detalhes sobre os períodos de retenção.

## Transferências de dados entre fronteiras {#data-transfers}

Quando transfere dados pessoais de clientes para além das fronteiras nacionais, o Audience Manager cumpre a legislação aplicável. Visite o [Centro de privacidade da Adobe](https://www.adobe.com/br/privacy/eudatatransfers.html) para obter mais informações.
