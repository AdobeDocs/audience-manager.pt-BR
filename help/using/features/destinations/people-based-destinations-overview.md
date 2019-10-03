---
description: 'Use destinos baseados em pessoas para enviar segmentos de público-alvo primários para ambientes baseados em pessoas. Esses ambientes são ecossistemas fechados pertencentes a uma entidade que controla o conteúdo que está sendo exibido dentro dele. Eles incluem plataformas sociais, como o Facebook, e outras plataformas que dependem das contas do cliente para personalizar o conteúdo exibido. '
seo-description: 'Use destinos baseados em pessoas para enviar segmentos de público-alvo primários para ambientes baseados em pessoas. Esses ambientes são ecossistemas fechados pertencentes a uma entidade que controla o conteúdo que está sendo exibido dentro dele. They include social platforms such as Facebook, and other platforms that rely on customer accounts to personalize the displayed content.  '
seo-title: People-Based Destinations Overview and Use Cases
solution: Audience Manager
title: Visão geral e casos de uso
translation-type: tm+mt
source-git-commit: 0eb6a6f67d87377a044b18118fac0185219b0347

---


# Overview and Use Cases {#overview-use-cases}

Use  to send first-party audience segments to people-based environments. [!DNL People-Based Destinations] These environments are closed ecosystems belonging to one entity that controls the content that is being displayed within it. They include social platforms such as , and other platforms that rely on customer accounts to personalize the displayed content.[!DNL Facebook]

>[!IMPORTANT]
>This article contains product documentation meant to guide you through the setup and usage of this feature. Nothing contained herein is legal advice. Please consult your own legal counsel for legal guidance.

## Visão geral {#overview}

[!DNL People-Based Destinations] permite que você aplique a segmentação em dados online e offline para criar segmentos de público-alvo com base em identificadores [com](people-based-destinations-prerequisites.md#hashing-requirements)hash, como endereços de email ou números de telefone. Em seguida, você pode enviar esses segmentos para "jardins instalados", como [!DNL Facebook], onde você pode direcionar seu público-alvo nas plataformas sociais. [!DNL People-Based Destinations] pode ajudá-lo a:

* Direcione públicos offline e online em plataformas como [!DNL Facebook], com base em endereços de email com hash;
* Complementar os recursos existentes de definição de metas de dispositivos e cookies do Audience Manager;
* Eliminar os custos associados às soluções de integração de dados de terceiros;
* Eliminar os custos associados ao desenvolvimento de fluxos de trabalho personalizados de integração de dados;
* públicos-alvo em ambientes sem cookies;
* Direcione públicos-alvo desduplicando endereços de email correspondentes às IDs do cliente.

Você pode usar [!DNL People-Based Destinations] para segmentar e direcionar clientes de alto valor que talvez não tenham visitado seu site, ou parar de direcionar aqueles que já se converteram offline. Além disso, você pode aproveitar [!DNL Profile Merge Rules] para combinar seus dados originais offline com seus dados originais online, incluindo dados de clientes de outras soluções da Adobe Experience Cloud, para otimizar seus esforços de publicidade em redes sociais.

![pbd-overview](assets/pbd-overview.png)

## Availability {#availability}

[!DNL People-Based Destinations] é uma integração premium do Audience Manager. Entre em contato com seu representante da Adobe para aproveitar esse recurso premium.

## Why You Should Use People-Based Destinations {#why-use}

**Provide your customers consistent cross-channel experiences by managing your entire audience segmentation from within Audience Manager.**

Not activating your audience segments in people-based channels through Audience Manager leads to disjointed experiences between what your customers see when visiting your website and what they see, for instance, in their  feeds. [!DNL Facebook] Having a consistent targeting across channels can increase your ad revenue while optimizing your ad spending.

**Reach audiences in people-based channels without the need of a dedicated data onboarding solution or custom workflows to send audiences.**

The more "traditional" way of targeting audiences across people-based channels involves you having to export your customer data in a format accepted by the platform that you want to advertise on, and then using the platform's dedicated data onboarding method to bring your customer data to your advertiser account. Este é todo o trabalho manual que você precisa fazer para cada plataforma que você deseja anunciar. Além disso, diferentes plataformas podem ter diferentes requisitos de formato de dados, tornando o processo ainda mais tedioso.

![pbd-overview](assets/pbd-diagram.png)

Por meio [!DNL People-Based Destinations], o Audience Manager ajuda a centralizar os dados do cliente, criar segmentos de público-alvo e ativá-los em vários canais baseados em pessoas. Você pode fazer isso tudo na interface do usuário do Audience Manager, evitando o trabalho adicional de carregar dados manualmente para cada plataforma, economizando tempo valioso no processo.

**Crie e ative segmentos de público-alvo a partir de perfis meramente offline.**

[!DNL People-Based Destinations] resolva o problema que anteriormente, você só podia ativar segmentos de público-alvo com base na atividade do dispositivo. Com [!DNL People-Based Destinations]o, você pode criar segmentos a partir de dados puramente offline [!DNL CRM]e ativá-los em plataformas baseadas em pessoas. Além disso, você pode correlacionar seus dados offline com os dados do dispositivo que já tem no Audience Manager.

**Aproveite o controle de dados e os controles de privacidade do Audience Manager para lidar com os dados do cliente com segurança.**

[!DNL People-Based Destinations] requer que você use somente identificadores com hash irreversivelmente. Isso reduz o risco associado ao upload manual dos dados do cliente em cada plataforma de destino.

Assista ao vídeo abaixo para obter uma visão geral do fluxo de dados ao usar [!UICONTROL People-Based Destinations].

[!VIDEO](https://video.tv.adobe.com/v/28968/?captions=por_br)

## Casos de uso {#use-cases}

Para ajudá-lo a entender melhor como e quando você deve usar [!DNL People-Based Destinations], há dois casos de uso de amostra que os clientes do Audience Manager podem resolver usando esse recurso.

### Use Case #1 {#use-case-1}

Um varejista online quer atingir os clientes existentes por meio de plataformas sociais e mostrar a eles ofertas personalizadas com base em seus pedidos anteriores. Com [!DNL People-Based Destinations]isso, o varejista online pode assimilar endereços de email com hash próprio [!DNL CRM] para o Audience Manager, criar segmentos a partir de seus próprios dados offline e enviar esses segmentos para as plataformas sociais nas quais deseja anunciar, otimizando seus gastos com publicidade.

### Use Case #2 {#use-case-2}

Uma companhia aérea tem níveis de clientes diferentes (Bronze, Prata e Ouro) e quer oferecer a cada um dos níveis ofertas personalizadas por meio de plataformas sociais. A empresa usa o Audience Manager para analisar a atividade do cliente no site. No entanto, nem todos os clientes usam o aplicativo móvel da companhia aérea e alguns deles não fizeram logon no site da empresa. Os únicos identificadores que a empresa tem sobre esses clientes são IDs de associação e endereços de email.

To target them across social media and similar people-based channels, they can onboard the customer data from their  into Audience Manager, using the hashed email addresses as identifiers.[!DNL CRM]

Em seguida, eles podem combinar seus dados offline com suas características de atividade online existentes, para criar novos segmentos de público-alvo através dos quais eles podem direcionar [!DNL People-Based Destinations].
