---
description: Use destinos com base em pessoas para enviar segmentos de público-alvo primários para ambientes com base em pessoas. Esses ambientes são ecossistemas fechados pertencentes a uma entidade que controla o conteúdo que está sendo exibido dentro dela. Eles incluem plataformas sociais, como o Facebook, e outras plataformas que dependem das contas do cliente para personalizar o conteúdo exibido.
seo-description: Use people-based destinations to send first-party audience segments to people-based environments. These environments are closed ecosystems belonging to one entity that controls the content that is being displayed within it. They include social platforms such as Facebook, and other platforms that rely on customer accounts to personalize the displayed content.
seo-title: People-Based Destinations Overview and Use Cases
solution: Audience Manager
title: Visão geral e casos de uso
feature: People-based Destinations
exl-id: 2edbda3b-e2a3-4a92-965b-206a21764cc8
source-git-commit: ab3361a0a54a7200d2f0c03a82ae6ef61a755be9
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 0%

---

# Visão geral e casos de uso {#overview-use-cases}

Use [!DNL People-Based Destinations] para enviar segmentos de público-alvo primários para ambientes baseados em pessoas. Esses ambientes são ecossistemas fechados pertencentes a uma entidade que controla o conteúdo que está sendo exibido dentro dela. Eles incluem plataformas sociais como [!DNL Facebook] e outras plataformas que dependem das contas do cliente para personalizar o conteúdo exibido.

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo pela configuração e pelo uso desse recurso. Nada contido aqui é aconselhamento jurídico. Consulte seu próprio serviço jurídico para obter orientação jurídica.

## Visão geral {#overview}

[!DNL People-Based Destinations] habilite você a aplicar a segmentação em dados online e offline para criar segmentos de público com base em [identificadores com hash](people-based-destinations-prerequisites.md#hashing-requirements), como endereços de email. Em seguida, você pode enviar esses segmentos para &quot;jardins murados&quot;, como [!DNL Facebook], em que é possível direcionar o público-alvo nas plataformas sociais. [!DNL People-Based Destinations] pode ajudá-lo a:

* Direcione públicos offline e online em plataformas como [!DNL Facebook], com base em endereços de email com hash;
* Complementar os recursos existentes de direcionamento por dispositivo e cookie do Audience Manager;
* Eliminar os custos associados a soluções de integração de dados de terceiros;
* Eliminar os custos associados ao desenvolvimento de fluxos de trabalho de integração de dados personalizados;
* Direcionar públicos-alvo em ambientes sem cookies;
* Direcione públicos-alvo desduplicando endereços de email com hash correspondentes às IDs do cliente.

Você pode usar o [!DNL People-Based Destinations] para segmentar e direcionar clientes de alto valor que talvez não visitem seu site ou parar de direcionar aqueles que já se converteram offline. Além disso, você pode aproveitar o [!DNL Profile Merge Rules] para combinar seus dados primários offline com seus dados primários online, incluindo dados do cliente de outras soluções da Adobe Experience Cloud, para otimizar seus esforços de publicidade em redes sociais.

![pbd-overview](assets/pbd-overview.png)

## Disponibilidade {#availability}

[!DNL People-Based Destinations] é uma integração premium do Audience Manager. Entre em contato com seu representante da Adobe para aproveitar esse recurso premium.

## Por que você deve usar o [!UICONTROL People-Based Destinations] {#why-use}

**Forneça aos clientes experiências consistentes entre canais, gerenciando toda a segmentação de público no Audience Manager.**

A não ativação de segmentos de público-alvo em canais com base em pessoas por meio do Audience Manager resulta em experiências desassociadas entre o que os clientes veem ao visitar seu site e o que veem, por exemplo, nos feeds do [!DNL Facebook]. Ter um direcionamento consistente em todos os canais pode aumentar a receita de anúncios enquanto otimiza os gastos com anúncios.

**Alcance públicos em canais com base em pessoas sem a necessidade de uma solução de integração de dados dedicada ou fluxos de trabalho personalizados para enviar públicos.**

A maneira mais &quot;tradicional&quot; de direcionar públicos-alvo em canais com base em pessoas envolve a necessidade de exportar os dados do cliente em um formato aceito pela plataforma na qual você deseja anunciar e o uso do método de integração de dados dedicado da plataforma para trazer os dados do cliente para a conta do anunciante. Este é todo o trabalho manual que você precisa fazer para cada plataforma que você deseja anunciar. Além disso, plataformas diferentes podem ter requisitos de formato de dados diferentes, tornando o processo ainda mais tedioso.

![pbd-overview](assets/pbd-diagram.png)

Por meio do [!DNL People-Based Destinations], a Audience Manager ajuda a centralizar os dados de clientes, criar segmentos de público-alvo e ativá-los em vários canais com base em pessoas. Você pode fazer tudo isso na interface do usuário do Audience Manager, evitando o trabalho adicional de carregar dados manualmente para cada plataforma e economizando um tempo valioso no processo.

**Crie e ative segmentos de público-alvo a partir de perfis exclusivamente offline.**

[!DNL People-Based Destinations] resolva o problema de que, anteriormente, você só podia ativar segmentos de público com base na atividade do dispositivo. Com o [!DNL People-Based Destinations], você pode criar segmentos a partir de dados exclusivamente offline do seu próprio [!DNL CRM] e ativá-los em plataformas com base em pessoas. Além disso, você pode correlacionar seus dados offline com os dados do dispositivo que já tem no Audience Manager.

**Aproveite os controles de privacidade e governança de dados da Audience Manager para gerenciar com segurança os dados do cliente.**

[!DNL People-Based Destinations] exige que você use apenas identificadores com hash irreversivelmente. Isso reduz o risco associado ao upload manual de dados do cliente em cada plataforma de destino.

Assista ao vídeo abaixo para obter uma visão geral do fluxo de dados ao usar o [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## Casos de uso {#use-cases}

Para ajudá-lo a entender melhor como e quando você deve usar o [!DNL People-Based Destinations], veja dois casos de uso de exemplo que os clientes da Audience Manager podem resolver usando este recurso.

### Caso de uso #1 {#use-case-1}

Uma retailer online deseja alcançar os clientes existentes por meio de plataformas sociais e mostrar ofertas personalizadas com base em seus pedidos anteriores. Com o [!DNL People-Based Destinations], a retailer online pode assimilar endereços de email com hash de seu próprio [!DNL CRM] para a Audience Manager, criar segmentos com seus próprios dados offline e enviar esses segmentos para as plataformas sociais nas quais deseja anunciar, otimizando seus gastos com publicidade.

### Caso de uso #2 {#use-case-2}

Uma companhia aérea tem diferentes níveis de clientes (Bronze, Prata e Ouro) e deseja fornecer ofertas personalizadas a cada um dos níveis por meio de plataformas sociais. A empresa usa o Audience Manager para analisar a atividade do cliente no site. No entanto, nem todos os clientes usam o aplicativo móvel da companhia aérea e alguns deles não fizeram logon no site da empresa. Os únicos identificadores que a empresa tem sobre esses clientes são IDs de associação e endereços de email.

Para direcioná-los por meio de redes sociais e canais semelhantes com base em pessoas, eles podem integrar os dados do cliente do [!DNL CRM] no Audience Manager, usando os endereços de email com hash como identificadores.

Em seguida, eles podem combinar seus dados offline com suas características de atividade online existentes, para criar novos segmentos de público-alvo que eles podem direcionar por meio do [!DNL People-Based Destinations].
