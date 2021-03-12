---
description: No Audience Manager, um destino é qualquer sistema de terceiros (servidor de anúncios, DSP, rede de anúncios etc.) com o qual você deseja compartilhar dados. O Construtor de destinos é a ferramenta usada para criar e gerenciar cookies, URL ou destinos de servidor para servidor.
keywords: código de integração, destino, visão geral do destino, destino, destino, destino, destino, destino, destino, destino, destino, destino, destino, destino, destino, destino
landing-page-description: Um destino é qualquer sistema de terceiros, como servidor de publicidade ou DSP, com o qual compartilhar dados. Use a ferramenta Construtor de destino para criar e gerenciar cookies, URL ou destinos de servidor para servidor.
seo-title: 'Destinos '
solution: Audience Manager
title: Destinos
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Noções básicas sobre o destino
translation-type: tm+mt
source-git-commit: e6348c85e7df6428802d54b2c90385ce95f50e1a
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 15%

---


# [!UICONTROL Destinations] Visão geral {#destinations}

No Audience Manager, um [!UICONTROL destination] é qualquer sistema de terceiros (servidor de anúncios, [!DNL DSP], rede de anúncios etc.) com o qual você deseja compartilhar dados. [!UICONTROL Destination Builder] é a ferramenta usada para criar e gerenciar  [!UICONTROL cookie],  [!DNL URL]ou  [!UICONTROL server-to-server destinations].

## Propósito e vantagens {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] e  [!UICONTROL Destination Builder] permitem criar  [!UICONTROL destinations] e enviar informações sobre usuários segmentados para seu parceiro de dados. Isso ajuda a:

* **Valor dos dados do Protect:** em vez de enviar todos os dados do usuário para um  [!UICONTROL destination],  [!UICONTROL Destination Builder] permite compartilhar informações específicas somente sobre usuários qualificados.
* **Execute ações em seus dados:** o envio de dados para um  [!UICONTROL destination] parceiro os ajuda a desenvolver e direcionar rapidamente segmentos de público-alvo qualificados.
* **Reduza a sobrecarga técnica:** os usuários empresariais podem configurar com  [!UICONTROL destinations] segurança na  [!UICONTROL Destination Builder] interface. Isso ajuda a reduzir o tempo necessário para testes de pré-implantação. Com [!UICONTROL Destination Builder], você cria, gerencia e exclui [!UICONTROL destinations] conforme suas necessidades comerciais mudam, tudo sem trabalhar em um longo ciclo de desenvolvimento.

## Considerações técnicas {#technical-considerations}

<!-- destination-delivery-methods.xml -->

A entrega de dados depende de como seu parceiro de dados deseja ou pode receber informações [!UICONTROL destination]. As restrições técnicas ou de engenharia podem impedir que [!UICONTROL destination] receba dados por meio de [!DNL URL], [!UICONTROL cookie] ou [!UICONTROL server-to-server] processos. Trabalhe com seu parceiro de terceiros para determinar qual método pode ser usado.

## Considerações comerciais {#business-considerations}

As decisões de negócios para selecionar um método de delivery em vez de outro dependem dos recursos técnicos do [!UICONTROL destination] parceiro e do que você deseja fazer com informações qualificadas do usuário. Por exemplo, restrições técnicas podem limitar suas opções se um [!UICONTROL destination] não puder receber dados por um método de delivery específico. No entanto, se não houver problemas técnicos, você poderá enviar informações com base em como deseja tomar medidas nesses dados. Por exemplo:

* [!DNL URL]O e o  [!UICONTROL cookie-based destinations] funcionam quase de forma síncrona com as ações do usuário em uma página.
* [!UICONTROL Server-to-server] métodos são bons para criar segmentos de público-alvo profundos ao longo do tempo.

## [!UICONTROL Destination] Tipos e usos típicos  {#destination-types}

Os exemplos na tabela a seguir podem ajudar você a entender quando usar um [!UICONTROL destination] específico e as diferenças entre cada tipo.

| [!UICONTROL Destination] Digite | Normalmente Usado Quando | Exemplo | Considerações |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | Você precisa enviar dados para outras soluções da Adobe Experience Cloud. | Envio de dados para o Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | Você precisa enviar segmentos de público-alvo para ambientes baseados em pessoas, como o Facebook. | Fornecer ofertas personalizadas aos clientes existentes, com base em seu histórico de compras | O direcionamento de público-alvo é feito por meio de identificadores com hash. Consulte [Destinos com base em pessoas](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**Servidor para servidor**) | <ul><li>Não é necessária a transferência imediata de dados.</li><li>Coleta de dados para criar um grande conjunto de públicos-alvo de usuários qualificados.</li></ul> | Coleta de dados ao longo do tempo (horas ou dias) para usá-los em um conjunto de campanhas a ser executado em uma data posterior. | <ul><li>Transfere dados sobre visitantes do site novos e anteriores. </li><li>Os visitantes não precisam ser vistos novamente para se qualificarem para outros segmentos.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**** URLou  **cookie**) | Você precisa transferir dados imediatamente para que um destino possa tomar medidas em um usuário qualificado imediatamente. | Envio de dados de um site de compra de tíquete. Use um [!UICONTROL URL] ou [!UICONTROL cookie destination] para qualificar o usuário e direcionar novamente imediatamente. | <ul><li>Transfere dados somente sobre novos visitantes. </li><li>Os visitantes devem ser vistos novamente para se qualificarem para o segmento.</li></ul> |
