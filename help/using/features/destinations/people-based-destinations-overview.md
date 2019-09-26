---
description: 'Use destinos baseados em pessoas para enviar segmentos de público-alvo primários para ambientes baseados em pessoas. Esses ambientes são ecossistemas fechados pertencentes a uma entidade que controla o conteúdo que está sendo exibido dentro dele. Eles incluem plataformas sociais, como o Facebook, e outras plataformas que dependem das contas do cliente para personalizar o conteúdo exibido. '
seo-description: 'Use destinos baseados em pessoas para enviar segmentos de público-alvo primários para ambientes baseados em pessoas. Esses ambientes são ecossistemas fechados pertencentes a uma entidade que controla o conteúdo que está sendo exibido dentro dele. Eles incluem plataformas sociais, como o Facebook, e outras plataformas que dependem das contas do cliente para personalizar o conteúdo exibido.  '
seo-title: Destinos baseados em pessoas - Visão geral e casos de uso
solution: Audience Manager
title: Visão geral e casos de uso
translation-type: tm+mt
source-git-commit: f500b4a763f1639392253b7e5f209395a978e45e

---


# Visão geral e casos de uso {#overview-use-cases}

Use [!DNL People-Based Destinations] para enviar segmentos de público-alvo primários para ambientes baseados em pessoas. Esses ambientes são ecossistemas fechados pertencentes a uma entidade que controla o conteúdo que está sendo exibido dentro dele. Eles incluem plataformas sociais, como [!DNL Facebook]e outras plataformas que dependem das contas do cliente para personalizar o conteúdo exibido.

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a guiá-lo pela configuração e uso deste recurso. Nada aqui contido é aconselhamento jurídico. Consulte o seu próprio advogado para obter orientação jurídica.

## Visão geral {#overview}

[!DNL People-Based Destinations] permite que você aplique a segmentação em dados online e offline para criar segmentos de público-alvo com base em identificadores [com](people-based-destinations-prerequisites.md#hashing-requirements)hash, como endereços de email ou números de telefone. Em seguida, você pode enviar esses segmentos para "jardins instalados", como [!DNL Facebook], onde você pode direcionar seu público-alvo nas plataformas sociais. [!DNL People-Based Destinations] pode ajudá-lo a:

* Direcione públicos offline e online em plataformas como [!DNL Facebook], com base em endereços de email com hash;
* Complementar os recursos existentes de definição de metas de dispositivos e cookies do Audience Manager;
* Eliminar os custos associados às soluções de integração de dados de terceiros;
* Eliminate costs associated with developing custom data onboarding workflows;
* Target audiences in cookie-less environments;
* Direcione públicos-alvo desduplicando endereços de email correspondentes às IDs do cliente.

Você pode usar [!DNL People-Based Destinations] para segmentar e direcionar clientes de alto valor que talvez não tenham visitado seu site, ou parar de direcionar aqueles que já se converteram offline. Além disso, você pode aproveitar [!DNL Profile Merge Rules] para combinar seus dados originais offline com seus dados originais online, incluindo dados de clientes de outras soluções da Adobe Experience Cloud, para otimizar seus esforços de publicidade em redes sociais.

![pbd-overview](assets/pbd-overview.png)

## Availability {#availability}

[!DNL People-Based Destinations] is a premium Audience Manager integration. Please contact your Adobe representative to take advantage of this premium feature.

## Por que você deve usar destinos baseados em pessoas {#why-use}

**Provide your customers consistent cross-channel experiences by managing your entire audience segmentation from within Audience Manager.**

Not activating your audience segments in people-based channels through Audience Manager leads to disjointed experiences between what your customers see when visiting your website and what they see, for instance, in their  feeds. [!DNL Facebook] Having a consistent targeting across channels can increase your ad revenue while optimizing your ad spending.

**Alcance públicos-alvo em canais baseados em pessoas sem a necessidade de uma solução dedicada de integração de dados ou fluxos de trabalho personalizados para enviar públicos-alvo.**

A maneira mais "tradicional" de direcionar públicos-alvo em canais baseados em pessoas envolve a necessidade de exportar os dados do cliente em um formato aceito pela plataforma para a qual você deseja anunciar e, em seguida, usar o método dedicado de integração de dados da plataforma para trazer os dados do cliente para a conta do anunciante. Este é todo o trabalho manual que você precisa fazer para cada plataforma que você deseja anunciar. Além disso, diferentes plataformas podem ter diferentes requisitos de formato de dados, tornando o processo ainda mais tedioso.

![pbd-overview](assets/pbd-diagram.png)

Por meio [!DNL People-Based Destinations], o Audience Manager ajuda a centralizar os dados do cliente, criar segmentos de público-alvo e ativá-los em vários canais baseados em pessoas. Você pode fazer isso tudo na interface do usuário do Audience Manager, evitando o trabalho adicional de carregar dados manualmente para cada plataforma, economizando tempo valioso no processo.

**Crie e ative segmentos de público-alvo a partir de perfis meramente offline.**

[!DNL People-Based Destinations] resolva o problema que anteriormente, você só podia ativar segmentos de público-alvo com base na atividade do dispositivo. Com [!DNL People-Based Destinations]o, você pode criar segmentos a partir de dados puramente offline [!DNL CRM]e ativá-los em plataformas baseadas em pessoas. Additionally, you can correlate your offline data with device data that you already have in Audience Manager.

**Leverage Audience Manager's data governance and privacy controls to safely handle customer data.**

[!DNL People-Based Destinations] requer que você use somente identificadores com hash irreversivelmente. Isso reduz o risco associado ao upload manual dos dados do cliente em cada plataforma de destino.

## Casos de uso {#use-cases}

Para ajudá-lo a entender melhor como e quando você deve usar [!DNL People-Based Destinations], há dois casos de uso de amostra que os clientes do Audience Manager podem resolver usando esse recurso.

### Use Case #1 {#use-case-1}

Um varejista online quer atingir os clientes existentes por meio de plataformas sociais e mostrar a eles ofertas personalizadas com base em seus pedidos anteriores. Com [!DNL People-Based Destinations]isso, o varejista online pode assimilar endereços de email com hash próprio [!DNL CRM] para o Audience Manager, criar segmentos a partir de seus próprios dados offline e enviar esses segmentos para as plataformas sociais nas quais deseja anunciar, otimizando seus gastos com publicidade.

### Use Case #2 {#use-case-2}

An airline has different customer tiers (Bronze, Silver, and Gold), and wants to provide each of the tiers with personalized offers via social platforms. The company uses Audience Manager to analyze customer activity on the website. However, not all customers use the airline's mobile app, and some of them have not logged in to the company's website. The only identifiers the company has about these customers are membership IDs and email addresses.

To target them across social media and similar people-based channels, they can onboard the customer data from their  into Audience Manager, using the hashed email addresses as identifiers.[!DNL CRM]

Next, they can combine their offline data with their existing online activity traits, to build new audience segments that they can target through .[!DNL People-Based Destinations]
