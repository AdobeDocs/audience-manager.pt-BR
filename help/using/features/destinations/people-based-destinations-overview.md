---
description: 'Use destinos com base em pessoas para enviar segmentos de público-alvo primários para ambientes com base em pessoas. Esses ambientes são ecossistemas fechados pertencentes a uma entidade que controla o conteúdo que está sendo exibido dentro dele. Eles incluem plataformas sociais, como o Facebook, e outras plataformas que dependem de contas de clientes para personalizar o conteúdo exibido. '
seo-description: 'Use destinos com base em pessoas para enviar segmentos de público-alvo primários para ambientes com base em pessoas. Esses ambientes são ecossistemas fechados pertencentes a uma entidade que controla o conteúdo que está sendo exibido dentro dele. Eles incluem plataformas sociais, como o Facebook, e outras plataformas que dependem de contas de clientes para personalizar o conteúdo exibido.  '
seo-title: Visão geral dos destinos com base em pessoas e casos de uso
solution: Audience Manager
title: Visão geral e casos de uso
feature: Destinos com base em pessoas
exl-id: 2edbda3b-e2a3-4a92-965b-206a21764cc8
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 1%

---

# Visão geral e casos de uso {#overview-use-cases}

Use [!DNL People-Based Destinations] para enviar segmentos de público-alvo primários para ambientes baseados em pessoas. Esses ambientes são ecossistemas fechados pertencentes a uma entidade que controla o conteúdo que está sendo exibido dentro dele. Eles incluem plataformas sociais, como [!DNL Facebook], e outras plataformas que dependem de contas de clientes para personalizar o conteúdo exibido.

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo pela configuração e uso deste recurso. Nada neste documento é de aconselhamento jurídico. Consulte o seu advogado para obter orientação jurídica.

## Visão geral {#overview}

[!DNL People-Based Destinations] permitem aplicar a segmentação em dados online e offline para criar segmentos de público com base em identificadores  [com hash](people-based-destinations-prerequisites.md#hashing-requirements), como endereços de email ou números de telefone. Em seguida, é possível enviar esses segmentos para &quot;jardins instalados&quot;, como [!DNL Facebook], onde é possível direcionar seu público-alvo nas plataformas sociais. [!DNL People-Based Destinations] O pode ajudá-lo a:

* Direcione públicos offline e online em plataformas como [!DNL Facebook], com base em endereços de email com hash;
* Complementar os recursos existentes de definição de metas de dispositivos e cookies do Audience Manager;
* Eliminar os custos associados às soluções de integração de dados de terceiros;
* Eliminar os custos associados ao desenvolvimento de fluxos de trabalho personalizados de integração de dados;
* Públicos-alvo em ambientes sem cookies;
* Direcione públicos-alvo desduplicando endereços de email com hash correspondentes às IDs do cliente.

Você pode usar [!DNL People-Based Destinations] para segmentar e direcionar clientes de alto valor que podem não ter visitado seu site ou parar de direcionar aqueles que já se converteram offline. Além disso, você pode aproveitar [!DNL Profile Merge Rules] para combinar seus dados originais offline com seus dados originais online, incluindo dados de clientes de outras soluções da Adobe Experience Cloud, para otimizar seus esforços de publicidade em redes sociais.

![pbd-overview](assets/pbd-overview.png)

## Disponibilidade {#availability}

[!DNL People-Based Destinations] é uma integração premium de Audience Manager. Entre em contato com seu representante de Adobe para aproveitar esse recurso premium.

## Por que você deve usar [!UICONTROL People-Based Destinations] {#why-use}

**Forneça experiências consistentes entre canais aos clientes, gerenciando toda a segmentação de público-alvo no Audience Manager.**

Não ativar seus segmentos de público-alvo em canais com base em pessoas por meio do Audience Manager leva a experiências dissociadas entre o que seus clientes veem ao visitar seu site e o que eles veem, por exemplo, em seus feeds [!DNL Facebook]. Ter uma definição de metas consistente em todos os canais pode aumentar a receita de seus anúncios e, ao mesmo tempo, otimizar os gastos com seus anúncios.

**Alcance públicos-alvo em canais com base em pessoas sem a necessidade de uma solução dedicada de integração de dados ou fluxos de trabalho personalizados para enviar públicos-alvo.**

A maneira mais &quot;tradicional&quot; de direcionar públicos em canais baseados em pessoas envolve exportar os dados do cliente em um formato aceito pela plataforma na qual você deseja fazer publicidade e usar o método dedicado de integração de dados da plataforma para trazer os dados do cliente para a conta do anunciante. Este é todo o trabalho manual que você precisa fazer para cada plataforma na qual deseja anunciar. Além disso, plataformas diferentes podem ter diferentes requisitos de formato de dados, tornando o processo ainda mais tedioso.

![pbd-overview](assets/pbd-diagram.png)

Por meio do [!DNL People-Based Destinations], o Audience Manager ajuda a centralizar os dados do cliente, criar segmentos de público-alvo e ativá-los em vários canais com base em pessoas. Você pode fazer isso tudo na interface do usuário do Audience Manager, evitando o trabalho adicional de carregar dados manualmente em cada plataforma, economizando tempo valioso no processo.

**Crie e ative segmentos de público-alvo a partir de perfis meramente offline.**

[!DNL People-Based Destinations] solucione o problema que, anteriormente, você só podia ativar segmentos de público-alvo com base na atividade do dispositivo. Com [!DNL People-Based Destinations], você pode criar segmentos a partir de dados meramente offline a partir de seu próprio [!DNL CRM], e ativá-los em plataformas baseadas em pessoas. Além disso, você pode correlacionar seus dados offline com os dados do dispositivo que você já tem no Audience Manager.

**Aproveite o controle de dados e os controles de privacidade do Audience Manager com segurança.**

[!DNL People-Based Destinations] O exige que você use somente identificadores com hash irreversivelmente. Isso reduz o risco associado ao upload manual dos dados do cliente em cada plataforma de destino.

Assista ao vídeo abaixo para obter uma visão geral do fluxo de dados ao usar [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## Casos de uso {#use-cases}

Para ajudá-lo a entender melhor como e quando você deve usar [!DNL People-Based Destinations], aqui estão dois casos de uso de exemplo que os clientes do Audience Manager podem resolver usando esse recurso.

### Caso de uso nº 1 {#use-case-1}

Um varejista online deseja alcançar clientes existentes por meio de plataformas sociais e mostrar a eles ofertas personalizadas com base em seus pedidos anteriores. Com [!DNL People-Based Destinations], o varejista online pode assimilar endereços de email com hash de seu próprio [!DNL CRM] para o Audience Manager, criar segmentos a partir de seus próprios dados offline e enviar esses segmentos para as plataformas sociais nas quais deseja fazer publicidade, otimizando seus gastos com publicidade.

### Caso de uso nº 2 {#use-case-2}

Uma companhia aérea tem níveis de clientes diferentes (Bronze, Prata e Ouro) e deseja fornecer a cada um dos níveis ofertas personalizadas por meio de plataformas sociais. A empresa usa o Audience Manager para analisar a atividade do cliente no site. No entanto, nem todos os clientes usam o aplicativo móvel da companhia aérea e alguns deles não fizeram logon no site da empresa. Os únicos identificadores que a empresa tem sobre esses clientes são IDs de associação e endereços de email.

Para direcioná-los em redes sociais e canais baseados em pessoas semelhantes, eles podem integrar os dados do cliente de seu [!DNL CRM] no Audience Manager, usando os endereços de email com hash como identificadores.

Em seguida, é possível combinar seus dados offline com suas características de atividade online existentes, para criar novos segmentos de público-alvo que podem ser direcionados por meio de [!DNL People-Based Destinations].
