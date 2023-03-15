---
description: Descubra as vantagens, os tipos e os usos dos destinos — qualquer sistema de terceiros, como um servidor de anúncios ou DSP, em que você compartilha dados. Use o Construtor de destino para criar e gerenciar cookies, URLs ou destinos de servidor para servidor.
keywords: código de integração, destino, visão geral do destino, destino, destino, destino, destino, destino, destino, destino, destino, destino, destino, destino, destino, destino
landing-page-description: Descubra as vantagens, os tipos e os usos dos destinos — qualquer sistema de terceiros, como um servidor de anúncios ou DSP, em que você compartilha dados. Use o Construtor de destino para criar e gerenciar cookies, URLs ou destinos de servidor para servidor.
short-description: Discover the advantages, types, and uses of destinations – any third-party system, such as an ad server or DSP, where you share data. Use Destination Builder to create and manage cookies, URL, or server-to-server destinations.
seo-title: Destinations
solution: Audience Manager
title: Destinos
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!UICONTROL Destinations] Visão geral {#destinations}

No Audience Manager, um [!UICONTROL destination] é qualquer sistema de terceiros (servidor de anúncios, [!DNL DSP], rede de anúncios etc.) com o qual você deseja compartilhar dados. [!UICONTROL Destination Builder] é a ferramenta usada para criar e gerenciar [!UICONTROL cookie], [!DNL URL]ou [!UICONTROL server-to-server destinations].

## Propósito e vantagens {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] e [!UICONTROL Destination Builder] permite criar [!UICONTROL destinations] e enviar informações sobre usuários segmentados para seu parceiro de dados. Isso ajuda a:

* **Valor dos dados do Protect:** Em vez de enviar todos os dados do usuário para uma [!UICONTROL destination], [!UICONTROL Destination Builder] permite compartilhar informações específicas somente sobre usuários qualificados.
* **Execute ações em seus dados:** Envio de dados a um [!UICONTROL destination] ajuda o parceiro a desenvolver e direcionar rapidamente segmentos de público-alvo qualificados.
* **Reduza a sobrecarga técnica:** Os usuários empresariais podem configurar [!UICONTROL destinations] em segurança [!UICONTROL Destination Builder] interface. Isso ajuda a reduzir o tempo necessário para testes de pré-implantação. Com [!UICONTROL Destination Builder], criar, gerenciar e excluir [!UICONTROL destinations] conforme as necessidades de sua empresa mudam, tudo sem trabalhar em um longo ciclo de desenvolvimento.

## Considerações técnicas {#technical-considerations}

<!-- destination-delivery-methods.xml -->

A entrega de dados depende de como seu parceiro de dados deseja ou pode receber [!UICONTROL destination] informações. As restrições técnicas ou de engenharia podem impedir que uma [!UICONTROL destination] do recebimento de dados via [!DNL URL], [!UICONTROL cookie]ou [!UICONTROL server-to-server] processos. Trabalhe com seu parceiro de terceiros para determinar qual método pode ser usado.

## Considerações comerciais {#business-considerations}

As decisões de negócios para selecionar um método de delivery em vez de outro dependem dos recursos técnicos de seu [!UICONTROL destination] parceiro e o que você deseja fazer com informações qualificadas do usuário. Por exemplo, restrições técnicas podem limitar suas opções se uma [!UICONTROL destination] O não pode receber dados por um método de delivery específico. No entanto, se não houver problemas técnicos, você poderá enviar informações com base em como deseja tomar medidas nesses dados. Por exemplo:

* [!DNL URL]s e [!UICONTROL cookie-based destinations] trabalhe de forma quase síncrona com ações do usuário em uma página.
* [!UICONTROL Server-to-server] métodos são bons para criar segmentos de público-alvo profundos ao longo do tempo.

## [!UICONTROL Destination] Tipos e usos típicos {#destination-types}

Os exemplos na tabela a seguir podem ajudar você a entender quando usar um [!UICONTROL destination] e as diferenças entre cada tipo.

| [!UICONTROL Destination] Digite | Normalmente Usado Quando | Exemplo | Considerações |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | Você precisa enviar dados para outras soluções da Adobe Experience Cloud. | Envio de dados para o Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | Você precisa enviar segmentos de público-alvo para ambientes baseados em pessoas, como o Facebook. | Fornecer ofertas personalizadas aos clientes existentes, com base em seu histórico de compras | O direcionamento de público-alvo é feito por meio de identificadores com hash. Consulte [Destinos com base em pessoas](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**Servidor para servidor**) | <ul><li>Não é necessária a transferência imediata de dados.</li><li>Coleta de dados para criar um grande conjunto de públicos-alvo de usuários qualificados.</li></ul> | Coleta de dados ao longo do tempo (horas ou dias) para usá-los em um conjunto de campanhas a ser executado em uma data posterior. | <ul><li>Transfere dados sobre visitantes do site novos e anteriores. </li><li>Os visitantes não precisam ser vistos novamente para se qualificarem para outros segmentos.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**URL** ou **Cookie**) | Você precisa transferir dados imediatamente para que um destino possa tomar medidas em um usuário qualificado imediatamente. | Envio de dados de um site de compra de tíquete. Use um [!UICONTROL URL] ou [!UICONTROL cookie destination] para qualificar o usuário e direcionar novamente imediatamente. | <ul><li>Transfere dados somente sobre novos visitantes. </li><li>Os visitantes devem ser vistos novamente para se qualificarem para o segmento.</li></ul> |
