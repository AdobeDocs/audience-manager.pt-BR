---
description: Este documento explica como o gerenciamento de consentimento funciona no Audience Manager.
seo-description: This document explains how consent management works in Audience Manager.
seo-title: Consent Management
solution: Audience Manager
keywords: Interface do GDPR, API do GDPR, CCPA, privacidade, consentimento
title: Gerenciamento de consentimento
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: Data Governance & Privacy
exl-id: 9e545e8d-dbe4-4df9-8801-af3c2c73e406
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 98%

---

# Gerenciamento de consentimento

## Visão geral {#overview}

Nos casos em que o consentimento é necessário para determinadas atividades de marketing, os clientes do Audience Manager devem determinar o escopo e se determinados consentimentos precisam ser atualizados para poderem continuar usando os dados a partir de agora.

O Audience Manager oferece ferramentas para ajudar você a obter os consentimentos necessários de seus usuários, para que você possa fornecer experiências personalizadas para eles em todos os canais.

>[!IMPORTANT]
>
> O conteúdo desse documento não é um aconselhamento jurídico e não se destina a substituir tal aconselhamento.
>
> Como processador de dados, a Adobe não pode fornecer assistência jurídica para obter consentimento. Você também pode considerar trabalhar com um provedor de soluções de gerenciamento de consentimento, como [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) ou [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/), e consultar o departamento jurídico da empresa para obter conselhos sobre consentimento e práticas ao configurar a implementação de aceitação.

## Serviço de aceitação da Experience Cloud

O [Serviço de aceitação da Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=pt-BR) permite configurar os protocolos para o visitante a fim de determinar se você pode adicionar um cookie no dispositivo ou no navegador de pessoas físicas durante visitas ao site.

É uma extensão do [!DNL Experience Cloud ID (ECID) Service], desenvolvida para controlar se e quais soluções da Experience Cloud podem criar cookies nas páginas da web para os visitantes ante do consentimento do usuário.

O [Serviço de aceitação da Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=pt-BR) também permite que você defina protocolos para integrar à sua Plataforma de gerenciamento de consentimento (CMP) e aos sistemas existentes como parte de um projeto maior.

## Gerenciamento de aceitação/Obtenção de consentimento

Os clientes do Audience Manager podem armazenar o consentimento do usuário para vários casos de uso, como publicidade ou personalização, como características no Audience Manager. Os segmentos criados com essas características incluirão apenas os usuários que fornecerem o respectivo consentimento para cada um desses casos de uso. Observe que o uso dessa abordagem não interrompe a coleta de dados, mas afetará somente o uso de dados quando você enviar segmentos para ativação. Quando os usuários retiram o consentimento, você pode remover essas características do perfil do usuário usando o [processo de entrada em lote](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) ou o processo de recusa do Audience Manager, conforme detalhado abaixo.

## Gerenciamento de recusa/Retirada do consentimento

A recusa pode ser gerenciada na Adobe Experience Cloud por meio da página [Suas escolhas de privacidade](https://www.adobe.com/br/privacy/opt-out.html#customeruse). Os recursos de 1 clique permitem que os usuários finais controlem e excluam a coleta de dados pelas soluções de publicidade da Adobe Experience Cloud (incluindo o Audience Manager). Especificamente, consulte a [seção de cliente comercial](https://www.adobe.com/br/privacy/opt-out.html#customeruse) da página Opções de privacidade. Para navegadores que não aceitam cookies de terceiros, consulte [Direcionamento de ID declarada](../../features/declared-ids.md#declared-id-targeting). Para dispositivos móveis, recupere os identificadores relevantes do Audience Manager e chame as APIs de opção de recusa do Audience Manager, conforme mencionado nos [exemplos de recusa de ID declarada](../../features/declared-ids.md#opt-out-examples). Em seguida, você pode interromper toda a coleta de dados para os usuários com as APIs de recusa do SDK móvel - consulte [Dispositivos Android](https://experienceleague.adobe.com/docs/mobile-services/android/gdpr-privacy-android/privacy.html?lang=pt-BR) e [Dispositivos iOS](https://experienceleague.adobe.com/docs/mobile-services/ios/privacy-gdpr-ios/privacy.html?lang=pt-BR). Você pode encontrar detalhes adicionais para opção de recusa na [Documentação de solicitações de privacidade de dados](../../overview/data-security-and-privacy/data-privacy-requests.md).

## Gerenciamento do consentimento de parceiros secundários

Em geral, os parceiros secundários também são os controladores de dados e proprietários do processo para obter qualquer consentimento necessário do titular dos dados para compartilhar os dados com os parceiros de dados secundários. É sua responsabilidade, como cliente do Audience Manager, determinar se o parceiro secundário obteve o consentimento necessário para o caso de uso. Mais detalhes sobre a obtenção do consentimento são abordados acima.

## Gerenciamento do consentimento para parceiros de terceiros do Audience Marketplace

Parceiros de terceiros do Audience Marketplace também são controladores de dados e proprietários de seu processo para obter consentimento e gerenciar solicitações de acesso/exclusão/correção. A Adobe está solicitando proativamente que os parceiros de terceiros do Audience Marketplace atualizem as informações de perfil da empresa no [Adobe Audience Finder](https://www.adobe-audience-finder.com/) com informações adicionais sobre a coleta de dados do usuário. As informações serão fornecidas pelos parceiros de terceiros do Audience Marketplace e serão atualizadas regularmente. No entanto, cabe a cada cliente do Audience Manager determinar se o parceiro de terceiros do Audience Marketplace obteve o consentimento necessário para o caso de uso do cliente. A Adobe não faz declarações sobre o escopo ou a validade do consentimento obtido ou relatado por um parceiro de terceiros do Audience Marketplace para um determinado caso de uso.
