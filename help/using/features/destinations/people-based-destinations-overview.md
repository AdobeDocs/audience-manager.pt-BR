---
description: 'Use destinos baseados em pessoas para enviar segmentos de público-alvo primários para ambientes baseados em pessoas. Esses ambientes são os ecossistemas fechados pertencentes a uma entidade que controla o conteúdo que está sendo exibido dentro dele. Eles incluem plataformas sociais como Facebook, e outras plataformas que dependem de contas de clientes para personalizar o conteúdo exibido. '
seo-description: 'Use destinos baseados em pessoas para enviar segmentos de público-alvo primários para ambientes baseados em pessoas. Esses ambientes são os ecossistemas fechados pertencentes a uma entidade que controla o conteúdo que está sendo exibido dentro dele. Eles incluem plataformas sociais como Facebook, e outras plataformas que dependem de contas de clientes para personalizar o conteúdo exibido.  '
seo-title: Visão geral de destinos com base em pessoas e casos de uso
solution: Audience Manager
title: Visão geral e casos de uso
translation-type: tm+mt
source-git-commit: 5624eac36a7f2b8892136688f89fc22af241fc3a

---


# Visão geral e casos de uso {#overview-use-cases}

Use [!DNL People-Based Destinations] para enviar segmentos de público-alvo primários para ambientes baseados em pessoas. Esses ambientes são os ecossistemas fechados pertencentes a uma entidade que controla o conteúdo que está sendo exibido dentro dele. Eles incluem plataformas sociais como [!DNL Facebook], por exemplo, outras plataformas que dependem de contas de clientes para personalizar o conteúdo exibido.

## Visão geral {#overview}

[!DNL People-Based Destinations] permitem aplicar segmentação em dados online e offline para criar segmentos de público-alvo com base em identificadores hash, como endereços de email ou números de telefone. Em seguida, você pode enviar esses segmentos para "jardins intitulados", como [!DNL Facebook], onde você pode direcionar seu público-alvo independentemente das interações online ou do estado de autenticação. [!DNL People-Based Destinations] pode ajudá-lo a:

* Direcione públicos-alvo offline e online em plataformas como, por exemplo, [!DNL Facebook]com base em endereços de email com hash;
* Elogie os recursos existentes de definição de metas de dispositivo e cookie do Audience Manager;
* Elimine os custos associados a soluções de integração de dados de terceiros;
* Elimine os custos associados ao desenvolvimento de fluxos de trabalho personalizados de devolução de dados;
* Públicos-alvo do Target em ambientes sem cookies;
* Públicos-alvo do Target desduplicando endereços de email correspondentes às IDs do cliente.

Você pode usar [!DNL People-Based Destinations] para segmentar e direcionar clientes de alto valor que podem nunca ter visitado o site ou parar a definição de metas aqueles que já foram convertidos offline. Além disso, você pode aproveitar [!DNL Profile Merge Rules] os dados originais offline com dados originais da Adobe Experience Cloud, inclusive os dados de clientes de outras soluções da Adobe Experience Cloud, para otimizar seus esforços publicitários de redes sociais.

![pbd-overview](assets/pbd-overview.png)

## Availability {#availability}

[!DNL People-Based Destinations] é uma integração premium do Audience Manager. Entre em contato com o consultor do Audience Manager para obter detalhes sobre os preços e a implementação.

## Por que você deve usar destinos baseados em pessoas {#why-use}

**Forneça aos seus clientes experiências consistentes entre canais, gerenciando toda a segmentação de público-alvo no Audience Manager.**

A não ativação de seus segmentos de público-alvo em canais baseados em pessoas por meio do Audience Manager leva a experiências desvinculadas entre o que seus clientes veem ao visitar seu site e o que eles veem, por exemplo, em seus [!DNL Facebook] feeds. Ter uma segmentação consistente entre canais pode aumentar a receita do anúncio ao otimizar as despesas de anúncios.

**Alcance públicos-alvo em canais baseados em pessoas sem precisar de uma solução de onboarding de dados dedicada ou fluxos de trabalho personalizados para enviar públicos.**

A maneira mais "tradicional" de segmentação de públicos-alvo nos canais baseados em pessoas envolve exportar os dados do cliente em um formato aceito pela plataforma que você deseja anunciar e usar o método de onboarding de dados dedicado da plataforma para trazer os dados do cliente para a conta do anunciante. Este é todo trabalho manual que você precisa fazer para cada plataforma que deseja anunciar. Além disso, diferentes plataformas podem ter requisitos diferentes de formato de dados, tornando o processo ainda mais tedioso.

![pbd-overview](assets/pbd-diagram.png)

Por meio [!DNL People-Based Destinations]disso, o Audience Manager ajuda a centralizar todos os dados do cliente, construir segmentos de público-alvo e ativá-los em vários canais baseados em pessoas. Você pode fazer isso tudo na interface do usuário do Audience Manager, evitando o trabalho adicional de carregamento manual de dados para cada plataforma, poupando um tempo valioso no processo.

**Crie e ative segmentos de público-alvo de perfis offline.**

[!DNL People-Based Destinations] resolver o problema anteriormente, você só pode ativar os segmentos de público-alvo com base na atividade do dispositivo. Com [!DNL People-Based Destinations], você pode criar segmentos a partir de dados meramente offline da sua própria [!DNL CRM]e ativá-los em plataformas baseadas em pessoas. Além disso, é possível correlacionar dados offline com os dados do dispositivo que você já possui no Audience Manager.

**Aproveite os controles de governança e gerenciamento de dados do Audience Manager para lidar com os dados do cliente com segurança.**

[!DNL People-Based Destinations] use identificadores com hash, para que os dados do cliente sejam sempre protegidos, a partir do momento em que você o coloca no Audience Manager, até o momento em que atinge o destino de destino. Isso elimina os riscos de privacidade associados ao upload manual de dados de clientes confidenciais em cada plataforma de ativação.

## Casos de uso {#use-cases}

Para ajudá-lo a entender melhor como e quando você deve usar [!DNL People-Based Destinations], veja dois casos de uso de exemplo que os clientes do Audience Manager podem resolver usando este recurso.

### Use Case #1 {#use-case-1}

Um revendedor online deseja alcançar clientes existentes por meio de plataformas sociais e exibi-los ofertas personalizadas com base em seus pedidos anteriores. Com [!DNL People-Based Destinations], eles podem assimilar endereços de email com hash próprios [!DNL CRM] ao Audience Manager, construir segmentos a partir de dados offline e enviar esses segmentos para as plataformas sociais que deseja anunciar, otimizando suas despesas de publicidade.

### Use Case #2 {#use-case-2}

Uma companhia aérea possui diferentes níveis de clientes (Bronze, Silver e Gold) e deseja fornecer cada um dos níveis com ofertas personalizadas por plataformas sociais. A empresa usa o Audience Manager para analisar a atividade do cliente no site. No entanto, nem todos os clientes usam o aplicativo para dispositivos móveis da companhia aérea, e alguns deles nunca fizeram logon no site da empresa. Os únicos identificadores que a empresa tem sobre esses clientes são IDs de associação e endereços de email.

Para direcioná-los em redes sociais e canais similares baseados em pessoas, eles podem colocar os dados do cliente no [!DNL CRM] Audience Manager usando os endereços de email hash como identificadores.

Em seguida, eles podem combinar os dados offline com as características existentes da atividade online, para criar novos segmentos de público-alvo que [!DNL People-Based Destinations]podem ser alvo.
