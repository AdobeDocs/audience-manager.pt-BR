---
description: 'Use people-based destinations to send first-party audience segments to people-based environments. These environments are closed ecosystems belonging to one entity that controls the content that is being displayed within it. They include social platforms such as Facebook, and other platforms that rely on customer accounts to personalize the displayed content. '
seo-description: 'Use people-based destinations to send first-party audience segments to people-based environments. These environments are closed ecosystems belonging to one entity that controls the content that is being displayed within it. Eles incluem plataformas sociais, como o Facebook, e outras plataformas que dependem das contas do cliente para personalizar o conteúdo exibido.  '
seo-title: Destinos baseados em pessoas - Visão geral e casos de uso
solution: Audience Manager
title: Visão geral e casos de uso
translation-type: tm+mt
source-git-commit: 6093def9c5853572c064a4e398d5e328bcb9d181

---


# Visão geral e casos de uso {#overview-use-cases}

Use [!DNL People-Based Destinations] para enviar segmentos de público-alvo primários para ambientes baseados em pessoas. Esses ambientes são ecossistemas fechados pertencentes a uma entidade que controla o conteúdo que está sendo exibido dentro dele. Eles incluem plataformas sociais, como [!DNL Facebook]e outras plataformas que dependem das contas do cliente para personalizar o conteúdo exibido.

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

## Por que você deve usar destinos baseados em pessoas {#why-use}

**Forneça aos seus clientes experiências consistentes entre canais, gerenciando toda a segmentação do público-alvo no Audience Manager.**

Não ativar seus segmentos de público-alvo em canais baseados em pessoas por meio do Audience Manager resulta em experiências dissociadas entre o que seus clientes veem ao visitar seu site e o que eles veem, por exemplo, em seus [!DNL Facebook] feeds. Ter uma definição de metas consistente em todos os canais pode aumentar a receita de seus anúncios e, ao mesmo tempo, otimizar os gastos com seus anúncios.

**Alcance públicos-alvo em canais baseados em pessoas sem a necessidade de uma solução dedicada de integração de dados ou fluxos de trabalho personalizados para enviar públicos-alvo.**

A maneira mais "tradicional" de direcionar públicos-alvo em canais baseados em pessoas envolve a necessidade de exportar os dados do cliente em um formato aceito pela plataforma para a qual você deseja anunciar e, em seguida, usar o método dedicado de integração de dados da plataforma para trazer os dados do cliente para a conta do anunciante. Este é todo o trabalho manual que você precisa fazer para cada plataforma que você deseja anunciar. Além disso, diferentes plataformas podem ter diferentes requisitos de formato de dados, tornando o processo ainda mais tedioso.

![pbd-overview](assets/pbd-diagram.png)

Por meio [!DNL People-Based Destinations], o Audience Manager ajuda a centralizar os dados do cliente, criar segmentos de público-alvo e ativá-los em vários canais baseados em pessoas. You can do this all from within the Audience Manager UI, avoiding the additional work of manually uploading data to each platform, saving you valuable time in the process.

**Crie e ative segmentos de público-alvo a partir de perfis meramente offline.**

[!DNL People-Based Destinations] solve the issue that previously, you could only activate audience segments based on device activity. With , you can create segments from purely offline data from your own , and activate them in people-based platforms. [!DNL People-Based Destinations][!DNL CRM] Additionally, you can correlate your offline data with device data that you already have in Audience Manager.

**Leverage Audience Manager's data governance and privacy controls to safely handle customer data.**

[!DNL People-Based Destinations] requires that you only use irreversibly hashed identifiers. This reduces the risk associated with manually uploading customer data into each destination platform.

## Casos de uso {#use-cases}

To help you better understand how and when you should use , here are two sample use cases that Audience Manager customers can solve by using this feature.[!DNL People-Based Destinations]

### Use Case #1 {#use-case-1}

An online retailer wants to reach existing customers through social platforms and show them personalized offers based on their previous orders. With , the online retailer can ingest hashed email addresses from their own  to Audience Manager, build segments from their own offline data, and send these segments to the social platforms they want to advertise on, optimizing their advertising spending.[!DNL People-Based Destinations][!DNL CRM]

### Use Case #2 {#use-case-2}

An airline has different customer tiers (Bronze, Silver, and Gold), and wants to provide each of the tiers with personalized offers via social platforms. The company uses Audience Manager to analyze customer activity on the website. However, not all customers use the airline's mobile app, and some of them have not logged in to the company's website. Os únicos identificadores que a empresa tem sobre esses clientes são IDs de associação e endereços de email.

To target them across social media and similar people-based channels, they can onboard the customer data from their  into Audience Manager, using the hashed email addresses as identifiers.[!DNL CRM]

Em seguida, eles podem combinar seus dados offline com suas características de atividade online existentes, para criar novos segmentos de público-alvo através dos quais eles podem direcionar [!DNL People-Based Destinations].
