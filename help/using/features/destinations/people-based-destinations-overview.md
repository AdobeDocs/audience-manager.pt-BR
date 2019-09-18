---
description: 'Use destinos baseados em pessoas para enviar segmentos de público-alvo primários para ambientes baseados em pessoas. Esses ambientes são ecossistemas fechados pertencentes a uma entidade que controla o conteúdo que está sendo exibido dentro dele. Eles incluem plataformas sociais, como o Facebook, e outras plataformas que dependem das contas do cliente para personalizar o conteúdo exibido. '
seo-description: 'Use destinos baseados em pessoas para enviar segmentos de público-alvo primários para ambientes baseados em pessoas. Esses ambientes são ecossistemas fechados pertencentes a uma entidade que controla o conteúdo que está sendo exibido dentro dele. Eles incluem plataformas sociais, como o Facebook, e outras plataformas que dependem das contas do cliente para personalizar o conteúdo exibido.  '
seo-title: Destinos baseados em pessoas - Visão geral e casos de uso
solution: Audience Manager
title: Visão geral e casos de uso
translation-type: tm+mt
source-git-commit: 62c27a3990c2c39d069c7a6e4ef32e8e8b3f1998

---


# Visão geral e casos de uso {#overview-use-cases}

Use [!DNL People-Based Destinations] para enviar segmentos de público-alvo primários para ambientes baseados em pessoas. Esses ambientes são ecossistemas fechados pertencentes a uma entidade que controla o conteúdo que está sendo exibido dentro dele. Eles incluem plataformas sociais, como [!DNL Facebook]e outras plataformas que dependem das contas do cliente para personalizar o conteúdo exibido.

## Visão geral {#overview}

[!DNL People-Based Destinations] permite aplicar a segmentação em dados online e offline para criar segmentos de público-alvo com base em identificadores com hash, como endereços de email ou números de telefone. Em seguida, você pode enviar esses segmentos para "jardins instalados", como [!DNL Facebook], onde você pode direcionar seu público-alvo independentemente de suas interações online ou estado de autenticação. [!DNL People-Based Destinations] pode ajudá-lo a:

* Direcione públicos offline e online em plataformas como [!DNL Facebook], com base em endereços de email com hash;
* Complementar os recursos existentes de definição de metas de dispositivos e cookies do Audience Manager;
* Eliminar os custos associados às soluções de integração de dados de terceiros;
* Eliminar os custos associados ao desenvolvimento de fluxos de trabalho personalizados de integração de dados;
* públicos-alvo em ambientes sem cookies;
* Direcione públicos-alvo desduplicando endereços de email correspondentes às IDs do cliente.

Você pode usar [!DNL People-Based Destinations] para segmentar e direcionar clientes de alto valor que podem nunca ter visitado seu site, ou parar de segmentar aqueles que já se converteram offline. Além disso, você pode aproveitar [!DNL Profile Merge Rules] para combinar dados offline primários com dados online primários, incluindo dados de clientes de outras soluções da Adobe Experience Cloud, para otimizar seus esforços de publicidade em redes sociais.

![pbd-overview](assets/pbd-overview.png)

## Availability {#availability}

[!DNL People-Based Destinations] é uma integração premium do Audience Manager. Entre em contato com seu representante da Adobe para aproveitar esse recurso premium.

## Por que você deve usar destinos baseados em pessoas {#why-use}

**Forneça aos seus clientes experiências consistentes entre canais, gerenciando toda a segmentação do público-alvo no Audience Manager.**

Não ativar seus segmentos de público-alvo em canais baseados em pessoas por meio do Audience Manager resulta em experiências dissociadas entre o que seus clientes veem ao visitar seu site e o que eles veem, por exemplo, em seus [!DNL Facebook] feeds. Ter uma definição de metas consistente em todos os canais pode aumentar a receita de seus anúncios e, ao mesmo tempo, otimizar os gastos com seus anúncios.

**Alcance públicos-alvo em canais baseados em pessoas sem a necessidade de uma solução dedicada de integração de dados ou fluxos de trabalho personalizados para enviar públicos-alvo.**

A maneira mais "tradicional" de direcionar públicos-alvo em canais baseados em pessoas envolve a necessidade de exportar os dados do cliente em um formato aceito pela plataforma para a qual você deseja anunciar e, em seguida, usar o método dedicado de integração de dados da plataforma para trazer os dados do cliente para a conta do anunciante. Este é todo o trabalho manual que você precisa fazer para cada plataforma que você deseja anunciar. Além disso, diferentes plataformas podem ter diferentes requisitos de formato de dados, tornando o processo ainda mais tedioso.

![pbd-overview](assets/pbd-diagram.png)

Por meio [!DNL People-Based Destinations], o Audience Manager ajuda você a centralizar todos os dados do cliente, criar segmentos de público-alvo e ativá-los em vários canais baseados em pessoas. Você pode fazer isso tudo na interface do usuário do Audience Manager, evitando o trabalho adicional de carregar dados manualmente para cada plataforma, economizando tempo valioso no processo.

**Crie e ative segmentos de público-alvo a partir de perfis meramente offline.**

[!DNL People-Based Destinations] resolva o problema que anteriormente, você só podia ativar segmentos de público-alvo com base na atividade do dispositivo. Com [!DNL People-Based Destinations]o, você pode criar segmentos a partir de dados puramente offline [!DNL CRM]e ativá-los em plataformas baseadas em pessoas. Além disso, você pode correlacionar dados offline com dados de dispositivo que já têm no Audience Manager.

**Aproveite o controle de dados e os controles de privacidade do Audience Manager para lidar com os dados do cliente com segurança.**

[!DNL People-Based Destinations] use apenas identificadores com hash, para que os dados do cliente estejam sempre protegidos, do momento em que você os embarca no Audience Manager até o momento em que ele atinge o destino. Isso elimina os riscos de privacidade associados ao upload manual de dados confidenciais do cliente em cada plataforma de ativação.

## Casos de uso {#use-cases}

Para ajudá-lo a entender melhor como e quando você deve usar [!DNL People-Based Destinations], há dois casos de uso de amostra que os clientes do Audience Manager podem resolver usando esse recurso.

### Use Case #1 {#use-case-1}

Um varejista online quer atingir os clientes existentes por meio de plataformas sociais e mostrar a eles ofertas personalizadas com base em seus pedidos anteriores. Com [!DNL People-Based Destinations], eles podem assimilar endereços de email com hash [!DNL CRM] para o Audience Manager, criar segmentos a partir dos dados offline e enviar esses segmentos para as plataformas sociais nas quais desejam anunciar, otimizando seus gastos com publicidade.

### Use Case #2 {#use-case-2}

Uma companhia aérea tem níveis de clientes diferentes (Bronze, Prata e Ouro) e quer oferecer a cada um dos níveis ofertas personalizadas por meio de plataformas sociais. A empresa usa o Audience Manager para analisar a atividade do cliente no site. No entanto, nem todos os clientes usam o aplicativo móvel da companhia aérea, e alguns deles nunca fizeram logon no site da empresa. Os únicos identificadores que a empresa tem sobre esses clientes são IDs de associação e endereços de email.

Para direcioná-los pelas mídias sociais e canais semelhantes baseados em pessoas, eles podem integrar os dados do cliente do [!DNL CRM] no Audience Manager, usando os endereços de email com hash como identificadores.

Em seguida, eles podem combinar os dados offline com as características de atividade online existentes, para criar novos segmentos de público-alvo com os quais eles podem direcionar [!DNL People-Based Destinations].
