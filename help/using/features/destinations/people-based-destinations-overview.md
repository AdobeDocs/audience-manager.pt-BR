---
description: 'Use destinos baseados em pessoas para enviar segmentos de audiência primários para ambientes baseados em pessoas. Esses ambientes são ecossistemas fechados pertencentes a uma entidade que controla o conteúdo que está sendo exibido dentro dela. Eles incluem plataformas sociais, como o Facebook, e outras plataformas que dependem das contas do cliente para personalizar o conteúdo exibido. '
seo-description: 'Use destinos baseados em pessoas para enviar segmentos de audiência primários para ambientes baseados em pessoas. Esses ambientes são ecossistemas fechados pertencentes a uma entidade que controla o conteúdo que está sendo exibido dentro dela. Eles incluem plataformas sociais, como o Facebook, e outras plataformas que dependem das contas do cliente para personalizar o conteúdo exibido.  '
seo-title: Destinos baseados em pessoas - Visão geral e casos de uso
solution: Audience Manager
title: Visão geral e casos de uso
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 1%

---


# Visão geral e casos de uso {#overview-use-cases}

Use [!DNL People-Based Destinations] para enviar segmentos de audiência primários para ambientes baseados em pessoas. Esses ambientes são ecossistemas fechados pertencentes a uma entidade que controla o conteúdo que está sendo exibido dentro dela. Eles incluem plataformas sociais, como [!DNL Facebook], e outras plataformas que dependem das contas do cliente para personalizar o conteúdo exibido.

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo durante a configuração e o uso deste recurso. Nada aqui contido é aconselhamento jurídico. Consulte o seu próprio advogado para obter orientação jurídica.

## Visão geral {#overview}

[!DNL People-Based Destinations] permite que você aplique a segmentação em dados online e offline para criar segmentos de audiência com base em identificadores [ com ](people-based-destinations-prerequisites.md#hashing-requirements)hash, como endereços de email ou números de telefone. Em seguida, você pode enviar esses segmentos para &quot;jardins instalados&quot;, como [!DNL Facebook], onde você pode público alvo sua audiência nas plataformas sociais. [!DNL People-Based Destinations] pode ajudá-lo a:

* Público alvo de audiências offline e online em plataformas como [!DNL Facebook], com base em endereços de email com hash;
* Complementar os recursos existentes de segmentação de dispositivos e cookies do Audience Manager;
* Eliminar os custos associados às soluções de integração de dados de terceiros;
* Eliminar os custos associados ao desenvolvimento de workflows personalizados de integração de dados;
* Audiências públicos alvos em ambientes sem cookies;
* Audiências de público alvo desduplicando endereços de email com hash correspondentes às IDs do cliente.

Você pode usar [!DNL People-Based Destinations] para segmentar e público alvo clientes de alto valor que talvez não tenham visitado seu site, ou parar de direcionar aqueles que já se converteram offline. Além disso, você pode aproveitar [!DNL Profile Merge Rules] para combinar seus dados offline primários com seus dados on-line, incluindo dados de clientes de outras soluções da Adobe Experience Cloud, para otimizar seus esforços de publicidade em redes sociais.

![pbd-overview](assets/pbd-overview.png)

## Disponibilidade {#availability}

[!DNL People-Based Destinations] é uma integração de Audience Manager premium. Entre em contato com seu representante de Adobe para aproveitar esse recurso premium.

## Por que você deve usar [!UICONTROL People-Based Destinations] {#why-use}

**Forneça aos seus clientes experiências consistentes entre canais, gerenciando toda a segmentação de audiências de dentro do Audience Manager.**

Não ativar seus segmentos de audiência em canais baseados em pessoas por meio do Audience Manager, resulta em experiências dissociadas entre o que seus clientes veem ao visitar seu site e o que eles veem, por exemplo, em seus feeds [!DNL Facebook]. Ter uma definição de metas consistente entre canais pode aumentar a receita de seus anúncios e, ao mesmo tempo, otimizar os gastos com seus anúncios.

**Alcance audiências em canais baseados em pessoas sem a necessidade de uma solução dedicada de integração de dados ou workflows personalizados para enviar audiências.**

A maneira mais &quot;tradicional&quot; de direcionar audiências em canais baseados em pessoas envolve a necessidade de exportar os dados do cliente em um formato aceito pela plataforma para a qual você deseja anunciar e, em seguida, usar o método dedicado de integração de dados da plataforma para trazer os dados do cliente para a conta do anunciante. Este é todo o trabalho manual que você precisa fazer para cada plataforma que você deseja anunciar. Além disso, diferentes plataformas podem ter diferentes requisitos de formato de dados, tornando o processo ainda mais tedioso.

![pbd-overview](assets/pbd-diagram.png)

Por meio de [!DNL People-Based Destinations], o Audience Manager ajuda a centralizar os dados do cliente, criar segmentos de audiência e ativá-los em vários canais baseados em pessoas. Você pode fazer isso tudo na interface do usuário do Audience Manager, evitando o trabalho adicional de carregar dados manualmente para cada plataforma, economizando tempo valioso no processo.

**Crie e ative segmentos de audiência de perfis puramente offline.**

[!DNL People-Based Destinations] resolva o problema que anteriormente, você só podia ativar segmentos de audiência com base na atividade do dispositivo. Com [!DNL People-Based Destinations], você pode criar segmentos a partir de dados puramente offline de seu próprio [!DNL CRM], e ativá-los em plataformas baseadas em pessoas. Além disso, você pode correlacionar seus dados offline com os dados do dispositivo que já tem no Audience Manager.

**Aproveite o controle de dados Audience Manager e os controles de privacidade para lidar com segurança com os dados do cliente.**

[!DNL People-Based Destinations] requer que você use somente identificadores com hash irreversivelmente. Isso reduz o risco associado ao upload manual dos dados do cliente em cada plataforma de destino.

Assista ao vídeo abaixo para obter uma visão geral do fluxo de dados ao usar [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## Casos de uso {#use-cases}

Para ajudá-lo a entender melhor como e quando você deve usar [!DNL People-Based Destinations], há dois casos de uso de amostra que os clientes do Audience Manager podem resolver usando esse recurso.

### Caso de uso nº 1 {#use-case-1}

Um varejista online quer atingir os clientes existentes por meio de plataformas sociais e mostrar-lhes ofertas personalizadas com base em seus pedidos anteriores. Com [!DNL People-Based Destinations], o varejista online pode assimilar endereços de email com hash de seus próprios [!DNL CRM] para o Audience Manager, criar segmentos a partir de seus próprios dados offline e enviar esses segmentos para as plataformas sociais nas quais deseja fazer publicidade, otimizando seus gastos com publicidade.

### Caso de uso nº 2 {#use-case-2}

Uma companhia aérea tem níveis de clientes diferentes (Bronze, Prata e Ouro) e deseja fornecer a cada um dos níveis ofertas personalizadas por meio de plataformas sociais. A empresa usa a Audience Manager para analisar a atividade do cliente no site. No entanto, nem todos os clientes usam o aplicativo móvel da companhia aérea e alguns deles não fizeram logon no site da empresa. Os únicos identificadores que a empresa tem sobre esses clientes são IDs de associação e endereços de email.

Para público alvo em redes sociais e canais semelhantes baseados em pessoas, eles podem integrar os dados do cliente de seu [!DNL CRM] no Audience Manager, usando os endereços de email com hash como identificadores.

Em seguida, eles podem combinar seus dados offline com suas características de atividade online existentes, para criar novos segmentos de audiência que podem ser públicos alvos por [!DNL People-Based Destinations].
