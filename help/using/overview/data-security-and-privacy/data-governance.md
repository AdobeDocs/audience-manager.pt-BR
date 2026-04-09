---
description: Este documento explica como os dados do cliente são controlados no Audience Manager.
seo-description: TThis document explains how customer data is governed in Audience Manager.
seo-title: Data Governance
solution: Audience Manager
keywords: Interface do GDPR, API do GDPR, CCPA, privacidade, consentimento, ofuscação, governança
title: Controle de dados
feature: Data Governance & Privacy
exl-id: 52aeca00-73f2-4525-9e11-34a472ec45c6
TQID: https://experienceleague.adobe.com/HVF-SxKO4mcE7YkiiwXLBPn2K3N5NIjpZHFWgZb0CoI
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2:
  - id: a49258d4-867f-4130-b875-d72c001bdf6c
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: cc72dcf1-72e1-48cc-b434-e7c27d62d67c
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 451
ht-degree: 90%

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
>Consulte [Ofuscação de endereço IP](../../features/administration/ip-obfuscation.md) para saber como habilitar a ofuscação de endereço [!DNL IP] na interface do usuário do Audience Manager.

Assista ao vídeo abaixo para entender como a ofuscação de endereços [!DNL IP] funciona no Audience Manager.

>[!VIDEO](https://video.tv.adobe.com/v/34983?captions=por_br)

**Segmentação geográfica:** se você ativar a ofuscação de endereço [!DNL IP], os octetos restantes do endereço [!DNL IP] ainda poderão ser usados para a segmentação geográfica e em relatórios no Audience Manager. Se você não ativar a ofuscação de endereço [!DNL IP], o Audience Manager usará o endereço [!DNL IP] completo. Você pode usar o recurso Segmentação geográfica que permite identificar um local [!DNL IP] por área geográfica em ambos os casos, mas com uma pequena perda de precisão quando a ofuscação de [!DNL IP] está sendo usada. A obtenção de informações do nível da cidade provavelmente será muito afeta pela ofuscação do endereço [!DNL IP]. A obtenção de informações do nível da região e do país será pouco afetada. Os dados de segmentação geográfica são granulares somente no nível da cidade ou no nível de código postal, e não no nível individual. Leia mais sobre [geolocalização](../../features/traits/trait-geotarget-keys.md) e como configurar características com variáveis geográficas.

## Retenção de dados no Audience Manager {#data-retention}

A aplicação de políticas apropriadas, seguras e oportunas de retenção de dados é uma parte importante do cumprimento das regras de privacidade dos dados. Os clientes do Audience Manager podem definir períodos de retenção personalizados em características e segmentos definindo o TTL (tempo de vida útil) necessário. Consulte [Perguntas frequentes sobre retenção de dados](../../faq/faq-privacy.md) para obter mais detalhes sobre os períodos de retenção.

## Transferências de dados entre fronteiras {#data-transfers}

Quando transfere dados pessoais de clientes para além das fronteiras nacionais, o Audience Manager cumpre a legislação aplicável. Visite o [Centro de privacidade da Adobe](https://www.adobe.com/br/privacy/eudatatransfers.html) para obter mais informações.
