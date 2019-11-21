---
description: Este documento explica como o gerenciamento de consentimento funciona no Audience Manager.
seo-description: Este documento explica como o gerenciamento de consentimento funciona no Audience Manager.
seo-title: Gerenciamento de consentimento
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent
title: Gerenciamento de consentimento
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: fbe4e8c912093c495f27ca887a44ac31d394811a

---


# Gerenciamento de consentimento

## Visão geral {#overview}

Nos casos em que o consentimento é necessário para determinadas atividades de marketing, o consentimento do consumidor precisa de estar ativo (por exemplo, não há caixas pré-marcadas ou silêncio como parecer favorável), desagregado e as ofertas de serviços podem não estar sujeitas à condição de a pessoa em causa dar o seu consentimento. Pode até haver casos em que certos consentimentos precisam ser atualizados para que os dados possam continuar a ser usados.

O Audience Manager oferece as ferramentas necessárias para obter o consentimento necessário dos usuários, para que você possa fornecer experiências personalizadas para eles em todos os canais.

>[!IMPORTANT]
>
> O conteúdo deste documento não é um aconselhamento jurídico e não se destina a substituir o aconselhamento jurídico.
>
> Como seu processador de dados, a Adobe não pode fornecer assistência jurídica para obter consentimento. Recomendamos que você trabalhe com um provedor de soluções de gerenciamento de consentimento, como [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) ou [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/), para receber as melhores recomendações e consultar o departamento jurídico da sua empresa para obter conselhos sobre consentimento e práticas ao configurar sua implementação de aceitação.

## Serviço de aceitação da Experience Cloud

The [Experience Cloud Opt-in Service](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) service lets you set up protocols for the visitor to determine if you can set a cookie on the user's device or browser when visiting your site.

This is an extension of the [!DNL Experience Cloud ID (ECID) Service], designed to let you control whether and which Experience Cloud solutions can place cookies on web pages for visitors prior to user consent.

O Serviço [de aceitação da](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) Experience Cloud também permite que você defina protocolos para integrar-se à sua Plataforma de gerenciamento de consentimento (CMP) e aos sistemas existentes como parte de seu projeto maior.

## Gerenciando aceitação / Obtendo consentimento

Os clientes do Audience Manager podem armazenar o consentimento do usuário para vários casos de uso, como publicidade ou personalização como características no Audience Manager. A construção de segmentos com essas características incluirá apenas os usuários que fornecerem o respectivo consentimento para cada um desses casos de uso. Observe que o uso dessa abordagem não interrompe a coleta de dados, mas afetará somente o uso de dados quando você enviar segmentos para ativação. Quando os usuários retiram seu consentimento, você pode remover essas características do perfil do usuário usando o processo [de lote de](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) entrada do Audience Manager ou o processo de não participação do Audience Manager, conforme detalhado abaixo.

## Gerenciando a recusa/retirada do consentimento

A recusa pode ser gerenciada para a Adobe Experience Cloud por meio da página [Suas escolhas](https://www.adobe.com/privacy/opt-out.html#customeruse) de privacidade. Os recursos de 1 clique permitem que os usuários finais controlem e excluam a coleta de dados pelas soluções de publicidade da Adobe Experience Cloud (incluindo o Audience Manager). Especificamente, consulte a seção [Cliente](https://www.adobe.com/privacy/opt-out.html#customeruse) comercial da página Opções de privacidade. Para navegadores que não suportam cookies de terceiros, consulte Definição de metas [de ID](../../features/declared-ids.md#declared-id-targeting)declarada. Para dispositivos móveis, recupere os identificadores relevantes do Audience Manager e chame as APIs de opção de não participação do Audience Manager, conforme mencionado nos exemplos [de opção de não participação da ID](../../features/declared-ids.md#opt-out-examples)declarada. Em seguida, você pode interromper toda a coleta de dados para os usuários com as APIs de opção de não participação do SDK móvel - consulte Dispositivos [Android e dispositivos](https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html) [](https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html)iOS. Você pode encontrar detalhes adicionais para opção de não participação na Documentação [de solicitações de privacidade de](../../overview/data-security-and-privacy/data-privacy-requests.md)dados.

## Gerenciando Consentimento para Provedores de Dados de Terceiros

Em geral, os provedores de dados secundários também são controladores de dados e são proprietários do processo para obter qualquer consentimento necessário da pessoa de dados para compartilhar dados com seus parceiros de dados secundários. Como cliente do Audience Manager, é sua responsabilidade determinar se o provedor de dados de terceiros obteve o consentimento necessário para o caso de uso. Mais detalhes sobre a obtenção do consentimento são abordados acima.

## Gerenciando o consentimento para provedores de dados de terceiros

Os provedores de dados de terceiros também são controladores de dados e são proprietários de seus processos para obter consentimento e gerenciar solicitações de acesso/exclusão/correção. A Adobe está solicitando proativamente que os Provedores de Dados atualizem as informações de perfil de sua empresa no [Adobe Audience Finder](https://www.adobe-audience-finder.com/) com informações adicionais sobre a coleta de dados do usuário. As informações serão fornecidas pelos provedores de dados e serão atualizadas regularmente. No entanto, cabe a cada cliente do Audience Manager determinar que o provedor de dados de terceiros obteve o consentimento necessário para o caso de uso do cliente. A Adobe não faz declarações sobre o escopo ou a validade do consentimento obtido ou relatado por um Provedor de dados de terceiros para um determinado caso de uso.
